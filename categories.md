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
 Set `Yes` to require admin/manager approval of all newly submitted listings from the site front-end before they are published. Listings that are pending approval can be reviewed in the Mosets Tree's back-end:

  "**Mosets Tree -> Pending Approval -> Listings**"

 ### Number of days to show as new listing
 A "New" badge/icon will be shown next to a listing's title/name if it is a recently added listing. This configuration allows you to set the number of days that a listing will be displayed with the new listing badge/icon.

 ### Number of average unique pageviews per day to show as popular listing
 A "Popular" badge/icon is shown next to a listing's title/name when the listing has an average hits equal to, or greater than the number configured here.
 
 Demo: http://demo.mosetstree.com/real-estate-companies/958-capridien-properties.html

 ### Unique pageviews session (in seconds) {#hit_lag}
 Mosets Tree uses cookies to track if a user has visited a listing details page before. This way multiple visits to the same listings will be counted as only 1 pageview during a session.

 By default, this cookie expires after 86400 seconds (24 hours). The time between the user's first visit and the cookie expiration is called a session. If the user visits the same listing after the cookie expires, the visit will be counted as another pageview.

 You can disable this by setting it to 0 (zero). Disabling this will increase the pageview count everytime a listing page is viewed.

 ### Use WYSIWYG Editor in front-end Description field
 By selecting `Yes` in this field will allow you to use HTML tags in the description core field. Please note that HTML tags will be stripped in the summary view and are only shown in the details view for the listing. NOTE: When you edit the description core field, there are additional parameter settings required to enable HTML tags in the description field.

 ### Allow JSON Output {#allow_json_output}
 JSON is a data format that produces human-readable text and data that are easily parsable by other apps. If JSON output is enabled, you can access some of the pages in Mosets Tree in JSON format by appending the <strong>&format=json</strong> query string to its URL.<p />e.g.: < yoursite >/index.php?option=com_mtree&format=json
 
## Permission

 ### Edit Permission
 Permissions allow you to control which user groups will gain access to certain functions in Mosets Tree.

 ### Managers 
  By default, only listing owners can edit and delete their listings in the site front-end. Managers are users who can edit or delete listings in the front-end, even when they do not own the listings. This allows you to assign user groups to manage your directory. Select the checkboxes for "Edit listings" and "Delete listings" to choose which user groups can manage listings in the site front-end.

