# Search

It would be tedious if you have to browse through categories and look through many listings to find the listings you're looking for. Mosets Tree comes with 3 types of searches to help your users to search for listings quickly.

## Simple Search
Simple Search is one of the popular module a directory will publish. It provides a text box for searching keyword that matches all listing's fields that is set to "[Simple Searchable]({{version}}/fields#simple-searchable)". You can choose to display a drop down categories list through setting in [Search module]({{version}}/modules#mod-mt-search). This allows users to limit their searches in a specific category. 

By default, this searching action performed within the entire directory because its "Parent Cat. ID" is set to the root ID. You can customize a parent ID and thus if "Show Category" is set to `No`, users' searches through Search module will be limited to the appointed parent category. Note that you can get the "Parent Cat. ID" in left hand side table of the "Category" page in back-end. 

## Advanced Search
Advanced Search provides users a more precise search to a listing in your directory. It narrowed down the search results by allowing users to enter several searching criteria and only display those listings that match all or any of the criteria entered by users. You can customize which searching criteria fields to be provided for your user by setting the fields to [Advanced Searchable]({{version}}/fields#advanced-searchable).

Advanced Search usually search against all your directory pages. In order to search within a specific category, you can modify the directory's URL. With [SEF URLs]({{version}}/configuration#sefurls) enabled, you can direct to the specific category advanced search page by entering the category's alias in front of `/advanced-search`. For example: 
    
    http://www.example.com/directory/movies/advanced-search  
    
When no SEF URLs is enable, you can go to any of the category page and replace `list.cats` to `advsearch` in URL for entering to the category Advanced Search.

## Filters
Filters is available by publishing Mosets Tree's [Filter module]({{version}}/modules#mod-mt-filter) to your directory. Similar to Advanced Search, Filters is also an option that allows users to filter the listings to quickly find the listing they are looking, except that users can use this searching method in any pages of your directory from where you want the module to be published.  

Instead of searching against the entire directory, you can change the 'Category ID' in Filter module so searches will be performed within the specified category. Bear in mind that you have to configure the fields to [Filter Searchable]({{version}}/fields#filter-searchable) before you can allow your users to search through Filters. 

