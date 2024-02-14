## Events and observers

**Events** 
- Events are dispatched by modules when specific actions are triggered.
- Custom events can be created within the application and dispatched in the code.

1. Dispatching Events :
    - Events are dispatched using the Magento\Framework\Event\ManagerInterface class.
    - Obtain the event manager class through dependency injection.
    - Call the dispatch function with the event name and optional data array.
       ```php
        $this->eventManager->dispatch('my_module_event_before'); 
        // More code that sets $eventData...
        $this->eventManager->dispatch('my_module_event_after', ['myEventData' => $eventData]);
       ```
2. Creating New Events.
- To dispatch a custom event, provide a unique event name to the event manager's dispatch function. This unique event name is referenced in your module's events.xml file, where you specify which observers will react to the event.
- Example 
```php
<!-- MyCompany/MyModule/etc/events.xml -->
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Event/etc/events.xsd">
    <event name="my_module_event_after">
        <observer name="my_module_event_after_observer" instance="MyCompany\MyModule\Observer\MyEvent"/>
    </event>
</config>
```
- Declaring Observers in Different Areas:
```markdown
AREA	               FILE LOCATION
    Global	            <module-dir>/etc/events.xml
    Adminhtml	        <module-dir>/etc/adminhtml/events.xml
    Crontab	            <module-dir>/etc/crontab/events.xml
    Frontend	        <module-dir>/etc/frontend/events.xml
    GraphQL	            <module-dir>/etc/graphql/events.xml
    WebAPI REST	        <module-dir>/etc/webapi_rest/events.xml
    WebAPI SOAP	        <module-dir>/etc/webapi_soap/events.xml
```
**Observers** 
- Observers are a fundamental concept in Magento that allow classes to influence general behavior, performance, or alter business logic. 
- They are executed whenever the event they are configured to watch is dispatched by the event manager.
1. Creating an Observer
    - To create an observer, place your class file under your  **module-root/Observer** directory. Your observer class should **implement Magento\Framework\Event\ObserverInterface** and define its execute function.

2. Example Structure:

```php
namespace MyCompany\MyModule\Observer;

use Magento\Framework\Event\Observer;
use Magento\Framework\Event\ObserverInterface;

class MyObserver implements ObserverInterface
{
    public function __construct()
    {
        // Initialization code...
    }

    public function execute(Observer $observer)
    {
        // Execution code...
    }
}
```
3. Subscribing to Events
 - Observers are configured to watch certain events in the events.xml file. The observer XML element specifies the name and instance of the observer.

4. Example Configuration:
 
```php
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Event/etc/events.xsd">
    <event name="my_module_event_before">
        <observer name="myObserverName" instance="MyCompany\MyModule\Observer\MyObserver" />
    </event>
</config>
```
5. Unique Observer Names
Observer names must be unique per event definition. If you declare an observer with a name that is already in use within the same event, the application merges these nodes into a single observer declaration.

6. Disabling Observers
 - Existing observers can be disabled if you don't want them to run. It's good practice to disable an observer if you want to change its logic rather than override it.

 - Example Disabling Observer:

```php
    <config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Event/etc/events.xsd">
        <event name="my_module_event_before">
            <observer name="myObserverName" disabled="true" />
        </event>
    </config>
```
