# Frequently Asked Questions

{question}How can I change the word 'Directory'?{/question}

{answer}Most the texts used in Mosets Tree's front-end can be [overrided]({{version}}/language#overrides) through Joomla's Language manager. 

Alternatively, you can insert the following text:
 

	COM_MTREE_ROOT="Directory"
	
to the the override file located at this location in your joomla path:

	/language/overrides/en-GB.override.ini
	
Be sure to replace the word 'Directory' with the replacement you want, and replace the override file name's 'en-GB' prefix, if the language you are overriding is not English language.

{/answer}

{question}How can I use HTML tags in Description field?{/question}

{answer}
Description field by default strips HTML tags. In order to use and allow HTML tags in Description, follow these steps:

1. Login to the back-end
2. Go to Mosets Tree
3. Click _Custom Fields_
4. Click '_Description_'
5. Scroll to the lower part of the page and you will see a list of parameters
6. Set the following parameters:
	- _Strip all HTML tags in Summary view_ - `Yes`
	- _Strip all HTML tags in Details view_ - `No`
	- _Parse URL as link in Details view_ - `No`
	- _Strip all HTML tags before storing to database_ - `No`

This will allow you to use HTML tags in description field. Please note that HTML tags will be stripped in Summary view and only shown in Details view.

{/answer}

{question}How do I publish the extension to my Joomla's site frontpage?{/question}

{answer}
The steps outlined here applies to other component as well.

1. Login to yout website's administrator back-end.
2. Goto "_Menus -> Main Menu_"
3. Look for a Mosets Tree menu item in the list of menus. Otherwise you need to create one:
	- Click the "New" icon.
	- Click "Select" and choose "_Mosets Tree > Home_" for the 'Menu Item Type'.
	- Enter a title to "Menu Title"
	- Click the "Save" icon on top of the page to save this new menu item.
	
4. To publish this menu item to your site's frontpage, look for the menu item in the list of menu items and click on the 'star' icon under "_Home_" column. This will mark the menu item as your site's frontpage.

{/answer}

{question}How can I back up my Mosets Tree data?{/question}

{answer}
Data in Mosets Tree are stored in 2 places. The main data are stored in the database and the uploaded images and attachments are stored in the file system.

### Images and Attachments

