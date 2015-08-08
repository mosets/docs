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
"Add your listing here" link will appear in all category pages if you set the "Allow listing submission" function to "Yes". It allows your users to submit listings to the categories. 

### Use Main Index template page
By enabling this function, all the category pages will look and work like the Alpha Index page. 

### Alias
Alias is used to generate SEF URLs which worked like a pointer that direct your users to each page of your site. Alias preferably should contain alphanumerics and dashes. 

### Custom Title
Custom Title allows you to create a name for the browser tab of your categories. By default, browser title for each category is the name of the category itself.

### Template
Mosets Tree allows you to configure the layout of your categories by selecting any templates provided. You can always customize the templates according to your preference through the Template function in Mosets Tree back-end interface. All you need to do is make a copy of the default Mosets Tree template and make changes to your new template.  

## Field Assignments
Instead of showing all your custom fields to all categories, Fields Assignment lets you to choose which field to appear in each top level category. Let's say if you have a top level category for "Real Estate Properties". You can assign "Rooms", "Bathroom" and "Facilities" to it. This way, the 3 fields only appear in Real Estate Properties and no where else. 

Alternatively, you can select which top level categories the custom field will appear through Custom Field function in Mosets Tree back-end interface.  

## Association

@TODO: CY

## Operations
Directory page of the Mosets Tree back-end interface shows you the total number of sub-categories for each top level category. 

How does this feature function well?

### Force recount of categories and listings
Full recount will force Mosets Tree to recount all sub-categories of the current category. If you have a big category, this method will be very slow and might cause PHP execution timeout. However this method is the most accurate.

### Full recount of categories and listings
Fast recount will only count the current active category's listings and add all sub-category listings(if available) based on the total stored in database. This is a faster method but will not be accurate if the subcategories total is not correct.