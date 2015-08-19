# Categories

- [Introduction]({{version}}/categories#intro)
- [Top Level Categories]({{version}}/categories#tlc)
- [Edit Screen]({{version}}/categories#edit)
- [Fields Assignment]({{version}}/categories#fields-assignment)
- [Association]({{version}}/categories#association)
	- [Setting up Category Association]({{version}}/categories#setting-up-association)
	- [Using Category Association]({{version}}/categories#using-association)
- [Operations]({{version}}/categories#operations)

## Introduction {#intro}

Categories in Mosets Tree are the primary way to structure your directory in Mosets Tree. Categories are among the first thing your users will see when they visit your directory. They also dictate how search engine friendly (SEF) URLs are generated for your listings.

Categories can be added to your directory in a few ways. You can them through Mosets Tree back-end interface or you can allow your users to add them in front-end.

## Top Level Categories {#tlc}

Top level categories are the first level of categories in your directory. They have the additional capability called Category Configuration. Category Configuration lets you override [Mosets Tree configuration]({{version}}/configuration) that will only affects this category and its sub-categories.

For example, you can disable reviews in a top level categories while they are accepted in other categories. Or you can show User Profile in a top level category while they are not shown in others.

Top Level Categories and Category Configuration are part of the system that make the [Multi Directory]({{version}}/multi-directory) support possible.


## Edit Screen {#edit}

### Related Categories

Related Categories allows you to select one or more categories that are related to a current category. This allows your users who are browsing the current category can access to relevant categories through the links provided.

### Allow listing submission
"_Add your listing here_" link appears in all category pages if you set the "Allow listing submission" function to "Yes". It allows your users to submit listings to the categories.

Setting this to "_No_" will hide this link in your category page and will prevent user from being able to submit listings here.

### Use Main Index template page
By enabling this function, the category page will look and work like the Index page.

### Alias
Aliases are short pieces of text that represent the title of your category. They are used to make Search Engine Friendly URLs. Mosets Tree will generates one for your category if you leave it empty.

Alias preferably should contain only lowercase letters and dashes(-).

### Custom Title
By default, the category page's `<TITLE>` tag for each category is the name of the category itself. Custom Title allows you to override this with a custom title.

### Template
Allows you to select which [Mosets Tree template]({{version}}/template) to use in this category. Changing this only affects the template used by pages from this category only. If you want to apply the same template to all its sub-categories, check the "_Change all sub categories to use this template_" checkbox and save the category.

## Fields Assignments {#fields-assignment}
Instead of showing all your custom fields to all categories, Fields Assignment lets you to choose which field to appear in a top level category. Let's say if you are editing a top level category for "Real Estate Properties". You can assign "Rooms", "Bathroom" and "Facilities" custom fields to it. This way, the 3 fields only appear in Real Estate Properties and no where else.

Alternatively, you can select which top level categories a custom field will appear through Custom Field section in Mosets Tree back-end interface.

## Association {#association}

Category association allows you to create "is a member of" relationship with an associated category. For example, a "_Persons_" category can be associated with "_Companies_" category. In such association, listings created under "_Persons_" category will have an option to associate itself with one of the listings listed under "_Companies_" category.

### Setting up category association {#setting-up-association}

1. To set up category association in Mosets Tree, start by creating two top level categories. Following the example above, the two categories will be "_Companies_" and "_Persons_".
2. In our example, listings under "_Persons_" category will be a member of company listings in "_Companies_" category. To such association, edit the "_Persons_" category and set its "_Associated Category_" to "_Companies_" category.
3. Next, go to "_Custom Fields_" section and create a new custom field based on [Associated Listing]({{version}}/fields#fieldtype-associatedlisting) field type. Enter its caption as "_Company_". Because this field is only used in "_Persons_" category, assign this custom field to "_Persons_" category only.

### Using category association {#using-association}

1. Now that you've done setting up category association, you can start by creating a few companies under "Companies" category. For this example, create 2 listings under "Companies" category, ie: 'Mosets' and 'Joomla' as their name.
2. Next, create 2 listings under "Persons" category. Let's name them "_Amy_" and "_Ben_". You will see the "_Company_" custom field you've created in steps above while doing this. This is a special type of custom field that shows you the selection based on the listings available in the associated category you set up above. In this example, it will show you 2 listings from "_Companies_" category.
Choose "_Mosets_" as the company for both "_Amy_" and "_Ben_" listings.
3. Go to your site's front-end and view the "_Mosets_" listing. If you've set up everything correctly, you will see the Mosets listing, just like any other listing in Mosets Tree. Scroll down the page and you will see "_Amy_" and "_Ben_" listings underneath it.

This is the result of setting up the category association in "_Persons_" category to "_Companies_" and then using "_Associated Listing_" field type to let you define listings relationship between the 2 categories.

Demo: http://demo.mosetstree.com/real-estate-companies/957-joomla-estate.html

: _Properties_ category is associated with _Real Estate Companies_ company. We have a couple of listings from _Properties_ that is associated with "_Joomla Estate_" listing from _Real Estate Companies_. In this page, you can see all the listings that are associated with it.

## Operations {#operations}
For performance reason, Mosets Tree keeps track on the total number of sub-categories and listings for each category in its own database table. Some times, these number might be inaccurate. Thus, operations help you to recount categories and listings to fix this.

### Force recount of categories and listings
Full recount will force Mosets Tree to recount all sub-categories of the current category. If you have a big category, this method may be very slow and might cause PHP execution timeout. However this method is the most accurate.

### Full recount of categories and listings
Fast recount will only count the current active category's listings and add all sub-category listings(if available) based on the total stored in database. This is a faster method but will not be accurate if the subcategories total are not correct.