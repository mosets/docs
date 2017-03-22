# What Is New in Mosets Tree 3.9

- [Cluster Maps]({{version}}/what-is-new#cluster-maps)
- [JSON Output]({{version}}/what-is-new#json-output)
- [Listing Renewal]({{version}}/what-is-new#listing-renewal)
- [Featuring a listing in front-end]({{version}}/what-is-new#feature-listing-front-end)
- [Joomla Update Support]({{version}}/what-is-new#joomla-update-support)
- [Miscellaneous]({{version}}/what-is-new#misc)

## Cluster Maps {#cluster-maps}

Mosets Tree 3.9 introduces Cluster Maps that lets you show Google Maps with markers from multiple listings. You can show Cluster Maps in Category, Index, Search Results, Top Listings and All Listings pages. 

## JSON Output {#json-output}

JSON output allows other app or services to consume data from Mosets Tree in a machine readable way. This is disabled by default and can be enabled through Mosets Tree Configuration. Check out the [full documentation]({{version}}/configuration#allow_json_output) to learn more about this. 

## Listing Renewal {#listing-renewal}

Mosets Tree has always allow you to set the number of days new listings stay published before they expire. Mosets Tree 3.9 introduces a new feature that allow your users to renew their listings before they expire. Check out the [full documentation]({{version}}/configuration#allow_listing_renewal) to learn more about listing renewal.

## Featuring a Listing in Front-end {#feature-listing-front-end}

 Featuring a listing has always been a privilege for administrator in back-end. Mosets Tree 3.9 introduces support for listing owner to feature their own listing in front-end.

## Joomla Update Support {#joomla-update-support}

 Mosets Tree 3.9.6 introduces Joomla Update support through the use of Access Key. Easily check for Mosets Tree update and update your Mosets Tree on site in 2 clicks. For more information, please refer to the [Access Key documentation]({{version}}/access-key).
 
## Miscellaneous {#misc}
 
- Number based fields now defaults to a Slider based ranged search.
- Filter module (mod_mt_filter) now has auto search.
- Number fieldtype now uses number input field.
- E-mails sent through contact and recommended form now originates from the site's sender name & email.
- Google Maps in listing details page now uses API Keys.
- New cron controller that execute scheduled tasks within Mosets Tree's context. Hook name: onMTreeExecuteCron
- "Search By" values are now sorted naturally instead of frequency.
- Listing Owners page now supports category.
- mod_mt_owners now links to 'Read more...' page.
- Don't show Reviews data in Listing Owners page when Reviews are disabled.
- E-mails to admin for pending reviews now contains URL to the listing.
