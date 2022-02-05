# Upgrade

- [Introduction]({{version}}/upgrade#intro)
- [Upgrade to Joomla 4.0]({{version}}/upgrade#to-joomla-4)
- [Upgrade Mosets Tree 3.10 to 4.0]({{version}}/upgrade#from-310-to-40)


## Introduction {#intro}

This article documents the process involved in upgrading from Mosets Tree 3.10 running on Joomla 3 to Mosets Tree 4.0 running on Joomla 4.

If you're running an earlier version of Mosets Tree, please refer to [Mosets Tree 3.10 Upgrade](3.10/upgrade) page.

This upgrade involves 2 steps:

1. [Upgrade to Joomla 4.0]({{version}}/upgrade#to-joomla-4)
2. [Upgrade Mosets Tree 3.10 to 4.0]({{version}}/upgrade#from-310-to-40)

## Upgrade to Joomla 4.0 {#to-joomla-4}

The first thing you need to do before upgrading Mosets Tree is to upgrade your Joomla website to Joomla 4.0. If you've been keeping your Joomla website up-to-date, the upgrade from Joomla 3.10 to 4.0 can be done entirely through Joomla's back-end via the Joomla Update extension. 

The update extension will walk you through the pre-update checks and then start your Joomla update process.

You can visit Joomla's documentation on detailed step-by-step guide on [upgrading to Joomla 4.0](https://docs.joomla.org/Joomla_3.x_to_4.x_Step_by_Step_Migration).

## Upgrade Mosets Tree 3.10 to 4.0 {#from-310-to-40}

Download the Mosets Tree 4.0 package file from your [Mosets Account ](https://www.mosets.com/login). This will be the file you use to upgrade your Mosets Tree installation on your newly upgraded Joomla 4 website. 

To upgrade:

1. Login to your Joomla's administrator back-end.
2. Goto "**System -> Install -> Extensions**".
3. Under "Upload Package File", Click "**Or browse for file**" to select "`pkg_mtree-{{version}}.x.zip`" from your computer.

If your upgrade is successful, you will see the message "_Installation of the package was successful._".