## Category {#category}

 ### Primary ordering
 Primary ordering allows you to set the order of how categories will be displayed in Mosets Tree. If you set the ordering to `Custom`, you can custom order your categories by clicking the up/down arrow icons in the ordering column of the directory page.

 ### Secondary ordering 
 This parameter decides the second ordering option to follow if two or more categories have the same order in primary ordering.

 ### Type of listings to show in Index
 By default, listings displayed in the Index page are those assigned to the current category. You can change this by showing other types of listings in the Index, for example, displaying the Top Rated listings or Popular listings.
 
 Demo: http://demo.mosetstree.com/
 
 : Scrolling down the Index page, you can see all listings shown are **Top Rated** listings. 
 
 ### Number of listings in index
 Set the number of top listings to be shown in index view. If you set the type of listing to show in the index to "Default", then the number of listings shown will be based on the "Number of listings per page" setting you have configured in the [Listing]({{version}}/configuration#listings) tab.

 ### Display categories
 If this configuration is set to `No`, then categories will only be displayed to users on the "All Categories" page and nowhere else. 
 
 ### Display empty category
 Empty category means a category that contains no sub-categories or listings. By setting `No` for this parameter, all the empty categories will be hidden. By setting `Yes` for this parameter, all the empty categories will be visible.

 ### Display 'All Listings' link
 This parameter enables the 'All Listings' link to be displayed at the top of the listings list. "All Listings" displays all the listings that belong to the category, including sub-category listings.

 ### Display Filters {#filters}
 Filters lets you to use a filter for the listings displayed in a category. This is available when you view a category through "_All Listings_". Setting this to `No` will remove the filter function.

## Listing {#listing}
Data entered into a field is displayed in two places in the Mosets Tree front-end, Summary view and Details view.

 ### Listing details view access level
 Choose which access level groups are authorized to view listings in details view. Unauthorized users can only view listings in summary view.

 ### Default sorting in All Listings
 This configuration lets you choose the default sorting when your users view the "All Listings" page.
 
 Demo: http://demo.mosetstree.com/games/all.html
 
 : Once users enter this page, they will see the most recent listings first because sorting is set to "**Recently Added**". Mosets Tree provides several options to let you decide how you want your listings to be displayed to users. 
 
 ### Default secondary sorting in All Listings
 This configuration lets you choose the secondary sorting option for the "All Listings" page. The default is set to "None".
  
 ### All Listings page sort options
 This allows you to select which "Sort by" options are available on the "All Listings" page.

 ### Show user profile in Listing Details page
 Setting this to `Yes` will show the listing owner's profile in the listing details page.
 
 Demo: http://demo.mosetstree.com/properties/factories/929-assiniaboine.html
 
 : In this listing page, you can see user profile is displayed under the listing details. Clicking the user name will allow you to view details of the user profile, including the user's listings, reviews and favored listings.
 
 ### Show Previous/Next listing link
 This will disply 2 links at the bottom of the listing details pages to allow users to navigate to adjacent (previous or next) listings within a category.
 
 This only works well when you order your listings based upon a column where all your listings have unique values. For example, this works best when you order your listings by 'Name'. 
 
 This does not work well when your categories are ordered by a column where some listings have no value or they share the same value. For example, you can not use this feature when you order your listings by the Featured or Random options.

 ### Additional characters for Alpha Index
 By default, Mosets Tree displays an Alpha Index with alphabetic and numeric characters links. This configuration allows you to add additional characters to the end of the alpha list as part of the available links displayed to users.

 ### Allow listings submission in root
 If you allow listings submission in root of your directory, then your users will be able to submit listings through the Index page.

 ### Show 'Add Listing' link
  Configure when to show the 'Add your listing here' link in the front-end.
  
  `Never`: The link will never be shown. Select this if you don't intend to allow users to register and submit listings.
  
  `All the time`: The link will be shown all the time, unless a category has explicitly set not to allow listing submission. Select this if you want to encourage your users to submit listings to your directory.
  
  `Only when user has permission`: The link will only be shown when a user has permission to do so and the category allows listing submission.

 ### Allow changing of category in Add Listing
 Set this parameter to `Yes` to allow changing of the category when users add listings. Otherwise, listings added will be assigned to the category from where your users click the "Add your listing here" link.
 
 Demo: http://demo.mosetstree.com/business/add.html

 ### Allow user to assign more than one category to listing
 Sometimes your users may have a listing which is related to multiple categories. You can set this to `Yes` to let users assign their listings to more than one category. Your users can assign more than one category to a listing when clicking the "Also appear in this category" link.

 Be sure to also set `Yes` for "_Allow user to assign more than one category to listing_" in order to use this.
 
 Demo: http://demo.mosetstree.com/877-mosets.html
 
 : "**Also appear in these categories**" is displayed in listing details to show all the categories which a listing is assigned to.

 ### Max. number of assignable secondary categories
 This configuration lets you limit the maximum number of categories which a listing can be assigned to.

 ### Max. number of listings per user
 Set the maximum number of listings a user can have in the directory. This includes all published, unpublished and unapproved listings. When your users reached this limit, they will not be able to submit additional listings. Setting this to `0`, will disable the limit.
 
 ### Display listings in root
 Set whether to display listings on the directory Index page. Setting this to `No` display no listings on the Index page.

 Take note that if you set any of your categories to use the index template page ("_Use Main Index template page_" is set to `Yes`), then it will follow this configuration setting to decide whether to display listings on the index page.

 ### Required fields to mark listing as updated
 By default, any updates made to a listing will cause that listing to be marked as updated with a new modified date. This option allows you to enter the ID of one or more fields (separated by commas) that must be changed before a listing is marked as updated. You can get the field's ID from the ID column in the Mosets Tree back-end "_Custom Fields_" interface.

 ### Number of listings per page
 This configuration lets you set the maximum number of listings to be displayed on one page.
 
 Demo: http://demo.mosetstree.com/health.html
 
 : In this page, we have set "**Number of listings per page**" to 20, as a result, you can see 20 listings at the most are shown on each page. Click on the page navigation link to view other listings on the subsequent pages. 
 
 ### Number of new listings per page
 This parameter controls the number of new listings per page that will be displayed on the "Recently Added" page.
 
 Demo: http://demo.mosetstree.com/new.html
 
 ### Total new listings
 You can set the total number of recently added listings to be displayed on the "Recently Added" page.

 ### Number of days to expire listing {#days_to_expire}
 Specify the number of days for a listing to remain published after it is submitted. Once this number of days has passed, the listing will be changed to 'Published Down' and they will not be visible on the site front-end. Enter 0 to disable this feature. This configuration is useful for setting up a classified ads/listings type of directory.

 ### Allow Listing Renewal {#allow_listing_renewal}
 You can set a listing to expire by setting their 'Publish Down' date. Once a listing has expired, it will not be visible on the site front-end. If you allow 'Listing Renewal', then listing owners can edit their listings that are near the expiration date and click 'Submit' to renew their listings.
 
 The renewed listings will have their expiration date extended by the same number of days set in the 'Number of days to expire listing'.

 ### Days Remaining To Renew
 Set the number of days prior to a listing expiration before that listing can be renewed.
 
## Search {#search}
Mosets Tree has three types of searching functions to help your user find listings in your directory: _Simple Search_, _Advanced Search_ and _Filters Search_. [Filter Search]({{version}}/configuration#filters) is displayed on the "All Listing" page (which has been explained earlier).

 ### Simple Search

 Simple Search is provided by Mosets Tree's [Search module]({{version}}/modules#mod-mt-search) and consist of a single text input field. When users search through this module, the search keyword will be matched against fields that are marked as Simple Searchable.

  #### Primary ordering
  Primary ordering controls the ordering of the tags search and simple search results through the search module.

  #### Secondary ordering
  Secondary ordering works if two or more search results have the same order in primary ordering. 

  #### Minimum & Maximum characters
  Specify the required minimum and maximum number of characters allowed when users search using simple search. When a user enters less than the required minimum or more than the allowed maximum number of characters, they will be shown a message and can retry their search.

 ### Advanced Search
 Advanced search appears on its own dedicated page. This page is accessible through a link in the Search module. Advanced search allows users to locate listings with specific criteria.

  #### Default sorting in results page
  This configuration allows you to choose how listings are ordered in the advanced search results.

 ### Filter Search

  #### Show keyword search
  Enabling keyword search will show a text input filter in a category page's filter form. This allows your users to enter a keyword to search in all simple searchable fields. This is in addition to other custom fields you have setup as filter searchable.
 
## Rating/Rev {#ratingrev}

 ### Rating
 
  #### Show rating
  Setting this to `Yes` enables users to rate listings.
  
 Demo: http://demo.mosetstree.com/games/889-super-smash-bros-brawl.html

 : In this page, you can see the rating is placed under the listing's description field to allow users to rate the listing. 

 Demo: http://demo.mosetstree.com/properties/houses/931-blue-house.html

 : "**Show Rating**" in _Properties_ category has been set to `No`, thus the rating section is not displayed on the site front-end.
  
  #### User can only rate once
  By default, users are only allowed to rate each listing one time. If you set this to `No`, your users will be able to rate your listings multiple times.

  #### Prevent user from rating own listing
  You can prevent the listing owners from being able to rate their own listings by setting this to `Yes`.
  
  Demo: http://demo.mosetstree.com/properties/lands/942-land-of-tulips.html
  
  : By signing in to Mosets Tree's demo page as **Demo User**, you can see from the user profile, this listing belongs to the logged in user, thus rating their own listing is not allowed if "_Prevent user from rating own listing_" is set to `Yes`.
   
  #### Minimum number of votes to be considered for top rated listings
  To be fair in the calculation for showing top rated listings, you can set a requirement for the minimum number of votes a listing must get before it can be considered for inclusion on the list of top rated listings.

  This avoids common problems, such as, it prevents a new listing that only received one rating of 5-stars from being displayed in the top rated list above other listings that have been in the directory for a longer period of time.

  #### Minimum number of votes to show rating
  This sets the minimum number of votes a listing must get before their ratings are shown on the site front-end. This helps maintain fairness in the directory with other listings who have been in the directory for a longer period of time.

 ### Review
 
  #### Show review
  Setting this to `Yes` will show all the listing's reviews on the listings details page.
  
  Demo: http://demo.mosetstree.com/business/875-domino-s-pizza.html
    
  : Scrolling down the page, you will see several reviews from users for this listing.
  
  #### Allow rating during review
  If you set this parameter to `Yes`, a select list will be provided to your users on the "Submit review" page for them to submit a rating along with their review for the listing.
  
  Demo: http://demo.mosetstree.com/business/875-domino-s-pizza/review.html
  
  #### Require rating during review
  Enabling the Require Rating during review option will make the rating field entry mandatory in the "Submit review" page. In this situation, users will be required to select a rating before they can submit their review.
  
  #### Adding new review requires approval
  Mosets Tree lets you evaluate the appropriateness of a new review before it is published on the site front-end. Users will be notified that their review is awaiting approval after they submit a new review. If require approval is disabled, new reviews will be posted directly to the listing without being evaluated by the directory admin/manager.
  
  #### Prevent user from reviewing own listing
  Set this parameter to `Yes` so the listing owners will not be able to submit reviews for their own listings.
  
  Demo: http://demo.mosetstree.com/movies/979-frozen/review.html
      
  : By signing in to Mosets Tree's demo page as **Demo User**, go to _My Page_ and simply choose a listing which belongs to the logged in user, for example "Frozen" from _Movie_ category. Try to submit a review for this listing, and you will be directed to the page that notifies you that reviewing your own listing is not allowed.
  
  #### Primary ordering
  Ordering lets you decide which review you want to be displayed first on the listings details page. For instance, you can show the reviews according to their total number of [helpful votes]({{version}}/configuration#helpful-votes) or by review date.
  
  #### Allow owner to reply reviews
  By setting this to `Yes`, the listing owners are allowed to reply to reviews which are shown with their own listings.
  
  #### Replying to review requires approval
  Similar to the other Require Approval function, set this to `Yes` so you can moderate the owner's reply to a review before it is published on the site front-end.
  
  #### User can only review once
  If you choose `Yes` for this setting, users will be limited to submitting only one review per listing.
  
  #### Allow registered user to vote on helpful reviews {#helpful-votes}
  You can display the helpful votes section on each review for registered users. This allows them to provide feedback to reviews by clicking the `Yes` or `No` link to indicate if they feel a review is helpful.
   
 ### Pre-defined e-mails to reviewer
 Mosets Tree allows you to create up to 5 pre-defined e-mails that you can choose to be sent to a reviewer after an approval or rejection of a review. This helps you to respond to any common rejection reasons for reviews, or just to say thanks upon an approval of a review.
 
  #### Pre-defined replies
  You are able to enter up to 5 pre-defined e-mail replies. Every pre-defined reply you entered will become the option of the selection list in Mosets Tree back-end review's pending approval interface. If you checked the "Send e-mail to reviewer upon approval/rejection" checkbox, this selection list will be displayed and allow you to choose a pre-defined e-mail reply to be sent along with the approval or rejection of a review.
  
## Map {#map}

 ### Show map in listing details page
 Mosets Tree comes with support for Google Maps on the listings details page which shows a marker on the listing's address. Setting this to `No` will disable this feature. This setting also decides if Map is available for you or your users to add an address marker when editing a listing. 
 
 ### Default Country, State & City
 If your users do not enter a country, state or city to a listing, then when they click to "Locate listing in map", the default value set in this configuration will be used for the geocoding process.

 This is useful when your directory deals with listings mainly from one location.

 ### Show link to map
 Enable this feature to provide users a link to view the listing's location in Google Maps.
 

 ### Show map in category, index, search results, top listings and list all pages
 These are the individual settings for Cluster Maps. Cluster Map shows a map with multiple location markers from your listings. This appears near the top of the pages before the listing summaries are shown, with a toggle to Show or Hide the map. 

 ### Google Maps API Key
 Enter your Google Maps API Key.

 ### Google Maps Types
 Select the type of maps you want to make available to your users in your Cluster Maps.


 ### Default Google Maps Type
 Choose the map type to load by default. 

 ### Google Maps' 'Styled Map' JS style array
 Enter the javascript style array codes to define a custom style to your map. You can find some popular styles at https://snazzymaps.com/.

## Features {#features}
Features allows you to configure most of the functions in the listing page of your directory.
 
 ### Show Favourite
 This shows the "Add as Favourite" link on the listings details page for readers to favorite a listing.
 
 ### Show print
 Shows a "_Print_" button that allows users to print a listing along with the listing details.
 
 ### Show visit
 Shows a "_Visit_" button where users can visit a listing's website (if the URL was provided by listing's owner).
 
 ### Show claim {#show_claim}
 Shows a "_Claim_" button to allow users to claim listings as their own. When users claim a listing, a pending approval notification will be sent to the Administrator. The Administrator can view this claim in the Mosets Tree's back-end to approve or reject the claim.
 
 ### Show owner's listings
 Shows an "_Owner's listings_" link will provide a link for other readers to view all the owner's listings.
 
 ### Default owner's listings
 Each user on your site will have a user profile page that shows all their listings, reviews and favored listings. This setting lets you choose which tab (either `Listings`, `Favourites` or `Reviews`) is to be shown first when someone views a user profile.
  
 ### Show contact
 "Contact" link allows users to contact the listing's owner by sending an e-mail to them through a contact form. 
 
 E-mails that are sent through this contact form are sent to the e-mail address entered in the listing's `E-mail` field. If this field is empty and the `Use user's e-mail address if listing e-mail is empty` setting is set to `Yes`, the e-mail will be sent to the owner of the listing.
 
 ### Display contact form in
 Contact form will be shown on a separate page if you select to display the contact form on a `Standalone Page`. Otherwise you can select to display the contact form on the `Listing Details Page` and users can see the contact form by scrolling down the listing page.
 
 ### Contact BCC E-mail
 All e-mails that are sent through the contact form will be BCC-ed (Blind Carbon Copied) to the email address(es) provided in this field. If you have more than one BCC e-mail address, separate them by commas.
 
 ### Show report
 "Report" link allows users, both registered and non-registered public users, to send a report message for a listing to the Administrator. This can notify the Administrator about listing content that may be offensive, or has inaccurate information, or contains any other reasons that should be reported.
 
 ### Show recommend
 If your users find a listing they like, then this "Recommend" link will allow them to recommend that listing to their friends through the e-mail form.
 
 ### Use user's e-mail address if listing e-mail is empty
 Any messages related to a listing will be sent to the listing's owner with the e-mail address provided during submission of the listing. Otherwise, messages will be sent to the e-mail address of the user's account.

## Notify {#notify}
Notify allows you to configure when to send a notification e-mail to the Admin and a Listing's owner.
 
### Admin
 For Admin, you can configure if notification e-mails will be sent when the following events occur:  
 - New listing
 - Modify listing
 - Delete listing  
 - New review  
 
### Owner
 For the listing's owner, you can configure the notification e-mails to be sent when the following events occur:
 - New listing
 - Modify listing
 - Listing approved
 - Review approved
 - Review added to own listing

## Image {#image}
When an image is uploaded the system will save the image in three formats: the original image, a thumbnail sized image, and a medium sized image.

> **Note**: Changing the value for image sizes or squared thumbnail feature will not change the images that are already uploaded to your listings. To apply the new configuration to your existing images, you need to rebuild your images using the **Rebuild Thumbnails** tool. This tool will rebuild your listings' small & medium images by resizing them based on the configuration settings you have.

> You can access the tool at:

> **Mosets Tree -> Tools -> Rebuild Thumbnails**

 ### Small/Thumbnail's image size
 This allows you to set the maximum width and height of a thumbnail image.
 
 ### Squared thumbnail
 Setting this to `Yes` will generate thumbnails with a square dimension. This will produce a consistent set of thumbnails with the same dimensions in the directory. However for some images, the sides of the thumbnail could be cropped out in order to fit into a square.
 
 ### Medium's image size
 This is the maximum width and height of a medium sized image.
 
 ### Minimum image width in pixels
 You can set the minimum image width in pixels required for users to upload a medium sized image. 
 
 ### Minimum image height in pixels
 This parameter controls the minimum image height required for users to upload a medium sized image.
 
 ### Category's image size
 This is the maximum width and height of a category image.
 
 ### Allow owner to upload image
 Setting this to `Yes` allows the listing's owner to upload images when adding or editing a listing.
 
 ### Images per listing
 Images per listing lets you set the maximum number of images that can be uploaded to a listing.

## Sharing {#sharing}
In sharing you can control whether to insert social bookmarking buttons in the listings details view so that users can share your directory pages in popular social networks, such as, Facebook, Twitter, Pinterest, Google+ and LinkedIn.

 ### Facebook Like
 By setting this to `Yes`, Facebook Like will show the like button on every listing details page.
 
 ### Pinterest On Hover Pin
 On Hover Pin will show Pinterest's `Pin it` button on your listing's main image when a user mouses over it.
 
 ### Twitter Card
 Mosets Tree supports [Twitter Cards](https://dev.twitter.com/cards/overview) that helps your users to tweet with a better media experience.
 
  #### Use Twitter Card
  When a listing contains at least one image, Twitter Card will attach the image when your users share or tweet the listings.
  
  #### Site Twitter
  Enter your site's Twitter username without the `@` sign. This will be used in content attribution when users share listings to Twitter.
  
  #### Twitter Card Type
  Select one of these values: `summary`, `summary_large_image` or `photo`. To check out more about Twitter Card Types, click [here](https://dev.twitter.com/cards/types).

  If you're using `summary_large_image` or `photo` card type, be sure to allow the Twitter crawler to access your photos. Mosets Tree's listings photos are located in the /media/com_mtree folder and Joomla's robots.txt file by default prevents any crawler to access `/media` directory. 
  
  To lift this restriction, edit your site's robots.txt file and remove the following Disallow line:
   
	Disallow: /media/
  
  For more information, refer to [Twitter's Getting Started Guide for Cards](https://dev.twitter.com/cards/getting-started#crawling).
  
## RSS{#rss}
Mosets Tree generates an RSS Feed for all categories recently added and recently updated. This is useful when you want to let users know of changes made in your directory without them needing to check your website constantly. They can get the RSS Feed data with any RSS feed reader or news aggregator.

 Demo: http://demo.mosetstree.com/new.html

 : The RSS's feed icon can be seen next to the "_Recently Added Listings_" title. You can also see this in [Recently Updated](http://demo.mosetstree.com/updated.html) page.

Mosets Tree RSS contains your listing names, descriptions, URLs and images. Options in the Configuration's RSS tab allow you to add additional elements to your RSS feeds. The additional elements will look like this:

	<mtree:cust_1>value</mtree>

 where "*cust_1*" will be replaced by the custom field name and "_value_" is the value of the field for a listing. The caption and the field's value will also be shown as part of the feed item's description.

## SEF URLs {#sefurls}
Enable Search engine friendly (SEF) URLs to provide an easier way for users to access your directory pages. SEF URLs also help with Search Engine Optimization (SEO) by having relevant names and keywords in your URLs.

To enable Mosets Tree' SEF URLs, turn on Joomla Search Engine Friendly URLs in Joomla's Configuration (Go to "**System -> Global Configuration**", under SEO Settings) and Mosets Tree will generate SEF URLs for your directory.

 ### Listing's slug type
 You can control how to represent each listing with an SEF URL.

 #### Alias
 When a listing or category is added to Mosets Tree, an alias is created based on their title/name. This is typically done by lowercasing the name and replacing all the blank spaces with dashes. Choosing the "_Alias_" slug type will use this for your listing slug URL. eg:

 	http://www.example.com/directory/business/acme-inc

 #### Link ID
 Instead of using an alias, "_Link ID_" will use the listing ID number as the listing slug URL. eg:

  	 	http://www.example.com/directory/business/119

 #### Link ID & Alias Hybrid
 "_Link ID & Alias Hybrid_" slug type uses both the listing alias and the listing ID number for your listing's URL slug. This gives the best of both worlds. Using link ID number guarantees that each of your listings have a unique URL, and using the alias gives each listing a human-friendly SEF URL.

## Captcha {#captcha}
You can decide which feature you want to use a [Captcha]({{version}}/fields#fieldtype-captcha) for submissions to verify that your site visitors are real humans and not bots or crawlers.

## Admin {#admin}
This section lets you control some aspects of Mosets Tree's back-end interface.

 ### Use Explorer
 By setting this to `Yes`, you can see the explorer folders that contain your site's directory in a tree-like form on the left hand side of the interface.
 
 ### Explorer's Tree Level
 By default, Mosets Tree limits the depth of your Explorer's Tree to prevent it from loading too many categories at once. You can change the value here to increase or decrease the level of categories you want to show in your Explorer.

 ### Use Internal Notes
 Mosets Tree allows you to write down notes for each listings and most items that are pending approval. This is useful when you are collaborating with multiple editors that manage your directory. You can turn this feature off by setting it to `No`.
 
 ### Use WYSIWYG Editor description field in back-end
 Set this to `Yes` if you want to use a WYSIWYG Editor in your core description field.

## Frequently Asked Questions {#faqs}
{question}How can I manage reviews of my directory?{/question}
{answer}
You can manage all the reviews from your directory through the Mosets Tree's back-end component. Under the _Listings_ section, you will see a "_Reviews_" column which shows the total number of reviews for each listing in hyperlink. Click on the link to manage reviews for a particular listing.
Demo: http://demo.mosetstree.com/administrator/index.php?option=com_mtree&task=reviews_list&link_id=878
{/answer}

{question}Why is "Report" link still displayed in Reviews when I set "Show Report" to `No` under the _Feature_ tab in configuration?{/question}
{answer}
**Show Report** under the _Feature_ tab is used for reporting a listing, not a review. To disable "_Report_" link in reviews, you can configure it under _Permission_. Go to:

 **Mosets Tree -> Configurations -> Edit Permissions... (under "Main" tab)**

 set the permission for **Report Review** to "_Denied_".
{/answer}
