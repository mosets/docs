<style>
    .modules-list {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
        margin-top:10px;
    }

    .modules-list a {
        display: block;
        font-weight: 400;
    }
</style>
# Modules

- [Introduction]({{version}}/modules#intro)
- [Assignment Options]({{version}}/modules#assignment)
- [Module Types]({{version}}/modules#types)
<div class="modules-list" markdown="1">
    - [Alpha Index]({{version}}/modules#mod-mt-alphaindex)
    - [Browse]({{version}}/modules#mod-mt-browse)
    - [Categories]({{version}}/modules#mod-mt-categories)
    - [Categories Expanding]({{version}}/modules#mod-mt-categories-expanding)
    - [Directory Menu]({{version}}/modules#mod-mt-menu)
    - [Directory Stats]({{version}}/modules#mod-mt-stats)
    - [Directory's Last Update]({{version}}/modules#mod-mt-lastupdate)
    - [Dynamic Tree]({{version}}/modules#mod-mt-dtree)
    - [Filter]({{version}}/modules#mod-mt-filter)
    - [Search]({{version}}/modules#mod-mt-search)
    - [Static Categories]({{version}}/modules#mod-mt-staticcats)
    - [Tag Cloud]({{version}}/modules#mod-mt-tagcloud)
    - [Top Listings]({{version}}/modules#mod-mt-listings)
    - [Voted Best]({{version}}/modules#mod-mt-votedbest)
</div>

## Introduction {#intro}
Mosets Tree comes with 14 modules that helps you to display snippets of your directory across your site. If you just started using Joomla, you can refer to Joomla Documentation on [general information about modules](https://docs.joomla.org/Module).

## Assignment Options {#assignment}
Mosets Tree allows you to publish modules exactly where you want it. Each Mosets Tree modules includes a pane that allows you to control where within your directory pages that a module will be displayed. For example, you can assign a module to appear in all pages of your site or hide it from your site; or show in a single top level category while being hidden in others; or only display either in category or listing pages; or both.

## Module Types {#types}

 ### Alpha Index {#mod-mt-alphaindex}
 Shows an alphabetically list of A-Z and 0-9. This allows user to quickly view listings starting from a particular alphabet or number.

 ### Browse {#mod-mt-browse}
 Shows a tree-like structure to help user to browse the directory. The categories displayed by this module is updated according to the current category a user is viewing. It only shows link from the current category (and its predecessor) and sub categories only.

 ### Categories {#mod-mt-categories}
 This module shows a list of sibling categories or sub-categories based on the current category a user is on. This list changes across pages depend on the pages a user is reading. 

 ### Categories Expanding {#mod-mt-categories-expanding}
 This module shows a list of sub categories in the current category a user is on. Instead of changing list across pages, it also shows links to the parent's category and its predecessor, including their siblings categories.

 ### Directory Menu {#mod-mt-menu}
 Most directory will publish this module because it shows a list to some of the most common directory pages in Mosets Tree.

 ### Directory Stats {#mod-mt-stats}
 Publish this module will shows the total number of categories and listings available in the directory.

 ### Directory's Last Update {#mod-mt-lastupdate}
 Displays the date of the listing that has been updated the most recent. 

 ### Dynamic Tree {#mod-mt-dtree}
 Displays a javascript tree menu that lets users browse categories in a tree like structure. This is the module that allows easy navigation around tree categories.

 ### Filter {#mod-mt-filter}
 Shows a list of configurable filters that allow users to search for listing based on specific criteria. 
 Note that when ticking the checkboxes, filter for the fields does not display in front-end unless the checked fields is made [Filter Searchable]({{version}}/fields#filter-searchable) in Custom Fields.

 Demo: http://demo.mosetstree.com/movies.html
 
 : You can see the example of filter module in _Movie_ category. It is placed under the top menu and contain search criteria that related to _Movie_ category such as "**Director**" and "**Genre**" to refine users' searches in this category.

 ### Search {#mod-mt-search}
 Displays a search box for searching the directory and optionally a link to the Advanced Search page. It can also be configured to display a list of categories in a drop down menu to allow users filtering their searches through selected category.

 ### Static Categories {#mod-mt-staticcats}
 Similar to Categories module, except that Static Categories does not change across different pages. Static Categories display from a specific configurable parent categories.

 ### Tag Cloud {#mod-mt-tagcloud}
 Displays a list of popular tags from a tag field.

 ### Top Listings {#mod-mt-listings}
 This is a multipurpose module that allows you to display top listings in your directory. This module can be configured to show New, Recently Updated, Featured, Popular, Most Rated, Top Rated and Most Reviewed listings. This can also be used to show random listings.

 ### Voted Best {#mod-mt-votedbest}
 Voted Best module displays a table of top rated listings.
