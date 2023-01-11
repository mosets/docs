# Migration Guide

- [Migrating from Joomla 3.x]({{version}}/migration-guide#from-joomla-3)
- [Migrating from Joomla 4]({{version}}/migration-guide#from-joomla-4)

The guides here show how you can migrate all your Mosets Tree data from Joomla 3 or 4 to another Joomla 4 site. This Joomla 4 website can be an existing Joomla site or a freshly installed site. If you're looking to upgrade your Mosets Tree 3 running on Joomla 3 to Mosets Tree 4 running on Joomla 4, please refer to the [upgrade guide]({{version}}/upgrade).

## Migrating from Joomla 3.x {#from-joomla-3}

This section guides you through the process of moving your Mosets Tree directory from an existing site running Mosets Tree 3 on Joomla 3 to another newly installed Mosets Tree directory, running the same Mosets Tree version {{version}} on Joomla 4.

This migration will copy all Mosets Tree data, including listings, categories, fields, images, attachments and templates from your existing directory to your new directory.

1. Make sure you have installed a new copy of Mosets Tree {{version}}.x on your Joomla 4 site.
2. Migrate all your Mosets Tree tables from your old J3 site to the new J4 site. This will replace all the MT tables (#__mt_*) that were created during the fresh installation in Step 1. Be sure to update the database prefix during your table migration.

3. Run all the SQL files starting from 4_0_0.sql onwards:

        administrator/components/com_mtree/upgrade/4_0_0.sql
        administrator/components/com_mtree/upgrade/4_0_1.sql
        ...

    Be sure to replace all #__ with your site’s database table prefix.

4. If your old J3 sites has images and/or attachment, copy them over to your new site. These are located at these directories:

        /media/com_mtree/attachments/*
        /media/com_mtree/images/listings/*
        /media/com_mtree/images/cats/*

5. Your migration is complete.

## Migrating from Joomla 4.x {#from-joomla-4}
This section guides you through the process of moving your Mosets Tree directory from an existing site to another newly installed Mosets Tree directory, running the same Mosets Tree version {{version}}. 

This migration will copy all Mosets Tree data, including listings, categories, fields, images, attachments and templates from your existing directory to your new directory.

### Requirements

- Both the existing and the new directory must be up-to-date and running the same version of Mosets Tree. We will be using Mosets Tree {{version}} in our example here.
- The new directory should be a newly installed Mosets Tree running the latest version of Mosets Tree.

### Let's Start

Data in Mosets Tree are stored in the following locations:

- MySQL database tables with `#__mt_*` prefix.
- `/components/com_mtree/templates/*`
- `/media/com_mtree/attachments/*`
- `/media/com_mtree/images/listings/*`
- `/media/com_mtree/images/cats/*`

To migrate the data, all you need to do is copy the data above to your new directory. 

#### MySQL Database

You can use your favourite MySQL database client such as phpMyAdmin to copy your Mosets Tree data from your existing directory's database to your new site.

To do this, select all Mosets Tree database tables that start with `#__mt_*` prefix (replace `#__` with your Joomla database table prefix. You can check this in your Joomla's Global Configuration) and select "**Export**".

Be sure to export the **structure and data**, and select to add the `DROP TABLE` statement.
 
 Once you've exported the database, proceed to run the SQL file on your new directory's database. This will replace all the default Mosets Tree data on your new directory with your existing directory's data.
 
 
#### Files
 
To migrate Mosets Tree's files, use your favourite FTP program to copy all the folder and files inside each of these paths to the new site in the same locations: 

- `/components/com_mtree/templates/*`
- `/media/com_mtree/attachments/*`
- `/media/com_mtree/images/listings/*`
- `/media/com_mtree/images/cats/*`

### Completion

To complete the migration, login to your new site's back-end and go to Mosets Tree's Configuration and save it. This will let Mosets Tree run some basic housekeeping to make sure everything is in order. 
