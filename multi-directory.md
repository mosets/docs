# Multi Directory

- [Introduction]({{version}}/multi-directory#introduction)
- [Category Specific Custom Fields]({{version}}/multi-directory#category-specific-custom-fields)
- [Custom Configuration at Top Level Categories]({{version}}/multi-directory#custom-config-at-TLC)
- [Category Template and Main Index Template Page]({{version}}/multi-directory#category-template-main-index-template)
- [More]({{version}}/multi-directory#more)

## Introduction {#introduction}
In Mosets Tree, you can create two or more directories at the same time on a single Mosets Tree installation.

## Category Specific Custom Fields {#category-specific-custom-fields}
This allows you to assign [custom fields]({{version}}/fields#custom-fields) to selected top level categories. Such assignment is inherited to all sub-categories.
 
Custom fields' assignment to top level categories can be done while you're editing/adding a custom field or top level category in Mosets Tree's back-end. While you're editing a custom field, you can select which top level categories the custom field will appear. Similarly, when you are editing a category, you can select which custom field will appear in this top level category and its sub-categories.

## Custom Configuration at Top Level Categories {#custom-config-at-TLC}
Custom Configuration lets you override Mosets Tree's configuration in top level category. Any overrides configured here will be inherited to all listings and sub-categories underneath it. 
To access this feature, simply create or edit existing top level category. The overridable configurations can be found near the middle of the page. 
By default, all configurations are disabled (unchecked checkboxes) and will inherit values from Mosets Tree Global configurations. To override it, tick the checkbox on the left and set a desired value.

## Category Template and Main Index Template Page {#category-template-main-index-template}
Categories in Mosets Tree can be configured to use any template. Additionally, it can be configured to use Index Template Page so that it looks and works like a directory. Both of these can be configured when you edit/add a category.
Making use of these 2 features further allow you to give a unique look and feel to a top level category.

## More {#more}
The above are the major configurations that you can use to create multiple unique directories out of top level categories. There are other improvements in Mosets Tree that helps you to run multiple directories:
 - All Mosets Tree allows you to limit its appearance at selected top level categories.
 - You can create a menu item based on Mosets Tree's Category menu item type and give it a unique alias. Whenever a listing or category that is a descendant of this category, it will use its alias to generate SEF URLs, without any hint of alias of Mosets Tree's Root category.
 - A 'Directory' field type is available to display the name and link to a listing's top level category.
 - Each category and listing page contains a class in the form of _tlcat-id-#_, where _#_ is the ID of the category. You can use this in your CSS, to target specific style to a directory.