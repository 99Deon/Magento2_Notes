# Product Attribute Overview

## Overview

Product attributes are fundamental in building your product catalog, describing specific characteristics of a product. They can be organized into attribute sets, which are then used as templates to create products.

Attributes determine the type of input control used for product options and provide additional information for product pages. They also serve as parameters and search criteria for layered navigation, product comparison reports, and promotions. You can create as many attributes and attribute sets as necessary to describe the products in your catalog. In addition to custom attributes, system attributes like price are integrated into the main Commerce platform and cannot be modified.

## Creating an Attribute during Product Editing

Follow best practices outlined in the following sections when planning and creating product attributes.

### Attribute Names

Define consistent naming conventions for attributes, including letter case and punctuation. For example: "Color:Green" and "Color:green" might be considered as two different attribute values by different systems. This data noise can impact business rules, search results, and data filters for applications matching products to rules.

### Attribute Usage

Consider how attributes should be used when assigning properties and values. Identify attributes used as labels for presentation, such as product name, image, price, and description, as well as attributes used for data input. Consider how attributes are represented on different site pages and their appearance on category pages, product detail pages, category grids, and thumbnails.

### Color

Ad hoc color descriptions can pose database operation challenges. Color names like "Azure Skies" or "Red Skies" may be visually appealing but may not return the best results when used as search criteria, or if merchandising requires specifying "Color_Family:Blue." Consider color representation in search results and layered navigation and establish guidelines based on your business needs. Then be consistent when assigning color attribute values in your catalog.

### Handling Variations

Utilize product configuration options and configurable products to manage variations in your product offerings. These features make it easier to classify products, create cart price rules and dynamic category rules, and offer a selection of options with different types of text input, selection, and date.

### Weighted Search

Product attributes enabled for catalog search can be assigned a weight to give them higher value in search results. Attributes with higher weight are returned before those with lower weight. For example, if two attributes in the system: color with a search weight of 3 and description with a search weight of 1. Searching for the word "red" returns a list of products with a color attribute value of red but does not return products containing descriptions containing the word "red." In this example, the color attribute has a defined weight higher than that of the description attribute.

### Unused Properties

Remove unused product properties for better structure and faster indexing.

## Types of Attribute Input

When displayed from the admin, attributes are the fields you fill in when creating a product. The input type assigned to an attribute determines the type of data that can be entered and the format of the input field or control.

### Attribute Input Types

- Text Field
- Text Area
- Text Editor
- Date
- Date and Time
- Yes/No
- Dropdown
- Multiple Select
- Price
- Media Image
- Fixed Product Tax
- Visual Swatch
- Text Swatch
- Page Builder

## Step 1: Adding an Attribute

1. Open the product in edit mode.
2. In the top right corner, click on "Add Attribute".

![New product with default attribute set](image-link-here)

To add an existing attribute to the product, use the filter controls to find the attribute in the grid and proceed as follows:

- Check the box in the first column of each attribute to add.
- Click on "Add Selected".

![Selecting an attribute](image-link-here)

To define a new attribute, click on "Create New Attribute" and fill in the details in step 2.

## Step 2: Describing Basic Attribute Properties

### Attribute Properties

- Enter an Attribute Label to identify the attribute.
- Set Catalog Input Type for Store Owner to the input control type to use for data entry.
- If the attribute is used for a configurable product, choose Dropdown. Then set Required to Yes.

For Dropdown and Multiple Select input types, proceed as follows:

- Under Values, click on "Add Value".
- Enter the first value you want to appear in the list.
- You can enter a value for the admin and a translation of the value for each store view. If you have only one store view, you can only enter the Admin value; it is also used for the storefront.
- Click on "Add Value" and repeat the previous step for each option to include in the list.
- Select Is Default to use the option as the default value.

### Advanced Attribute Properties (Optional)

- Enter a lowercase Attribute Code without spaces.
- Set Scope to indicate where in your store hierarchy the attribute can be used.
- If the attribute is used for a configurable product, choose Global.
- If this attribute applies only to this product, set Unique Value to Yes.
- To perform data validity check in a text field, set Input Validation for Store Owner to the data type the field must contain.
- This field is not available for input types with selected values. Input validation can be used for Decimal Number, Integer Number, Email, URL, Letters, or Letters (a-z, A-Z) or Numbers (0-9).

