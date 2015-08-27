# Listings

- [Introduction]({{version}}/listings#intro)
    - [Summary view]({{version}}/listings#summary)
    - [Details view]({{version}}/listings#details)
- [Edit Screen]({{version}}/listings#edit-screen)
	- [Images]({{version}}/listings#images)
	- [Map]({{version}}/listings#map)
	- [Publishing]({{version}}/listings#publishing)
	- [Parameters]({{version}}/listings#parameters)
	- [Notes]({{version}}/listings#notes)
- [Claim]({{version}}/listings#claim)
- [Frequently Asked Questions]({{version}}/listings#faq)

## Introduction {#intro}
Listings are the primary way to store information on your directory. They are what your users ultimately looks for in your directory. Mosets Tree provides host of options and capabilities to manage them.  

A listing is displayed in two forms in the front-end - Details view and Summary view.
 
 ### Summary view {#summary}

 In summary view, part of the listing's data is shown to your users in a limited amount of space. What will always be shown here is the listing name. Rating and the number of reviews are also shown if they are enabled. If you want to show additional custom fields or hide the default ones in this view, toggle the "_Shown in summary view_" setting by editing the field in "**Mosets Tree -> Custom Fields**".
 
 Demo: http://demo.mosetstree.com/models.html

 ### Details view {#details}
 Details view is the dedicated page that shows all published information about your listing. This includes all your fields data, images, ratings, reviews, user profile and maps. Listing details view is also the primary place where you can find links to or perform interaction with your listing.
 
 Demo: http://demo.mosetstree.com/models/970-alex-pettyfer.html

## Edit Screen {#edit-screen}

### Images {#images}
Mosets Tree allows your users to add images along with their listings to be displayed in listings details view.

When the images are uploaded, you can drag to sort the images. The first image in the list will be displayed in listings summary view. You can uncheck the checkbox to mark any unwanted image for removal. Make sure to save the listing to actually remove the image.

### Map {#map}
Mosets Tree comes with support for Google Map. To enable this map, set "Show Map" to `Yes` in [Features]({{version}}/configuration#features) tab of Mosets Tree global configuration.  

When you have a listing's address entered, you can press `Locate in map`. Mosets Tree will geocode this address and place a marker on the map to show you the listing's location.

You can also provide better geocode experience by setting default country, state and city in Mosets Tree's configuration. By doing this, Mosets Tree will use these default value when they are not entered to a listing. For example, when you have set a default city, state and country, your users only need to enter an address in order to perform a geocode.

Demo: http://demo.mosetstree.com/business/872-carl-s-jr.html

: Listings in _Business_ category usually attach an address. In this page, Mosets Tree geocode the address and you can see the marker is placed at the business address showing users the business location.

### Publishing {#publishing}
Publishing lets you configure many of the listing's meta data.

#### Owner

Owner is the designated user that owns the listing. They are the one that can manage the listing in front-end. You can change the owner by clicking on the person icon.

#### Alias

Alias is used as your listing slugs when you have SEF URLs enabled. When a new listing is created, the alias is automatically generated for you by using a lower case name and replacing spaces and dash.
 
#### Created Date
If you want to change a listing's date created, you can do this by editing "_Created Date_". Changing this may affect the "New Listing" status of a listing in front-end.
 
#### Start Publishing

By default, Start Publishing date is the creation date of the listing. You can override this date in order for the listing to be published on a later date.
 
#### Finish Publishing

Similar to Start Publishing date, you can set a Finish Publishing date to expire a listing. Once a listing is published down, it will no longer be visible in the front-end interface.

By default, all listings do not have a "_Finish Publishing_" date set, so they are published as long as they are set as such. If you have set a value for "[Number of days to expire listing]({{version}}/configuration#days_to_expire)" config, the "_Finish Publishing_" date will be set with a future expiry date.

#### Template

Allows you to select which [Mosets Tree template]({{version}}/template) to use in this listing. Changing this only affects the layout of current listing.
 
#### Rating

Shows the listing's average rating and allows you to alter its rating. Note that changing value of this may affect the listing's position in "_Top Rated listing_" page.
 
#### Votes

Shows the total number of votes and allows you to change it. Note that changing value of this may affect the listing's position in "Most Rated" page.
 
#### Unique Pageviews

Shows the total number of times your users has viewed a listing. A unique pageview is counted as one when a user view a listing in a session. The user can view the listing page multiple times within a session and it will count as one unique page view.

By default a session is 24 hours. You can change this in Configuration for "[Unique pageviews session (in seconds)]({{version}}/configuration#hit_lag)"
 This parameter lets you view or change the number of visitors who viewed the listing. 
 
#### Website Clicks

Shows the number of times your users has visited a listings websites through the "Visit" link in listings details page.

### Parameters {#parameters}
Listing's parameter configuration overrides Mosets Tree global configuration. Parameters enable you to configure how certain features of a listing behave. Choosing `Use Global` will inherit values from Mosets Tree global configurations. To override global configuration, choose either `Hide` or `Show` the features. 

### Notes {#notes}
Internal notes provides a place for you to record any comments about a listing. If you have multiple editor managing your directory, you can use this as a place to comment and collaborate on a listing.

## Claim {#claim}
If any of your listings are owned by user from _Super Users_, _Administrator_ or _Manager_ group, they can be claimed by users. When a user claim a listing, you will be notified by e-mail. You can then view this claim in Mosets Tree's back-end to approve or reject the claim.

Approving the claim will assign the ownership of the listing to the claimant, essentially making the claimant the owner of the listing which allow them to manage the listing in front-end.

You can disable this [feature]({{version}}/configuration#show_claim) in Configuration.

## Frequently Asked Questions {#faq}

{question}Is it possible to have multiple marker in a single map?{/question}
{answer}
No. Mosets Tree does not show multiple markers in a single map. You can however search a third party addons that allows you to do this.
{/answer}

{question}How can I hide the message "No records Found"{/question}
{answer}
The message "No records found" appears when you browse to a Mosets Tree category that contains no listings.  
 
If you do not intend to have listings in Index and wish to remove the message, you can go to "**Mosets Tree -> Configuration -> Listing tab**", set "Display listings in root" to `No`.  

If you do not intend to have listings in a particular category and wish to remove the message, you can go to Mosets Tree back-end and browse to edit category, set "Show Listings" in that category to `No`.
{/answer}