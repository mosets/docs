# Installation

- [Server Requirements]({{version}}/installation#requirements)
- [Installing Mosets Tree]({{version}}/installation#install)
- [Accessing Mosets Tree Back-end]({{version}}/installation#back-end)
- [Publish Mosets Tree to Front-end]({{version}}/installation#publish-to-front-end)
- [Frequently Asked Question]({{version}}/installation#faq)

## Server Requirements {#requirements}

Mosets Tree has a few basic server requirements:

- Joomla >= 3.4
- PHP = 5.3.10+, 5.4.x, 5.5.x, 5.6.x, 7.0.x
- MySQL >= 5.1
- Apache >= 2.0
- GD Library >= 2.0

If your site runs on Joomla 3.4 and above, chances are your server can run Mosets Tree.

## Installing Mosets Tree {#install}

Installation of Mosets Tree requires you to install a single package file that you receive when you purchase Mosets Tree. You can also download the latest version of Mosets Tree package from your [Mosets account](http://www.mosets.com/login/). The package includes all the modules, plugins and component that comes with Mosets Tree.

To install:

1. Login to your Joomla's administrator back-end.
2. Goto "**Extensions -> Manage -> Install**".
3. Click "**Browse...**" to select "`pkg_mtree-{{version}}.x.zip`" from your computer.
4. Click "**Upload & Install**" to start the installation.

If your installation is successful, you will see the message "_Installing package was successful._".

## Accessing Mosets Tree Back-end {#access-back-end}

To access Mosets Tree's back-end, go to "**Components -> Mosets Tree**" from your admin menu.

## Publish Mosets Tree to Front-end {#publish-to-front-end}

You need to publish Mosets Tree to front-end in order for your user to be able to access your directory. You do this by creating a "Menu Item" for Mosets Tree's Home:

1. Go to "**Menus -> Main Menu -> Add New Menu Item**"
2. Click the '**Select**' button and select '**Mosets Tree**' > '**Home**' link from the modal dialog.
3. Fill in the '**Menu Title**' field and leave other field as default.
4. Click '**Save**' to save the menu.

You have successfully publish Mosets Tree to your Joomla website. A link for Mosets Tree is now available in front-end under your Main Menu module.

## Frequently Asked Question {#faq}

{question}Which PHP version should I use?{/question}
{answer}
Although both Joomla and Mosets specify PHP 5.3.10 as the minimum requirement, it is an [End-of-life](http://php.net/supported-versions.php) (EOL) version that is not supported by PHP project any more.

PHP 5.6 is the recommended version because it currently has active support and is not estimated to be EOL'd until 28 Aug 2017.
{/answer}