### Step 3: Entering Field Label

Expand "Manage Titles" field.

Enter a Title to use as the label for the field.

If your store is available in different languages, you can enter a translated title for each display.

## Step 4: Describing Storefront Properties

Expand "Storefront Properties" field.

- To make the attribute available for search, set Use in Search to Yes.
- To include the attribute in product comparison, set Comparable on Storefront to Yes.
- To include dropdown, multiple select, or price attributes in layered navigation, set Use in Search Results Layered Navigation to one of the following options:

    - **Filterable** (with results)
    - **Filterable** (no results)

- To use in layered navigation on search results pages, set Use in Search Results Navigation to Yes and enter a number in the Position field.
- To use the attribute in price rules, set Use for Promo Rule Conditions to Yes.
- To allow HTML formatting in the text, set Allow HTML Tags on Storefront to Yes.
- This setting makes the WYSIWYG editor available when editing the field.
- To include the attribute on the product page, set Visible on Catalog Pages on Storefront to Yes.
- Set the following parameters, as supported by your theme:

    - To include the attribute in product lists, set Used in Product Listing to Yes.
    - To use the attribute as a sorting parameter for product lists, set Used for Sorting in Product Listing to Yes.

When finished, click on "Save Attribute".

# Product Swatches

Customers have high expectations when it comes to choosing a color, and accurately representing each available color, pattern, or texture in product descriptions is crucial. For example, the pants in the following example are available in specific shades of red, green, and blue, rather than just generic red, green, and blue.

## Swatches on a Product Page

For configurable products, color can be indicated by visual swatches, text swatches, or input controls. Swatches can be used on product pages, in product listings, and in layered navigation. On the product page, swatches are synchronized to display the corresponding product image when selected. Additionally, the selected swatch's value appears in the input field, and the swatch is outlined as the current selection.

### Note

Swatch attributes can be configured to not display corresponding simple product images when the swatch is selected by setting the "Update Product Preview Image" option value to No on the Attribute Edit page in the Admin.

## Text-Based Swatches

If an image isn't available for a swatch, the attribute value appears as text. A text-based swatch functions like a button with a text label and behaves similarly to a swatch with an image. When text-based swatches are used to display available sizes, any unavailable size is crossed out.

## Swatches in Layered Navigation

Swatches can also be used in layered navigation if the "Use in Layered Navigation" property of the color attribute is set to Yes.

## Creating Swatches for Products

### Step 1: Create the Swatches

#### Method 1: Add a Color Swatch

1. Open the image in a photo editor and use the eye dropper tool to identify the exact color and note the hexadecimal value.
2. Navigate to Stores > Attributes > Product in the Admin sidebar.
3. Open the color attribute in edit mode.
4. Verify that "Catalog Input Type for Store Owner" is set to "Visual Swatch".
5. Under "Manage Swatch (Values of Your Attribute)", click "Add Swatch" and follow the instructions to add the swatch.
6. Save the attribute.

#### Method 2: Upload a Swatch Image

1. Open the product image in a photo editor and save a square area that depicts the color, pattern, or texture.
2. Navigate to Stores > Attributes > Product in the Admin sidebar.
3. Open the color attribute in edit mode.
4. Verify that "Catalog Input Type for Store Owner" is set to "Visual Swatch".
5. Under "Manage Swatch (Values of Your Attribute)", click "Add Swatch" and follow the instructions to upload the swatch image.
6. Save the attribute.

### Step 2: Update the Products

1. Navigate to Catalog > Products in the Admin sidebar.
2. Filter and select the applicable products.
3. Set Actions to "Update Attributes".
4. Scroll down to the Color attribute, select the desired swatch, and save.
5. Refresh the cache.

## Adding Swatches to a Simple Product

1. Navigate to Catalog > Products in the Admin sidebar.
2. Open the product in edit mode.
3. Click "Create Configurations" under the Configurations tab.
4. Choose the Color attribute and proceed with the configuration.
5. Configure the images, price, and quantity for each variation.
6. Click "Generate Products" when satisfied.