**/media/com_mtree/images/cats/**	
**/media/com_mtree/images/listings/**
**/media/com_mtree/attachments/**

The 3 directories above contains all uploaded images (both original and scaled version) for categories & listings and listings' attachments. If you have any uploaded images or attachments in your directory, make sure you back up these 2 directories, including all its sub-directories and files.

### Database
Assuming your database is using '_jos\__' as the database prefix, backup all tables that start with _jos\_mt\_*_. Most hosting provider provide an interface through phpMyAdmin for you to export the data in a SQL file. Be sure to export the data structures and the data.

### Templates

**/components/com_mtree/templates/**	

All Mosets Tree templates are stored in the above directory in its own sub-directory. Mosets Tree comes with a default template called '_kinabalu_' which is stored at `/components/com_mtree/templates/kinabalu/`. If you did not modify the default template, you can skip this directory, otherwise, backup all files and directories in this template directory.

{/answer}

{question}Why my site's Mosets Tree back-end is slow. We have a lot of categories in Mosets Tree.{/question}

{answer}
Most of the load time issue in the back-end is cause by the time needed to load all categories in the Explorer menu. You can reduce the time needed for this by reducing the number of levels (of categories) the explorer load:

1. Goto Mosets Tree **Configuration**
2. Click on **Admin** tab
3. Set **Explorer's Tree Level**: to `1`

The above setting will load only 1 level of categories in your Explorer, reducing the time needed to load Mosets Tree's back-end pages.
{/answer}

{question}How do I reorder my listing images?{/question}

{answer}
You can reorder the images by clicking and dragging the image and release. It's like drag-and-drop on your desktop.
{/answer}

{question}How do I enable the use of content plugins in listing's description?{/question}

{answer}
Mosets Tree allows you to use Joomla content plugins in your listings' description field. However this is disabled by default. To enable content plugin support, follow these steps:

1. Login to your site's the back-end.
2. Go to **Mosets Tree -> Custom Fields**
3. Click '_Description_' to edit the field.

Look for the parameter named "**Parse Content Plugin**" and set it to `Yes`. Click '_Save_' to save the field.
{/answer}

{question}How do I import large amount of categories?{/question}

{answer}
MT Importer currently only allows you to mass import listings. You can't import or create categories using this tool. However, if you are comfortable with MySQL, you can import categories through MySQL or phpMyAdmin. Here's a sample SQL query you can use to import one category:

	INSERT INTO `jos_mt_cats` (`cat_name`, `alias`, `cat_desc`, `cat_parent`, `cat_published`, `cat_approved`) VALUES ('Category Name', 'category-alias', 'Description', 0, 1, 1);
	
Here are the details of the query:

- `cat_name` and `cat_desc` is the category name and category description respectively
- `alias` is a shorthand for the category, used in SEF URL. Alias preferably should contain only alphanumerics and dashes.
- `cat_parent` refers to the parent category of the category that is being added. If you're adding it to the root, set this to `0`. Since you need to have the cat_id before you can assign a '_cat_parent_', you'll need to create top level categories first and work your way down from there
- `cat_published` and `cat_approved` control the status of the category. Both should be set to `1` if you want to publish the category to front-end

Once you have done the '_INSERT_'s, login to your site's back-end and run this URL:
 
	http://www.example.com/administrator/index2.php?option=com_mtree&task=rebuild_tree

Replace '_www.example.com_' with your site's domain and path. This URL will build the '_lft_' and '_rgt_' column's value which is needed for use in Mosets Tree.
{/answer}

{question}How do I delete all listings in my directory?{/question}

{answer}

The quickest way to clear all listings in your directory is by running these SQL queries queries to your database:

	TRUNCATE TABLE `jos_mt_cl`;
	TRUNCATE TABLE `jos_mt_links`;
	TRUNCATE TABLE `jos_mt_cfvalues`;
	TRUNCATE TABLE `jos_mt_cfvalues_att`;
	TRUNCATE TABLE `jos_mt_favourites`;
	TRUNCATE TABLE `jos_mt_images`;
	TRUNCATE TABLE `jos_mt_links_associations`;
	TRUNCATE TABLE `jos_mt_reviews`;

The query above assume you have '_jos\_' as your database table prefix. Replace it with your site's database table prefix before running the queries.

If your listings contain images or attachments, go to these directories on your server and delete all files:

- **/media/com_mtree/images/listings/**
- **/media/com_mtree/attachments/**

> **Warning**: Running the above SQL queries will remove all listings in your directory. Make sure you know what you're doing before running it.

{/answer}

{question}Resetting hits, visits, votes and reviews.{/question}

{answer}
You can use the following SQL queries to reset Unique Pageviews, Website Clicks, Votes and Reviews. This is useful when you gathered these data during development phase and wish to reset it before deploying your directory to a live site:

	// Reset Unique Pageviews
	UPDATE jos_mt_links SET link_hits = 0;
	
	// Reset Website Clicks
	UPDATE jos_mt_links SET link_visited = 0;
	
	// Reset Votes
	UPDATE jos_mt_links SET link_votes = 0, link_rating = 0;
	DELETE FROM jos_mt_log WHERE log_type = 'vote';
	
	// Reset Reviews
	TRUNCATE TABLE jos_mt_reviews;
	DELETE FROM jos_mt_log WHERE log_type IN ('review','replyreview','votereview');

{/answer}

{question}How do I hide listings under categories in index page?{/question}

{answer}
Mosets Tree's default template '_kinabalu_', displays 3 listings below each root category in the index page. Here is how you can disable this:

1. Login to your site's back-end.
2. Go to **Mosets Tree > Templates > kinabalu**

Look for the parameter named 'Number of listings under top level cats.' and set it to `0`.
{/answer}

{question}Where do I manage reviews in Mosets Tree{/question}

{answer}
![Manage reviews in Mosets Tree](assets/img/content/manage-reviews.png)


The screenshot above shows where you can click to manage reviews in Mosets Tree's back-end. The link to this page is available on the same row where you have your listings, under "Reviews" column.
Clicking on this link will bring you to an interface where you can manage reviews for that particular listing.
{/answer}

{question}Does Mosets Tree accept payment for paid listings?{/question}

{answer}
Mosets Tree do not have support for paid listings at the moment. There are however third party addons that helps you to do this with Mosets Tree:

- [PayPlans](http://www.readybytes.net/payplans/)
- [Payments by Coding Mall](https://codingmall.com/products-mainmenu-8/90-payment-system-for-mosets-tree)

{/answer}

{question}How do I show breadcrumbs in Mosets Tree?{/question}

{answer}
Mosets Tree uses Joomla's Breadcrumbs (mod_breadcrumbs) module to show show its directory breadcrumbs. 

To publish the Breadcrumbs module:

1. Login to your site's back-end.
2. Go to: **Extensions -> Modules**
3. Click the "New" icon on top to create a new module instance.
4. Click to select "**Breadcrumbs**" module.
5. Fill in the module's "Title" and click "Save & Close".
 
{/answer}

{question}How do I change the default Google Maps marker in Mosets Tree?{/question}

{answer}
Mosets Tree allows you to show a Google Map with a marker in each listings. When you create a new listing, this marker is placed on a default location in Africa.

Follow the steps below to change this default location:

1. Login to your site's back-end.
2. Go to **<yoursite>/administrator/index.php?option=com_mtree&task=config&show=all**
3. Replace <yoursite> with your Joomla's site domain.
4. Click on the "**Features**" tab.
5. Look for the following 2 options in this tab: `map_default_lat` and `map_default_lng`. This is the default latitude and longitude value used to load the default marker position in Google Maps.
6. Enter new longitude and latitude values corresponding to the new default coordinate you want Google Maps to load.
7. Click the `Save` icon on top.

{/answer}

{question}How do I change the size of Google Maps in details view.{/question}

{answer}
The size of Google Maps in a listing details view are defined in this template file:

/components/com_mtree/templates/kinabalu/sub_map.tpl.php
in line 3 - 4:

		$width = '100%';
		$height = '300px';

Changing the value of the width and height will resize the Google Maps in listing details view.
{/answer}

{question}How do I increase the number of listings shown under each categories in index view?{/question}

{answer}
When viewing Mosets Tree's front page or any category pages that uses index page, 3 listings are shown below each category by default.

The number of listings shown here can be configure in your default Mosets Tree template:

1. Login to your site's the back-end/
2. Go to: **Mosets Tree -> Templates -> kinabalu**
3. Look for the parameter named "_Number of Listings shown in Index_".
4. This is the option that controls the number of listings shown under each category in index page. You can increase the value here to show more listings or all listings. You can also set this to "0" to show none.
5. Click "Save" icon on top to save your changes.

{/answer}

{question}How can I hide the message "No records found"?{/question}

{answer}
The message "_No records found_" appears when you browse to a Mosets Tree category that contains no listings.

If you do not intend to have listings in a category and wish to remove that message, here are the steps you can disable the message:

1. Login to your site's the back-end.
2. Go to: **Mosets Tree**
3. Browse to the category and edit it.
4. The right side of "Edit Category" page, there is an option called "**Show Listings**". Set this to `No`.
5. Click the "Save" button to save your changes.

This setting will hide listings from being shown in the category that you have edited. It will also hide the "No records found" message.
{/answer}


{question}How can I show category images in Mosets Tree's index?{/question}

{answer}
Categories image by default is shown only when you view the category page. You can configure your template to have the images to show in index page:

1. Login to your site's back-end.
2. Go to: **Mosets Tree > Templates > Kinabalu**
3. Look for the parameter named "**Show Categories**' images in Index" to `Yes`. This will display your category images in Index page.
4. Click the Save icon on top right of the page to save the changes.

{/answer}


{question}How to enable reCAPTCHA in Mosets Tree?{/question}

{answer}
### About CAPTCHA in Mosets Tree
Mosets Tree 3 introduces CAPTCHA support by making use of Joomla 2.5 new feature that supports CAPTCHA. This article will refer to the use of reCAPTCHA service as it comes as the default CAPTCHA plugin.

### Enable CAPTCHA in Joomla
To use CAPTCHA in Mosets Tree, you first need to enable reCAPTCHA in Joomla. You can refer to [this article in Joomla's documentation](https://docs.joomla.org/How_do_you_use_Recaptcha_in_Joomla%3F) on the instructions to do this. Once you have done this, you'll see reCAPTCHA appears in your site's front-end Register and Contact Us form.

### Enable CAPTCHA in Mosets Tree
CAPTCHA is enabled by default in Mosets Tree. You can confirm this by going to Mosets Tree's Configuration and check under "Captcha" tab. This tab contains 4 configuration that lets you control which form (Review, Contact Owner, Report Listing, Report Review and Recommend) to use CAPTCHA. Once you have enabled CAPTCHA in Joomla from above section, you will see CAPTCHA appearing in each of the Mosets Tree forms you've selected to use CAPTCHA.

### Enable CAPTCHA in Mosets Tree Add Listing form
To use CAPTCHA in Mosets Tree's front-end Add Listing form, create a new custom field based on "**Captcha**" field type. This is a new field type introduced in Mosets Tree 3 that allows you to use CAPTCHA in Add Listing form. A few things to note about Captcha field type in Mosets Tree:

- It only appears in front-end when adding a new listing.
- It does not appear when you editing existing listing.
- It does not appear in back-end.

Once published, it requires a correct answer to the Captcha test-challenge in order for a listing to save.

The answer is not saved to Mosets Tree.
{/answer}


{question}How to use Mosets Tree's 'Import Images' tool?{/question}

{answer}
MT Importer is the primary tool that helps you to mass import large number of listings using CSV formatted data. Because it accepts CSV format, only text-based data are supported. Non-text data such as images are not imported.

The new '**Image Images**' tool introduced in Mosets Tree 3, helps you to work around this issue by reading URLs from a custom field and convert it to a listing image.
This tool together with MT Importer enable you to import text-based data and images. There are 2 typical workflows when using this tool.

### Importing image URLs directly from CSV

This method is the easiest and most straightforward, but it requires that your script has the ability to export its images URL as part of their export routine. Once you've manage to prepare the CSV file, import them using the MT Importer tool and finally use the 'Import Images' tool to import the images to your listings.

### Importing image URLs through SQL query
An alternative way would be to programatically insert the URL value to by running the following SQL query to your database:


	INSERT INTO `jos_mt_cfvalues` (`cf_id`, `link_id`, `value`)
		VALUES (Custom Field ID,Listing ID,'http://example.com/path/image.jpg'); 

Note: Replace 'jos_' with your site's database table prefix, Custom Field ID with the ID of a weblink custom field and Listing ID with the ID of the listing that the image belongs to.

Once you've execute the queries, use the 'Import Images' tool to import the images to your listings.
{/answer}


{question}Why am I getting '404 error' when accessing Mosets Tree's Home?{/question}

{answer}

You may get a 404 error on your Mosets Tree directory's homepage after a database migration or restoration (done either manually or using third party backup and restore tool such as Akeeba Backup). This is due to Mosets Tree's Root directory's ID being changed from 0.

To fix this, simply login to your site's back-end and go to Mosets Tree Configuration. Click 'Save' and this will resolve the issue.
{/answer}


{question}Convert a custom field from Tag field type to Checkbox or Select Multiple field type{/question}

{answer}
Although you can change a custom field's field type from Tag to Checkbox, doing so directly from Mosets Tree's back-end UI may not be ideal due to the way data is stored in Tag and Checkbox field type. It may cause data loss when you or your users save their listings.

The following steps let you perform the conversion safely, without data loss:

1. Create a new custom field based on Checkbox and note its custom field ID. In this example, let say the custom field ID is 100. Also note down the custom field ID of your existing Tag custom field. Again, as an example, we assume this is 90.
2. Edit the new Checkbox field and populate its Elements input box with all possible values your users will enter. The tricky part here is knowing what your users has already entered and make sure that value is available as elements too. If a value that has been entered by your user but not in the list of elements, the value will be lost when users save their listing in the future.

	Each elements are separated by the bar character |.

	If you have access to MySQL or phpMyAdmin, you can perform the following query to return all values saved by your users, so that you know what to populate in the Elements box:

	SELECT * FROM `jos_mt_cfvalues` WHERE `cf_id` = '90';

	Note: replace jos_ with the database table prefix your site uses.

3. Now that you have the new Checkbox field ready, it's time to copy the data from your existing Tag custom field to it. Run the following SQL query:

		INSERT INTO jos_mt_cfvalues (`cf_id`, `link_id`, `value`) SELECT '100', `link_id`, REPLACE(REPLACE(`value`,', ',','),',','|') FROM jos_mt_cfvalues WHERE `cf_id` = 90;

Once you've perform the steps above, test the new Checkbox field to make sure the values are properly converted from your Tag field. You can then unpublish and eventually remove the old Tag custom field.

### Additional Notes
The steps above is applicable to converting your custom fields from Tag field type to Checkbox or Select Multiple.
{/answer}


{question}"Table '***.#__mt_config' doesn't exist SQL=SELECT value FROM #__mt_config WHERE varname ='version' LIMIT 1 " error appears when installing Mosets Tree{/question}

{answer}
### Symptom
When attempting to install Mosets Tree, you receive the following error message in Extension Manager:

	Table '***.#__mt_config' doesn't exist SQL=SELECT value FROM #__mt_config WHERE varname ='version' LIMIT 1
	
### Resolution

The error appears because Mosets Tree detects that you have prior installation of Mosets Tree that still exists in your server. To resolve this, remove the following directories from your server:

- **/components/com_mtree	**
- **/administrator/components/com_mtree**

