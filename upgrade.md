# Upgrade

 - [Introduction]({{version}}/upgrade#intro)
 - [Compatibility With Joomla]({{version}}/upgrade#compatibility-with-joomla)
 - [Upgrading From 2.0 To 2.1.12]({{version}}/upgrade#from-20-to-21)
 - [Upgrading From 2.1 To 2.2.6]({{version}}/upgrade#from-21-to-22)
 - [Upgrading From 2.2 To 3.0]({{version}}/upgrade#from-22-to-30)
 - [Upgrading From 3.0 To 3.9]({{version}}/upgrade#from-30-to-39)
 - [Upgrading To {{version}}]({{version}}/upgrade#to-39)
 - [Database Schema Updates]({{version}}/upgrade#db-schema)
 - [Frequently Asked Questions]({{version}}/upgrade#faqs)

## Introduction {#intro}

This article documents the process involved in upgrading Mosets Tree.

If you're running version 2.2 or later, upgrading to the next subsequent version is very straight forward because you only need to install the subsequent version over your existing Mosets Tree installation. This will update all Mosets Tree files and database table schema while retaining your existing data on your directory.

If you are few version behind the latest version, upgrading to the latest version requires you to perform multi-steps upgrade. For example, if you're currently running 2.0 on Joomla 1.0 and wish to upgrade to run {{version}} on Joomla 3.7, these are the steps to upgrade:

1. Upgrade to Joomla 1.5.
2. [Upgrade Mosets Tree 2.0 to 2.1.12]({{version}}/upgrade#from-20-to-21)
3. Upgrade to Joomla 2.5
4. [Upgrade Mosets Tree 2.1 to 2.2.6]({{version}}/upgrade#from-21-to-22)
5. [Upgrade Mosets Tree 2.2 to 3.0.13]({{version}}/upgrade#from-22-to-30)
6. Upgrade to Joomla 3.7
7. [Upgrading From 3.0 To 3.9]({{version}}/upgrade#from-30-to-39)

You can also refer to the steps above if you are upgrading from other version. For example, if you're upgrading from 2.2, you can start with Step 5 above.

{question}Can I just copy database tables to a new version of Mosets Tree to upgrade?{/question}
{answer}
No. The proper way to upgrade is by installing a newer version over your existing Mosets Tree or by following the multi-steps upgrade as described above.
{/answer}

## Compatibility With Joomla {#compatibility-with-joomla}
Use the information below to determine the latest version of Mosets Tree you can run on each major version of Joomla.

<style>
	.compatibility-with-joomla th, .compatibility-with-joomla td {
	  border:1px solid #CCC;
	  padding: 10px 20px;
	}
</style>
<div class="compatibility-with-joomla" markdown="1">
Joomla version | Mosets Tree version
---------------|---------------
Joomla 1.0 | Mosets Tree 2.0.9
Joomla 1.5 | Mosets Tree 2.1.12
Joomla 2.5 | Mosets Tree 2.2.6 & 3.0.13
Joomla 3.3 | Mosets Tree 3.5.9
Joomla 3.4 | Mosets Tree 3.6 & 3.7
Joomla 3.5 | Mosets Tree 3.8
Joomla 3.6 | Mosets Tree 3.8 & 3.9
Joomla 3.7 | Mosets Tree 3.9
</div>

## Upgrading From 2.0 To 2.1.12 {#from-20-to-21}

This section is intended for Mosets Tree users who wish to upgrade from Mosets Tree 2.0.x (running on Joomla 1.0) to Mosets Tree 2.1.12 (running on Joomla 1.5).

### Requirements
You need to be running on Joomla 1.5 and Mosets Tree 2.0. If you're still on Joomla 1.0, please upgrade. You can learn more about the **Joomla 1.0 -> 1.5** upgrade procedure at [Joomla documentation](https://docs.joomla.org/J1.5:Migrating_from_1.0.x_to_1.5_Stable) site.

### Preparations
Download `com_mtree-2.1.12.tar.gz` from your Mosets account. You need to have an active subscription in order to be able to download it.

Extract all files from `com_mtree-2.1.12.tar.gz` to your computer. You will find 3 directories named `administrator`, `components` and `language`. These directories mapped directly to your Joomla 1.5 installation.

### Upgrade
To upgrade, all you need to do is upload the 3 directories to the root of your Joomla site, overwriting existing Mosets Tree files present in those directories.

If you have modified any MT template file at `/components/com_mtree/m2`, please back-up those files as the upload will overwrite your changes.

Once you're done with the upload, remove these files:

- `/components/com_mtree/attachment.php`
- `/components/com_mtree/js/interface.js`
- `/components/com_mtree/language` (entire directory)

Finally, log in to your site's back-end and run the following URL:

	<yoursite>/administrator/index.php?option=com_mtree&task=upgrade

This will move your existing attachments from database to file system and update MT's table schema.

### Upgrading Mosets Tree modules
All modules in 2.1 has been rewritten for Joomla 1.5. You need to uninstall existing 2.0 modules and reinstall with the newer version. You will lose the modules' parameter setting when you uninstall them. These parameter settings have to be re-configured after they have been reinstalled.

### Upgrade completed
If you've reached this point, congratulation. Your upgrade has completed. You're now running Mosets Tree 2.1.12 on Joomla 1.5.

## Upgrading From 2.1 To 2.2.6 {#from-21-to-22}

This section shows how you can migrate your data from Mosets Tree 2.1.x running on Joomla 1.5 to Mosets Tree 2.2 running on Joomla 2.5.

Mosets Tree 2.1 and 2.2 shares the same database and file structures, therefore the migration can be done simply by moving Mosets Tree 2.1 data over to your new site running Mosets Tree 2.2:

1. On your new Joomla 2.5 site, install the latest version of Mosets Tree 2.2.
2. Remove all `jos_mt_*` tables from your new site's database. This is to make way for your original data from your existing old site.
3. Move all `jos_mt_*` tables from old site to new site's database by exporting all Mosets Tree tables (tables that starts with `jos_mt_` prefix) from your old site and import it back to your new site's database.
4. If you have images uploaded to your old site, migrate these directories over to your new site:
- `/components/com_mtree/img/listings/m/`
- `/components/com_mtree/img/listings/o/`
- `/components/com_mtree/img/listings/s/`
- `/components/com_mtree/img/cats/m/`
- `/components/com_mtree/img/cats/o/`
- `/components/com_mtree/img/cats/s/`
5. If you have attachments from your old site, migrate this directory over to your new site:
- `/components/com_mtree/attachments/`
6. If you have any non-default templates in Mosets Tree, migrate the template directories over to your new site at:
- `/components/com_mtree/templates/`
7. Login to your new site's back-end and go to this URL:

		<yoursite>/administrator/index.php?option=com_mtree&task=upgrade

### Upgrade completed
If you've reached this point, congratulation. Your upgrade has completed. You're now running Mosets Tree 2.2 on Joomla 2.5.

## Upgrading From 2.2 To 3.0 {#from-22-to-30}
Both Mosets Tree 2.2 and 3.0 runs on Joomla 2.5, therefore the upgrade is very straightforward.

If you're running Mosets Tree 2.2, all you need to do to upgrade to 3.0 is by installing Mosets Tree 3.0.13's package. `pkg_mtree-3.0.13.zip` to your Joomla 2.5 site.

> **Note**: At this point, you have Mosets Tree 3.0.13 running on Joomla 2.5. 

 If your intention is to migrate your Mosets Tree data to a Joomla 3.7 site running Mosets Tree {{version}}.x, you can follow the [migration instructions]({{version}}/migration-guide) to migrate your existing data from Mosets Tree 3.0.13 site to your new Mosets Tree {{version}} site. Once you've completed the migration, head on to [Database Schema Updates]({{version}}/upgrade#db-schema) and execute the queries specified there to bring your newly migrated data up-to-date with Mosets Tree's latest version schema.
 
> A couple of notes:
> - In the migration instruction, you can safely ignore the requirement where you need both sites to be on the same version.
> - As part of the migration, it mentions that you need to migrate Mosets Tree templates located at this path: `/components/com_mtree/templates/*`. You can skip this path so that your new site will use Mosets Tree 3.9's default `kinabalu` template. This is so that you can enjoy some of the new features introduced in Mosets Tree 3.5 and later.  

## Upgrading From 3.0 To 3.9 {#from-30-to-39}
If you're running Mosets Tree 3.0, you first need to upgrade your Joomla site from Joomla 2.5 to Joomla 3.7.

Once you’ve done that, the upgrade from MT 3.0 to 3.9 is again very straightforward, by installing the latest version of Mosets Tree 3.9 package, `pkg_mtree-3.9.x.zip`.

The following files are no longer used or have been moved to a new location. Remove these files:
- `/modules/mod_mt_tagcloud/css`
- `/administrator/components/com_mtree/models/listing.xml`
- `/language/en-GB/en-GB.fld_mfile.ini`

## Upgrading To {{version}} {#to-39}
This section shows how you can upgrade Mosets Tree from earlier version of 3.9.x to the latest version.

### Requirement
This upgrade requires Joomla! 3.6 and Mosets Tree 3.9.x.

### Full site backup
It is recommended that you perform a full site backup (files and database) before proceeding with the following upgrade.

### Upgrading through Joomla's back-end interface
The steps to upgrade from Mosets Tree 3.x to the latest version of Mosets Tree 3.9 are the same as installing a new extension. This method of upgrading will overwrite all Mosets Tree files including its template files. If you have done any template modification, back-up those files before you begin the upgrade. Mosets Tree templates files are located at:

- `/components/com_mtree/templates/kinabalu/`

1. Download the latest package for Mosets Tree 3.9.x. This is the same package you use to install Mosets Tree 3.9 on a new Joomla site, but here, we are going to use this to upgrade your copy of Mosets Tree 3.6.x to 3.9.x.
2. Log in to your site's back-end and go to:
	1. Goto "**Extensions -> Extension Manager**"
	2. Click "**Browse...**" to select "pkg_mtree-3.9.x.zip" from your computer.
	3. Click "**Upload & Install**" to start the upgrade.
	4. If the upgrade is successful, you will see a "_Installing package was successful._" message.
3. If you have backed up your modified template files prior to the upgrade, restore these files, replacing the ones that have been replace by the upgrade.

### Upgrade completed
If you've reached this point, congratulation. Your upgrade has completed. You're now running the latest version of Mosets Tree 3.9 on Joomla 3.7.

## Database Schema Updates {#db-schema}

Starting with 3.0.11, you can migrate your Mosets Tree database tables to another site running a later version of Mosets Tree, without going through the multi-steps upgrade outlined above. Once you've moved the database tables to your new site, you need to run the SQL queries listed below.

The SQL queries below will update Mosets Tree's database table schema from 3.0.11 to Mosets Tree version {{version}} schema.

If you're not running on Mosets Tree 3.0.11, you must upgrade to this version or later before you can run the SQL queries.

To run these SQL queries, replace `#__` with your database table prefix. You can find this in Joomla's Global Configuration.

```sql

############################
# Mosets Tree version 3.5.0
DELETE FROM `#__mt_config` WHERE `varname` IN ('relative_path_to_js_library');
UPDATE `#__mt_config` SET `configcode` = 'text' WHERE `varname` = 'linkchecker_num_of_links';

############################
# Mosets Tree version 3.5.2
DELETE FROM `#__mt_config` WHERE `varname` IN ('load_js_framework_frontend');
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ( 'load_bootstrap_css', 'core', '1', '1', 'yesno', '0', '0', '0');

############################
# Mosets Tree version 3.5.4
ALTER TABLE `#__mt_links` CHANGE `price` `price` DOUBLE(12,2) NOT NULL DEFAULT '0.00';

############################
# Mosets Tree version 3.5.6
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ( 'demo_mode', 'core', '', '0', 'yesno', '0', '0', '0');

############################
# Mosets Tree version 3.5.8
ALTER TABLE `#__mt_links` ADD INDEX `link_created` (`link_created`);

############################
# Mosets Tree version 3.5.10
UPDATE `#__mt_fieldtypes` SET `ft_desc` = 'Audio Player allows users to upload audio files and play the music from within the listing page. Provides basic playback options such as play, pause and volume control. Made possible by http://www.1pixelout.net/code/audio-player-wordpress-plugin/.' WHERE `field_type` = 'audioplayer';

############################
# Mosets Tree version 3.5.11
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ( 'fe_num_of_related', 'listing', '', '50', 'text', '6800', '0', '0');

############################
# Mosets Tree version 3.5.13
# No upgrade queries.

############################
# Mosets Tree version 3.6.0
DELETE FROM #__mt_config WHERE varname IN ('user_addcategory','user_addlisting','user_contact','user_recommend','user_report','user_report_review','user_rating','user_review');

INSERT IGNORE INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ( 'note_permission',  'main',  '',  '',  'note',  '11100',  '1',  '0'), ( 'link_to_configure_permission',  'main',  '',  '',  'label',  '11110',  '1',  '0'), ( 'listing_details_access_level', 'listing', '1', '1', 'access_level', '0', '1', '1'), ('category_view_access_level', 'main', '', '1', 'access_level', 450, 1, 1), ('schema_type', 'main', '', 'Thing', 'text', 460, 0, 1), ('load_font_awesome', 'core', '1', '1', 'yesno', 0, 0, 0), ('show_share_with_email', 'sharing', '1', '1', 'yesno', 100, 1, 1), ('show_share_with_facebook', 'sharing', '1', '1', 'yesno', 200, 1, 1), ('show_share_with_twitter', 'sharing', '1', '1', 'yesno', 300, 1, 1), ('show_share_with_pinterest', 'sharing', '1', '1', 'yesno', 400, 1, 1), ('show_share_with_googleplus', 'sharing', '1', '1', 'yesno', 500, 1, 1), ('note_facebook_like', 'sharing', '', '', 'note', 1000, 1, 1), ('use_facebook_like', 'sharing', '1', '1', 'yesno', 1010, 1, 1),  ('note_pinterest_on_hover_pin', 'sharing', '', '', 'note', '1100', '1', '1'), ('use_pinterest_on_hover_pin', 'sharing', '1', '1', 'yesno', '1110', '1', '1'), ('note_twitter_card', 'sharing', '', '', 'note', '1200', '1', '0'), ('use_twitter_card', 'sharing', '1', '1', 'yesno', '1210', '1', '0'), ('twitter_site', 'sharing', '', '', 'text', '1220', '1', '0'), ('twitter_card_type', 'sharing', 'summary', 'summary', 'text', '1230', '1', '0');

INSERT IGNORE INTO `#__mt_configgroup` (`groupname`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('sharing', '660', '1', '1');

ALTER TABLE `#__mt_customfields` ADD access_level INT NOT NULL DEFAULT '1' AFTER published;

ALTER TABLE `#__mt_links` ADD mobile VARCHAR(255) NOT NULL DEFAULT '' AFTER telephone;

ALTER TABLE `#__mt_links` ADD contactperson VARCHAR(255) NOT NULL DEFAULT '' AFTER postcode;

ALTER TABLE `#__mt_links` ADD `date` DATE NOT NULL AFTER website;

ALTER TABLE `#__mt_links` ADD `year` INT(11) NOT NULL AFTER website;

INSERT IGNORE INTO `#__mt_customfields` (`field_type`, `caption`, `alias`, `default_value`, `size`, `field_elements`, `prefix_text_mod`, `suffix_text_mod`, `prefix_text_display`, `suffix_text_display`, `placeholder_text`, `cat_id`, `ordering`, `hidden`, `required_field`, `published`, `access_level`, `hide_caption`, `advanced_search`, `simple_search`, `tag_search`, `filter_search`, `details_view`, `summary_view`, `search_caption`, `params`, `iscore`) VALUES ('corecontactperson', 'Contact Person', 'contact-person', '', 0, '', '', '', '', '', '', 0, 9, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, '', '', 1), ('coremobile', 'Mobile', 'mobile', '', 0, '', '', '', '', '', '', 0, 9, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, '', '', 1), ('coredate', 'Date', 'date', '', 0, '', '', '', '', '', '', 0, 9, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, '', '', 1), ('coreyear', 'Year Established', 'year', '', 0, '', '', '', '', '', '', 0, 9, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, '', '', 1);

INSERT IGNORE INTO `#__assets` (`parent_id`, `lft`, `rgt`, `level`, `name`, `title`, `rules`) VALUES (1, 0, 0, 1, 'com_mtree', 'com_mtree', '{\"core.admin\":[],\"core.manage\":[],\"mtree.listing.create\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.category.create\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.rate\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.review\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.contact\":{\"1\":1,\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.recommend\":{\"1\":1,\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.report\":{\"1\":1,\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.report_review\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.claim\":{\"6\":1,\"2\":1,\"8\":1}}') ON DUPLICATE KEY UPDATE rules = '{\"core.admin\":[],\"core.manage\":[],\"mtree.listing.create\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.category.create\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.rate\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.review\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.contact\":{\"1\":1,\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.recommend\":{\"1\":1,\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.report\":{\"1\":1,\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.report_review\":{\"6\":1,\"2\":1,\"8\":1},\"mtree.listing.claim\":{\"6\":1,\"2\":1,\"8\":1}}';

UPDATE `#__mt_fieldtypes` SET `field_type` = 'myear' WHERE `field_type` = 'year';

UPDATE `#__mt_customfields` SET `field_type` = 'myear' WHERE `field_type` = 'year';

############################
# Mosets Tree version 3.6.1
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ( 'prevent_rate_own_listing',  'ratingreview',  '1',  '1',  'yesno',  '1450',  '1',  '1'), ( 'prevent_review_own_listing',  'ratingreview',  '1',  '1',  'yesno',  '2750',  '1',  '1');

ALTER TABLE `#__mt_customfields` CHANGE `access_level` `view_access_level` INT(11)  NOT NULL  DEFAULT '1';

ALTER TABLE `#__mt_customfields` ADD `edit_access_level` INT(11)  NOT NULL  DEFAULT '1'  AFTER `view_access_level`;

INSERT IGNORE INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('show_share_with_linkedin', 'sharing', '1', '1', 'yesno', 600, 1, 1);

############################
# Mosets Tree version 3.6.2
UPDATE `#__assets` SET lft = 9999, rgt = 9999 WHERE name = 'com_mtree' AND lft = 0 AND rgt = 0 LIMIT 1;

############################
# Mosets Tree version 3.6.3
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ( 'use_captcha_recommend',  'captcha',  '0',  '0',  'yesno',  '5000',  '1',  '0');

############################
# Mosets Tree version 3.6.4
# No upgrade queries.

############################
# Mosets Tree version 3.6.5
UPDATE `#__mt_fieldtypes` SET `ft_caption` = 'Unique Pageviews' WHERE `field_type` = 'corehits';

UPDATE `#__mt_fieldtypes` SET `ft_caption` = 'Website Clicks' WHERE `field_type` = 'corevisited';

UPDATE `#__mt_config` SET `displayed` = '1' WHERE `varname` = 'limit_max_chars';

############################
# Mosets Tree version 3.6.6
INSERT INTO `#__mt_fieldtypes` (`field_type`, `ft_caption`, `ft_version`, `ft_website`, `ft_desc`, `use_elements`, `use_size`, `use_columns`, `use_placeholder`, `is_file`, `taggable`, `iscore`) VALUES ('vimeo', 'Vimeo', '1.0.0', '', '', 0, 1, 0, 0, 0, 0, 0);

############################
# Mosets Tree version 3.7.0
INSERT INTO `#__mt_fieldtypes` (`field_type`, `ft_caption`, `ft_version`, `ft_website`, `ft_desc`, `use_elements`, `use_size`, `use_columns`, `use_placeholder`, `is_file`, `taggable`, `iscore`) VALUES ('mtelephone', 'Telephone', '1.0.0', '', '', 0, 1, 0, 1, 0, 0, 0);

INSERT INTO `#__mt_fieldtypes` (`field_type`, `ft_caption`, `ft_version`, `ft_website`, `ft_desc`, `use_elements`, `use_size`, `use_columns`, `use_placeholder`, `is_file`, `taggable`, `iscore`) VALUES ('listings', 'Listings', '1.0.3', 'www.mosets.com', 'Allows you to select listings within your directory and show them as part of a listing.', 0, 0, 0, 0, 0, 0, 0);

INSERT INTO `#__mt_fieldtypes` (`field_type`, `ft_caption`, `ft_version`, `ft_website`, `ft_desc`, `use_elements`, `use_size`, `use_columns`, `use_placeholder`, `is_file`, `taggable`, `iscore`) VALUES ('multipledates', 'Multiple Dates', '1.0.2', 'www.mosets.com', 'Show multiple dates.', 0, 1, 0, 0, 0, 0, 0);

INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES  ('group_ids_authorised_to_create_listing', 'permission', '8', '8', 'user_groups', '13050', '1', '1'), ('group_ids_authorised_to_edit_listing', 'permission', '8', '8', 'user_groups', '13100', '1', '1'), ('group_ids_authorised_to_delete_listing', 'permission', '8', '8', 'user_groups', '13200', '1', '1');

INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('note_managers', 'permission', '', '', 'note', '13000', '1', '1');

INSERT INTO `#__mt_configgroup` (`groupname`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('permission', 200, 1, 1);

DELETE FROM `#__mt_config` WHERE `varname` IN ('note_permission');

UPDATE `#__mt_config` SET `groupname` = 'permission' WHERE `varname` = 'link_to_configure_permission';

UPDATE `#__mt_config` SET `displayed` = '1' WHERE `varname` = 'limit_min_chars';

UPDATE `#__mt_config` SET `configcode` = 'second_listing_order' WHERE `varname` = 'second_listing_order1';

INSERT IGNORE INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('show_previous_next_listing_in_listing_details', 'listing', '1', '1', 'yesno', '2550', '1', '1'), ('sef_adjacentlisting_next', 'sef', 'next-listing', 'next-listing', 'text', '1651', '1', '0'), ('sef_adjacentlisting_previous', 'sef', 'previous-listing', 'previous-listing', 'text', '1652', '1', '0'), ('rss_firstname', 'rss', '0', '0', 'yesno', '1075', '1', '1'), ('rss_lastname', 'rss', '0', '0', 'yesno', '1076', '1', '1'), ('rss_contactperson', 'rss', '0', '0', 'yesno', '1080', '1', '1'), ('rss_mobile', 'rss', '0', '0', 'yesno', '1090', '1', '1'), ('rss_date', 'rss', '0', '0', 'yesno', '1091', '1', '1'), ('rss_year', 'rss', '0', '0', 'yesno', '1092', '1', '1'), ('fe_num_of_random', 'listing', '20', '20', 'text', '6710', '1', '1'), ('random_listings_shuffle_frequency', 'listing', '3600', '3600', 'random_listings_shuffle_frequency', '3530', '1', '0'), ('sef_random', 'sef', 'random', 'random', 'text', '2650', '1', '0'), ('fe_num_of_owners', 'listing', '', '20', 'text', '6730', '0', '0'), ('search_completion_max_listings', 'search', '', '8', 'text', '2300', '0', '0'), ('max_num_of_listings_per_user', 'listing', '', '0', 'text', '3590', '1', '0'), ('show_add_listing_link', 'listing', '', '1', 'show_requirements', '3520', '1', '1');

ALTER TABLE `#__mt_links` ADD lastname VARCHAR(255) NOT NULL DEFAULT '' AFTER link_visited;

ALTER TABLE `#__mt_links` ADD firstname VARCHAR(255) NOT NULL DEFAULT '' AFTER link_visited;

INSERT IGNORE INTO `#__mt_customfields` (`field_type`, `caption`, `alias`, `default_value`, `size`, `field_elements`, `prefix_text_mod`, `suffix_text_mod`, `prefix_text_display`, `suffix_text_display`, `placeholder_text`, `cat_id`, `ordering`, `hidden`, `required_field`, `published`, `view_access_level`, `hide_caption`, `advanced_search`, `simple_search`, `tag_search`, `filter_search`, `details_view`, `summary_view`, `search_caption`, `params`, `iscore`) VALUES ('corefirstname', 'First Name', 'first-name', '', 0, '', '', '', '', '', '', 0, 9, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, '', '', 1), ('corelastname', 'Last Name', 'last-name', '', 0, '', '', '', '', '', '', 0, 9, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, '', '', 1);

ALTER TABLE `#__mt_customfields` ADD `shown_in_backend_listings_column` TINYINT(3)  UNSIGNED  NOT NULL  DEFAULT '0'  AFTER `edit_access_level`;

ALTER TABLE `#__mt_images` ADD INDEX `ordering` (`ordering`);

UPDATE `#__mt_customfields` SET `field_type` = 'mselectmultiple' WHERE `field_type` = 'selectmultiple';

INSERT INTO `#__mt_fieldtypes` (`field_type`, `ft_caption`, `ft_version`, `ft_website`, `ft_desc`, `use_elements`, `use_size`, `use_columns`, `use_placeholder`, `is_file`, `taggable`, `iscore`) VALUES ('mselectmultiple', 'Select Multiple', '1.0.0', 'www.mosets.com', 'Select Multiple field allows you to select one or more value in a multiple select list.', 1, 1, 0, 0, 0, 1, 0);

############################
# Mosets Tree version 3.7.1
UPDATE `#__mt_fieldtypes` SET use_placeholder = 1 WHERE field_type IN ('mselectmultiple', 'multipledates');

############################
# Mosets Tree version 3.8.0
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('all_listings_sort_by2', 'listing', 'none', 'none', 'sort2', 100, 1, 1), ('note_filter_search', 'search', '', '', 'note', '2400', '1', '1'), ('filter_show_keyword_search', 'search', '1', '1', 'yesno', '2500', '1', '1'), ('redirect_url_needapproval_addlisting', 'listing', '', '', 'text', '3640', '0', '1'), ('sef_attachment', 'sef', 'attachment', 'attachment', 'text', 250, 1, 0);

UPDATE `#__mt_config` SET `ordering` = '200' WHERE `varname` = 'all_listings_sort_by_options';

UPDATE `#__mt_fieldtypes` SET `use_elements` = '1' WHERE `field_type` = 'coreyear';

INSERT INTO `#__mt_fieldtypes` (`field_type`, `ft_caption`, `ft_version`, `ft_website`, `ft_desc`, `use_elements`, `use_size`, `use_columns`, `use_placeholder`, `is_file`, `taggable`, `iscore`) VALUES ('audioplayer2', 'Audio Player 2.0', '1.0.0', '', 'Audio Player allows users to upload audio files and play the music from within the listing page. Provides basic playback options such as play, pause and volumne control. Made possible by http://mediaelementjs.com/.', '0', '0', '0', '0', '1', '0', '0');

############################
# Mosets Tree version 3.8.1
# No upgrade queries.

############################
# Mosets Tree version 3.8.2
INSERT INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('attachments_noindex_nofollow', 'listing', '', '1', 'yesno', '3700', '0', '1');

############################
# Mosets Tree version 3.8.3
INSERT IGNORE INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('show_listingreviewsrss', 'rss', '1', '1', 'yesno', '250', '1', '1'), ('sef_rss_listingreviews', 'sef', 'listing-reviews', 'listing-reviews', 'text', '3650', '1', '0');

############################
# Mosets Tree version 3.8.4
# No upgrade queries.

############################
# Mosets Tree version 3.8.5
INSERT IGNORE INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('show_userfavouritesrss', 'rss', '1', '1', 'yesno', '260', '1', '1'), ('sef_rss_userfavourites', 'sef', 'user-favourites', 'user-favourites', 'text', '3660', '1', '0'), ('fe_num_of_rss_favourite', 'listing', '100', '100', 'text', '6900', '0', '0');

############################
# Mosets Tree version 3.8.6
# No upgrade queries.

############################
# Mosets Tree version 3.9.0
UPDATE #__mt_config SET groupname = 'map' WHERE varname IN ('show_map', 'use_map', 'map_default_country', 'map_default_state', 'map_default_city', 'map_default_lat', 'map_default_lng', 'map_default_zoom');

DELETE FROM `#__mt_config` WHERE `varname` IN ('note_map', 'note_other_features');

INSERT IGNORE INTO `#__mt_configgroup` (`groupname`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('map', '475', '1', '1');

INSERT IGNORE INTO `#__mt_config` (`varname`, `groupname`, `value`, `default`, `configcode`, `ordering`, `displayed`, `overridable_by_category`) VALUES ('google_maps_api_key', 'map', '', '', 'text', '4110', '1', '0'), ('show_map_in_category_pages', 'map', '2', '2', 'yesno_default_shown_or_hidden', '4105', '1', '1'), ('show_map_in_index_pages', 'map', '2', '2', 'yesno_default_shown_or_hidden', 4106, 1, 1), ('show_map_in_search_results_pages', 'map', '2', '2', 'yesno_default_shown_or_hidden', 4107, 1, 1), ('show_map_in_top_listings_pages', 'map', '2', '2', 'yesno_default_shown_or_hidden', 4108, 1, 1), ('show_map_in_list_all_pages', 'map', '2', '2', 'yesno_default_shown_or_hidden', 4109, 1, 1), ('google_maps_type_ids', 'map', 'ROADMAP|SATELLITE|HYBRID|TERRAIN', 'ROADMAP|SATELLITE|HYBRID|TERRAIN', 'map_type_ids', '4115', '1', '0'), ('google_maps_styled_map_style_array', 'map', '', '', 'text', 4120, 1, 0), ('google_maps_type_id', 'map', 'ROADMAP', 'ROADMAP', 'map_type_id', 4116, 1, 0), ('google_maps_marker_image', 'map', '', '/media/com_mtree/images/map-marker-icon-32x32.png', 'text', 4125, 0, 1),('note_listing_expiration', 'listing', '', '', 'note', 6750, 1, 1),('allow_listing_renewal', 'listing', '0', '0', 'yesno', '6820', '1', '0'),('days_remaining_to_renew', 'listing', '30', '30', 'text', '6825', '1', '0'),('show_avl_search', 'search', '0', '0', 'yesno', 2600, 0, 1),('allow_json_output', 'main', '0', '0', 'yesno', 11500, 1, 0);

############################
# Mosets Tree version 3.9.1
# No upgrade queries.

############################
# Mosets Tree version 3.9.2
# No upgrade queries.

############################
# Mosets Tree version 3.9.3
# No upgrade queries.

############################
# Mosets Tree version 3.9.4
# No upgrade queries.

############################
# Update Mosets Tree Version number
UPDATE  `#__mt_config` SET  `value` =  '3.9.4' WHERE  `#__mt_config`.`varname` =  'version';
UPDATE  `#__mt_config` SET  `value` =  '3' WHERE  `#__mt_config`.`varname` =  'major_version';
UPDATE  `#__mt_config` SET  `value` =  '9' WHERE  `#__mt_config`.`varname` =  'minor_version';
UPDATE  `#__mt_config` SET  `value` =  '4' WHERE  `#__mt_config`.`varname` =  'dev_version';
```

## Frequently Asked Questions{#faqs}

{question}How to update Mosets Tree 2.1 (running on Joomla 1.5) to Mosets Tree 3.9 (Joomla 3.7)?{/question}

{answer}
These are the steps you need to perform to incrementally upgrade from Mosets Tree 2.1 to 3.9:

1. **Migrate Mosets Tree 2.1(Joomla 1.5) to Mosets Tree 2.2 (Joomla 2.5)**

	[You can refer to the full migration instruction here.](https://docs.mosets.com/{{version}}/upgrade#from-21-to-22)
	
2. **Update Mosets Tree 2.2 to Mosets Tree 3.0 (Joomla 2.5)**

	This update is straightforward as it involves installing MT 3.0 package to your Joomla 2.5 site.

3. **Update Mosets Tree 3.0 to Mosets Tree 3.9 (Joomla 3.7)**

	Once you've upgraded your Joomla site to Joomla 3.7, the upgrade from MT 3.0 to 3.9 is again straightforward like above, by installing the latest version of Mosets Tree 3.9 package.

{/answer}
