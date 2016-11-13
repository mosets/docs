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
	- [Audio Player 2.0]({{version}}/fields#fieldtype-audioplayer2)
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
	- [Listings]({{version}}/fields#fieldtype-listings)
	- [Multiple Dates]({{version}}/fields#fieldtype-multipledates)
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

Fields are the attributes for your listings. Mosets Tree comes with a host of fieldtypes that you can use to create custom fields for your directory. There are two types of fields.

- [Core fields]({{version}}/fields#core-fields)
- [Custom fields]({{version}}/fields#custom-fields)

## Core Fields {#core-fields}

Core fields are an important part of your listings. Their data is stored in a dedicated database table column, as a result they have better performance. Whenever possible use core fields. Since there is a limited amount of core fields, prioritize them as the fields you include as simple searchable fields. Generally, simple searchable core fields are have better performance than custom fields.

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

Custom fields are additional fields that you can create for your listings in Mosets Tree. Think of custom fields as custom attributes. Custom fields define the form control that will be used when your user fills in those fields. It also defines how the fields will be displayed, searched and validated.

You can create various type of custom fields from the various [fieldtypes]({{version}}/fields#fieldtypes) that come with Mosets Tree.

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
Choosing the fieldtype is the first thing you do when you create a new custom field. It controls what type of custom field you are going to create and the parameters available for customization. In order to see the available customization, it's important to click "**Save**" to register the new fieldtype selection. Mosets Tree will then update the "**Custom Field: Edit**" screen with the list of "_Parameters_" on the right hand side of the screen.

You can change a custom field's fieldtype after you have already entered some data in those fields for your listings. However, you may not get the desired results when viewing the custom field in the front-end after you have made that fieldtype change.

#### Caption
Caption is the name of the custom field. Every custom field must have a caption because it uniquely identifies the field for the users and admin. Captions should be short and precise. Sometimes certain fields are self-explanatory and the caption is not needed. Checking the "**Hide Caption**" checkbox will disable the caption from displaying.

#### Field Elements
Some fields such as Select List, Select Multiple, Checkbox and Radio Button require multiple choices to allow users to choose one or more selections. Field Elements is where you enter these choices, or elements. Elements have to be entered one after another, separated by the pipe character `|`. For example:

 	Apartment|Condominium|Penthouse|Terrace House

#### Prefix and Suffix text to display during field modification:
This option allows you to display additional information about a field when users are adding or modifying a listing. Prefix text will appear before a custom field. Suffix text will appear after a custom field. This is helpful when you want to provide instruction or more information about a field. 

You can use HTML elements in your prefix and suffix text. 

#### Prefix and Suffix text during display:
This option is similar to the Prefix and Suffix text that displays during field modification, with the exception that these will only appear during listing display in the site front-end. This is useful when you're displaying values which have associated metrics, such as, kg, acres, etc.

You can use HTML elements in your prefix and suffix text.

#### Alias {#alias}
When you enable SEF URLs in Joomla's Global Configuration, the alias of the fields are used to create SEF URLs for taggable fields. Alias is also used as a human-friendly column name when you[ import CSV data to a custom field]({{version}}/importer#csv-existing-fields).

#### Default Value
Default Value populates a value in the custom field when a new listing is created. This value will be pre-filled in the custom field and only shows in the "**Add Listing**" form. Your users can overwrite this value for their listing.


#### View Access level
You can select the access level permissions required for users to view a particular field. When a user does not have the access level permissions to view a field, then the field will not be shown. This affects both Summary and Details views.

#### Edit Access level
You can also select the access level permissions required for any field when users submit new listings or edit their existing listings in the site front-end. This does not affect the back-end component.

#### Published
This is the main toggle that disables or enables the use of a custom field. Setting this to `No` will remove that custom field from view in the site front-end and the edit page screen. This however will not remove the data entered into the field.

#### Show in details view
Data entered into a field is displayed in two places in the site front-end: Details view and Summary view. This option allows you to choose if a custom field is displayed in the details view.

#### Show in summary view
This is similar to the Show in details view setting, except that this option allow you to configure if a custom field is displayed in the summary view.

#### Taggable
When a field is set to taggable, the values that are shown in details and summary views will be displayed as links. Clicking these links will bring users to a page of listings with the same value in that taggable field. This is useful when you want to enable your users to quickly find related listings that have similar listing attributes.

#### Simple Searchable {#simple-searchable}
Mosets Tree provides three methods to search for listings. One method is Simple Search. This is provided by [Mosets Tree's Search module]({{version}}/modules#mod-mt-search) and consists of a single text input field. When users search through this module, the search word will be matched against all fields that are enabled as Simple Searchable. If you would like a field to be simple searchable, set `Yes` for this option.

It is not advisable to have too many fields set to simple searchable because that will affect the speed of the searches. To improve the performance of simple search, limit this option to just core fields.

#### Advanced Searchable {#advanced-searchable}
The second search method is Advanced Search. The advanced search form appears on a separate webpage. This page is accessible through a link in [Mosets Tree's Search module]({{version}}/modules#mod-mt-search). Advanced search allows users to find listings that meet detailed criteria. Set this to `Yes` if you would like a field to appear on the Advanced Search page.

#### Filter Searchable {#filter-searchable}
This parameter allows the custom fields to be available as an optional filter. Filters are available when you view a category page through "**All Listings**".

#### Required Field
Setting Required Field to `Yes` ensures that data is entered into a custom field before users can save a listing.

#### Hidden Field
Setting Hidden Field to `Yes` will make this field unavailable during front-end editing. However, this will still display this field in the details and summary views. To completely hide a field in the front-end, you need to remove it from the details view, summary view and select `No` for Simple Searchable and Advanced Searchable.

#### Back-end listings column
When you browse a category in the back-end component, you will see the assigned listings with their name, number of reviews, published and featured status. This setting allows you to show this field in the listings column. This setting is only available for core fields.

#### Ordering
You can customize your custom fields' order when they are displayed. Current field will be displayed beneath the selected field when displayed in list form. By default, a new custom field is placed at the last position of the list.

## Fieldtypes {#fieldtypes}

### Select List {#fieldtype-selectlist}
Select List provides a drop-down list that allows your users to choose a value from a list of items.

### Select Multiple {#fieldtype-selectmultiple}
Unlike Select List, Select Multiple enables users to choose one or more values from the list. In order to make multiple selections, after the first value is selected, users have to click while pressing the combination of `Shift` or `Ctrl` key to select the next desired value.

### Radio Button {#fieldtype-radiobutton}
Radio Button works similar to a Select List. Radio button allows users to choose only one value from multiple choices. However, Radio Button choices are all visible on the form, as opposed to Select List which only displays one value from the list at a time.

### Associated Listing {#fieldtype-associatedlisting}
Associated Listings shows you a drop-down list, with a selection based on the listings available from an associated category. It defines listing relationships between two associated categories. For more information on setting up and using category association, check out [the documentation]({{version}}/categories#association).
 
### Audio Player {#fieldtype-audioplayer}
Audio Player allows your users to upload an audio file with their listing. 
 
 #### Auto Start
 Set Auto Start to `Yes` so the audio plays automatically once users view the listings details view.
 
 #### Display Filename
 It allows the audio's filename to be displayed below the player.
 
 #### Loop
 By default, Loop is set to `No` so the audio track will not start over again when it is finished. If you want the track to loop indefinitely, then set it to `Yes`.

### Audio Player 2.0 {#fieldtype-audioplayer2}
The is a newer version of audio player that supersedes the previous non-2.0 version of audio player. Audio Player 2.0 uses MediaElement.js audio player for the playback and supports playing on mobile devices.

 #### Audio Player's Width
 Set the width of the audio player in 'px'.
 
 #### Auto Start
 Set Auto Start to `Yes` so the audio plays automatically once users view the listings details view.
 
 #### Display Filename
 It allows the audio's filename to be displayed below the player.
 
 #### Loop
 By default, Loop is set to `No` so the audio track will not start over again when it is finished. If you want the track to loop indefinitely, then set it to `Yes`.


### Captcha {#fieldtype-captcha}
If you have set the permission to allow Public users (guest visitors) to submit listings in Mosets Tree, you can use Captcha to make sure a human is submitting the listings and not automated bots. Make sure you [enable Captcha in Joomla](https://docs.joomla.org/How_do_you_use_Recaptcha_in_Joomla%3F) in order to use this.

Captcha custom field is only shown in the site front-end when your users submit a new listing. It is not shown in the back-end or front-end when modifying listings.

### Category {#fieldtype-category}
Category is a display-only field type that shows which categories a listings is assigned to. This field uses links to direct your users to the related categories.
 
 #### Search Category
 After enabling the searchable function in [Basic Settings]({{version}}/fields#edit-screen), select a parent category in this parameter. Sub-categories of the selected category will be available for search on the Filter and Advanced Search forms.
 
 #### Show Primary Category
 Selecting `Yes` will display the primary category assigned to the listing.
 
 #### Show Secondary Categories
 Selecting `Yes` will display all the secondary categories assigned to the listing.
 
 #### Show Breadcrumbs
 Selecting `Yes` will show the categories in a breadcrumbs format.

### Checkbox {#fieldtype-checkbox}
Similar to Radio Button, Checkbox displays all choices on the form except that it allows your users to have multiple selections in the field.
   
   #### Images
   Instead of using text to define the elements for the field, you can also use images to represent the elements by entering URLs of the images. Keep in mind that URLs must be separated by `|` if you have two or more checkboxes.
   
   If you have your own site, you can use `{live_site}` as the replacement for your site's base URL. Below is an example of the Images content for two checkboxes:

	{live_site}/media/images/mime-icon-32/zip.png|{live_site}/media/images/mime-icon-32/mp3.png
   
   #### Show Images
   You can choose whether or not to show your Images, or you can choose to only show Images in site front-end.
   
   #### Captions
   Captions are displayed beside the images to provide a short description for each checkbox. Enter the captions corresponding to the elements defined for the field. Captions must be separated by `|`.
   
   #### Show Captions
   This parameter lets you decide whether or not to show your Captions. You can also choose to show Captions only in the Edit screen.
   
   #### Image ALTs Attribute
   ALTs attribute are included in your image for accessibility and to allow user agents that cannot display images to use this as the alternate text. Keep this short and precise. If you leave this empty, the field elements will be used for this. Enter the ALT text corresponding to the elements defined for the field. ALT texts must be separated by `|`.
   
   #### Image TITLEs Attribute
   Title attribute will be added to your images and provide additional information for each of your images. Most browsers display title text as a tooltip when it is hovered over. Enter the TITLE text corresponding to the elements defined for the field. TITLE texts must be separated by `|`.
   
   #### Details view's output
   Choose how you want the values selected to be displayed in the listing details view when the field has two or more values.
   
   #### Horizontal output separator
   Horizontal output separator allows you to specify the string to separate each value when the field has two or more values. This separator string will be used in summary view and in details view if the details view output is set to display horizontally. 
   
   #### Columns
   You can configure the number of columns used to display each of the checkboxes on the Edit Listing form. By default, it is set to automatically arrange itself based on the available width and size of each checkbox.
   
   #### Search Operator
   Select how results are returned when searching a field. Selecting `Match All` will return listings matching all selected elements or values. Selecting `Match Any` will return listings matching any one of the selected elements or values.

### Date {#fieldtype-date}
Date provides a text box for date entry. An icon next to the text box provides a link to a pop-up calendar, which can also be used to enter the date value.

 #### Start year
 You can set the starting year or earliest year available for the selection. If this is left empty, it will default to 70 years ago from the current year.
 
 #### Enter year
 You can also set the latest year that is available for the selection. If left empty, the current year will be used.
 
 #### Date Format
 Date Format decides how the date will be displayed for the field. By default, "_Year-Month-Day_" (for example, 2015-12-31) is used for the field.

### Directory {#fieldtype-directory}
Directory is a display-only fieldtype that shows the top level category which a listing is assigned.

### E-mail {#fieldtype-email}
E-mail allows your users to enter an e-mail address for their listings.

### File {#fieldtype-file}
File is an attachment fieldtype that allows you to create a file input field for your users to upload files with their listings.

 #### Acceptable file extensions
 Enter the acceptable file type of extension for this field. If you have more than one extension, separate the extensions with a bar `|`. For example, `gif|png|jpg|jpeg` or `pdf`. Do not start or end the values with a bar.
 
 #### Maximum Size (in bytes)
 Set the maximum size for a file upload in bytes. By default, this is set to `10485760` bytes (10MB). Enter `0` for no limit. Note that your server may have a maximum upload limit.
 
 Files uploaded through this field must be equal to or less than the maximum size configured here. If a file exceeds the maximum size, the file will be ignored and the user will be prompted to re-upload the file again within the specified file size.
  
  The maximum file size limit is only enforced when a file is uploaded in the site front-end. Files uploaded in the back-end component are not restricted by this limit.
 
 #### Image
 You can use an image to link to the uploaded file as the display in the listing details view. Enter the URL to the image you would like to use to link to the file. You can use `{live_site}` as the replacement for the value of site's domain. For example:

	{live_site}/images/save_f2.png
 
 #### Show Counter
 Mosets Tree keeps track of the number of times a file has been downloaded. Setting this to `Yes` will show the counter besides the file link.
  
 #### Link Class Suffix
 Link Class Suffix sets a suffix to be applied to the CSS class of the download link.

### Image {#fieldtype-image}
Image is an attachment fieldtype that allows your users to upload image files with their listings.

 #### Min. width & height
 Enter the minimum width and height of the image. This will also be the minimum width and height required for the images uploaded by your users for this field. Enter 0 to use the value configured for the listing thumbnail's size.
 
 #### Max. File Size (in bytes)
 This is the maximum file size for the uploaded file in bytes. Default is `3145728 ` bytes (3MB). Enter `0` for no limit. Note that your server may have a maximum upload limit.

### Listing ID {#fieldtype-listingid}
Listing ID is a display-only fieldtype that shows the listing ID assigned to your listings.

### Month & Year {#fieldtype-monthandyear}
Month & Year field type allows you to create a field for users to only enter the month and year, but not the day.
 
 #### Start Year
 Set a starting year or earliest year available for the selection. If left empty, it will default to 70 years ago from the current year.
 
 #### End Year
 End Year is the last year available for the selection. If left empty, the current year will be used.
 
 #### Date Format
  Date Format lets you control how the dates are formatted for display. Refer to [http://php.net/strftime](http://php.net/strftime) for the list of available formats. By default it shows the full month name and year using the following format:

	%B %Y

### Listings {#fieldtype-listings}
Listings field type allows you to create a special type of custom field that shows other listings from your directory. You can customize the custom field to show the listings with images and/or any of their custom fields. This field type is great when you want to show related listings. 

Listings custom fields are not searchable. 


### Multiple Dates {#fieldtype-multipledates}
Multiple Dates allows you to enter one or more dates by entering the dates directly or by selecting the date through the displayed calendar. If you are entering the dates manually, the dates must be entered in the following format, separated by comma(s):

	YYYY-MM-DD
	
 #### Search's Start Month 
 Your users will be able to search your dates based on the month. Mosets Tree will offer a list of months for searching and this parameter allows you to specify which month the list will start with. By default, it will start with the current month.
 
 #### Total Searchable Months
 Select the total searchable months available to your users.
 
 #### Date Format
 Choose the format to use when outputting the dates in the site front-end.

### Number {#fieldtype-number}
Number renders an input text field and is specialized for handling only numeric values.
 
 #### Search Field Type
 When searchable function for this field is enabled, there are four options for you to select how your user can search this field :  
 
 **Exact:** A single input field will be shown for searching listings with the exact number.  
 
 **Contain:** A single input field will be shown for searching listings when any digits in the number match with the input value.  
 
 **From X to Y:** Two input fields will be shown to allow users to search for listings within a range of two numbers. When only one of the numbers is provided, it will be used as the minimum or maximum number cap.
 
 **Exactly/More Than/Less Than X:** A select list and an input field will be shown to allow users to search for listings with the exact value, or more than, or less than the given value.
 
 #### Decimals
 This sets the number of decimal places of the field.
 
 #### Decimal Point
 This sets the separator for the decimal point. By default, it is a dot `.`.
 
 #### Thousand Separator
 You can customize the thousands separator. By default, it is a comma `,`.

### Skype {#fieldtype-skype}
Skype displays a link for users to connect to the listing's owners through Skype.

 #### Action 
 You can choose which action you want the Skype link to perform when it's clicked. You can set the action to view the Skype profile of the listing's owner, add the owner to the user's own Skype's contacts, call or start a text chat with the listing's owner, or send a file to the listing's owner through Skype.

### Tags {#fieldtype-tags}
Tags allow your users to organize information using keywords that are separated by commas. Tags shown in listings can be clicked as links which will then display all the listings that have that same tag value.

 #### Max. characters
 This parameter allows you to set the maximum number of characters allowed in the tags field.
 
 #### Sort by
 You can select the sorting method when presenting the available tags, either sort them alphabetically, or sort them by the frequency used (most used first).
 
 #### Search Operator
 Search Operator decides how results are returned when searching in the Tags field. Selecting `Match All` will return listings matching all selected elements or values. Selecting `Match Any` will return listings matching any one of the selected elements or values.
 
 #### Search Filed Type
 You can select the field type to use when your users search in the Tags field. Field types provided are checkboxes, drop-down list and text.

### Telephone {#fieldtype-telephone}
Telephone allows your users to provide an additional telephone number for a listing.

 #### Show Link
 When set to Yes, telephone number will be clickable as a link. This is useful mobile device users so they can make a phone call to the number by clicking the link.

### Terms & Condition {#fieldtype-termsandcondition}
Depending on your type of directory, you may want your users to agree on certain terms and conditions before they can add any listings. This field type provides a link so your users can read the terms and conditions, and there is a checkbox for them to check if they agree.

 #### Select T&C Article
 You may select a Terms & Conditions article from the list provided. 
 
 #### Text
 You can customize the T&C text that will appear next to the checkbox. You can use `{article_title}` and `{article_url}` as a placeholder for the title and URL of the selected article from "_Select T&C Article_" section.

### Text {#fieldtype-text}
Text is the most universal fieldtype that accepts text input.

 #### Input type
 Choose between a Single or Multi-line (textarea) text box.
 
 #### Max. characters in Summary view
 If you expect this field to have a lot of text, you can set the maximum number of characters to show in summary view. Enter `0` if you do not want to impose any limit.

 #### Max. characters in Details view
 Sets the maximum number of characters to show in details view. Enter `0` if you do not want to impose any limit.
 
 #### Columns
 Columns specify the width (in columns) of multi-line textboxes if it is selected from the Input type section. You can specify the height (in rows) of the textbox by using the Size option at the [Basic Settings]({{version}}/fields#edit-screen).
 
 #### Preserve newline
 If you are using a Multi-line text box, this option allows you to control where to keep the newline in the text that is entered. You can either choose to preserve newline in the details view only or in summary view only, or you can choose to preserve newline in both of the views.
 
 #### Parse URL as link in Details view
 Sometimes, texts inserted in the field may contain URLs. Setting this to `Yes` will parse the URLs to be converted into clickable links in details view.
 
 #### Style
 Style allows you to specify an additional CSS style for the input field.

### Text Editor {#fieldtype-texteditor}
Text Editor allows you to publish a WYSIWYG editor as an input field. Users can insert content, such as, text and images into a WYSIWYG editor and the appearance of the content when it is displayed will closely correspond to what is inserted in the editor.

 #### Load Buttons
 If it is set to `Yes`, all editor buttons (except pagebreak and readmore) will be loaded.

### Time Zone {#fieldtype-timezone}
Time Zone provides a drop-down list of time zones for your users to select. 

### Vanity URL {#fieldtype-vanityurl}
Vanity URL is a simplified version of the Weblink field type. Instead of accepting a fully formed URL, you define the URL format and your user provides their username to form a complete URL. This is typically used to show URLs to social sites, such as, Facebook and Twitter.

 #### URL Format
 You may specify the URL format. Use `{username}` as a placeholder for the user defined name. For example:

	 http://www.twitter.com/{username}
 
 #### Display Format
 You may also specify the format in which the vanity URL is displayed. Use `{username}` as a placeholder for the user defined name. For example:

	@{username}
 
 #### Link Title
 This will be added to the link as a Title attribute. You can use this to provide additional information about the link. Most browsers display title text as a tooltip when it is hovered over. User `{username}` as a placeholder for the user defined name. For example:

	Follow the user @{username}
 
 #### Link Image
 Instead of showing links in text form, you can set this to use images to represent every link. Enter the URL of an image. This will be used for the weblink instead of the Vanity URL text. You can use `{live_site}` as the replacement for the value of your site's domain. For example:

	{live_site}/images/banners/white.png
  
 #### Max. number of characters
 This option decides the maximum number of characters that users can enter for their vanity URL username.
 
 #### Show Go button
 The Go button will be available besides the Vanity URL's field in the back-end Edit Listing page to allow administrators a fast way to open the linked website.
 
 #### Enable nofollow attribute
 `nofollow` is an HTML attribute value used to instruct some search engines that a hyperlink should not influence the current page's ranking in the search engine's index. Enabling this parameter will append the `nofollow` attribute to all links created using Vanity URL field type.
 
 #### Use GA tracking
 If your site uses Google Analytics, this option allows you to track outbound links of the Vanity URL field. Please make sure you have Google Analytics running on your site and have the latest version of the tracking code before using this option.
 
 #### GA's outbound directory
 If you use Google Analytics, this parameter allows you to enter an outgoing directory where all outbound clicks through the Vanity URL field will be recorded. More information is available [here](https://support.google.com/analytics/answer/1136920?cbid=1aul57ykjrzdd&src=cb&rd=1).

### Video Player {#fieldtype-videoplayer}
Mosets Tree allows your users to submit videos along with their listings. You can specify the width and height of the video player and whether or not to start the video automatically. 

### Vimeo {#fieldtype-vimeo}
Use Vimeo field type to let your users share a Vimeo video in their listing. Your users will be asked to enter a Vimeo video URL and Mosets Tree will display the Vimeo video player.

 #### Search's checkbox label
 When the field is set as "_Searchable_", your users can search to find listings that contain a video. This option allows you to change the default search label.

 #### Video player's width
 This parameter lets you set the width of the video player to be displayed in Details view. If this parameter is left empty, the default value will be set as the width of the video player.
 
 #### Video player's height
 This parameter lets you set the height of the video player to be displayed in Details view. Leave this parameter empty to use the default value.
 
 #### Parameter
 Mosets Tree allows you to enter additional Vimeo parameters. Separate each parameter by `&`. This allows you to control how Vimeo is presented to your visitors. Visit [here](https://developer.vimeo.com/player/embedding) for more of Vimeo's parameters information.
 
 #### Vimeo's Input description
 You can set an explanation for your Vimeo field and tell your users what to insert into this field. It is best to provide your users with an example along with the explanation.

### Web link {#fieldtype-weblink}
Web link allows your users to add URL links to their listings.

 #### Link Text
 Use this parameter to specify the link text. If this option is left empty, the full URL will be displayed as the link's text. If you specify an image to represent the link, the link's text will be used for its ALT attribute.
 
 #### Link Title 
 This will be added to the link as the Title attribute. Use this to provide additional information about the link provided by the listing's owner. Most browsers display the title text as a tooltip when it is hovered over. 
 
 #### Link Image
 You can replace text with an image to display the link. Enter the URL of an image. This will be used for the weblink instead of the weblink URL. You can use `{live_site}` as the replacement for your site's base URL. For example:

	{live_site}/images/banners/white.png
 
 #### Max. URL Length
 Enter the maximum URL length before it is cut short.
 
 #### Use internal redirect
 Using internal redirect will hide the actual destination URL and use an internal URL to redirect users to the actual URL. This option also allows you to track the number of clicks the link gets. The number of clicks can be shown in the site front-end when `Show Counter` option is set to `Yes`.
 
 #### Show counter
 This option shows the number of times the link has been clicked in the site front-end. Tracking the number of clicks is only available when you use the internal redirect setting.
 
 #### Clipped symbol
 Clipped symbol will be used to represent the remaining characters of a URL when it exceeds the maximum URL length.
 
 #### Show Go button
 Go button will be available next to the Web link's field in the back-end component Edit Listing page to allow administrators a fast way to open the linked website.
 
 #### Accept FTP links
 Setting this option to `Yes` will enable the Web link field to accept links with `ftp://` protocol.
 
 #### Use nofollow attribute
  `nofollow` is an HTML attribute value used to instruct some search engines that a hyperlink should not influence the current pages' ranking in the search engine's index. Enabling this parameter will append the `nofollow` attribute to all links created using the Web link field type.
 
 #### Use GA tracking
 If your site uses Google Analytics, this option allows you to track outbound links through the Web link field. Please make sure you have Google Analytics running on your site and have the latest version of the tracking code before using this.
  
 #### GA's outbound directory
 If you use Google Analytics, this parameter allows you to enter an outgoing directory where all outbound clicks through the Web link field will be counted. More information is available [here](https://support.google.com/analytics/answer/1136920?cbid=1aul57ykjrzdd&src=cb&rd=1).

### Year {#fieldtype-year}
Sometimes you only want the information for a year and nothing else. Mosets Tree provides you this field for your users to enter a year value.

 #### Start year
 Enter the starting year or earliest year available for the selection. If this parameter is left empty, it will default to 70 years ago from the current year.
 
 #### End year
 Enter the last year available for the selection. If this is left empty, the current year will be used.

### Youtube {#fieldtype-youtube}
If you want your users to showcase a Youtube video, use the Youtube field type. Your users will be asked to enter a Youtube video URL and Mosets Tree will display the Youtube video player.

 #### Search's checkbox label
 When the field is set as "_Searchable_", your users can search for listing that contain a video. This option allows you to change the default search label.

 #### Video player's width
 This parameter lets you set the width of the video player to be displayed in the Details view. If this parameter is left empty, the default value will be set as the width of the video player.
 
 #### Video player's height
 This parameter let you set the height of the video player to be displayed in the Details view. Leave this parameter empty if you want to use the default value.
 
 #### Parameter
 Mosets Tree allows you to enter additional Youtube parameters. Separate each parameter by `&`. This allows you to control how Youtube is presented to your visitors. Visit [here](https://developers.google.com/youtube/player_parameters#Parameters) for more Youtube parameters information.
 
 #### Youtube's Input description
 You can set an explanation for your Youtube field. You can tell your users what to insert into this field and guide your users by providing an example along with the description.
