# Templates

- [Introduction]({{version}}/template#intro)
- [Requirement]({{version}}/template#requirement)
- [Path & Files]({{version}}/template#path-and-files)
- [Copying A Template]({{version}}/template#copy)
- [Inheritance]({{version}}/template#inheritance)
- [Customize Listing Details Page]({{version}}/template#listing-details)
	- [Displaying Custom Fields]({{version}}/template#listing-details-displaying-custom-fields)
	- [Hiding Custom Fields]({{version}}/template#listing-details-hiding-custom-fields)
	- [Using Bootstrap Toggleable Tabs]({{version}}/template#listing-details-bootstrap-toggleable-tabs)
- [Customize Listing Summary Sub Template]({{version}}/template#listing-summary)
- [Module Positions]({{version}}/template#module-positions)

## Introduction {#intro}
Mosets Tree template a is simple, yet powerful feature that controls how your directory is displayed in front-end. It's designed to be modular and easy to customize to give you the full flexibility in designing your Mosets Tree directory.

This article shows how you can create your own Mosets Tree template and customize some of the frequently accessed Mosets Tree pages.

If you're comfortable with PHP, HTML and CSS, you will feel right at home. Even if you're not, our examples are simple and easy to follow.

To access Mosets Tree's template, go to:

**Mosets Tree -> Templates -> [your current template]**

You'll find many template parameters that lets you control many of the visual aspect of your directory. Note that they are grouped by "_Index_", "_Sub-categories_", "_Listing Details Page_", "_Listing Summaries_" and "_Others_" to indicate the part of directory you're customizing.


## Requirement {#requirement}
Mosets Tree requires Bootstrap version 2 that is shipped with Joomla.

## Path & Files {#path-and-files}
Mosets Tree comes with a default template called _Kinabalu_. The template files are located at this path:

	/components/com_mtree/templates/kinabalu/

This is where all the component's template files, `*.tpl.php` are located at. Files that starts with `page_*` prefix are the main files that constitute a page in Mosets Tree. Files with `sub_*` prefix are child pages that are called and use by `page_*` template file.

Template files are named according to the page they output to. For example:

- `page_index.tpl.php`: Directory Index
- `page_subCatIndex.tpl.php`: Category Page
- `page_addListing.tpl.php`: Add & Edit Listing Page
- `page_advSearch.tpl.php`: Advanced Search Form
- `page_listing.tpl.php`: Listing Details Page

Many of these page template includes sub template. Whenever you see statement like this:

	include $this->loadTemplate( 'sub_map.tpl.php' );

it means that the page template includes the `sub_map.tpl.php` sub template file. If you look at listing details page template file, you will see that it includes the following sub template files:

- `sub_listingDetails.tpl.php`
- `sub_map.tpl.php`
- `sub_reviews.tpl.php`
- `sub_listings.tpl.php`

This allows you to work on a specific part of a template without affecting other part of the same page. Later, you'll learn how you can create a Mosets Tree template by customizing a small part of the directory, while inheriting the rest from the default template.

## Copying A Template {#copy}
Every time you upgrade Mosets Tree, all _Kinabalu_ template files will be overwritten. Because of this, you shouldn't modify and use this template if you intend to customize it.

Instead, you should copy this template and make a new one for your directory:

1. Go to "**Mosets Tree -> Templates**"
2. Select the radio button beside "_kinabalu_" to select the template.
3. Click the "**Copy Template**" button.
4. Fill in the "_Template Name_" and "_Folder Name_" field. For our example, let's call our new template Awesome. Fill in "_Awesome_" for the template name and "_awesome_" for the folder name.
5. Click "**Save & Close**" to save your new template.

You should be directed back to Tree Templates page and see your new "_Awesome_" template. Because we want to modify and use this as our default template, check the radio button for "_Awesome_" and click the "**Default**" button.

Behind the scene, Mosets Tree is making a copy of all _Kinabalu_ files to the the new _Awesome_ template path:

	/components/com_mtree/templates/awesome/

## Inheritance {#inheritance}
Template inheritance in Mosets Tree allows you to include only the template file you're customizing in your template. When Mosets Tree does not find a template file in your template, it will fallback to "_Kinabalu_" version of the file.

Continuing our _Awesome_ example above, keep `templatedetails.xml` and delete all other files inside `/components/com_mtree/templates/awesome/`. This will leave a single XML file in your template:

	/components/com_mtree/templates/awesome/templatedetails.xml

If you view Mosets Tree in front-end, you will see that it looks unchanged. That's because the _Awesome_ template is inheriting all images, template and CSS files from _Kinabalu_.

> **Note**: `templatedetails.xml` contains the metadata about your Mosets Tree template. Each Mosets Tree template must contain this file in order for Mosets Tree to detect and use your template.

## Customize Listing Details Page {#listing-details}
Although the template file for listing details is `page_listing.tpl.php`, often it is the sub templates that we want to edit. The 2 common sub templates that we are interested in are:

- `sub_listingDetails.tpl.php`: Controls listings details page layout and outputs the description.
- `sub_listingDetailsFields.tpl.php`: Outputs all fields caption and value.

If you're coming from the previous _Awesome_ template example, copy the 2 template files from _Kinabalu_ to _Awesome_ template:

	/components
		/com_mtree
			/templates
				/awesome
					templatedetails.xml
					sub_listingDetails.tpl.php
					sub_listingDetailsFields.tpl.php


### Displaying Custom Fields {#listing-details-displaying-custom-fields}
You may display a custom field in listing details template page, `sub_listingDetails.tpl.php`,  by first getting the field object using its custom field ID. In the following example, the field ID is _33_:

	$myfield = $this->fields->getFieldById(33);

To display the output of the field:

    echo $myfield->getOutput();

Field outputs are often formatted with HTML elements. For example, a [Youtube]({{version}}/fields#fieldtype-youtube) custom field will display the actual video with `<IFRAME>` element. If you want to display the value:

    echo $myfield->geValue();

To display the caption of the field:

    echo $myfield->getCaption();

Taken all together, you may use the following codes to output a custom field together with caption:

	if($myfield = $this->fields->getFieldById(33))
    {
    	echo $myfield->getCaption();
    	echo ': ';
    	echo $myfield->getOutput();
    }

### Hiding Custom Fields {#listing-details-hiding-custom-fields}
Most of your fields caption and output are shown under the header "_Listing Details_". If want to prevent a field from being shown here, edit `sub_listingDetailsFields.tpl.php` template file. Near the top of the file, you should see this code:

	$skipped_field_ids = array(1,2);

Add a field ID to the `array()` to prevent it from being show under "_Listing Details_":

	$skipped_field_ids = array(1,2,33);
	
### Using Bootstrap Toggleable Tabs {#listing-details-bootstrap-toggleable-tabs}
Showing custom fields in toggleable tabs is possible in Mosets Tree by implementing bootstrap toggleable tabs in `sub_listingDetails.tpl.php` template file.

Basic bootstrap toggleable tabs:

	<ul class="nav nav-tabs" id="tab-title"> 
        <li><a href="#toggleabletab" data-toggle="tab">Tab Title</a></li>
    </ul>
    <div class="tab-content"> 
        <div class="tab-pane" id="toggleabletab">Tab Content</div>
    </div>

In the following example, three tabs will be created based on three custom fields: 

 - Text
 - Image 
 - Youtube

To create toggleable tab, first you need to [get custom fields]({{version}}/template#listing-details-displaying-custom-fields) through IDs and use them together with bootstrap. 

	$text = $this->fields->getFieldById(37);
    $image = $this->fields->getFieldById(36);
    $youtube = $this->fields->getFieldById(35);

To display field's caption for tab title:

	<ul class="nav nav-tabs" id="myTab">
		<?php if(isset($text)) { ?>
			<li><a href="#text" data-toggle="tab"><?php echo $text->getCaption(); ?></a></li>
		<?php } ?>
        <?php if(isset($image)) { ?>
			<li><a href="#image" data-toggle="tab"><?php echo $image->getCaption(); ?></a></li>
		<?php } ?>
        <?php if(isset($youtube)) { ?>
			<li><a href="#youtube" data-toggle="tab"><?php echo $youtube->getCaption(); ?></a></li>
		<?php } ?>
    </ul>
    
To output value for tab content:

	<div class="tab-content">
		<?php if(isset($text)) { ?>
			<div class="tab-pane" id="text">
				<?php if($text->hasValue()) {
					echo $text->getOutput(); 
				} else {
					echo 'User has no Description.';
				} ?>
			</div>
		<?php } ?>
        <?php if(isset($image)) { ?>
			<div class="tab-pane" id="image">
				<?php if($image->hasValue()) {
					echo $image->getOutput(); 
				} else {
					echo 'User has no Image.';
				} ?>
			</div> 
		<?php } ?>
        <?php if(isset($youtube)) { ?>
			<div class="tab-pane" id="youtube">
				<?php if ($youtube->hasValue()) {
					echo $youtube->getOutput(); 
				} else {
                	echo 'User has no Video';	
				} ?> 
			</div>
		<?php } ?>
    </div>
    
Make sure you [hide]({{version}}/template#listing-details-hiding-custom-fields) these custom fields under "_Listing Details_" so that a page is not showing repetitive content.  
    
## Customize Listing Summary Sub Template {#listing-summary}
Listing summary sub template file is located at this path:

	/components/com_mtree/templates/kinabalu/sub_listingSummary.tpl.php

If you're coming from the _Awesome_ template example, copy this file to _Awesome_ template:

	/components
		/com_mtree
			/templates
				/awesome
					templatedetails.xml
					sub_listingDetails.tpl.php
					sub_listingDetailsFields.tpl.php
					sub_listingSummary.tpl.php

All the codes from [Customize Listing Details Page]({{version}}/template#listing-details) are applicable here, with the exception of the fields object variable. Instead of `$this->fields`, use `$link_fields`. eg:

	if($myfield = $link_fields->getFieldById(33))
    {
    	echo $myfield->getCaption();
    	echo ': ';
    	echo $myfield->getOutput();
    }

To test the sample code above in your directory, make sure that:

- You have a custom field with ID 33. If not, replace the ID with one that you have in the directory.
- The custom field is **Published** and **Shown in summary view** is set to **Yes**.
- The listing that you are testing with has value in the custom field. Generally, fields that has no values will not be shown.

## Module Positions {#module-positions}

Mosets Tree's Kinabalu template supports additional module positions within the Mosets Tree extension. These module positions are available in index and category pages, opening up the possibilities of showing additional any modules inside these pages.

You may refer to the diagram below to see all the available module positions. Replace `{cat_id}` with the category ID you want the module to be displayed. For example, to use `category2-footer-id{cat_id}` in th category with ID 13, you'll enter `category2-footer-id13` as the module position.

![Module positions](http://demo.mosetstree.com/images/demo/mt-kinabalu-template-module-positions.png)

Here are some pages from demo that make use of these module positions:

Demo: http://demo.mosetstree.com/computers.html

: _Computer_ category using `category2-footer-id{cat_id}` to show listings in 2 positions.

Demo: http://demo.mosetstree.com/health.html

: _Health_ category using `category3-header-id{cat_id}` to show listings in 3 positions.

