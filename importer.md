# Importer

- [Installing MT Importer]({{version}}/importer#install)
- [Import from CSV]({{version}}/importer#csv)
	- [Formatting your CSV file]({{version}}/importer#csv-format)
	- [Category]({{version}}/importer#csv-category)
	- [Existing Custom Fields]({{version}}/importer#csv-existing-fields)
	- [New Custom Fields]({{version}}/importer#csv-new-fields)
	- [Select Multiple & Checkbox Field]({{version}}/importer#csv-select-multiple-checkbox)
	- [Owner]({{version}}/importer#csv-owner)
	- [Images]({{version}}/importer#csv-images)
	- [Listing Association]({{version}}/importer#csv-listing-assoc)
	- [Basic Rules & Tips]({{version}}/importer#csv-basic-rules-tips)
- [Import from Hot Property]({{version}}/importer#hot-property)
- [Import from SobiPro 1.1]({{version}}/importer#sobipro)
- [Import from K2 2.6 & 2.7]({{version}}/importer#k2)

MT Importer is a standalone extension that helps you to import your external data in to Mosets Tree.

If you're an active Mosets Tree subscriber, you can download MT Importer from your [Mosets account](http://www.mosets.com/login/).

> Note: MT Importer can not be used to import or upgrade from older version of Mosets Tree. Refer to the [Migration]({{version}}/migration-guide) section for migrating your Mosets Tree directory to another site. Refer to the [Upgrade]({{version}}/upgrade) section for upgrading Mosets Tree to the latest version.

## Installing MT Importer

Installation of MT Importer is similar to other component's installation in Joomla. 

To install:

1. Login to your Joomla's administrator back-end.
2. Goto "**Extensions -> Manage -> Install**".
3. Click "**Browse...**" to select "`com_mtimporter-xxx.zip`" from your computer.
4. Click "**Upload & Install**" to start the installation.

If your installation is successful, you will see the message "_Installing package was successful._".

## Import from CSV {#csv}

If you can export your existing data in to Comma Separated Values (CSV) format, you can use this tool to import your data directly to Mosets Tree:

1. Login to your Joomla's administrator back-end.
2. Goto "**Components -> MT Importer -> Import from .csv file**".
3. Click "**Choose File**" to select .csv file from your computer.
4. Click "**Import**" to start the import process.

You will be notified and redirected to Mosets Tree main page when the import is completed. Since you're importing data from another source, you need to perform "**Recount Cats/Listings**" after the import process is complete. This function will recount the number of categories and listings you have in Mosets Tree.

### Formatting your CSV file {#csv-format}

Here's a super simple CSV that imports a single listing named "My first import" in to the root of your directory. To test this sample, copy the texts below, save it to a file named _myfirstimport.csv_ and import the file through MT Importer:

	link_name
	My first import

If you have more fields, it will look something like this:

	link_name, address, city, country, website, email
	Acme Co., 34 Jefferson St., New York, USA, http://www.example.com, acme@example.com
	Ben Co., 81 Jefferson St., New York, USA, http://www.example2.com, ben@example.com

The first row define the columns of your data. Here are the column names of all core fields in which you can use as columns in CSV:

<style>
    .import-core-fields-list {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
    }

    .collection-method-list a {
        display: block;
    }
</style>

<div class="import-core-fields-list" markdown="1">
  - link_name
  - alias
  - link_desc
  - user_id
  - link_hits
  - link_votes
  - link_rating
  - link_featured
  - link_published
  - link_approved
  - link_template
  - attribs
  - metakey
  - metadesc
  - internal_notes
  - link_created
  - publish_up
  - publish_down
  - link_modified
  - link_visited
  - address
  - city
  - state
  - country
  - postcode
  - contactperson
  - mobile
  - date
  - year
  - telephone
  - fax
  - email
  - website
  - price
  - show_map
  - lat
  - lng
  - zoom
</div>

Only `link_name` is mandatory. Other columns are optional.

These column names are mapped directly to the columns for `#__mt_links` database table (where *#__* is your Joomla's database table prefix). Therefore the column names are fixed regardless of the alias or caption you use for each fields above.

### Category {#csv-category}
Use the `cat_id` column to specify the Category ID for your listings. This information can be found when you're browsing the category. If no category ID is specified, Importer will import the listing to Root category (0). To import a listing to more than one category, specify the category IDs separated by command. ie:

		link_name, cat_id
		"This listing will be imported in to 3 categories", "2,6,17"

### Existing Custom Fields {#csv-existing-fields}
If you want to import a column to an existing custom field that you have created in your directory, use the **ID** or [Alias]({{version}}/fields#alias) of the custom field as the column name. You can locate these IDs at Custom Fields page.

In the example below, we have 2 new columns named `25` and `31`. Mosets Tree will import data for these columns to custom field with those IDs:

	link_name, address, city, country, website, email, 25, 31
	Acme Co., 34 Jefferson St., New York, USA, http://www.example.com, acme@example.com, "@acmeco", "http://facebook.com/acmeco"
	Ben Co., 81 Jefferson St., New York, USA, http://www.example2.com, ben@example.com, "@bencoffee", "http://facebook.com/bencoffee"

### New Custom Fields {#csv-new-fields}
If your data have other columns that are not represented by any of the core fields, you can add them to the column row with any name. Mosets Tree will create a custom field to accommodate this column based on [Text fieldtype]({{version}}/fields#fieldtype-text):

	link_name, last_name, gender, dob, contactperson, telephone
	Alice, Aniston, f, "20 June 1998", Mitchell, 1800-99-7051
	Bobby, Bishop, m, "13 February 1991", Nigel, 1800-60-3132
	Cecil, Charles, m, "27 November 1988", Mitchell, 1800-99-7051

In the example above, `link_name`, `contactperson` and `telephone` is recognized as core fields, therefore will be imported to their respective core fields. Meanwhile, Mosets Tree will create custom fields based on Text field type for `last_name`, `gender` and `dob` and import them to there.

You may change the field type of these newly created custom field to best fit their data after the import.

### Select Multiple & Checkbox Field {#csv-select-multiple-checkbox}
If you have multiple values in a column (eg: Checkbox or Select Multiple field), separate each values with the bar character:

 		link_name, mycheckbox
 		"Example", "value1|value2|value3"

The order of the values are irrelevant. If the values you defined here are does not exists in any of your field elements, they will be removed when your listing is saved or updated. To fix this, edit your field and add the new value as part of your field elements.

### Owner {#csv-owner}
Enter User ID to the `user_id` column. This information can be found from Joomla's User Manager. If no user ID is specified, the listing will be assigned to the current user running MT Importer.

### Images {#csv-images}
Typically, you can only import plain text data from CSV file. If you want to import images, you can specify them in separate columns with values pointing to your images' URLs:

	link_name, myimage
    "Grand Canyon, Colorado",http://i.imgur.com/3uuXtsFl.jpg
    "Cape Hauy, Tasmania",http://i.imgur.com/aKi7oVZl.jpg
    "Lofoten Islands, Norway",http://i.imgur.com/9lDdLYR.jpg

Once you've imported these data, follow these steps:

1. Edit the "_Myimage_" custom field and change its field type from "_Text_" to "_Weblink_".
2. Go to "**Mosets Tree -> Tools**"
3. Look for "_Import Images_" tool and select "_Myimage_" custom field.
4. Click the "_Import Images_" link.

Mosets Tree will read through the selected custom field and import images through the specified URLs to your listings.

### Listing Associations {#csv-listing-assoc}
If you have setup [Category Association]({{version}}/categories#association) in your directory, you can use `link_id1` column to specify your listings association with the associated listing's ID as the value.

Note that you still need to set up category association and create an [Associated Listing]({{version}}/fields#fieldtype-associatedlisting) custom field in order to manage and view the association in front-end.

### Basic Rules & Tips {#csv-basic-rules-tips}

- The first line of sample.csv contains the list of column names that map to Mosets Tree's database. Only the column `link_name` is compulsory. Other columns are optional and can be safely removed. If you're removing a column, make sure you remove the corresponding values for the listings.
- Second line and onwards is where you insert your data. One line for each listing.
- You may use Microsoft Excel or any other word processor to edit the file. Make sure you do not save the formatting when prompted.
- If you want a particular listing to be featured, set `link_featured` column to `1`.
- There is no need to enter `link_published` or `link_approved`'s value. All imported listings will be published and approved automatically.
- The field separator is comma `,`, and the fields should be enclosed by double quote `"` if the values contains comma.
- Your CSV file should be saved with **UTF8** encoding and **LF** (Line Feed) line endings.
- Use the "**Dry Run**" option to check if your CSV file is properly formatted. Dry run will scan your CSV file and report any errors if it finds any. Importing using the dry-run option does not write any data to your database.
- The order of the column does not matter.

> One of the most common issue importing CSV file is when your file is not using **UTF-8** encoding or **LF** line endings. When you're doing a dry-run, you may find out that MT Importer detects your entire file as the column header (not using LF line endings); or it may not import non-latin characters (not using UTF-8 encoding).

#### What Importer doesn't do:
- It does not support importing files or binary based data.
- It does not create categories. You have to create the categories first before starting the import.

{question}How can I check my file's encoding and line endings?{/question}
{answer}
You can use the _Notepad_ program in _Windows_ to check both file's encoding and line endings.

On Unix, run the following command:

	$ file myfile.csv
    myfile.csv: UTF-8 Unicode text

An ideal output would be `UTF-8 Unicode text` or `UTF-8 Unicode English text, with very long lines`.
{/answer}

## Import from Hot Property {#hot-property}
MT Importer will import all types, companies, agents and properties from Hot Property 1.0 to Mosets Tree version 3.5+. During the import, 3 new top level categories will be created, namely 'Hot Property Properties', 'Hot Property Agents' and 'Hot Property Companies' to store the imported properties, agents and companies respectively.

No data will be removed during or after the import process. Any data that you currently have in Mosets Tree will be retained.

To prepare for the import:

1. Have a running version of Mosets Tree 3.5+.
2. Export the following database tables to your current database. Be sure the rename the database table prefix below (*jos_*) with your current site's database table prefix:
	- jos_hp_agents
	- jos_hp_companies
	- jos_hp_photos
	- jos_hp_properties
	- jos_hp_properties2
	- jos_hp_prop_ef
	- jos_hp_prop_types
3. Copy the following directories and the files in it from your old Hot Property site to your new Mosets Tree site:
 - /media/com_hotproperty/images/std
 - /media/com_hotproperty/images/thb
 - /media/com_hotproperty/images/ori
 - /media/com_hotproperty/images/agent
 - /media/com_hotproperty/images/company

To import:

1. Login to your Joomla's administrator back-end.
2. Goto "**Components -> MT Importer -> Import from Hot Property**".
3. Click "**Import**" to start the import process.

You will be notified and redirected to Mosets Tree main page once the import is complete. Since you're importing data from another component, you need to perform "**Recount Cats/Listings**" after the import process is complete to recount the number of categories and listings you have in Mosets Tree. This function is available under the "**Tools**" section in Mosets Tree back-end.

## Import from SobiPro 1.1 {#sobipro}
Mosets Tree can help you to import your data from SobiPro 1.1 to Mosets Tree 3.6+. This includes SobiPro sections, categories, entries, fields and images.

The import is fairly straight forward. All you need to to have your SobiPro data resides in same MySQL database using the same table prefix and images in your server's filesystem.

> **Warning**: Your data in Mosets Tree will be erased when you're importing from SobiPro. If you have any data you wish to retain, please backup your site prior to running the import.

To import from SobiPro:

1. Login to your Joomla's administrator back-end.
2. Goto "**Components -> MT Importer -> Import from SobiPro**".
3. Click "**Import**" to start the import process.

You will be notified and redirected to Mosets Tree main page once the import is complete. Since you're importing data from another component, you need to perform "**Recount Cats/Listings**" after the import process is complete to recount the number of categories and listings you have in Mosets Tree. This function is available under the "**Tools**" section in Mosets Tree back-end.

## Import from K2 2.6 & 2.7 {#k2}

 MT Importer will import all items, categories, images and extra fields from K2 2.6 or 2.7 to Mosets Tree version 3.6. This import tool does not import your items' Image Gallery, Media, Attachments, Videos, Tags and Comments. 

The import is fairly straight forward. All you need to to have your K2 data resides in same MySQL database using the same table prefix and images in your server's filesystem.

> **Warning**: Your data in Mosets Tree will be erased when you're importing from K2. If you have any data you wish to retain, please backup your site prior to running the import.

To import from K2:

1. Login to your Joomla's administrator back-end.
2. Goto "**Components -> MT Importer -> Import from K2**".
3. Click "**Import**" to start the import process.

You will be notified and redirected to Mosets Tree main page once the import is complete. Since you're importing data from another component, you need to perform "**Recount Cats/Listings**" after the import process is complete to recount the number of categories and listings you have in Mosets Tree. This function is available under the "**Tools**" section in Mosets Tree back-end.