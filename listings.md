# Listings

- [Introduction]({{version}}/listings#intro)
    - [Summary view]({{version}}/listings#summary)
    - [Details view]({{version}}/listings#details)
- [Images]({{version}}/listings#images)
- [Map]({{version}}/listings#map)
- [Publishing]({{version}}/listings#publishing)
- [Parameters]({{version}}/listings#parameters)
- [Notes]({{version}}/listings#notes)

## Introduction {#intro}
Listings are the primary way to store information on your directory. They are what your users ultimately looks for in your directory. Mosets Tree provides host of options and capabilities to manage them.  

A listing is displayed in two forms in the front-end - Details view and Summary view.
 
 ### Summary view {#summary}
 In summarized view, part of the listing's data is shown to your users in a limited amount of space. What will be shown in this view is usually the listing's rating, total number of reviews and core fields' data of the listing. If you want to show custom fields in this view, select `Yes` to "Shown in summary view" parameter when creating the field. 
 
 ### Details view {#details}
 Details view expand full information about a listing. Links will be provided which enable your users to share the directory page to social networks or to connect other website which is related to the listing. Users may also be able to rate and review the listing in listings details page.

## Images {#images}
Mosets Tree allows your users to add images along with their listings to be displayed in listings details view.  

When the images are uploaded, you can drag to sort the images. The first image in the list will be displayed in listings summary view. On the other hand, you can deselect the checkbox to remove any unwanted image and then save the listing. 

## Map {#map}
Mosets Tree comes with support for Google Map. To enable this map, set "Show Map" to `Yes` in [Features]({{version}}/configuration#features) tab of Mosets Tree global configuration.  

With a listing's address entered, press `Locate in map`. Mosets Tree will geocode this address and place a marker on the map to show you the listing's location.  

You can also provide a native search by setting default country, state and city in Mosets Tree global configuration. By doing this, Mosets Tree can geocode the location with the default values entered when only certain address information is provided.

## Publishing {#publishing}
Publishing lets you configure how listing is viewed in front-end interface.

 ### Owner
 You can a change a listing's owner through this parameter. For example, you may want to change the listing's owner once user [claiming]({{version}}/configuration#claiming) listing request is approved.
 
 ### Alias
 You can customize each listing's alias which to be used to generate its own URL later.
 
 ### Created Date
 If you want to change a listing's date created, you can always do this through Created Date. Sometimes, changing of creation date may affect the "New Listing" status of a listing to be published in front-end interface. 
 
 ### Start Publishing
 By default, Start Publishing date is the creation date of the listing. You can also set when to publish a listing to Mosets Tree front-end interface by customizing a Start Publishing date to it.
 
 ### Finish Publishing
 Similar to Start Publishing date, you can set a Finish Publishing date to expire a listing. Once a listing is published down, it will no longer be visible in the front-end interface.  
 
 This field will override the number of day set to expire a listing in Mosets Tree back-end configuration. If no Finish Publishing date is chosen, "[Number of days to expire listing]({{version}}/configuration#expiredDate)" in Mosets Tree global configuration will be used.
 
 ### Template
 Allows you to select which [Mosets Tree template]({{version}}/template) to use in this listing. Changing this only affects the layout of current listing.
 
 ### Rating
 Mosets Tree allows you to rectify the number of rating which a listing gained. Changing values of this parameter may affect the "Top Rated listing" raking in front-end interface.
 
 ### Votes
 Similar to rating, you can change the number of votes which a listing gained. Changing of this value may affect the listing's position in "Most Rated" ranking.
 
 ### Views
 This parameter lets you view or change the number of visitors who viewed the listing. 
 
 ### Visited
 Visited indicates the number of users who visit to the listing's website through "Visit" link provided in listings details page.

## Parameters {#parameters}
Listing's parameter configuration overrides Mosets Tree global configuration. Parameters enable you to configure how certain features of a listing behave. Choosing `Use Global` will inherit values from Mosets Tree global configurations. To override global configuration, choose either `Hide` or `Show` the features. 

## Notes {#notes}
Notes provides a place for you to record any comments about a listing. 
