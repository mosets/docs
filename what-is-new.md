# What Is New in Mosets Tree 3.7

## Managers

You can now assign one or more user groups as Managers. Managers are users who can edit or delete listings in front-end, even when they do not own the listings. This allows you to assign user groups to manage your directory. This makes it extremely convenient to change or update your listings when you see them in front-end, without going back and forth between front and back-end.

Since you can override this in category configuration, you can assign different user group to manage different categories.

## Search Completion

Search module (mod_mt_search) now has search completion. Search completion activates as soon as you start typing in the search box. Results are returned by matching the search keyword against category and listing names. The results are shown under the search box as a list of drop down. Clicking on any of the search results will bring you directly to the category or listing.

## Listing Owners

There is now a dedicated page showing all listings owners. These are users who has one or more listings in the directory.

## Next/Previous Listings

Often times, you want to check out one listing details after another. This update brings a new feature to let you navigate between your listings details page, one after another through a Previous and Next listing link at the bottom of each listing details page.

## Random Listings

When showing a list of listings, they are typically ordered by a core fields. In this update, you have a new option to order your listings randomly. Surprise your users and let them discover more listings from your directory.

## 3 new fieldtypes

### Listings

Listings fieldtype allows you to create a special type of custom fields that shows other listings from your directory. You can customise the custom field to show the listings with images and/or any of their custom fields.

### Multi Dates

Multi Dates allows you to enter one or more dates by entering the dates directly or by selecting the date through a displayed calendar.

### Telephone

Similar to the core Telephone field, Telephone fieldtype lets you create a telephone custom field with an option to show them with a tel: link.

## Back-end

- When you browse a category or edit a listing in back-end, there is an easy to access link to let you open a listing in front-end in a new window. 
- Core fields has a new setting called "Back-end listings column". This setting allows you to show additional core fields in back-end's listings column.

## Miscellaneous

- SEO improvement to allow sprintf to searchby and sub-category's title and header.
- Adds support for detecting https in parsing description field's URL.
- Listing ID field is now searchable.
- mod_mt_listings now can have up to 3 filters.
- RSS now outputs raw custom fields data as part of description.
- Adds a menu item type for "All Listings".
- Adds "Alternative Layout" option to all modules.
- mod_mt_search: Drop-down categories now only show top level categories for the current user who is authorized to access.
- Advanced Search and Edit Listing's categories option now only show top level categories for the current user who is authorized to access.
- Adds a new config to control when to show "Add your listing here" link.
- Adds a new config to limit the number of listings a user can have.
- Add Year & Date field as sorting options.
- Adds 2 new core fields: firstname, lastname
- Addresses now displays according to ordering.
- Listings' pending approval e-mails to admin now contains direct link to review listings in back-end.
- Searching with empty keyword in mod_mt_search now brings you to All Listings page.
- Minimum search characters' configuration is now visible.
- Remove link in listing summary image when listing is pending for approval.