# Multi Directory

- [Introduction]({{version}}/multi-directory#introduction)
- [Category Specific Custom Fields]({{version}}/multi-directory#category-specific-custom-fields)
- [Category Configuration at Top Level Categories]({{version}}/multi-directory#category-config-at-TLC)
- [Category Template and Main Index Template Page]({{version}}/multi-directory#category-template-main-index-template)
- [Modules]({{version}}/multi-directory#modules)
- [Related Features]({{version}}/multi-directory#related-features)

## Introduction {#introduction}
In Mosets Tree, you can create two or more directories at the same time on a single installation. This is possible by leveraging 3 Mosets Tree features:

- Category Specific Custom Fields
- Category Configuration at Top Level Categories
- Category Template and Main Index Template Page

Each on its own provides way for you to create different type of categories that behave, display and work differently. Using all 3 allows allows you to create top level categories that behave and works like a separate directory.

## Category Specific Custom Fields {#category-specific-custom-fields}
This allows you to assign [custom fields]({{version}}/fields#custom-fields) to selected top level categories. Such assignment is inherited to all sub-categories.

Custom fields' assignment to top level categories can be done while you're editing/adding a custom field or top level category in Mosets Tree's back-end. While you're editing a custom field, you can select which top level categories the custom field will appear. Similarly, when you are editing a category, you can select which custom field will appear in this top level category and its sub-categories.

Demo: http://demo.mosetstree.com/properties/apartments/add.html

: You can see that the **Add Listing** form for _Apartment_ category has, among others, fields for _Bedrooms_, _Bathrooms_ and _Facilities_. These fields are only assigned to _Properties_ top level category.

: Compare this with _Models_ category's [Add Listing form](http://demo.mosetstree.com/models/add.html). You will see fields like _Gender_, _Skin Color_ and _Body Type_. Again, these fields are assigned to _Models_ category, thus only available to listings created within it.

## Category Configuration at Top Level Categories {#category-config-at-TLC}
Category Configuration lets you override Mosets Tree's configuration in top level category. Any overrides configured here will be inherited to all listings and sub-categories underneath it.

To access this feature, just create or edit existing top level category. The overridable configurations can be found under "**Category Configuration**" tab.

By default, all configurations are disabled (unchecked checkboxes) and will inherit values from Mosets Tree Global configurations. To override it, tick the checkbox on the left and set a desired value.

## Category Template and Main Index Template Page {#category-template-main-index-template}
Categories in Mosets Tree can be configured to use any template. Additionally, it can be configured to use Index Template Page so that it looks and works like a directory. Both of these can be configured when you edit/add a category.

## Modules {#modules}

Each Mosets Tree modules has a tab called [Mosets Tree Assignment Options]({{version}}/modules#assignment) that lets you publish to a specific set of top level categories. Many modules also have a parameter for "**Category ID**" that lets you set the active category in which the module operate on.

With these 2 features, you can, for example, create a [Search module]({{version}}/modules#mod-mt-search) that are published in a top level category and search listings within it.

## Related Features {#related-features}
The above are the major configurations that you can use to create multiple unique directories out of top level categories. There are other features in Mosets Tree that helps you to run multiple directories:

- You can create a menu item based on Mosets Tree's Category menu item type and give it a unique alias. Whenever a listing or category that is a descendant of this category, it will use its alias to generate SEF URLs, without any hint of alias of Mosets Tree's Root category.
- A [Directory]({{version}}/fields#fieldtype-directory) field type is available to display the name and link to a listing's top level category.
- [Mosets Tree localization]({{version}}/language#top-level-categories) has support that helps you to show different term in for some language string in top level categories.
- Each category and listing page contains a class in the following format "_tlcat-id-#_", where _#_ is the ID of the category. You can use this in your CSS, to apply specific style to a directory.
