# Language

- [Introduction]({{version}}/language#intro)
- [Translations]({{version}}/language#translations)
- [Overrides]({{version}}/language#overrides)
	- [Language Manager]({{version}}/language#language-manager)
	- [Language Overrides File]({{version}}/language#overrides-file)
- [Top Level Categories]({{version}}/language#top-level-categories)
- [Best Practise]({{version}}/language#best-practise)
- [Frequently Asked Questions]({{version}}/language#faqs)

## Introduction {#intro}

Mosets Tree has great support for localization that provides an easy way to change any text in Mosets Tree and translate in to a new language. If you have used Joomla's Language Overrides feature before, you will feel right at home because this is the same method you can use to change text in Mosets Tree.

Mosets Tree's front-end and back-end language files are stored in these files:

	/administrator
		/language
			/en-GB
				en-GB.com_mtree.ini
				en-GB.com_mtree.sys.ini
	/language
		/en-GB
			en-GB.com_mtree.ini
			en-GB.fld_audioplayer.ini
			en-GB.fld_corefeatured.ini
			en-GB.fld_coreprice.ini
			en-GB.fld_corewebsite.ini
			en-GB.fld_date.ini
			en-GB.fld_email.ini
			en-GB.fld_file.ini
			en-GB.fld_image.ini
			en-GB.fld_number.ini
			en-GB.fld_vanityurl.ini
			en-GB.fld_videoplayer.ini
			en-GB.fld_weblink.ini
			en-GB.fld_year.ini
			en-GB.mod_mt_alphaindex.ini
			en-GB.mod_mt_alphaindex.sys.ini
			en-GB.mod_mt_browse.ini
			en-GB.mod_mt_browse.sys.ini
			en-GB.mod_mt_categories.ini
			en-GB.mod_mt_categories.sys.ini
			en-GB.mod_mt_categories_expanding.ini
			en-GB.mod_mt_categories_expanding.sys.ini
			en-GB.mod_mt_dtree.ini
			en-GB.mod_mt_dtree.sys.ini
			en-GB.mod_mt_filter.ini
			en-GB.mod_mt_filter.sys.ini
			en-GB.mod_mt_lastupdate.ini
			en-GB.mod_mt_lastupdate.sys.ini
			en-GB.mod_mt_listings.ini
			en-GB.mod_mt_listings.sys.ini
			en-GB.mod_mt_menu.ini
			en-GB.mod_mt_menu.sys.ini
			en-GB.mod_mt_search.ini
			en-GB.mod_mt_search.sys.ini
			en-GB.mod_mt_staticcats.ini
			en-GB.mod_mt_staticcats.sys.ini
			en-GB.mod_mt_stats.ini
			en-GB.mod_mt_stats.sys.ini
			en-GB.mod_mt_tagcloud.ini
			en-GB.mod_mt_tagcloud.sys.ini
			en-GB.mod_mt_votedbest.ini
			en-GB.mod_mt_votedbest.sys.ini
	/plugins
		/finder
			/mtree_listings
				/language
					/en-GB
						en-GB.plg_finder_mtree_listings.ini
						en-GB.plg_finder_mtree_listings.sys.ini
	/plugins
		/search
			/mtree
				/language
					/en-GB
						en-GB.plg_search_mtree.ini
						en-GB.plg_search_mtree.sys.ini

That's a lot of files, but don't be intimidated by it. Following Joomla's convention, all texts are stored in files according to where they are used.

`/administrator/language/en-GB/` directory stores text that are used in Joomla's back-end and in our case, Mosets Tree's backend.

`/language/en-GB/` directory stores text that are used in Joomla's front-end. `en-GB.com_mtree.ini` will be of most interest to you because it stores almost all the texts you see displayed in Mosets Tree front-end. Texts used in fields are stored in files with the following file name format: `en-GB.fld_*.ini`.

All modules texts are stored in files with the following file name format: `en-GB.mod_*.ini`. These files store texts that are used in both front-end mode and also its back-end interface.

`/plugins/finder/mtree_listings/language/en-GB/` directory stores the text used in Mosets Tree's Finder plugin.

`/plugins/search/mtree/language/en-GB/` directory stores the text used in Mosets Tree's Search plugin.

## Translations {#translations}

Thanks to our community, many translations for Mosets Tree are [available for download from our forum](http://forum.mosets.com/showthread.php?t=21022).

We are starting to use Transifex to let our users collaborate on translations work. If you would like to help with Mosets Tree's translation, please head on to [Mosets Tree's Transifex page](https://www.transifex.com/cy/mosets-tree/).

## Overrides {#overrides}

### Language Manager {#language-manager}

You can easily override any texts in Mosets Tree through Joomla's Language Overrides:

1. Go to "**Extensions -> Language Manager -> Add New Menu Item**"
2. Click "**Overrides**" from your left hand side menu.
3. Set "**Filter**" to "**English (en-GB) - Site**".
4. Click "**New**" button.

You're now in the "**Create a New Override**" screen.

Let's say we want to change the text in the e-mail that gets sent when your user adds a listing for your approval. We know the e-mail message contains the text "_You will be notified by e-mail when the listing is approved._", so let's put this under the section "**Search text you want to change.**". Make sure the "**Search For**" dropdown is set to "**Value**" and click "**Search**". This will search for for the strings in all Joomla's front-end language files and return all results matching it.

Once you get the results from your search, click on the text you want to change. In our example, this will be the one with the key "**COM_MTREE_NEW_LISTING_EMAIL_MSG_WAITING_APPROVAL**". This will populate "**Language Constant**" and "**Text**" field in your form.

Change the value in the Text field to override this specific text. Click the "**Save**" button to save the changes.

Now your e-mail will contain your newly overrided text whenever your user submit a new listing to your directory.

Note that in step 3 above, we set the filter to search for _English_ language's _Site_. This allows your to search and override Front-end English text. You can change this Filter to manage other language overrides in front or back-end.

You can use these same steps to override any text in Joomla.

### Language Overrides File {#overrides-file}

All the overrides your did in the above screen are stored in a specific overrides INI file in your language directory:

	/language/overrides/en-GB.override.ini

You can manage your language overrides directly in the file above. This is especially helpful during site development when you need to create many language overrides.

If you have added the override from our previous example, you should see the following line in en-GB.override.ini:

	COM_MTREE_NEW_LISTING_EMAIL_MSG_WAITING_APPROVAL="Thank you for your submission. Your Listing will be reviewed shortly by our Administrator and added to our directory once it is approved.\n\nYou will be notified by e-mail when the listing is approved."

The value after the equal sign will match the one you added in our previous example.

## Top Level Categories {#top-level-categories}

If you use Mosets Tree's [Multi Directory]({{version}}/multi-directory) feature to host different type of listings in your top level categories, you may want to override the term '_listings_' with something more specific to each top level categories.

Let's say we want to change the text '_Listings_' to '_Properties_' for our real estate top level category. Typically, your override will looks something like this:

 	COM_MTREE_LISTINGS="Properties"

But the problem is, this will affects your entire directory.

You may insert "**_TL_CAT_ID_X**" after the "**COM_MTREE**" prefix to instruct Mosets Tree to apply the override to top level category with ID X only. Here's an override example with category ID _4_:

 	COM_MTREE_TL_CAT_ID_4_LISTINGS="Properties"

These are the language constants with their default language values that are available for specifying top level category ID during their overrides:

	COM_MTREE_ALL_LISTINGS="All Listings"
	COM_MTREE_LISTINGS="Listings"
	COM_MTREE_LISTINGS_1="Listing"
	COM_MTREE_PAGE_TITLE_TOP_RATED_LISTING="Top Rated Listings"
	COM_MTREE_PAGE_TITLE_ALL_LISTINGS="All Listings"
	COM_MTREE_VIEW_MORE_ALL_LISTINGS="View More Listings"
	COM_MTREE_PATHWAY_LISTALL="All Listings"
	COM_MTREE_FILTER_LISTINGS="Filter Listings"
	COM_MTREE_ALL_OWNERS_LISTING="Owner's listing"
	COM_MTREE_CONTACT_OWNER="Contact Owner"
	COM_MTREE_LISTING_DETAILS="Listing Details"
	COM_MTREE_FILTER_LISTINGS="Filter listings..."
	COM_MTREE_LISTING_DETAILS_USER="User"
	COM_MTREE_BE_THE_FIRST_TO_REVIEW="Be the first to review this listing!"
	COM_MTREE_PAGE_HEADER_LIST_LISTINGS="%1$s: %2$s"
	COM_MTREE_PAGE_TITLE_LIST_LISTINGS="%1$s: %2$s"
	COM_MTREE_PATHWAY_ROOT="Directory"
	COM_MTREE_PATHWAY_LISTNEW="Recently Added Listings"
	COM_MTREE_PATHWAY_LISTFEATURED="Featured Listings"
	COM_MTREE_PATHWAY_LISTALL="All Listings"
	COM_MTREE_PATHWAY_LISTPOPULAR="Popular Listings"
	COM_MTREE_PATHWAY_LISTMOSTRATED="Most Rated Listings"
	COM_MTREE_PATHWAY_LISTTOPRATED="Top Rated Listings"
	COM_MTREE_PATHWAY_LISTMOSTREVIEW="Most Reviewed Listings"
	COM_MTREE_PATHWAY_LISTFAVOURITE="Most Favoured Listings"
	COM_MTREE_PATHWAY_LISTALPHA="A-Z"
	COM_MTREE_PATHWAY_ADVSEARCH="Advanced Search"
	COM_MTREE_PATHWAY_SEARCH="Search Results"
	COM_MTREE_PATHWAY_CLAIM="Claim Listing"
	COM_MTREE_PATHWAY_SEARCHBY="Search By"
	COM_MTREE_PATHWAY_ADDCATEGORY="Add Category"
	COM_MTREE_PATHWAY_ADDLISTING="Add Listing"
	COM_MTREE_PATHWAY_LISTUPDATED="Recently Updated"
	COM_MTREE_PATHWAY_VIEWIMAGE="Image"
	COM_MTREE_PATHWAY_REPORTREVIEW="Report Review"
	COM_MTREE_PATHWAY_REPLYREVIEW="Reply Review"
	COM_MTREE_PATHWAY_REPLYREVIEW="Listings"
	COM_MTREE_PATHWAY_USERS_REVIEWS="Reviews"
	COM_MTREE_PATHWAY_USERS_FAVOURITES="Favourites"
	COM_MTREE_PATHWAY_RECOMMEND="Recommend"
	COM_MTREE_PATHWAY_WRITEREVIEW="Write Review"
	COM_MTREE_PATHWAY_RATE="Rate"
	COM_MTREE_PATHWAY_VIEWGALLERY="Gallery"
	COM_MTREE_PATHWAY_EDITLISTING="Edit Listing"
	COM_MTREE_PATHWAY_CONTACT="Contact Owner"
	COM_MTREE_PATHWAY_REPORT="Report Listing"
	COM_MTREE_PATHWAY_VIEWREVIEWS="Reviews"
	COM_MTREE_PATHWAY_VIEWREVIEW="View Review"
	COM_MTREE_PATHWAY_DELETELISTING="Delete Listing"

## Best Practise {#best-practise}

Any texts changes should be done by overriding them using the steps outline above, either directly to the overrides INI file or through Joomla's Language Manager. Unless you're making a new translation for Mosets Tree, you shouldn't edit Mosets Tree language file, because these files are overwritten during Mosets Tree upgrade.

Using language override will ensure that your changes will be maintained even after you update Mosets Tree.

## Frequently Asked Questions {#faqs}

{question}Does Mosets Tree support multi-language?{/question}
{answer}
No, Mosets Tree does not support multi-language.
{/answer}

{question}How can I change the word 'Directory'?{/question}
{answer}
Following the [override instructions]({{version}}/language#overrides), look for the following constants:

	COM_MTREE_ROOT
    COM_MTREE_PAGE_TITLE_ROOT

to replace the word "_Directory_".
{/answer}
