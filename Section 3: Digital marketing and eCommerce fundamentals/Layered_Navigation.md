## Layered Navigation

**Layered navigation** simplifies product discovery based on categories, price range, or other available attributes. It typically appears in the left column of search results, category pages, and sometimes on the home page. The standard navigation includes a "Shop By" list of categories and price range. You can configure the display of layered navigation, including product count and price range.

### Layered Navigation by Category and Price

1. **Filterable Attributes**

    Layered navigation allows searching for products by category or attribute. For instance, when a shopper selects the "Mens/Shorts" category, the initial results display all products in that category. Further filtering can be done by selecting specific attributes like style, climate, color, etc. Attributes appear in an expanding section, listing each attribute value.

    The Catalog Input Type for Store Owner property and Use in Layered Navigation property define which attributes can be used for layered navigation. It's available only for anchor categories but can also be added to search results pages.

2. **Setting Up Basic Layered Navigation**

    **Step 1: Set up the attribute properties**
    
    - Navigate to **Stores > Attributes > Product** in the Admin sidebar.
    - Find the attribute and set **Use In Layered Navigation** to either "Filterable (with results)" or "Filterable (no results)".

    **Step 2: Make the category an anchor**
    
    - Go to **Catalog > Categories**.
    - Select the category, expand **Display Settings**, and set **Anchor** to Yes.

    **Step 3: Test the results**
    
    - Visit your store, navigate to the category, and observe the filterable attributes in the layered navigation.

3. **Remove Filterable Attribute Values with 0 Products**

    To remove attributes with zero products:
    
    - Go to **Stores > Attributes > Product**.
    - Edit the attribute, set **Layered Navigation** to "Filterable (with results)", and save.

4. **Price Navigation**

    Price navigation distributes products by price range in layered navigation. You can choose between automatic or manual methods for calculating price ranges.

    1. **Automatic (Equalize Price Ranges):** Default method.
    2. **Automatic (Equalize Product Counts):** For equalizing product counts.
    3. **Manual:** Customized price intervals.

    Configure price navigation settings under **Stores > Settings > Configuration > Catalog > Layered Navigation**.
## Configure Layered Navigation

Under **Stores > Settings > Configuration > Catalog > Layered Navigation**, adjust settings for product count display and price navigation step calculation.

This comprehensive guide covers setting up and configuring layered navigation in Magento, enhancing the shopping experience and improving product discovery.