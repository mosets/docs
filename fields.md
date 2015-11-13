<style>
    .fieldtypes-list {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
        margin-top:10px;
    }

    .fieldtypes-list a {
        display: block;
        font-weight: 400;
    }
</style>
# Fields

- [Core Fields]({{version}}/fields#core-fields)
- [Custom Fields]({{version}}/fields#custom-fields)
- [Creating a Custom Field]({{version}}/fields#create)
- [Fieldtypes]({{version}}/fields#fieldtypes)
<div class="fieldtypes-list" markdown="1">
	- [Select List]({{version}}/fields#fieldtype-selectlist)
	- [Select Multiple]({{version}}/fields#fieldtype-selectmultiple)
	- [Radio Button]({{version}}/fields#fieldtype-radiobutton)
	- [Associated Listing]({{version}}/fields#fieldtype-associatedlisting)
	- [Audio Player]({{version}}/fields#fieldtype-audioplayer)
	- [Captcha]({{version}}/fields#fieldtype-captcha)
	- [Category]({{version}}/fields#fieldtype-category)
	- [Checkbox]({{version}}/fields#fieldtype-checkbox)
	- [Date]({{version}}/fields#fieldtype-date)
	- [Directory]({{version}}/fields#fieldtype-directory)
	- [E-mail]({{version}}/fields#fieldtype-email)
	- [File]({{version}}/fields#fieldtype-file)
	- [Image]({{version}}/fields#fieldtype-image)
	- [Listing ID]({{version}}/fields#fieldtype-listingid)
	- [Month & Year]({{version}}/fields#fieldtype-monthandyear)
	- [Number]({{version}}/fields#fieldtype-number)
	- [Skype]({{version}}/fields#fieldtype-skype)
	- [Tags]({{version}}/fields#fieldtype-tags)
	- [Telephone]({{version}}/fields#fieldtype-telephone)
	- [Terms & Condition]({{version}}/fields#fieldtype-termsandcondition)
	- [Text]({{version}}/fields#fieldtype-text)
	- [Text Editor]({{version}}/fields#fieldtype-texteditor)
	- [Time Zone]({{version}}/fields#fieldtype-timezone)
	- [Vanity URL]({{version}}/fields#fieldtype-vanityurl)
	- [Video Player]({{version}}/fields#fieldtype-videoplayer)
	- [Vimeo]({{version}}/fields#fieldtype-vimeo)
	- [Web link]({{version}}/fields#fieldtype-weblink)
	- [Year]({{version}}/fields#fieldtype-year)
	- [Youtube]({{version}}/fields#fieldtype-youtube)
	</div>

Fields are your listings attributes. Mosets Tree comes with a host of fieldtypes that you can use to create custom fields for your directory. There are two types of fields.

- [Core fields]({{version}}/fields#core-fields)
- [Custom fields]({{version}}/fields#custom-fields)

## Core Fields {#core-fields}

Core fields are important part of your listings. Their data are stored in a dedicated database table column, thus more performant. Whenever possible, use core fields. Because there are limited amount of core fields, prioritize using core fields for fields that you will be making as simple searchable. Generally simple searchable core fields are more performant than custom fields.

Mosets Tree comes with the following set of core fields:
<style>
    .core-fields-list {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
    }

</style>
<div class="core-fields-list" markdown="1">
  - Name
  - Contact Person
  - Mobile
  - Date
  - Year Established 
  - Description
  - Owner
  - Address
  - City
  - State
  - Country
  - Postcode
  - Telephone
  - Fax
  - E-mail
  - Website
  - Price
  - Unique Pageviews
  - Votes
  - Rating
  - Featured
  - Created
  - Modified
  - Website Clicks
  - Publish up
  - Publish down
  - Meta Keys
  - Meta Desciption
</div>
## Custom Fields {#custom-fields}

Custom fields are additional fields that you create for your listings in Mosets Tree. Think of it as a custom attribute. It defines the form control that will be used when your user fill in your fields. It also define how the fields will be displayed, searched and validated.

You can create various type of custom fields from the various [fieldtypes]({{version}}/fields#fieldtypes) that comes with Mosets Tree.

## Creating a Custom Field {#create}

To create a custom field:

1. Goto "**Extensions -> Mosets Tree -> Custom Fields**".
2. Click the "**New**" button.
3. Choose the type of custom field you want to create by selecting the `Field Type`.
4. Fill in the `Caption` for your custom field.
5. If the selected field type offers selections (eg: Select List, Checkbox, Radio Buttons etc.), fill in the `Field Elements`.
6. Click "**Save**" to create your new custom field.

Some fieldtypes offer additional customization through "**Parameters**". After you've saved your custom field, you will see the list of Parameters available for customization on the right hand side of the "**Custom Field: Edit**" screen.

### Basic Settings

#### Fieldtype
Choosing the fieldtype is the first thing you do when you create a new custom field. It controls what type of custom field you are going to create an the parameters available for customization. In order to see the available customization, it's important to click "**Save**" to register the new fieldtype selection. Mosets Tree will then update the "**Custom Field: Edit**" screen with the list of "_Parameters_" on the right hand side of the screen.

Although you can change a custom field's fieldtype after you've entered some data through your listings, you may not get the desirable results when viewing the custom field in front-end after the change.

#### Caption
Caption is the name of the custom field. Every custom field must have a caption as it uniquely identifies the field to the users and admin. Caption should be short and precise. Sometimes, certain fields are self-explanatory and caption is not needed. Checking the "**Hide Caption**" checkbox will disable the caption from appearing.

#### Field Elements
Some fields such as Select List, Select Multiple, Checkbox and Radio Button requires multiple choices to allow users to choose one or more selection. Field Elements is where you enter these choices, or elements. Elements has to be entered one after another, separated by the pipe character `|`. For example:

 	Apartment|Condominium|Penthouse|Terrace House

#### Prefix and Suffix text to display during field modification:
This option allow you to display additional information about a field when user is adding or modifying a listing. Prefix text will appear before a custom field while suffix text will appear after a custom field.

#### Prefix and Suffix text during display:
The option is similar with Prefix and Suffix text to display during field modification with the exception that these only appears during output in front-end. This is useful when you're displaying values which has associated metrics such as kg, acres and the others.

#### Alias {#alias}
When you enable SEF URLs in Joomla's Configuration, alias is used to create SEF URLs for taggable fields. Alias is also used as a human-friendly column name when you[ import CSV data to a custom field]({{version}}/importer#csv-existing-fields).

#### Default Value
Default Value populates a value in the custom field when a new listing is created. This value will be prefilled on the custom field and only shown on a "**Add Listing**" form. Your users can overwrite this value for their listing.


#### View Access level
You can select the access level that can view a particular field. When a user does not have the access level to view a field, the field will not be shown. This affects both Summary and Details view.

#### Edit Access level
You can also select the access level that can use a particular field when they submit new listings or edit their existing ones in front-end. This does not affect the back-end.

#### Published
This is the main toggle that disable or enable the use of a custom field. Setting this to `No` will remove it from view in the front-end and edit page. This however will not remove the data entered to the field.

#### Show in details view
Data entered to a field is displayed in 2 places in the front-end - Details view and Summary view. This option allows you to choose if a custom field is displayed in the details view.

#### Show in summary view
Similar to Show in details view, except that this option allow you to configure if a custom field is displayed in the summary view.

#### Taggable
When a field is set to taggable, the values that are shown in details and summary view will be shown as links. Clicking these links will show users a page of listings with the same value. This is useful when you want to let your users to quickly find related listings sharing similar attributes.

#### Simple Searchable {#simple-searchable}
Mosets Tree provides 3 methods to search for listings. One of them is Simple Search. This is provided by [Mosets Tree's Search module]({{version}}/modules#mod-mt-search) and consist of a single text input field. When users search through this module, the search word will be matched against fields that are marked as Simple Searchable. If you would like a field to be simple searchable, set `Yes` for this option.

It is not advisable to have too many fields set to simple searchable, as it will affect the speed of the searches. To improve the performance of simple search, limit this option to just core field..

#### Advanced Searchable {#advanced-searchable}
The second search method is advanced search. Advanced search form appears in a dedicated page. This page is accessible through a link in [Mosets Tree's Search module]({{version}}/modules#mod-mt-search). Advanced search allow users to find listings that meet specific criteria. Set this to `Yes` if you would like a field to appear in Advanced Search page.

#### Filter Searchable {#filter-searchable}
This parameter allows the custom fields to be available as an optional filter. Filters are available when you view a category page through "**All Listings**".

#### Required Field
Setting Required Field to `Yes` ensure that data is entered to a custom field before users can proceed to save a listing.

#### Hidden Field
Setting Hidden Field to `Yes` will make this field unavailable during front-end editing. You can still however display this field in details and summary view. To completely hide a field in the front-end, you need to remove it from details, summary view and select `No` for Simple Searchable and Advanced Searchable.

#### Ordering
You can customize your custom fields' order when they are displayed. Current field will be displayed beneath the selected field when display in list form. By default, a new custom field is placed at the last position of the list.

## Fieldtypes {#fieldtypes}

### Select List {#fieldtype-selectlist}
Select List provides a drop-down list that allows your users to choose a value from the list.

### Select Multiple {#fieldtype-selectmultiple}
Unlike Select List, Select Multiple enables users to choose one or more values from the list. In order to make multiple selection, after the first value is selected, users have to work in combination with `Shift` or `Ctrl` key to select the next desired value.

### Radio Button {#fieldtype-radiobutton}
Radio Button works similar to a Select List which allows users to choose only one value from multiple choice. However, Radio Button makes each choice permanently visible on the form while Select List only shows one value from the list at a time.

### Associated Listing {#fieldtype-associatedlisting}
Associated Listings shows you a drop-down list, with a selection based on the listings available from associated category. It defines listings relationship between two associated categories. For more information on setting up and using category association, check out [the documentation]({{version}}/categories#association).
 
### Audio Player {#fieldtype-audioplayer}
Audio Player allows your users to upload an audio file along with their listing. 
 
 #### Auto Start
 Set Auto Start to `Yes` so the audio plays automatically once users enter listings details view.
 
 #### Display Filename
 It allows the audio's filename to be displayed below the player.
 
 #### Loop
 By default, Loop is set to `No` so the audio track will not start over again when it is finished. If you want the track to loop indefinitely, set it to `Yes` then.
 
### Captcha {#fieldtype-captcha}
If you've set the permission to allow Public to submit listings to Mosets Tree, you can use Captcha to make sure the person submitting the listings are human and not an automated bot. Make sure you [enable Captcha in Joomla](https://docs.joomla.org/How_do_you_use_Recaptcha_in_Joomla%3F) in order to use this.

Captcha custom field is only shown in front-end when your users submit new listing. It's not shown in back-end or front-end when modifying listings.

### Category {#fieldtype-category}

Category is a display-only field type that shows which categories a listings belongs to. Links are displayed to direct your users to the related categories.
 
 #### Search Category
 After enabling searchable function in [Basic Settings]({{version}}/fields#edit-screen), select a parent category in this parameter. Sub-categories of the selected category will be available for search in Filter and Advanced Search form.
 
 #### Show Primary Category
 Selecting `Yes` will show the primary category assigned to the listing will be displayed.
 
 #### Show Secondary Categories
 Selecting `Yes` will display all the secondary categories assigned to the listing.
 
 #### Show Breadcrumbs
 Selecting `Yes` will show the categories with breadcrumbs.

### Checkbox {#fieldtype-checkbox}
Similar to Radio Button, Checkbox makes all choices permanently visible on the form, except that it allows your users to have multiple selection on the field.
   
   #### Images
   Instead of using texts to define the elements for the field, you can also use images to represent the elements by entering URLs of the images. Be sure to keep in mind, URLs must be separated by `|` if you have two or more checkboxes.
   
   If you have your own site, you can use `{live_site}` as the replacement for your site's base URL. Below is an example of the Images content for two checkboxes:

	{live_site}/media/images/mime-icon-32/zip.png|{live_site}/media/images/mime-icon-32/mp3.png
   
   #### Show Images
   You can choose whether to show your Images or you can also choose to show Images only in front-end.
   
   #### Captions
   Captions are display beside the image to provide a short description for each checkbox. Enter the captions corresponding to the elements defined for the field. Captions must be separated by `|`.
   
   #### Show Captions
   This parameter lets you decide whether or not to show your Captions. You can also choose to show Captions only in Edit screen.
   
   #### Image ALTs Attribute
   ALTs attribute are included in your image for accessibility and allow user agents that cannot display images to use this as alternate text. Keep it short and precise. If you leave this empty, field elements will be used for this. Enter the ALT text corresponding to the elements defined for the field. ALT texts must be separated by `|`.
   
   #### Image TITLEs Attribute
   Tittle attribute will be added to your images and provide additional information to each of your image. Most browsers display title text as a tooltip when it is hovered over. Enter the TITLE texts corresponding to the elements defined for the field. TITLE texts must be separated by `|`.
   
   #### Details view's output
   Choose how you want the values selected to be displayed in listing details view when the field has 2 or more values.
   
   #### Horizontal output separator
   Horizontal output separator allows you to specify the string to separate each value when the field has 2 or more values. This separator string will be used in summary view and in details view if the details view output is set to display horizontally. 
   
   #### Columns
   You can configure the number of column used to display each of the checkboxes in Edit Listing form. By default, it is set to automatically arrange itself based on available width and the size of each checkbox.
   
   #### Search Operator
   Select how results are being returned when searching against the field. Selecting `Match All` will return listings matching all selected elements or values. Selecting `Match Any` will return listings matching any one of the selected elements or values.

### Date {#fieldtype-date}
Date provides a text box for entry of a date. An icon next to the text box provides a link to a pop-up calendar, which can also be used to enter date value.

 #### Start year
 You can set the starting year or earliest year available for selection. If this is left empty, it will default to 70 years ago from the current year.
 
 #### Enter year
 You can also set the latest year that available for selection. If left empty, the current year will be used.
 
 #### Date Format
 Date Format decides how the date to be displayed for the field. By default, "_Year-Month-Day_" (for example, 2015-12-31) is used for the field.

### Directory {#fieldtype-directory}
Directory is a display-only fieldtype that shows the top level category which a listing belongs to.

### E-mail {#fieldtype-email}
E-mail allows your users to enter an e-mail address to your listings.

### File {#fieldtype-file}
File is an attachment fieldtype that allows you to create a file input field for your users to upload files along with their listings.

 #### Acceptable file extensions
 Enter the acceptable file type of extension for the field. If you have more than one extension, separate the extension with a bar `|`. For example, `gif|png|jpg|jpeg` or `pdf`. Do not start or end the value with a bar.
 
 #### Maximum Size (in bytes)
 Set the maximum size for a file upload in bytes. By default, this is set to `10485760` bytes (10MB). Enter `0` for no limit. Note that your server may have a maximum upload limit.
 
 #### Image
 You can use an image to link to the uploaded file to be displayed in listing details view. Enter the URL to the image you would like to use to link to the file. You can use `{live_site}` as the replacement for the value of site's domain. For example:

	{live_site}/images/save_f2.png
 
 #### Show Counter
 Mosets Tree keep track of the number of times a file has been downloaded. Setting this to `Yes` will show the counter besides the file.
  
 #### Link Class Suffix
 Link Class Suffix sets a suffix to be applied to the CSS class of the download link.

### Image {#fieldtype-image}
Image is an attachment fieldtype that allows your users to upload image files along with their listings.

 #### Min. width & height
 Enter the minimum width and height of the image. This will also be the minimum width and height required for the images uploaded by your users for this field. Enter 0 to use the value configured for listing thumbnail's size.
 
 #### Max. File Size (in bytes)
 This is the maximum file size for the uploaded file in bytes. Default is `3145728 ` bytes (3MB). Enter `0` for no limit. Note that your server may have a maximum upload limit.

### Listing ID {#fieldtype-listingid}
Listing ID is a display-only fieldtype that shows the listing ID assigned to your listings.

### Month & Year {#fieldtype-monthandyear}
Month & Year field type allows you to create a field for users to enter only month and year, without day. 
 
 #### Start Year
 Set a starting year or earliest year available for selection. If left empty, it will default to 70 years ago from the current year.
 
 #### End Year
 End Year is the latest year that available for selection. If left empty, the current year will be used.
 
 #### Date Format
  Date Format lets you control how the date are formatted for display. Refer to [http://php.net/strftime](http://php.net/strftime) for the list of available formats. By default it shows the full month name and year using the following format:

	%B %Y

### Number {#fieldtype-number}
Number renders an input text field and specialized in handling only numeric value.
 
 #### Search Field Type
 When searchable function for this field is enabled, there are four options for you to select how your user can search this field :  
 
 **Exact:** A single input field will be shown for searching listings with the exact number.  
 
 **Contain:** A single input field will be shown for searching listings when any digits in the number match with the input value.  
 
 **From X to Y:** 2 input fields will be shown to allow users to search for listings within a range of 2 numbers. When only one of the number is provided, it will be used as the minimum or maximum cap.
 
 **Exactly/More Than/Less Than X:** A select list and an input field will be shown to allow users to search for listings with exact, more than or less than the given value. 
 
 #### Decimals
 This sets the number of decimal points of the field.
 
 #### Decimal Point
 This sets the separator for the decimal point. By default, it is a dot `.`.
 
 #### Thousand Separator
 You can customize the thousand separator. By default, it is a comma `,`.

### Skype {#fieldtype-skype}
Skype displays a link for users to connect the listing's owners through Skype.

 #### Action 
 You can choose which action you want the Skype link to perform when it's clicked. You can set the action to view the Skype profile of the listing's owner, add the owner to own Skype's contact, call or start a text chat with the listing's owner or send a file to the listing's owner through Skype.

### Tags {#fieldtype-tags}
Tags let your users to organize information using keywords separated by commas. Tags shown in listings are clickable, which will in turn show all listings having the same tag value.

 #### Max. characters
 This parameter allows you to set the maximum number of characters allowed in tags field.
 
 #### Sort by
 You can select the sorting method when presenting the available tags, either sort alphabetically or sort by frequency (most used first).
 
 #### Search Operator
 Search Operator decides how results are being returned when searching against Tags field. Selecting `Match All` will return listings matching all selected elements or values. Selecting `Match Any` will return listings matching any one of the selected elements or values.
 
 #### Search Filed Type
 You can select the field type to use when your users search against Tags field. Field types provided are checkboxes, drop-down list and text.

### Telephone {#fieldtype-telephone}
Telephone allows your users to provide additional telephone number to a listing.

 #### Show Link
 When set to Yes, telephone number will be made as clickable link. This is useful to users using mobile device to make a phone call to the number by clicking the link.

### Terms & Condition {#fieldtype-termsandcondition}
Depending on your type of directory, you may want your users to agree on certain terms and conditions before they can add any listings. This field type provides a link so your users can read the terms and conditions prescribed and a checkbox for them to check to agree.

 #### Select T&C Article
 You may select a Terms & Conditions article from the list provided. 
 
 #### Text
 You can customize the T&C text that will appear beside the checkbox. You can use `{article_title}` and `{article_url}` as a placeholder for the title and URL of the selected article from "_Select T&C Article_" section.

### Text {#fieldtype-text}
Text is the most universal fieldtype that accepts text input.

 #### Input type
 Choose between Single or Multi-line (textarea) text box.
 
 #### Max. characters in Summary view
 If you expect this field to have a lot of text, you can set the maximum number of character to show in summary view. Enter `0` if you do not want to impose any limit.

 #### Max. characters in Details view
 Sets the maximum number of characters to show in details view. Enter `0` if you do not want to impose any limit.
 
 #### Columns
 Columns specify the width (in columns) of multi-line textbox if it is selected from the Input type section. You can specify the height (in rows) of the textbox by using Size option at the [Basic Settings]({{version}}/fields#edit-screen).
 
 #### Preserve newline
 If you're using a Multi-line text box, this option allows you to control where to preserve the newline in the text that is entered. You can either choose to preserve newline in details view only or summary view only, or you can choose to preserve newline in both of the views.
 
 #### Parse URL as link in Details view
 Sometimes, texts inserted in the field may contain URLs. Setting this to `Yes` will parsed URLs as clickable links in details view.
 
 #### Style
 Style allows you to specify additional CSS style for the input field.

### Text Editor {#fieldtype-texteditor}
Text Editor allows you to publish a WYSIWYG editor as an input field. Users can insert content such as texts and images into a WYSIWYG editor and the appearance of the content when it is displayed will be closely corresponding to what is inserted in the editor.

 #### Load Buttons
 If it is set to `Yes`, all editor buttons (except pagebreak and readmore) will be loaded.

### Time Zone {#fieldtype-timezone}
Time Zone provides a drop-down list of time zones for your users to select. 

### Vanity URL {#fieldtype-vanityurl}
Vanity URL is a simplified version of Weblink field type. Instead of accepting a fully formed URL, you define the URL format and your user provides their username to form a complete URL. This is typically used to show URL to social sites such as Facebook and Twitter.

 #### URL Format
 You may specify the URL format. Use `{username}` as a placeholder for the user defined name. For example:

	 http://www.twitter.com/{username}
 
 #### Display Format
 You may also specify the format in which the vanity URL is displayed. Use `{username}` as a placeholder for the user defined name. For example:

	@{username}
 
 #### Link Title
 This will be added to the link as Title attribute. You can use this to provide additional information about the link. Most browser display title text as a tooltip when it is hovered over. User `{username}` as a placeholder for the user defined name. For example:

	Follow the user @{username}
 
 #### Link Image
 Instead of showing link in texts form, you can set to use graphics to represent every link. Enter the URL of an image. This will be used for the weblink instead of the Vanity URL text. You can use `{live_site}` as the replacement for the value of your site's domain. For example:

	{live_site}/images/banners/white.png
  
 #### Max. number of characters
 This option decides the maximum number of characters that users can enter for their vanity URL username.
 
 #### Show Go button
 This Go button will be available beside Vanity URL's field of the back-end Edit Listing page to allow administrator a fast way to open the linked website.
 
 #### Enable nofollow attribute
 `nofollow` is an HTML attribute value used to instruct some search engines that a hyperlink should not influence the link target's ranking in the search engine's index. Enabling this parameter will append the `nofollow` attribute to all links created using Vanity URL field type.
 
 #### Use GA tracking
 If your site uses Google Analytics, this option allows you to track outbound link through Vanity URL field. Please make sure you have Google Analytics running on your site and have the latest version of the tracking code before using this.
 
 #### GA's outbound directory
 If you use Google Analytics, this parameter allows you to enter an outgoing directory where all outbound clicks through Vanity URL field will be recorded. More information is available [here](https://support.google.com/analytics/answer/1136920?cbid=1aul57ykjrzdd&src=cb&rd=1).

### Video Player {#fieldtype-videoplayer}
Mosets Tree allows your users to submit video along with their new listings. You can specify the width and height of the video player and whether or not to start the video automatically. 

### Vimeo {#fieldtype-vimeo}
Use Vimeo field type to let your users share a Vimeo video to their listing. Your users will be asked to enter a Vimeo video URL and Mosets Tree will display the Vimeo video player.

 #### Search's checkbox label
 When the field is set as "_Searchable_", your users can search whether a listing contains a video. This option allows you to change the default search label.

 #### Video player's width
 This parameter lets you set the width of the video player to be displayed in Details view. If this parameter is left empty, default value will be set as width of the video player.
 
 #### Video player's height
 This parameter let you set the height of the video player to be displayed in details view. Leave this parameter empty for default value.
 
 #### Parameter
 Mosets Tree allows you to enter additional Vimeo parameters. Separate each parameter by `&`. This allows you to control how Vimeo is presented to your visitors. Visit [here](https://developer.vimeo.com/player/embedding) for more Vimeo's parameters information.
 
 #### Vimeo's Input description
 You can set an explanation for your Vimeo field and tell your users what to insert into this field. The best guide is provide your user an example along with the explanation.

### Web link {#fieldtype-weblink}
Web link allows your users to add URL links to their listings.

 #### Link Text
 Use this parameter to specify the link text. If this option is left empty, the full URL will be displayed as the link's text. If you specify an image to represent the link, link's text will be used for its ALT attribute.
 
 #### Link Title 
 This will be added to the link as Title attribute. Use this to provide additional information about the link provided by the listing's owner. Most browsers display title text as a tooltip when it is hovered over. 
 
 #### Link Image
 You can replace texts with an image to display the link. Enter the URL of an image. This will be used for the weblink instead of the weblink URL. You can use `{live_site}` as the replacement for your site's base URL. For example:

	{live_site}/images/banners/white.png
 
 #### Max. URL Length
 Enter the maximum URL's length before it is clipped.
 
 #### Use internal redirect
 Using internal redirect will hide the actual destination URL and use an internal URL to redirect users to the actual URL. This option also allows you to track the number of clicks the link gets. The number of clicks can be shown in front-end interface when `Show Counter` option is set to `Yes`.
 
 #### Show counter
 This option shows the number of time the link has been clicked in front-end interface. Tracking the number of clicks is only available when you use internal redirect.
 
 #### Clipped symbol
 Clipped symbol represents the remaining characters of a URL which exceeds maximum URL's length.
 
 #### Show Go button
 Go button will be available beside Web link's field of the back-end Edit Listing page to allow administrator a fast way to open the linked website.
 
 #### Accept FTP links
 Setting this option to `Yes` will enable Web link field to accept links with `ftp://` protocol.
 
 #### Use nofollow attribute
  `nofollow` is an HTML attribute value used to instruct some search engines that a hyperlink should not influence the link target's ranking in the search engine's index. Enabling this parameter will append the `nofollow` attribute to all links created using Web link field type.
 
 #### Use GA tracking
 If your site uses Google Analytics, this option allows you to track outbound link through Web link field. Please make sure you have Google Analytics running on your site and have the latest version of the tracking code before using this.
  
 #### GA's outbound directory
 If you use Google Analytics, this parameter allows you to enter an outgoing directory where all outbound clicks through Web link field will be recorded. More information is available [here](https://support.google.com/analytics/answer/1136920?cbid=1aul57ykjrzdd&src=cb&rd=1).

### Year {#fieldtype-year}
Sometimes, you only want the information about years and nothing else. Mosets Tree provides you this field for your users to enter a year value.

 #### Start year
 Enter the starting year or earliest year available for the selection. If this parameter is left empty, it will default to 70 years ago from the current year.
 
 #### End year
 Enter the latest year that available for selection. If this is left empty, the current year will be used.

### Youtube {#fieldtype-youtube}
If you want your users to showcase a Youtube video, use Youtube field type. Your users will be asked to enter a Youtube video URL and Mosets Tree will display the Youtube video player.

 #### Search's checkbox label
 When the field is set as "_Searchable_", your users can search whether a listing contains a video. This option allows you to change the default search label.

 #### Video player's width
 This parameter lets you set the width of the video player to be displayed in Details view. If this parameter is left empty, default value will be set as width of the video player.
 
 #### Video player's height
 This parameter let you set the height of the video player to be displayed in details view. Leave this parameter empty for default value.
 
 #### Parameter
 Mosets Tree allows you to enter additional Youtube parameters. Separate each parameter by `&`. This allows you to control how Youtube is presented to your visitors. Visit [here](https://developers.google.com/youtube/player_parameters#Parameters) for more Youtube's parameters information.
 
 #### Youtube's Input description
 You can set an explanation for your Youtube field. You can tell your users what to insert into this field and guide your users by providing an example along with the description.
