# Configuration

Configurations in Mosets Tree controls most aspects of how Mosets Tree works. It can be access in Mosets Tree's back-end: "**Mosets Tree -> Configuration**". Most of the configurations are self explanatory (at least we try to be!), so we will cover some of the importants one here.

## Main

 ### View access level
 View access level allows you to decide who can view your directory or top level category. 

 ### Admin e-mail
 This is where all the notification e-mails are sent to. You can enter more than one e-mail separated by commas.

 ### Adding new listing requires approval
 Setting this parameter to Yes so that you can choose whether or not to approve a new listing before it is published.

 ### Number of days to show as new listing
 A "New" badge will be shown beside the listing's name if it is a new added listing. This parameter let you decide the number of days you want a listing to be displayed as new listing. 

 ### Use WYSIWYG Editor in front-end Description field
 By selecting "Yes" in this parameter will allow you to use HTML tags in description field. Please note that HTML tags will be stripped in summary view and only shown in details view. 

 ### Permission
 Permission allows you to control which user group will gain access to certain function. 

## Category

 ### Primary ordering
 Primary ordering allows you to set the order of how categories will appear in the explorer section of Mosets Tree back-end interface. You can customize the order by clicking the arrow signs in the ordering column of directory page.

 ### Secondary ordering 
 This parameter decides the second ordering option to follow if two or more categories have the same order in primary ordering.

 ### Type of listings to show in Index
 In the index page, you can set which type of listings to be displayed. By default, it will show listings that assigned to current category.

 ### Number of listings in index
 You can enter the number of top listings to show in index view. If you set the type of listing to show in index to "Default", the number of listings shown will be based on "Number of listings per page" setting you have configured in [Listing]({{version}}/configuration#listings) tab.

 ### Display categories
 If this parameter is set to No, Categories will only be displayed to users in "All Categories" page and no where else.

 ### Display empty category
 Empty category means category that contains no sub-categories or listings. By setting Yes to this parameter, all the hidden categories will be hidden.

 ### Display 'All Listings' link
 This parameter enables 'All Listings' link to be displayed at the top of listing list. "All Listings" displays all the listings that belong to the category, including sub-categories' listing.

 ### Display Filters {#filters}
 It's never been easier to search for a listing in the category other than enabling "Display Filters". By doing this, an option will be shown in "All Listings" page that allows your users to filter the listings so they can find the listing they are looking for in a faster way. 

## Listing {#listings}
Data entered to a field is displayed in two places in Mosets Tree front-end , Summary view and Details view. 

 ### Listing details view access level
 You can always decide who are authorized to access listings in details view. Unauthorized parties can only view listings in summary view.

 ### Default sorting in All Listings
 This parameter let you decide what sort of listing you want your users to view first in All Listings page.
 
 ### All Listings page sort options
 You can also customize the option in "Sort by" field from Mosets Tree back-end interface.

 ### Show user profile in Listing Details page
 By setting Show user profile in Listing Details page to Yes, your users will be able to view the details of every listing's owner.
 
 ### Additional characters for Alpha Index
 By default, Mosets Tree displays Alpha Index in alphabetic and numeric characters for your users to select. This parameter allows you to add additional characters to the end of the alpha list as part of the selection.

 ### Allow listings submission in root
 If you allow listings submission in root, your users will be able to submit listings through Index page.

 ### Allow changing of category in Add Listing
 Set this parameter to Yes to allow changing of category when users add listings. Otherwise, listing added will belong to the category from where the users click "Add your listing here" link.

 ### Allow user to assign more than one category to listing
 Sometimes, your users may have a listing which is related to multiple categories. With "Allow changing of category in Add Listing" set to Yes, enable also "Allow user to assign more than one category to listing". By doing this, your users can assign more than one category to a listing when clicking "Also appear in this category" link.

 ### Max. number of assignable secondary categories
 This parameter lets you limit your users about the maximum number of categories which a listing can assign to. 

 ### Display listings in root
 You can choose whether or not to display listings in Index page. Set parameter to Yes so your users can access to all the listings through Index page.

 ### Required fields to mark listing as updated
 By default, any update to a listing causes the listing to be updated with a new modified date. This option allows you to enter the ID of one or more fields (separated by comma) that must be changed before a listing is marked as updated. You can get the field's ID from the ID column in Mosets Tree back-end "Custom Fields" interface. 

 ### Number of new listings per page
 This parameter control the number of new listings per page that will be displayed to users in "Recently Added" page.

 ### Total new listings
 You can set the total number of most recently added listings to be displayed in "Recently Added" page.

 ### Number of days to expire listing
 Specify the number of days for a listing to remain published upon submission. Once this number of days has passed, the listing will be published down and not visible in front-end. Enter 0 to disable this feature.

## Search
Mosets Tree currently support three types of searching functions, which are Simple Search, Advanced Search and Filters Search. [Filter Search]({{version}}/configuration#filters) is displayed in "All Listing" page which has been explained earlier. 

 ### Simple Search
 Simple Search provided by mod_mt_search module and consist of a single text input field. When users search through this module, the search word will be matched against fields that are marked as Simple Searchable.
 
  #### Primary ordering
  Primary ordering controls the ordering of the tags search and simple search results through the search module.

  #### Secondary ordering
  Secondary ordering only works if two or more search results have the same order in primary ordering. 

 ### Advanced Search
 Advanced Search will appear in a dedicated page. This page is accessible through a link in mod_mt_search. Advanced search allow users to locate listings that meet any or all criteria entered, based on user's option in Advanced Search page.

  #### Default sorting in results page
  Through Mosets Tree back-end interface, you can decide in what sort type you want the listing result to be viewed in Advanced Search.

## Rating/Rev


## Features


## Notify


## Image


## Sharing


## RSS


## SEF URLs


## Captcha


## Admin