Once you've removed the directories above, attempt to install Mosets Tree again.
{/answer}


{question}How to uninstall Mosets Tree?{/question}

{answer}
Follow these steps to fully uninstall Mosets Tree from your Joomla website.

1. Login to your Joomla site's back-end.
2. Go to: **Extensions -> Manage -> Manage**
3. Search for "Mosets Tree Package"
4. Toggle the checkbox for "Mosets Tree Package" and click "Uninstall"

> **Warning**: Uninstalling Mosets Tree will remove all Mosets Tree extensions, listings, categories and their associated fields, images and attachments. This action is not reversible.
{/answer}


{question}What are 'Related Categories'?{/question}

{answer}
'Related Categories' allows you to select one or more categories that are related to a current category. It allows you to expose additional categories to users browsing the current category.

'Related Categories' does not offer any relationship between categories, other than displaying links to it.
{/answer}


{question}Creating subheaders between fields{/question}

{answer}
Mosets Tree allows you to create unlimited number of fields to be used with your listings. It is sometimes useful to add subheaders in between fields to visually group a set of related fields together. This article shows how you can do this by adding a few CSS rules.

The following 2 instructions show how to add a subheader called 'Useful Link(s)' on top of the 'Website' field. To target 'Website', we use its custom field ID, 12, in our CSS rules. If you're targetting another field (ie: adding subheader above a different field), you can find out its field ID through your browser's Inspector or Mosets Tree's back-end.

