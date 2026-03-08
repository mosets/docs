# What Is New in Mosets Tree 4.1

- [New in 4.1.1]({{version}}/what-is-new#411)
- [Cluster Maps]({{version}}/what-is-new#cluster-maps)
- [JSON Output]({{version}}/what-is-new#json-output)
- [Listing Renewal]({{version}}/what-is-new#listing-renewal)
- [Featuring a listing in front-end]({{version}}/what-is-new#feature-listing-front-end)
- [Miscellaneous]({{version}}/what-is-new#misc)

## New in 4.1.1 {#411}

### Facebook App ID Configuration {#facebook-app-id}

You can now configure a Facebook App ID for the Facebook Like button. This allows you to associate the Like button with your Facebook app for better analytics and control. The new setting is available under **Mosets Tree -> Configuration -> Sharing**. See the [configuration documentation]({{version}}/configuration#facebook_app_id) for more details.

### WCAG 2.2 Accessibility Improvements {#accessibility}

Mosets Tree 4.1.1 includes comprehensive accessibility improvements across templates and modules to better comply with WCAG 2.2 guidelines. These include:

- Added accessible names, labels, and ARIA attributes for star ratings, images, buttons, and links
- Decorative icons are now marked with `aria-hidden`
- Added `aria-current` attribute to the current category in tree browse navigation
- Added `aria-label` to category select dropdowns, edit menu buttons, and search form inputs
- External links now include `rel="noopener noreferrer"` for security
- Empty content is handled gracefully to avoid broken links

### Swiper Replaces FlexSlider {#swiper}

The image gallery slider has been upgraded from FlexSlider to [Swiper](https://swiperjs.com/), a modern, performant and touch-friendly slider library. This provides smoother transitions and better mobile support for listing image galleries.

### Native Audio & Video Players {#native-media-players}

Video.js and MediaElement.js have been replaced with native HTML5 video and audio players. This reduces the number of third-party libraries, improves page load performance, and enables seeking in audio and video players.

### Flatpickr Replaces jQuery Datepick {#flatpickr}

The Multiple Dates custom field now uses [Flatpickr](https://flatpickr.js.org/) instead of jQuery datepick, providing a modern, lightweight date picker with better mobile support.

## Cluster Maps {#cluster-maps}

Mosets Tree 3.9 introduces Cluster Maps that lets you show Google Maps with markers from multiple listings. You can show Cluster Maps in Category, Index, Search Results, Top Listings and All Listings pages. 

## JSON Output {#json-output}

JSON output allows other app or services to consume data from Mosets Tree in a machine readable way. This is disabled by default and can be enabled through Mosets Tree Configuration. Check out the [full documentation]({{version}}/configuration#allow_json_output) to learn more about this. 

## Listing Renewal {#listing-renewal}

Mosets Tree has always allow you to set the number of days new listings stay published before they expire. Mosets Tree 3.9 introduces a new feature that allow your users to renew their listings before they expire. Check out the [full documentation]({{version}}/configuration#allow_listing_renewal) to learn more about listing renewal.

## Featuring a Listing in Front-end {#feature-listing-front-end}

 Featuring a listing has always been a privilege for administrator in back-end. Mosets Tree 3.9 introduces support for listing owner to feature their own listing in front-end.
 
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