# Migration Guide


This article guides you through the process of moving your Mosets Tree directory from an existing site to another newly installed Mosets Tree directory. 

This migration will copy all Mosets Tree data, including listings, categories, fields, images, attachments and templates from your existing directory to your new directory.

## Requirements

- Both the existing and the new directory must be up-to-date and running the same version of Mosets Tree. We will be using Mosets Tree {{version}} in our example here.
- The new directory should be a newly installed Mosets Tree running the latest version of Mosets Tree.

## Let's Start

Data in Mosets Tree are stored in the following locations:

- MySQL database tables with `#__mt_*` prefix.
- `/components/com_mtree/templates/*`
- `/media/com_mtree/attachments/*`
- `/media/com_mtree/images/listings/*`
- `/media/com_mtree/images/cats/*`

To migrate the data, all you need to do is copy the data above to your new directory. 

### MySQL Database

You can use your favourite MySQL database client such as phpMyAdmin to copy your Mosets Tree data from your existing directory's database to your new site.

To do this, select all Mosets Tree database tables that start with `#__mt_*` prefix (replace `#__` with your Joomla database table prefix. You can check this in your Joomla's Global Configuration) and select "**Export**".

Be sure to export the **structure and data**, and select to add the `DROP TABLE` statement.
 
 Once you've exported the database, proceed to run the SQL file on your new directory's database. This will replace all the default Mosets Tree data on your new directory with your existing directory's data.
 
 
### Files
 
To migrate Mosets Tree's files, use your favourite FTP program to copy all the folder and files inside each of these paths to the new site in the same locations: 

- `/components/com_mtree/templates/*`
- `/media/com_mtree/attachments/*`
- `/media/com_mtree/images/listings/*`
- `/media/com_mtree/images/cats/*`

## Completion

To complete the migration, login to your new site's back-end and go to Mosets Tree's Configuration and save it. This will let Mosets Tree run some basic housekeeping to make sure everything is in order. 

