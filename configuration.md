# Configuration

Configurations in Mosets Tree controls most aspects of how Mosets Tree works. It can be access in Mosets Tree's back-end: "**Mosets Tree -> Configuration**". Most of the configurations are self explanatory (at least we try to be!), so we will cover some of the importants one here.

## Main

 ### View access level
 View access level allows you to decide who can view your directory or top level category. 

 ### Admin e-mail
 This is where all the notification e-mails are sent to. You can enter more than one e-mail separated by commas.

 ### Adding new listing requires approval
 Setting this parameter to `Yes` so that you can choose whether to approve a new listing before it is published.

 ### Number of days to show as new listing
 A "New" badge will be shown beside listing's name if it is a new added listing. This parameter let you decide the number of days you want a listing to be displayed as new listing. 

 ### Use WYSIWYG Editor in front-end Description field
 By selecting `Yes` in this parameter will allow you to use HTML tags in description field. Please note that HTML tags will be stripped in summary view and only shown in details view. 

 ### Permission
 Permission allows you to control which user group will gain access to certain function. 

## Category

 ### Primary ordering
 Primary ordering allows you to set the order of how categories will be appeared in Mosets Tree back-end interface. You can customize the order by clicking the arrow signs in the ordering column of directory page.

 ### Secondary ordering 
 This parameter decides the second ordering option to follow if two or more categories have the same order in primary ordering.

 ### Type of listings to show in Index
 By default, listings displayed in Index page are those had assigned to the current category. You can always customize the type of listings to show in Index, for example, displaying the Top Rated listings instead of the default type.

 ### Number of listings in index
 You can set the number of top listings to be shown in index view. If you set the type of listing to show in index to "Default", the number of listings shown will be based on "Number of listings per page" setting you have configured in [Listing]({{version}}/configuration#listings) tab.

 ### Display categories
 If this parameter is set to No, Categories will only be displayed to users in "All Categories" page and no where else.

 ### Display empty category
 Empty category means category that contains no sub-categories or listings. By setting `Yes` to this parameter, all the empty categories will be hidden.

 ### Display 'All Listings' link
 This parameter enables 'All Listings' link to be displayed at the top of listing list. "All Listings" displays all the listings that belong to the category, including sub-categories' listing.

 ### Display Filters {#filters}
 It's never been easier to search for a listing in the directory other than enabling "Display Filters". By doing this, an option will be shown in "All Listings" page that allows your users to filter the listings so they can find the listing they are looking for in a faster way. 

## Listing {#listings}
Data entered to a field is displayed in two places in Mosets Tree front-end , Summary view and Details view. 

 ### Listing details view access level
 You can always decide who are authorized to access listings in details view. Unauthorized parties can only view listings in summary view.

 ### Default sorting in All Listings
 This parameter let you decide which sort of listing you want your users to view first in "All Listings" page.
 
 ### All Listings page sort options
 Sort options allows you to customize the option of "Sort by" selection list in "All Listings" page.

 ### Show user profile in Listing Details page
 By setting Show user profile in Listings Details page to `Yes`, other readers will be able to view the details of the listing's owner.
 
 ### Additional characters for Alpha Index
 By default, Mosets Tree displays Alpha Index in alphabetic and numeric characters for your users to select. This parameter allows you to add additional characters to the end of the alpha list as part of the selection.

 ### Allow listings submission in root
 If you allow listings submission in root, your users will be able to submit listings through Index page.

 ### Allow changing of category in Add Listing
 Set this parameter to `Yes` to allow changing of category when users add listings. Otherwise, listing added will belong to the category from where users click the "Add your listing here" link.

 ### Allow user to assign more than one category to listing
 Sometimes, your users may have a listing which is related to multiple categories. With "Allow changing of category in Add Listing" set to `Yes`, enable also "Allow user to assign more than one category to listing". By doing this, your users can assign more than one category to a listing when clicking "Also appear in this category" link.

 ### Max. number of assignable secondary categories
 This parameter lets you limit your users the maximum number of categories which a listing can assign to. 

 ### Display listings in root
 You can choose whether to display listings in Index page. Set parameter to `Yes` so your users can access to the listings through Index page.

 ### Required fields to mark listing as updated
 By default, any update to a listing causes the listing to be updated with a new modified date. This option allows you to enter the ID of one or more fields (separated by comma) that must be changed before a listing is marked as updated. You can get the field's ID from the ID column in Mosets Tree back-end "Custom Fields" interface. 

 ### Number of listings per page
 This parameter let you set the maximum number of listings to be displayed in one page.
 
 ### Number of new listings per page
 This parameter control the number of new listings per page that will be displayed in "Recently Added" page.

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
  Secondary ordering works if two or more search results have the same order in primary ordering. 

 ### Advanced Search
 Advanced Search will appear in a dedicated page. This page is accessible through a link in mod_mt_search. Advanced search allow users to locate listings that meet any or all criteria entered, based on user's option in Advanced Search page.

  #### Default sorting in results page
  Through Mosets Tree back-end interface, you can decide how you want the listing result to be viewed in Advanced Search.

## Rating/Rev

 ### Rating
 
  #### Show rating
  Set Show rating to `Yes` so users is able to rate the listings.
  
  #### User can only rate once
  You can set this to `Yes` and therefore for every listing, users may only rate one time. No re-rating is allowed.
  
  #### Prevent user from rating own listing
  You can also prevent the listing's owners to rate their own listings by setting this to `Yes`.
   
  #### Minimum number of votes to be considered for top rated listings
  To be fair in the calculation for top rated listings, it is recommended to set a minimum number of votes for a listing before it can be considered as top rated listing. For example, in order for a listing to be considered as top rated, it needs to gain good votes from at least 100 voters.
  
  #### Minimum number of votes to show rating
  You can sets a minimum number of votes that a listing need to gain before a rating can be shown. Set 0 to disable this function.
  
 ### Review
 
  #### Show review
  Set Show review to `Yes` so all the listing's reviews will be shown when users scroll down the listings details page. 
  
  #### Allow rating during review
  If you set this parameter to `Yes`, a select list will be provided to your users in "Submit review" page for them to submit rating along with their review for a listing.
  
  #### Require rating during review
  Enable Require rating during review will make the rating field a mandatory field in "Submit review" page. In this case, users have to enter a rating before they can submit their review.
  
  #### Adding new review requires approval
  Mosets Tree lets you examine the appropriateness of a new review before it is published in front-end interface. Users will be notify that their review is sent for approval whenever they submit a new review. If require approval is disable, new reviews will be posted directly to the listing without filtering.
  
  #### Prevent user from reviewing own listing
  Set this parameter to `Yes` so the listing's owners won't be able to submit reviews for their own listings.
  
  #### Primary ordering
  Ordering lets you decide what kind of review you want to be displayed first in listings details page. For instance, you can show the reviews according to their total number of [helpful votes]({{version}}/configuration#helpful-votes). 
  
  #### Allow owner to reply reviews
  By setting this to `Yes`, listing's owners are allowed to reply the reviews which have been submitted to their listings.
  
  #### Replying to review requires approval
  Similar to others Require Approval function, setting this to `Yes` so you can examine the owner's reply towards a review before it is published in front-end interface.
  
  #### User can only review once
  If you choose `Yes` for this parameter, you can limit users to submit only one review per listing. 
  
  #### Allow registered user to vote on helpful reviews {#helpful-votes}
  You can display helpful votes section on each review for only registered users and thus they can provide feedback to reviews by clicking on `Yes` or `No` link to indicate a review's helpfulness.
   
 ### E-main section
 If you have a large directory, it is always helpful for you to set an optional e-mail to be sent to reviewer after an approval or rejection of a review.
 
  #### Pre-defined replies
  You are able to enter up to 5 pre-defined e-mail replies. Every pre-defined reply you entered will become the option of the selection list in Mosets Tree back-end review's pending approval interface. If you checked the "Send e-mail to reviewer upon approval/rejection" checkbox, this selection list will be appeared and allowed you to choose a pre-defined e-mail reply to be sent along with the approval or rejection of a review. 
  
## Features
Features allows you to configure some functions in the listing page of your directory.

 ### Show map
 Mosets Tree comes with support for Google Maps in listings details page which showed a marker on the listing's address. While in add listing page, this marker is placed on a default location in Africa.
 
 ### Default Country
 You can set a default country into this parameter. If users click on the "Map" link in a listing, listing's address will be searched within this country together with the insufficient address information provided by listing's owner.
 
 ### Default State
 With a default country set, enter a "Default State" helps to refine the searching of a listing's address. 
 
 ### Default City
 Similar to the parameters above, enter a "Default City " will help even more in searching of an address on Google Maps. 
 
 ### Show link to map
 Enable this feature to provide users a link to view the listing's address in Google Maps.
 
 ### Show Favourite
 This shows "Add as Favourite" link on listings details page for readers to favourite a listing. 
 
 ### Show print
 Show print allows users to print a listing along with the listing details.
 
 ### Show visit
 In listings details page, users can visit to the listing's website (if provided by listing's owner) by clicking this Visit link.
 
 ### Show claim
 "Claim" link allows users to claim other user's listing as their own. When users claiming a listings, an approval notification will be sent to Administrator in order to verify that the right user has claimed the right listing.
 
 ### Show owner's listing
 Enable "Owner's listing" link will provide a link for other readers to view all the owner's listings.
 
 ### Default owner's listing
 Each users on your site will have a user profile that show all their listings, reviews and favoured listings. Default owner's listing let you choose which tab (either "Listings", "Favourites" or "Reviews") to be shown first when one enter a user profile.
  
 ### Show contact
 "Contact" link allows users to contact the listing's owner by sending an e-mail to them.
 
 ### Display contact form in
 Contact form will be shown in a dedicated page if you select to display contact form in `Standalone Page`. Otherwise you can select to display contact form in `Listing Details Page` so your users can see the contact form by scrolling down the page.
 
 ### Contact BCC E-mail
 All e-mails that are sent through the contact form will be BCC-ed to the email address(es) provided in this field. If you have more than one BCC e-mail address, separate them by commas.
 
 ### Show report
 "Report" link allows users or public to send a report message to Administrator for a listing that may be offensive or giving inaccurate information or contain any other appropriate reasons for reporting. 
 
 ### Show recommend
 If your users found a great listing, this "Recommend" link will let them to recommend that listing to their friends through e-mail. 
 
 ### Use user's e-mail address if listing e-mail is empty
 Any messages related to the listing will be sent to the listing's owner through the e-mail address provided during submission of the listing. Otherwise, messages will be sent to the e-mail address of the user's account.

## Notify
Notify allows you to configure when to send a notification e-mail to Admin and Listing's owner.
 
 ### Admin
 For Admin, you can configure if notification e-mails will be sent when the following event occurs:  
 - New listing
 - Modify listing
 - Delete listing  
 - New review  
 
 ### Owner 
 While for Listing's owner, you can configure if notification e-mails will be sent when the following event occurs:
 - New listing
 - Modify listing
 - Listing approved
 - Review approved
 - Review added to own listing

## Image
When an image is uploaded, system will save the image in three formats: the original image, thumbnail sized image and medium sized image.

 ### Small/Thumbnail's image size
 This allows you to set the maximum width and height of a thumbnail image.
 
 ### Squared thumbnail
 Setting this to `Yes` will generate thumbnails with a square dimension. This will produce a consistent set of thumbnails with same dimension in the directory. However for some images, the sides of the thumbnail could be cropped out in order to fit in to a square.
 
 ### Medium's image size
 This is the maximum width and height of a medium sized image.
 
 ### Minimum image width in pixels
 You can set the minimum image width in pixels required for users to upload a medium sized image. 
 
 ### Minimum image height in pixels
 This parameter controls the minimum image height required for users to upload a medium sized image.
 
 ### Category's image size
 This is the maximum width and height of a category image.
 
 ### Allow owner to upload image
 Setting `Yes` to this so listing's owner will be able to upload images when adding or editing a listing. 
 
 ### Images per listing
 Images per listing lets you set the maximum number of images can be uploaded to a listing.

## Sharing
In sharing, you can control whether to insert social bookmarking buttons in listings details view so that users can share your directory pages in most important social networks such as  Facebook, Twitter, Pinterest, Google+ and LinkedIn.

 ### Facebook Like
 By setting this to `Yes`, Facebook Like will show the like button on every listings details page.
 
 ### Pinterest On Hover Pin
 On Hover Pin will show Pinterest's `Pin it` button on your listing's main image when a user mouses over it.
 
 ### Twitter Card
 With [Twitter Cards](https://dev.twitter.com/cards/overview), you can attach rich photos, videos and media experience to Tweets to your website.
 
  #### Use Twitter Card
  When a listing contains at least one image, Twitter Card will attach the image when your users share or tweet the listings.
  
  #### Site Twitter
  Enter site's Twitter username without the `@` sign. This will be used in content attribution when users share listings to Twitter.
  
  #### Twitter Card Type
  Select one of these values: `summary`, `summary_large_image` or `photo`. To check out more about Twitter Card Types, click [here](https://dev.twitter.com/cards/types).

## SEF URLs
Enable Search engine friendly (SEF) URLs to provide a easier way to access to your directory pages by using a succinct URL in search engine. Turn on Joomla Search Engine Friendly URLs in Joomla's Configuration (Go to "**System -> Global Configuration**",  under SEO Settings) and Mosets Tree will generate SEF URLs for your directory. 

 ### Listing's slug type
 You can control how to represent listing in SEF URL.  
 For **Alias**, SEF URLs generated usually using listing's name yet it can be customized in  Mosets Tree back-end interface.   
 Using **Link ID** will use listing's link ID to represent your listing's URL.  
 **Link ID & Alias Hybrid** combines a listing's alias and link ID to give a more unique URL for the listing.

## Captcha
You can decide which feature you want to use a [Captcha]({{version}}/fields#fieldtype-captcha) to verify your site's visitors are real human and not a robot.

## Admin
This section lets you control the Administrator back-end interface.

 ### Use Explorer
 By setting this to `Yes`, you can see the explorer that contain your site's directory in tree-like form on the left hand side of the interface. 
 
 ### Explorer's Tree Level
 This parameter is helpful to limit the explorer level to provide you a neat view when viewing your directory in back-end interface. It is recommended to allow only main level to be displayed on screen while you can expand the main level to view its subordinate level.
 
 ### Use Internal Notes
 Internal Notes provides you a text box to record your comments on the actions you had performed such as approving or rejecting a review.
 
 ### Use WYSIWYG Editor description field in back-end
 By setting this to `Yes`, you can to use [WYSIWYG]({{version}}/fields#fieldtype-texteditor) editor description field in back-end interface.

