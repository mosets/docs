# Categories

- [Introduction]({{version}}/categories#intro)
- [Top Level Categories]({{version}}/categories#tlc)
- [Edit Screen]({{version}}/categories#edit)
- [Fields Assignment]({{version}}/categories#fields-assignment)
- [Association]({{version}}/categories#association)
	- [Setting up Category Association]({{version}}/categories#setting-up-association)
	- [Using Category Association]({{version}}/categories#using-association)
- [Operations]({{version}}/categories#operations)
- [Frequently Asked Questions]({{version}}/categories#faqs)

## Introduction {#intro}

Categories in Mosets Tree are the primary way to structure your Mosets Tree directory. Categories are among the first thing your users will see when they visit your directory. The categories will also dictate how search engine friendly (SEF) URLs are created for your listings.

Categories can be added to your directory in a few ways. You can add them through the Mosets Tree back-end component interface; or you can allow your users to add categories in the directory front-end.

## Top Level Categories {#tlc}

Top Level categories are the first level of categories in your directory. They have an additional capability that is called Category Configuration. Category Configuration lets you override [Mosets Tree configuration]({{version}}/configuration) that will only affects this Top Level category and its sub-categories.

For example, you can disable reviews in a top level category while reviews are still accepted in other categories. Or you can show User Profiles in a top level category while they are not shown in categories.

Top Level Categories and Category Configuration are part of the system that make the [Multi Directory]({{version}}/multi-directory) support possible.


## Edit Screen {#edit}

### Related Categories

Related Categories allow you to select one or more categories that are related to the current category. This allows your users who are browsing the current category to have access to relevant categories through the links provided.

### Allow listing submission
"_Add your listing here_" link appears in all category pages if you set the "Allow listing submission" function to "Yes". It allows your users to submit listings on the directory category pages.

Setting this to "_No_" will hide this link in your category pages and will prevent users from being able to submit listings on those pages.

### Use Main Index template page
By enabling this option, the category page will look and function like the directory Index page.

Demo: http://demo.mosetstree.com/properties.html

: When using the main index template in a category page, you can see the category page displays some modules that are the same as what you see in the Main Index, for example, the Alpha Index and the Directory Menu. You can customize this template through the Mosets Tree back-end component to position the modules where you want them to display.

### Alias
Aliases are the text that represent the title of your category. They are used to make Search Engine Friendly URLs. Mosets Tree will generates an alias for your category if you leave this field empty when saving category edits.

It is recommended that the Alias should only contain lowercase letters and dashes(-), and no blank spaces, because it is used to create the category URL.

### Custom Title
By default, the category page's `<TITLE>` tag for each category is the name of the category itself. The Custom Title field allows you to replace the title tag text with a custom title.

### Template
Allows you to select which [Mosets Tree template]({{version}}/template) to use in this category. Changing this only affects the template used by pages for this category only. If you want to apply the same template to all of its sub-categories, then check the "_Change all sub categories to use this template_" checkbox and save the category.

### META Description & META Keywords

META Description describes your category page to search engines. META Keywords, on the other hand, tells the search engines what keywords or topics your category uses. You can customize each individual category's META Description and Keywords in their fields in the category Edit page.

However, for your directory's index, you need to [override]({{version}}/language#overrides) these 2 language keys:

	COM_MTREE_METADESC_ROOT
    COM_MTREE_METAKEY_ROOT

in order to set the directory index's META Description and Keywords.

## Fields Assignments {#fields-assignment}
Instead of showing all your custom fields in all categories, Fields Assignment lets you choose which field(s) you want to display in a top level category. For example, let's say you are editing a top level category for "Real Estate Properties". You can assign the "Rooms", "Bathroom" and "Facilities" custom fields to this category. In this situation, the 3 fields will only appear in the Real Estate Properties top level category, and no where else.

Alternatively, you can also select which top level categories you want specific custom field(s) to display in by editing the Custom Field section in the Mosets Tree back-end component.

## Association {#association}

Category association allows you to create a "is a member of" relationship with an associated category. For example, a "_Persons_" category can be associated with a "_Companies_" category. In this type of association, the listings created under the "_Persons_" category will have the option to associate those listings with one of the listings listed under the "_Companies_" category.

### Setting up category association {#setting-up-association}

1. To set up a category association in Mosets Tree, start by creating two top level categories. Following the example above, the two categories will be "_Companies_" and "_Persons_".
2. In our example, listings under the "_Persons_" category will be a member of company listings in the "_Companies_" category. In this type of association, edit the "_Persons_" category and set its "_Associated Category_" to the "_Companies_" category.
3. Next, go to the "_Custom Fields_" section and create a new custom field based on [Associated Listing]({{version}}/fields#fieldtype-associatedlisting) field type. Enter its caption as "_Company_". Since this field will only be used in the "_Persons_" category, assign this custom field to the "_Persons_" category only.

### Using category association {#using-association}

1. Now that you have setup the category association, then you can start creating a few companies under the "Companies" category. For this example, create 2 listings under the "Companies" category, ie: 'Mosets' and 'Joomla' as their name.
2. Next, create 2 listings under the "Persons" category. For this exmaple, let's name them "_Amy_" and "_Ben_". You will see the "_Company_" custom field you've created in the steps above while doing this. This is a special type of custom field that shows you the selection based upon the listings available in the associated category you set up above. In this example, it will show you 2 listings from the "_Companies_" category.
Choose "_Mosets_" as the company for both "_Amy_" and "_Ben_" listings.
3. Go to your site's front-end and view the "_Mosets_" listing. If you have set up everything correctly, you will see the Mosets listing, just like any other listing in Mosets Tree. Scroll down the page and you will see "_Amy_" and "_Ben_" listings underneath it.

This is the result of setting up the category association in the "_Persons_" category to the "_Companies_" and then using the "_Associated Listing_" field type which enables you to define the listing relationships between the 2 categories.

Demo: http://demo.mosetstree.com/real-estate-companies/957-joomla-estate.html

: _Properties_ category is associated with _Real Estate Companies_ company. We have a couple of listings from _Properties_ that are associated with the "_Joomla Estate_" listing from _Real Estate Companies_. On that page, you can see all the listings that are associated with it.

## Operations {#operations}
For performance reasons, Mosets Tree keeps track of the total number of sub-categories and listings for each category in its own database table. Sometimes these number might be inaccurate and you can use the Operations tab features to recount the categories and listings to correct the total number inaccuracy.

### Force recount of categories and listings
Full recount that will force Mosets Tree to recount all sub-categories of the current category. If you have a big category, this method may be very slow and might cause a PHP execution timeout. However, this method is the most accurate.

### Full recount of categories and listings
Fast recount will only count the current active category's listings and add all sub-category listings (if available) based on the total stored in database. This is a faster method but will not be as accurate if the subcategories totals are not correct.

## Frequently Asked Questions {#faqs}

{question}How do I show category images in the Mosets Tree's Index?{/question}
{answer}
Category images by default are shown only when you view the category page. You can configure this in:

**Mosets Tree -> Templates -> current default template**

 set "**Show Categories' images**" to `Yes` to have the images display in the directory Main Index.
{/answer}

{question}Is it possible to hide all listings of a specific category?{/question}
{answer}
Yes. You can hide all listings of a category by using the Mosets Tree back-end component. Go to the edit category page, set "**Show Listing**" to `No` in the category's _Edit Screen_.
{/answer}

{question}I don't want listings to be shown underneath every category in Main Index. How can I do that?{/question}
{answer}
In order to hide all the listings under each top level categories, you can go to:

**Mosets Tree back-end -> Templates -> [current default template]**

set "**Number of listings under top level cats.**" to `0`. Make sure you check whether your settings use the Main Index template for the category pages. This configuration will affect the index page and all the category pages that use the main index template page.
{/answer}

{question}My categories are showing an incorrect number of listings or categories. How can I fix that?{/question}
{answer}
You can fix this by performing a recount through the [**Operations**]({{version}}/categories#operations) tab when you're editing a category in the Mosets Tree back-end.
{/answer}
