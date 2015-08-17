# Upgrade

 - [Introduction]({{version}}/upgrade#intro)
 - [Compatibility With Joomla]({{version}}/upgrade#compatibility-with-joomla)
 - [Upgrading From 2.0 To 2.1.12]({{version}}/upgrade#from-20-to-21)
 - [Upgrading From 2.1 To 2.2.6]({{version}}/upgrade#from-21-to-22)
 - [Upgrading From 2.2 To 3.0]({{version}}/upgrade#from-22-to-30)
 - [Upgrading From 3.0 To 3.6]({{version}}/upgrade#from-30-to-36)
 - [Upgrading To 3.6]({{version}}/upgrade#to-36)

## Introduction {#intro}

This article documents the process involved in upgrading Mosets Tree.

If you're running version 2.2 or later, upgrading to the next subsequent version is very straight forward because you only need to install the subsequent version over your existing Mosets Tree installation. This will update all Mosets Tree files and database table schema while retaining your existing data on your directory.

If you are few version behind the latest version, upgrading to the latest version requires you to perform multi-steps upgrade. For example, if you're currently running 2.0 on Joomla 1.0 and wish to upgrade to run {{version}} on Joomla 3.4, these are the steps to upgrade:

1. Upgrade to Joomla 1.5.
2. [Upgrade Mosets Tree 2.0 to 2.1.12]({{version}}/upgrade#from-20-to-21)
3. Upgrade to Joomla 2.5
4. [Upgrade Mosets Tree 2.1 to 2.2.6]({{version}}/upgrade#from-21-to-22)
5. [Upgrade Mosets Tree 2.2 to 3.0.13]({{version}}/upgrade#from-22-to-30)
6. Upgrade to Joomla 3.4
7. [Upgrading From 3.0 To 3.6]({{version}}/upgrade#from-30-to-36)

You can also refer to the steps above if you are upgrading from other version. For example, if you're upgrading from 2.2, you can start with Step 5 above.

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
Joomla 3.4 | Mosets Tree 3.6
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
2. Remove all jos_mt_* tables from your new site's database. This is to make way for your original data from your existing old site.
3. Move all jos_mt_* tables from old site to new site's database by exporting all Mosets Tree tables (tables that starts with jos_mt_ prefix) from your old site and import it back to your new site's database.
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

## Upgrading From 3.0 To 3.6 {#from-30-to-36}
Once you’ve upgraded your Joomla site to Joomla 3.4, the upgrade from MT 3.0 to 3.6 is again very straightforward like above, by installing the latest version of Mosets Tree 3.6 package, `pkg_mtree-3.6.x.zip`.

The following files are no longer used or have been moved to a new location. Remove these files:
- `/modules/mod_mt_tagcloud/css`
- `/administrator/components/com_mtree/models/listing.xml`
- `/language/en-GB/en-GB.fld_mfile.ini`

## Upgrading To 3.6 {#to-36}
This section shows how you can upgrade Mosets Tree from earlier version of 3.6.x to the latest version.

### Requirement
This upgrade requires Joomla! 3.4 and Mosets Tree 3.6.x.

### Full site backup
It is recommended that you perform a full site backup (files and database) before proceeding with the following upgrade.

### Upgrading through Joomla's back-end interface
The steps to upgrade from Mosets Tree 3.x to the latest version of Mosets Tree 3.6 are the same as installing a new extension. This method of upgrading will overwrite all Mosets Tree files including its template files. If you have done any template modification, back-up those files before you begin the upgrade. Mosets Tree templates files are located at:

- `/components/com_mtree/templates/kinabalu/`

1. Download the latest package for Mosets Tree 3.6.x. This is the same package you use to install Mosets Tree 3.6 on a new Joomla site, but here, we are going to use this to upgrade your copy of Mosets Tree 3.6.x to 3.6.4.
2. Log in to your site's back-end and go to:
	1. Goto "**Extensions -> Extension Manager**"
	2. Click "**Browse...**" to select "pkg_mtree-3.6.x.zip" from your computer.
	3. Click "**Upload & Install**" to start the upgrade.
	4. If the upgrade is successful, you will see a "_Installing package was successful._" message.
3. If you have backed up your modified template files prior to the upgrade, restore these files, replacing the ones that have been replace by the upgrade.

### Upgrade completed
If you've reached this point, congratulation. Your upgrade has completed. You're now running the latest version of Mosets Tree 3.6 on Joomla 3.4.
