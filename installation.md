# Installation

- [Server Requirements]({{version}}/installation#requirements)
- [Installing Mosets Tree]({{version}}/installation#install)
- [Accessing Mosets Tree Back-end]({{version}}/installation#back-end)
- [Publish Mosets Tree to Front-end]({{version}}/installation#publish-to-front-end)
- [Frequently Asked Question]({{version}}/installation#faq)

## Server Requirements {#requirements}

Mosets Tree has a few basic server requirements:

- Joomla >= 4.0
- PHP >= 7.4
- MySQL >= 5.6
- GD Library >= 2.0

If your site runs on Joomla 4.0, chances are your server can run Mosets Tree.

## Installing Mosets Tree {#install}

Installation of Mosets Tree requires you to install a single package file that you receive when you purchase Mosets Tree. You can also download the latest version of Mosets Tree package from your [Mosets account](http://www.mosets.com/login/). The package includes all the modules, plugins and component that comes with Mosets Tree.

To install:

1. Login to your Joomla's administrator back-end.
2. Goto "**System -> Install -> Extensions**".
3. Under "Upload Package File", Click "**Or browse for file**" to select "`pkg_mtree-{{version}}.x.zip`" from your computer.

If your installation is successful, you will see the message "_Installation of the package was successful._".

## Accessing Mosets Tree Back-end {#access-back-end}

To access Mosets Tree's back-end, go to "**Components -> Mosets Tree**" from your admin menu.

## Publish Mosets Tree to Front-end {#publish-to-front-end}

You need to publish Mosets Tree to front-end in order for your user to be able to access your directory. You do this by creating a "Menu Item" for Mosets Tree's Home:

1. Go to "**Menus -> Main Menu -> New**"
2. Click the '**Select**' button and select '**Mosets Tree**' > '**Home**' link from the modal dialog.
3. Fill in the '**Title**' field and leave other field as default.
4. Click '**Save & Close**' to save the menu.

You have successfully publish Mosets Tree to your Joomla website. A link for Mosets Tree is now available in front-end under your Main Menu module.

## Frequently Asked Question {#faq}

{question}Which PHP version should I use?{/question}
{answer}
Although Joomla specify PHP 7.2 as the minimum requirement, it is [no longer being maintained](https://www.php.net/eol.php) by the PHP maintainers.

Therefore we recommend PHP 7.4 as the minimum requirement and PHP 8 as the recommended version.
{/answer}