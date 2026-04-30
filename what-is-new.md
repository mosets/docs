# What Is New in Mosets Tree 4.1

- [New in 4.1.2]({{version}}/what-is-new#412)
- [New in 4.1.1]({{version}}/what-is-new#411)
- [Grid-style Gallery Layout]({{version}}/what-is-new#grid-gallery)
- [JSON/ZIP Import]({{version}}/what-is-new#json-zip-import)
- [Category Export & CSV Download]({{version}}/what-is-new#category-export)
- [Updating Existing Listings via Import]({{version}}/what-is-new#import-update)
- [Search Respects Category Authorization]({{version}}/what-is-new#search-category-auth)
- [Category Breadcrumbs Tool]({{version}}/what-is-new#category-breadcrumbs)
- [Guest Email on Reports]({{version}}/what-is-new#guest-email-reports)
- [Font Awesome 6 Free]({{version}}/what-is-new#font-awesome-6)

## New in 4.1.2 {#412}

### Radius Search {#radius-search}

Mosets Tree 4.1.2 introduces location-based searching. Visitors can now find listings within a chosen distance of a place — for example, "all coffee shops within 10 km of my current location".

Radius search is configured under **Mosets Tree → Configuration → Search → Radius Search** and is available in the Advanced Search page when enabled. You can choose between kilometers and miles, define the distance options shown to users, and set a default radius.

See the [Search documentation]({{version}}/search#radius-search) and [configuration]({{version}}/configuration#radius-search-config) for details.

### Location Search Module {#location-search-module}

A new `mod_mt_location_search` module makes radius search accessible from anywhere on your site. The module displays a location input with optional autocomplete, an optional "Use my location" button, and an optional radius selector.

See the [Location Search module documentation]({{version}}/modules#mod-mt-location-search) for details.

### Heading Field Type {#heading-field}

A new **Heading** custom field type displays a section heading to visually organize related custom fields into groups in the Add Listing form, listing details page and search forms. Use it to break long forms into clearly labelled sections.

See the [Heading fieldtype documentation]({{version}}/fields#fieldtype-heading) for details.

### Bug Fixes {#412-fixes}

- Grid gallery lightbox now scopes navigation per listing instead of cycling through every image on the page
- "Trigger Modified Listing" configuration now supports core field IDs (Name, Description, etc.) in addition to custom fields

## New in 4.1.1 {#411}

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

## Grid-style Gallery Layout {#grid-gallery}
A new grid-style gallery layout option is available for listing images, in addition to the classic slider layout. This can be configured through the template parameters.

## JSON/ZIP Import {#json-zip-import}
MT Importer now supports importing data from JSON and ZIP files. ZIP files can contain CSV data, images, and a field type mapping file. See the [Importer documentation]({{version}}/importer#json-zip) for details.

## Category Export & CSV Download {#category-export}
You can now export your directory data as CSV files, with options to export by category or date range. See the [Export documentation]({{version}}/importer#export) for details.

## Updating Existing Listings via Import {#import-update}
MT Importer now supports updating existing listings by matching on `link_id`, instead of always creating new listings. See the [Importer documentation]({{version}}/importer#update-existing) for details.

## Search Respects Category Authorization {#search-category-auth}
Searching by category now respects the view access level authorization. Users will only see search results from categories they are authorized to view.

## Category Breadcrumbs Tool {#category-breadcrumbs}
A new category breadcrumbs tool is available to display the full category path for listings.

## Guest Email on Reports {#guest-email-reports}
Guest users can now provide their email address when reporting a listing, allowing administrators to follow up on reports.

## Font Awesome 6 Free {#font-awesome-6}
Mosets Tree now uses Font Awesome 6 Free icons, replacing the previous version for a wider selection of modern icons.