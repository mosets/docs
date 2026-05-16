# What Is New in Mosets Tree 4.1

- [New in 4.1.3]({{version}}/what-is-new#413)
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

## New in 4.1.3 {#413}

### Date Period Field Type {#date-period-field}

A new **Date Period** custom field type lets you store a period between two dates — for example, "1939-09-01 to 1945-05-09". The end date is optional, making it suitable for ongoing periods. When used in search, Date Period uses "active during" overlap matching, so users can find listings whose date period overlaps with a given date.

See the [Date Period fieldtype documentation]({{version}}/fields#fieldtype-dateperiod) for details.

### Unified Geocoder {#unified-geocoder}

Mosets Tree 4.1.3 introduces a unified geocoder abstraction. **Photon** ([photon.komoot.io](https://photon.komoot.io)) is now the default geocoder, replacing the hard-coded dependency on Google Maps Geocoder. Google Maps Geocoder remains available as a configurable alternative.

Key changes:

- **Photon autocomplete** with keyboard navigation (ArrowUp, ArrowDown, Enter, Escape) for location inputs.
- New **Geocoder** config under **Mosets Tree → Configuration → Map** lets you choose between Photon and Google Maps.
- New **Country Code** config restricts geocoding results to specific ISO 3166-1 alpha-2 country codes. Photon supports multiple comma-separated codes; Google Maps uses the first.
- Map configuration is reorganised into a **Geocoder** section (Geocoder, Country Code) and a **Google Maps** section (API Key, Map Types, Default Type, Styled Map).

See the [configuration documentation]({{version}}/configuration#map) for details.

### Custom No-Image Thumbnail {#noimage-thumbnail}

A new **No-Image Thumbnail** config (**Mosets Tree → Configuration → Image**) lets you override the default no-image placeholder with a custom path or URL. Mosets Tree also auto-detects a per-template `noimage_thb.png` at:

- `/components/com_mtree/templates/{template}/noimage_thb.png`
- `/images/noimage_thb.png`

Custom templates can ship their own placeholder without code changes.

### Filter Open State When Filtered {#filter-open-state}

A new `keep_filter_open_when_filtered` option in the template `config.php` (`listings_view` group) controls whether the filter dropdown is expanded by default when listings are filtered. This is useful for directories where users frequently refine filters.

### Accessibility: Heading Level Fix {#a11y-heading-fix}

The listing summary heading has been changed from `<h3>` to `<h2>` in all bundled templates (Banyan, Boldfire, Drift, Sienna, Slate, Zenith) to fix WCAG 2.1 heading order. If you have custom CSS targeting `.mt-ls-header h3`, you will need to update it to target `.mt-ls-header h2`.

### Bug Fixes {#413-fixes}

- Fixed radius search: distance is now shown in listing summaries even when the listing has no populated address fields, and resolved an SQL error when advanced search uses `sort=distance` without an active radius search.
- Fixed core fields (Address, City, State, Country, Postcode, etc.) going missing from listing summaries when stray `cfvalues` rows exist for some listings but not others.
- Fixed a malformed closing tag in the Category field type HTML output.
- Fixed COM_MTREE language strings not being loaded in Mosets Tree modules when displayed on non-Mosets Tree pages.

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