# Categories

Categories in Mosets Tree are the primary way to structure your directory in Mosets Tree. Categories are among the first thing your users will see when they visit your directory. They also dictate how search engine friendly (SEF) URLs are generated for your listings.

Categories can be added to your directory in a few ways. You can them through Mosets Tree back-end interface or you can allow your users to add them in front-end.

## Top Level Categories

Top level categories are the first level of categories in your directory. They have the additional capability called Category Configuration. Category Configuration lets you override [Mosets Tree configuration]({{version}}/configuration) that will only affects this category and its sub-categories.

For example, you can disable reviews in a top level categories while they are accepted in other categories. Or you can show User Profile in a top level category while they are not shown in others.

Top Level Categories and Category Configuration are part of the system that make the [Multi Directory]({{version}}/multi-directory) support possible.


## Edit Screen

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

## Field Assignments
Instead of showing all your custom fields to all categories, Fields Assignment lets you to choose which field to appear in each top level category. Let's say if you have a top level category for "Real Estate Properties". You can assign "Rooms", "Bathroom" and "Facilities" to it. This way, the 3 fields only appear in Real Estate Properties and no where else. 

Alternatively, you can select which top level categories the custom field will appear through Custom Field function in Mosets Tree back-end interface.  

## Association

@TODO: CY

## Operations
Mosets Tree always keep track on the total number of sub-categories and listings for each category. These number might be inaccurate sometimes. Thus, operations help to recount these number and return the actual number so a more accurate number will be displayed. 

### Force recount of categories and listings
Full recount will force Mosets Tree to recount all sub-categories of the current category. If you have a big category, this method will be very slow and might cause PHP execution timeout. However this method is the most accurate.

### Full recount of categories and listings
Fast recount will only count the current active category's listings and add all sub-category listings(if available) based on the total stored in database. This is a faster method but will not be accurate if the subcategories total is not correct.