### Adding subheader to listing details view

Add the following CSS rules to your site's CSS file:

	#field_12 {
		display: block;
		width: 98%;
	}
	#field_12:before {
		content: "Useful Link(s)";
		display: block;
		font-weight: bold;
		margin-top: 2em;
	}

### Adding subheader to front-end Add Listing form

	#cf12 {
	display: block;
	}
	
	#input_12:before {
	content: "Useful Link(s)";
	}

{/answer}


{question}Using custom field values in listing titles{/question}

{answer}
Mosets Tree uses listing names as page titles. This article shows how you can make a simple core modification to Mosets Tree's source codes to use one or more custom fields data in your listing title.

> **Note**: The steps below involve modifying a core Mosets Tree file. These modifications will be removed and overwritten when you upgrade Mosets Tree. This should only be performed if you're experienced with Joomla and PHP.
 
1. Edit this file: /components/com_mtree/mtree.php
2. Look for the following codes near line 2353:

		setTitle(JText::sprintf( 'COM_MTREE_PAGE_TITLE_VIEWLINK', $link->link_name ), null, $link_id);

3. Replace the line above with the following codes:

		// $cf_ids_for_title holds an array of fields ID to used in listing
		// title. ID 1 refers to listing name.
		$cf_ids_for_title = array(1, 41, 54);
		
		// $title_parameters contains an array of parameters to be passed to
		// JText::sprintf. Edit the line below to control how and where to
		// output each custom fields.
		$title_parameters[] = 'Your custom title - %s - %s - %s';
		
		foreach($cf_ids_for_title AS $cf_id )
		{
			$tmp  = $fields->getFieldById($cf_id);
			if( !is_null($tmp) )
			{
				$title_parameters[] = $tmp->getValue();
			}
		}
		
		// Output the title
		setTitle( call_user_func_array(array('JText','sprintf'), $title_parameters ));

4. `$cf_ids_for_title` holds an array of custom fields ID that you want to use in your title. In the example above, we have the listing name (ID: 1) and two custom fields, represented by ID 41 and 54. Remove and add additional field IDs as needed here.
5. The first assignment for `$title_parameters` controls how to output/arrange your static text and custom field values. Each of the %s specifier represents your field value. You can refer to PHP's sprintf documentation for more information.

This instruction is based on Mosets Tree 3.5.6, but it should work on any recent versions of Mosets Tree from version 2.1 up.

{/answer}

{question}Removing 'Add your listing here' link{/question}

{answer}
'Add your listing here' is added to each category's page to allow users to submit listings to your directory.

To remove this link in a category, edit the category in Mosets Tree's back-end. To the right of the page, you'll find an option called 'Allow listing submission'. Set this to 'No'. This will disable listing submission in front-end for that particular category and remove the 'Add your listing here' link.
{/answer}