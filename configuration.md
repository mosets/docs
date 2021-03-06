# Configuration

- [Introduction]({{version}}/configuration#intro)
- [Main]({{version}}/configuration#main)
- [Permission]({{version}}/configuration#permission)
- [Category]({{version}}/configuration#category)
- [Listing]({{version}}/configuration#listing)
- [Search]({{version}}/configuration#search)
- [Rating/Rev]({{version}}/configuration#ratingrev)
- [Map]({{version}}/configuration#map)
- [Features]({{version}}/configuration#features)
- [Notify]({{version}}/configuration#notify)
- [Image]({{version}}/configuration#image)
- [Sharing]({{version}}/configuration#sharing)
- [RSS]({{version}}/configuration#rss)
- [SEF URLs]({{version}}/configuration#sefurls)
- [Captcha]({{version}}/configuration#captcha)
- [Admin]({{version}}/configuration#admin)
- [Frequently Asked Questions]({{version}}/configuration#faqs)

## Introduction {#intro}
Configurations in Mosets Tree controls most aspects of how Mosets Tree works. It can be accessed in Mosets Tree's back-end: "**Mosets Tree -> Configuration**". Most of the configurations are self explanatory (at least we try to be!), so we will cover some of the important ones here.

As part of Mosets Tree's [multi-directory]({{version}}/multi-directory) system, many of the configurations here can be overridden in top level categories, giving you the possibility of creating top level categories with completely different configurations.

>  If you're looking to customize Mosets Tree, you may also find more configurable parameters by editing Mosets Tree's template:

> **Mosets Tree -> Templates -> [your default template]**

## Main {#main}

 ### View access level
 View access level allows you to decide who can view your directory or top level category.

 ### Admin e-mail
 This is where all the notification e-mails are sent to. You can enter more than one e-mail by separating them with commas.

 ### Adding new listing requires approval
 Set `Yes` if you want all newly submitted listings from front-end to go through approval before it is published. Listings that are pending for approval can be reviewed in Mosets Tree's back-end:

  "**Mosets Tree -> Pending Approval -> Listings**"

 ### Number of days to show as new listing
 A "New" badge will be shown beside listing's name if it is a recently added listing. This config lets you to configure the number of days you want a listing to be displayed as new listing.

 ### Number of average unique pageviews per day to show as popular listing
 A "Popular" badge is shown when a listing has an average hits equal of above the number configured here.
 
 Demo: http://demo.mosetstree.com/real-estate-companies/958-capridien-properties.html

 ### Unique pageviews session (in seconds) {#hit_lag}
 Mosets Tree uses cookies to track if a user has visited a listing details page before, so that multiple visits to the same listings will be counted as only 1 pageview during a session.

 By default, this cookie expires after 86400 seconds (24 hours). The time between the user's first visit and the cookie expiration is called a session. If the user visit the same listing after the cookie expires, the visit will be counted as another pageview.

 You can disable this by setting 0. Disabling this will increment the pageview everytime a listing page is viewed.

 ### Use WYSIWYG Editor in front-end Description field
 By selecting `Yes` in this parameter will allow you to use HTML tags in description field. Please note that HTML tags will be stripped in summary view and only shown in details view. 

 ### Allow JSON Output {#allow_json_output}
 JSON is a data format that produce human-readable text and data that are easily parsable by other app. If JSON output is enabled, you can access some of the pages in Mosets Tree in JSON format by appending <strong>&format=json</strong> query string to its URL.<p />e.g.: < yoursite >/index.php?option=com_mtree&format=json
 
## Permission

 ### Edit Permission
 Permission allows you to control which user group will gain access to certain functions in Mosets Tree.

 ### Managers 
  By default, only listing owners can edit and delete their listings in front-end. Managers are users who can edit or delete listings in front-end, even when they do not own the listings. This allows you to assign user groups to manage your directory. Check the checkboxes for "Edit listings" and "Delete listings" to choose which user group can manage listings in front-end.

## Category {#category}

 ### Primary ordering
 Primary ordering allows you to set the order of how categories will be appeared in Mosets Tree. If you set the ordering to `Custom`, you can custom order your categories by clicking the up/down arrow icons in the ordering column of directory page.

 ### Secondary ordering 
 This parameter decides the second ordering option to follow if two or more categories have the same order in primary ordering.

 ### Type of listings to show in Index
 By default, listings displayed in Index page are those had assigned to the current category. You can this by showing other types of listings in Index, for example, displaying the Top Rated listings or Popular listings.
 
 Demo: http://demo.mosetstree.com/
 
 : Scrolling down the Index page, you can see all listings shown are **Top Rated** listings. 
 
 ### Number of listings in index
 Set the number of top listings to be shown in index view. If you set the type of listing to show in index to "Default", the number of listings shown will be based on "Number of listings per page" setting you have configured in [Listing]({{version}}/configuration#listings) tab.

 ### Display categories
 If this config is set to `No`, categories will only be displayed to users in "All Categories" page and no where else. 
 
 ### Display empty category
 Empty category means category that contains no sub-categories or listings. By setting `Yes` to this parameter, all the empty categories will be hidden.

 ### Display 'All Listings' link
 This parameter enables 'All Listings' link to be displayed at the top of listing list. "All Listings" displays all the listings that belong to the category, including sub-categories' listing.

 ### Display Filters {#filters}
 Filters lets you to perform a filter on a list of listings. This is available when you view a category through "_All Listings_". Setting this to `No` will remove the filter function.

## Listing {#listing}
Data entered to a field is displayed in two places in Mosets Tree front-end, Summary view and Details view.

 ### Listing details view access level
 Choose who are authorized to access listings in details view. Unauthorized parties can only view listings in summary view.

 ### Default sorting in All Listings
 This config lets you choose the default sorting when your users to view "All Listings" page.
 
 Demo: http://demo.mosetstree.com/games/all.html
 
 : Once users enter this page, they will see the most recent listings first because sorting is set to "**Recently Added**". Mosets Tree provides several options to let you decide how you want your listings to be displayed to users. 
 
 ### Default secondary sorting in All Listings
 This config lets you choose the secondary sorting in "All Listings" page. The default is set to "None".
  
 ### All Listings page sort options
 Sort options allows you to select which "Sort by" options are available in "All Listings" page.

 ### Show user profile in Listing Details page
 Setting this to `Yes` will show the owner's profile in listing details page.
 
 Demo: http://demo.mosetstree.com/properties/factories/929-assiniaboine.html
 
 : In this listing page, you can see user profile is displayed under listing details. Clicking the user name will direct you to view details of the user profile including user's listings, reviews and favoured listings.
 
 ### Show Previous/Next listing link
 Show 2 links in listing details view to allow your users to navigate to adjacent (previous or next) listing within a category. 
 
 This only works well when you order your listings on a column where all your listings have unique values. For example, this works best when you order your listings by 'Name'. 
 
 This does not work well when your category are ordered by column where some listings have no value or share the same value. For example, you can not use this feature when you order your listings by Featured or Random.

 ### Additional characters for Alpha Index
 By default, Mosets Tree displays Alpha Index in alphabetic and numeric characters for your users to select. This config allows you to add additional characters to the end of the alpha list as part of the selection.

 ### Allow listings submission in root
 If you allow listings submission in root, your users will be able to submit listings through Index page.

 ### Show 'Add Listing' link
  Configure when to show the 'Add your listing here' link in front-end.
  
  `Never`: The link will never be shown. Select this if you don't intend to allow users to register and submit listings.
  
  `All the time`: The link will be shown all the time, unless a category has explicitly set not to allow listing submission. Select this if you want to encourage your users to submit listings to your directory.
  
  `Only when user has permission`: The link will only be shown when a user has permission to do so and the category allows listing submission.

 ### Allow changing of category in Add Listing
 Set this parameter to `Yes` to allow changing of category when users add listings. Otherwise, listing added will be assigned to the category from where your users click the "Add your listing here" link.
 
 Demo: http://demo.mosetstree.com/business/add.html

 ### Allow user to assign more than one category to listing
 Sometimes, your users may have a listing which is related to multiple categories. You can set this to `Yes` to let you user assign more than one category. Your users can assign more than one category to a listing when clicking "Also appear in this category" link.

 Be sure to also set `Yes` to "_Allow user to assign more than one category to listing_" in order to use this.
 
 Demo: http://demo.mosetstree.com/877-mosets.html
 
 : "**Also appear in these categories**" is displayed in listing details to show all the categories which a listing is assigned to.

 ### Max. number of assignable secondary categories
 This config lets you limit the maximum number of categories which a listing can be assigned to.

 ### Max. number of listings per user
 Set the maximum number of listings a user can have in the directory. This includes all published, unpublished and unapproved listings. When your users reached a limit, they will not be able to submit additional listing. Setting this to `0`, will disable the limit.
 
 ### Display listings in root
 Set whether to display listings in Index page. Setting this to `No` will not show any listings in Index page.

 Take note that if you set any of your category to use index template page ("_Use Main Index template page_" is set to `Yes`), it will follow this config to decide whether to show listings in the index page.

 ### Required fields to mark listing as updated
 By default, any updates to a listing causes the listing to be marked as updated with a new modified date. This option allows you to enter the ID of one or more fields (separated by comma) that must be changed before a listing is marked as updated. You can get the field's ID from the ID column in Mosets Tree back-end "_Custom Fields_" interface.

 ### Number of listings per page
 This config lets you set the maximum number of listings to be displayed in one page.
 
 Demo: http://demo.mosetstree.com/health.html
 
 : In this page, we have set "**Number of listings per page**" to 20 and thus you can see at most 20 listings is shown for each page. Click on the page navigation link to view other listings in subsequent pages. 
 
 ### Number of new listings per page
 This parameter control the number of new listings per page that will be displayed in "Recently Added" page.
 
 Demo: http://demo.mosetstree.com/new.html
 
 ### Total new listings
 You can set the total number of recently added listings to be displayed in "Recently Added" page.

 ### Number of days to expire listing {#days_to_expire}
 Specify the number of days for a listing to remain published upon submission. Once this number of days has passed, the listing will be published down and not visible in front-end. Enter 0 to disable this feature. This config is useful for setting up a classified-like directories.

 ### Allow Listing Renewal {#allow_listing_renewal}
 You can set a listing to expire by setting their 'Publish Down' date. Once a listing has expired, they will not be visible in front-end. If you allow 'Listing Renewal', listing owners can edit their listings that are nearing their expiration date and click 'Submit' to renew their listings.
 
 The renewed listings will have their expiry date extended by the same number of days set in 'Number of days to expire listing'.

 ### Days Remaining To Renew
 Set the number of days prior to a listing expiry before a listing can be renewed.
 
## Search {#search}
Mosets Tree has three types of searching functions to help your user find the listings in your directory: _Simple Search_, _Advanced Search_ and _Filters Search_. [Filter Search]({{version}}/configuration#filters) is displayed in "All Listing" page which has been explained earlier.

 ### Simple Search

 Simple Search is provided by Mosets Tree's [Search module]({{version}}/modules#mod-mt-search) and consist of a single text input field. When users search through this module, the search keyword will be matched against fields that are marked as Simple Searchable.

  #### Primary ordering
  Primary ordering controls the ordering of the tags search and simple search results through the search module.

  #### Secondary ordering
  Secondary ordering works if two or more search results have the same order in primary ordering. 

  #### Minimum & Maximum characters
  Specify the required minimum and the maximum number of characters allowed when your user search through simple search. When you user enter less than the required minimum or more than the allowed maximum number of characters, they will be shown a message and retry their search.

 ### Advanced Search
 Advanced search appears in its own dedicated page. This page is accessible through a link in Search module. Advanced search allow users to locate listings with specific criteria.

  #### Default sorting in results page
  This config allows you to choose how listings in advanced search results are ordered.

 ### Filter Search

  #### Show keyword search
  Enabling keyword search will show a text input filter in category page's filter form. This allows your users to enter a keyword and search against all  simple searchable fields. This is in addition to other custom fields you've made as filter searchable.
 
## Rating/Rev {#ratingrev}

 ### Rating
 
  #### Show rating
  Setting this to `Yes` enables users to rate listings.
  
 Demo: http://demo.mosetstree.com/games/889-super-smash-bros-brawl.html

 : In this page, you can see rating is placed under listing's description to allow users to rate listing. 

 Demo: http://demo.mosetstree.com/properties/houses/931-blue-house.html

 : "**Show Rating**" in _Properties_ category has been set to `No`, thus rating section is not displayed in front-end. 
  
  #### User can only rate once
  By default, users are only allowed to rate once for every listing. If you set this to `No`, your users will be able to rate your listings multiple times.

  #### Prevent user from rating own listing
  You can also prevent the listing's owners to rate their own listings by setting this to `Yes`.
  
  Demo: http://demo.mosetstree.com/properties/lands/942-land-of-tulips.html
  
  : By signing in to Mosets Tree's demo page as **Demo User**, you can see from the user profile, this listing is belongs to the logged in user, thus rating on own listing is not allowed if "_Prevent user from rating own listing_" is set to `Yes`.
   
  #### Minimum number of votes to be considered for top rated listings
  To be fair in the calculation for showing top rated listings, you can set a requirement for the minimum number of votes for a listing get before it can be considered for inclusion in the top rated listing list.

  This avoids the common problem where a new listing who has just receive a single 5-stars rating are shown above other listings in top rated list, who has been in the directory longer.

  #### Minimum number of votes to show rating
  Sets the minimum number of votes a listing must gets before their rating are shown in front-end. This helps maintain fairness in the directory to other listings who has been in the directory longer.

 ### Review
 
  #### Show review
  Setting this to `Yes` will show all listing's reviews in listings details page.
  
  Demo: http://demo.mosetstree.com/business/875-domino-s-pizza.html
    
  : Scrolling down the page, you will see several reviews from users regarding this listing.
  
  #### Allow rating during review
  If you set this parameter to `Yes`, a select list will be provided to your users in "Submit review" page for them to submit rating along with their review for a listing.
  
  Demo: http://demo.mosetstree.com/business/875-domino-s-pizza/review.html
  
  #### Require rating during review
  Enable Require rating during review will make the rating field a mandatory field in "Submit review" page. In this case, users have to enter a rating before they can submit their review.
  
  #### Adding new review requires approval
  Mosets Tree lets you examine the appropriateness of a new review before it is published in front-end interface. Users will be notify that their review is sent for approval whenever they submit a new review. If require approval is disable, new reviews will be posted directly to the listing without requiring approval.
  
  #### Prevent user from reviewing own listing
  Set this parameter to `Yes` so the listing's owners won't be able to submit reviews for their own listings.
  
  Demo: http://demo.mosetstree.com/movies/979-frozen/review.html
      
  : By signing in to Mosets Tree's demo page as **Demo User**, go to _My Page_ and simply choose a listing which belongs to the logged in user, for example "Frozen" from _Movie_ category. Try to submit review for this listing so you will be directed to the page to notify you reviewing on own listing is not allowed .
  
  #### Primary ordering
  Ordering lets you decide which review you want to be displayed first in listings details page. For instance, you can show the reviews according to their total number of [helpful votes]({{version}}/configuration#helpful-votes) or by review date.
  
  #### Allow owner to reply reviews
  By setting this to `Yes`, listing's owners are allowed to reply the reviews which is shown in their listings.
  
  #### Replying to review requires approval
  Similar to others Require Approval function, setting this to `Yes` so you can moderate the owner's reply towards a review before it is published in front-end.
  
  #### User can only review once
  If you choose `Yes` for this config, you can limit users to submit only one review per listing.
  
  #### Allow registered user to vote on helpful reviews {#helpful-votes}
  You can display helpful votes section on each review for registered users. This allows them to provide feedback to reviews by clicking on `Yes` or `No` link to indicate a review's helpfulness.
   
 ### Pre-defined e-mails to reviewer
 Mosets Tree allows you to create up to 5 pre-defined e-mails that you can choose to  be sent to reviewer after an approval or rejection of a review. This helps you to respond to any common rejection reason for reviews or just say thanks upon an approval of a review.
 
  #### Pre-defined replies
  You are able to enter up to 5 pre-defined e-mail replies. Every pre-defined reply you entered will become the option of the selection list in Mosets Tree back-end review's pending approval interface. If you checked the "Send e-mail to reviewer upon approval/rejection" checkbox, this selection list will be appeared and allowed you to choose a pre-defined e-mail reply to be sent along with the approval or rejection of a review.
  
## Map {#map}

 ### Show map in listing details page
 Mosets Tree comes with support for Google Maps in listings details page which shows a marker on the listing's address. Setting this to `No` will disable this feature. This config also decides if Map is available for you or your user to place a marker when editing a listing. 
 
 ### Default Country, State & City
 If your users does not enter a country, state or city to a listing when they click to "Locate listing in map", the default value set in this config will be used for the geocoding process.

 This is useful when your directory is catered only to a specific location.

 ### Show link to map
 Enable this feature to provide users a link to view the listing's location in Google Maps.
 

 ### Show map in category, index, search results, top listings and list all pages
 These are the individual settings for Cluster Maps. Cluster Map shows a map with multiple markers from your listings. This appear near the top of the pages before listing summaries are shown with a toggle to Show or Hide map. 

 ### Google Maps API Key
 Enter your Google Maps API Key.

 ### Google Maps Types
 Select the type of maps you want to make available to your user in your Cluster Maps.


 ### Default Google Maps Type
 Choose the map type to load by default. 

 ### Google Maps' 'Styled Map' JS style array
 Enter the javascript style array codes to define a custom style to your map. You can find some popular styles at https://snazzymaps.com/.

## Features {#features}
Features allows you to configure most of the functions in the listing page of your directory.
 
 ### Show Favourite
 This shows "Add as Favourite" link on listings details page for readers to favourite a listing. 
 
 ### Show print
 Shows a "_Print_" button that allows users to print a listing along with the listing details.
 
 ### Show visit
 Shows a "_Visit_" button where users can visit a listing's website (if provided by listing's owner).
 
 ### Show claim {#show_claim}
 Shows a "_Claim_" button to allow users to claim listings as their own. When users claiming a listings, a pending approval notification will be sent to Administrator. Administrator can view this claim in Mosets Tree's back-end to approve or reject the claim.
 
 ### Show owner's listings
 Shows a "_Owner's listings_" link will provide a link for other readers to view all the owner's listings.
 
 ### Default owner's listings
 Each users on your site will have a user profile page that show all their listings, reviews and favoured listings. This config lets you choose which tab (either `Listings`, `Favourites` or `Reviews`) is to be shown first when one enters a user profile.
  
 ### Show contact
 "Contact" link allows users to contact the listing's owner by sending an e-mail to them through a contact form. 
 
 E-mails that are sent through this contact form are sent to the e-mail address entered in the listing's `E-mail` field. If this field is empty and `Use user's e-mail address if listing e-mail is empty` config is set to `Yes`, the e-mail will be sent to the owner of the listing.
 
 ### Display contact form in
 Contact form will be shown in a dedicated page if you select to display contact form in `Standalone Page`. Otherwise you can select to display contact form in `Listing Details Page` so your users can see the contact form by scrolling down the page.
 
 ### Contact BCC E-mail
 All e-mails that are sent through the contact form will be BCC-ed to the email address(es) provided in this field. If you have more than one BCC e-mail address, separate them by commas.
 
 ### Show report
 "Report" link allows users or public to send a report message to Administrator for a listing that may be offensive, has inaccurate information or contain any other appropriate reasons, for reporting.
 
 ### Show recommend
 If your users find a great listing, this "Recommend" link will let them to recommend that listing to their friends through e-mail.
 
 ### Use user's e-mail address if listing e-mail is empty
 Any messages related to the listing will be sent to the listing's owner through the e-mail address provided during submission of the listing. Otherwise, messages will be sent to the e-mail address of the user's account.

## Notify {#notify}
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

## Image {#image}
When an image is uploaded, system will save the image in three formats: the original image, thumbnail sized image and medium sized image.

> **Note**: Changing the value for image sizes or squared thumbnail feature will not change the images you already uploaded to your listings. To apply the new configuration to your existing image, you need to rebuild your images using the **Rebuild Thumbnails** tool. This tool will rebuild your listings' small & medium images by resizing them based on the configuration you have.

> You can access the tool at:

> **Mosets Tree -> Tools -> Rebuild Thumbnails**

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
 Setting this to `Yes` allows listing's owner to upload images when adding or editing a listing.
 
 ### Images per listing
 Images per listing lets you set the maximum number of images can be uploaded to a listing.

## Sharing {#sharing}
In sharing, you can control whether to insert social bookmarking buttons in listings details view so that users can share your directory pages in popular social networks such as Facebook, Twitter, Pinterest, Google+ and LinkedIn.

 ### Facebook Like
 By setting this to `Yes`, Facebook Like will show the like button on every listings details page.
 
 ### Pinterest On Hover Pin
 On Hover Pin will show Pinterest's `Pin it` button on your listing's main image when a user mouses over it.
 
 ### Twitter Card
 Mosets Tree supports [Twitter Cards](https://dev.twitter.com/cards/overview) that helps your user to tweet with richer media experience.
 
  #### Use Twitter Card
  When a listing contains at least one image, Twitter Card will attach the image when your users share or tweet the listings.
  
  #### Site Twitter
  Enter site's Twitter username without the `@` sign. This will be used in content attribution when users share listings to Twitter.
  
  #### Twitter Card Type
  Select one of these values: `summary`, `summary_large_image` or `photo`. To check out more about Twitter Card Types, click [here](https://dev.twitter.com/cards/types).

  If you're using `summary_large_image` or `photo` card type, be sure to allow Twitter crawler to access your photos. Mosets Tree's listings' photos are located at /media/com_mtree directory and Joomla's robots.txt file by default prevents any crawler to access `/media` directory. 
  
  To lift this restriction, edit your site's robots.txt file and remove the following Disallow line:
   
	Disallow: /media/
  
  For more information, refer to [Twitter's Getting Started Guide for Cards](https://dev.twitter.com/cards/getting-started#crawling).
  
## RSS{#rss}

Mosets Tree generates an RSS Feed for all categories' recently added and recently updated page. This is often useful when you want to let users know of changes in your directory without needing them to check your website constantly through use of RSS feed readers or news aggregator.

 Demo: http://demo.mosetstree.com/new.html

 : The RSS's feed icon can be seen next to the "_Recently Added Listings_" title. You can also see this in [Recently Updated](http://demo.mosetstree.com/updated.html) page.

Mosets Tree RSS contains your listing names, descriptions, URLs and images. Options in Configuration's RSS tab allows you to add additional elements to your RSS feeds. The additional element will look like this:

	<mtree:cust_1>value</mtree>

 where "*cust_1*" will be replaced by the custom field name and "_value_" is the value of the field for a listing. The caption and and the field's value will also be shown as part of the feed item's description.

## SEF URLs {#sefurls}
Enable Search engine friendly (SEF) URLs to provide an easier way to access to your directory pages by using a succinct URLs in your directory. It also helps with Search Engine Optimization (SEO) by having relevant names and keywords in your URLs.

To enable Mosets Tree' SEF URLs, turn on Joomla Search Engine Friendly URLs in Joomla's Configuration (Go to "**System -> Global Configuration**",  under SEO Settings) and Mosets Tree will generate SEF URLs for your directory.

 ### Listing's slug type
 You can control how to represent listing in SEF URL.

 #### Alias
 When a listing or category is added to Mosets Tree, an alias is created based on their names. This is typically done by lowercasing the name and replace all spacing with dash. Choosing "_Alias_" slug type will use this for your listing slug. eg:

 	http://www.example.com/directory/business/acme-inc

 #### Link ID
 Instead of using an alias, "_Link ID_" will use the listing ID as the listing slug. eg:

  	 	http://www.example.com/directory/business/119

 #### Link ID & Alias Hybrid
 "_Link ID & Alias Hybrid_" slug type uses both alias and listing ID for your listing's slug. This gives the best of both world. Using link ID guarantees that each of your listing have unique URL and using alias gives each listing a human friendly URL.

## Captcha {#captcha}
You can decide which feature you want to use a [Captcha]({{version}}/fields#fieldtype-captcha) to verify your site's visitors are real human and not a robot.

## Admin {#admin}
This section lets you control some aspect of Mosets Tree's back-end interface.

 ### Use Explorer
 By setting this to `Yes`, you can see the explorer that contain your site's directory in tree-like form on the left hand side of the interface.
 
 ### Explorer's Tree Level
 By default, Mosets Tree limits the depth of your Explorer's Tree to prevent it from loading too many categories at once. You can change the value here to increase or decrease the level of categories you want to show in your Explorer.

 ### Use Internal Notes
 Mosets Tree allows you to write down notes for each listings and most items that are pending approval. This is useful when you are collaborating with multiple editors that manage your directory. You can turn this feature off by setting it to `No`.
 
 ### Use WYSIWYG Editor description field in back-end
 Set this to `Yes` if you want to use WYSIWYG Editor in your core description field.

## Frequently Asked Questions {#faqs}

{question}How can I manage reviews of my directory?{/question}
{answer}
You can manage all the reviews from your directory through Mosets Tree's back-end. Under the _Listings_ section, you will see a "_Reviews_" column which shows the total number of reviews for each listing in hyperlink. Click on the link to manage reviews for a particular listing.
Demo: http://demo.mosetstree.com/administrator/index.php?option=com_mtree&task=reviews_list&link_id=878
{/answer}

{question}Why "Report" link is still displayed in Reviews when I had set "Show Report" to `No` under the _Feature_ tab in configuration?{/question}
{answer}
**Show Report** under the _Feature_ tab is used for reporting a listing, not a review. To disable "_Report_" link in reviews, you can configure it under _Permission_. Go to:

 **Mosets Tree -> Configurations -> Edit Permissions... (under "Main" tab)**

 set the permission for **Report Review** to "_Denied_".
{/answer}

