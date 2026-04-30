# Search

- [Simple Search]({{version}}/search#simple-search)
- [Advanced Search]({{version}}/search#adv-search)
- [Radius Search]({{version}}/search#radius-search)
- [Filters]({{version}}/search#filters)

It would be tedious if you have to browse through categories and look through many listings to find the listings you're looking for. Mosets Tree comes with 3 types of searches to help your users to search for listings quickly.

## Simple Search {#simple-search}
Simple Search is one of the popular module of Mosets Tree. It provides a text box for searching keyword that matches all listing's fields that is set to "[Simple Searchable]({{version}}/fields#simple-searchable)". You can choose to display a drop down categories list through setting in [Search module]({{version}}/modules#mod-mt-search). This allows users to limit their searches in a specific category.

By default, the search is performed within the entire directory because its "Parent Cat. ID" is set to `0`, which is the root's category ID. You can set a `parent ID` and if "Show Category" is set to `No`, users' searches through Search module will be limited to the appointed parent category. Note that you can get the "Parent Cat. ID" in left hand side table of the "Category" page in back-end.

### Search Completion {#simple-search}

The Search module has built in support for search completion, or popularly known as Ajax Search. This is activated as soon as you start typing on the search box. Search completion will match your listing and category's names and return up to 8 results. You can then press the Up or Down arrow to navigate between the results. Press the 'Enter' key to go directly to the listing or category. 

For performance reason, results that are returned when using search completion are not sorted in any specific order.

## Advanced Search {#adv-search}
Advanced Search provides users a more precise search to a listing in your directory. It allows your user to enter several search criteria and only display those listings that match all or any of the criteria entered by users. You can customize which fields to be shown here for your user by setting the fields to [Advanced Searchable]({{version}}/fields#advanced-searchable).

> **Note**: Searching by category respects the view access level authorization. Users will only see search results from categories they are authorized to view.

Advanced Search usually search against all your directory pages. In order to search within a specific category, you can modify the directory's URL. With [SEF URLs]({{version}}/configuration#sefurls) enabled, you can direct to the specific category advanced search page by entering the category's alias in front of `/advanced-search`. For example: 
    
    http://www.example.com/directory/movies/advanced-search
    
When no SEF URLs is enable, you can go to any of the category page and replace `listcats` to `advsearch` in URL for entering to the category Advanced Search.

Demo: http://demo.mosetstree.com/advanced-search.html

## Radius Search {#radius-search}
Radius Search lets users find listings within a chosen distance of a place — for example, all listings within 25 km of an address. Once enabled, a location input and a distance selector appear in the Advanced Search page, and listing summaries can show the distance from the searched location.

To enable radius search, go to **Mosets Tree → Configuration → Search → Radius Search** and set "Enable Radius Search" to `Yes`. From the same screen you can choose the unit (kilometers or miles), define the distance options shown in the dropdown, and set a default radius. See the [configuration documentation]({{version}}/configuration#radius-search-config) for details.

You can also publish the [Location Search module]({{version}}/modules#mod-mt-location-search) to expose radius search anywhere on your site outside the Advanced Search page.

### Requirements {#radius-search-requirements}

Radius search uses Google Maps for location autocomplete and geocoding. To use it, you need:

1. **A Google Maps API key** entered under **Mosets Tree → Configuration → Map → Google Maps API Key**. This is the same key used by Cluster Maps.
2. The following APIs enabled on that key in [Google Cloud Console](https://console.cloud.google.com/):
    - **Maps JavaScript API** — loads the map library (already required for Cluster Maps).
    - **Places API** (or **Places API (New)**) — powers the location autocomplete dropdown.
    - **Geocoding API** — converts the chosen place into coordinates used for the distance calculation, and converts the user's current location (from the "Use my location" button) into a readable address.
3. **Geocoded listings**. Radius search measures distance from the searched location to each listing's stored latitude and longitude. Listings without coordinates will not appear in results. Use the back-end **Locate Listings in Map** tool to geocode existing listings.

If autocomplete suggestions don't appear or the search returns no results despite nearby listings existing, the most common cause is one of the APIs above not being enabled, or the API key having referrer or billing restrictions that block these specific APIs.

## Filters {#filters}
Filters are available by publishing Mosets Tree's [Filter module]({{version}}/modules#mod-mt-filter) to your directory. Similar to Advanced Search, Filters is also an option that allows users to filter the listings to quickly find the listing they are looking, except that users can use this searching method in any pages of your directory from where you want the module to be published.

Instead of searching against the entire directory, you can change the `Category ID` in Filter module so searches will be performed within the specified category. Bear in mind that you have to configure your fields to [Filter Searchable]({{version}}/fields#filter-searchable) before you can allow your users to search through Filters.

Filters are also available when your users view your category through 'All Listings' in front-end. They can access it by clicking on the "**Filter listings...**" link.

Demo: http://demo.mosetstree.com/properties/all.html

: In this page, users can click on the "**Filter Properties**" link to review filters. 
