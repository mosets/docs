# Fields

- [Core Fields]({{version}}/fields#core-fields)
- [Custom Fields]({{version}}/fields#custom-fields)
- [Edit Screen]({{version}}/fields#edit-screen)
- [Fieldtypes]({{version}}/fields#fieldtypes)
	- [Select List]({{version}}/fields#custom-field-selectlist)
	- [Select Multiple]({{version}}/fields#custom-field-selectmultiple)
	- [Radio Button]({{version}}/fields#custom-field-radiobutton)
	- [Associated Listing]({{version}}/fields#custom-field-associatedlisting)
	- [Audio Player]({{version}}/fields#custom-field-audioplayer)
	- [Captcha]({{version}}/fields#custom-field-captcha)
	- [Category]({{version}}/fields#custom-field-category)
	- [Checkbox]({{version}}/fields#custom-field-checkbox)
	- [Checkbox with Text]({{version}}/fields#custom-field-checkboxwithtext)
	- [Date]({{version}}/fields#custom-field-date)
	- [Directory]({{version}}/fields#custom-field-directory)
	- [E-mail]({{version}}/fields#custom-field-email)
	- [File]({{version}}/fields#custom-field-file)
	- [Image]({{version}}/fields#custom-field-image)
	- [Listing ID]({{version}}/fields#custom-field-listingid)
	- [Month & Year]({{version}}/fields#custom-field-monthandyear)
	- [Number]({{version}}/fields#custom-field-number)
	- [Skype]({{version}}/fields#custom-field-skype)
	- [Tags]({{version}}/fields#custom-field-tags)
	- [Terms & Condition]({{version}}/fields#custom-field-termsandcondition)
	- [Text]({{version}}/fields#custom-field-text)
	- [Text Editor]({{version}}/fields#custom-field-texteditor)
	- [Time Zone]({{version}}/fields#custom-field-timezone)
	- [Vanity URL]({{version}}/fields#custom-field-vanityurl)
	- [Video Player]({{version}}/fields#custom-field-videoplayer)
	- [Web link]({{version}}/fields#custom-field-weblink)
	- [Year]({{version}}/fields#custom-field-year)
	- [Youtube]({{version}}/fields#custom-field-youtube)
	

Fields are your listings attributes. Mosets Tree comes with a host of fieldtypes that you can use to create custom fields for your directory. There are two types of fields.

- [Core fields]({{version}}/fields#core-fields)
- [Custom fields]({{version}}/fields#custom-fields)

## Core Fields {#core-fields}

Core fields are important part of your listings. Their data are stored in a dedicated database table column, thus more performant. Whenever possible, use core fields. Because there are limited amount of core fields, prioritize using core fields for fields that you will be making as simple searchable. Generally simple searchable core fields are more performant than custom fields.

Mosets Tree comes with the following set of core fields:

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
  - Hits
  - Votes
  - Rating
  - Featured
  - Created
  - Modified
  - Visited
  - Publish up
  - Publish down
  - Meta Keys
  - Meta Desciption

## Custom Fields {#custom-fields}

Custom fields are additional fields that you create for your listings in Mosets Tree. Think of it as a custom attribute. It defines the form control that will be used when your user fill in your fields. It also define how the fields will be displayed, searched and validated.

You can create various type of custom fields from the following fieldtypes.

## Fieldtypes {#fieldtypes}

### Select List {#custom-field-selectlist}
Select List provides a drop-down menu that allows your users to choose a value from the list.

### Select Multiple {#custom-field-selectmultiple}
Unlike Select List, Select Multiple enables users to choose one or more values from the list. In order to make multiple selection, after the first value is selected, users have to work in combination with "Shift" or "Ctrl" key to select the next desired value.

### Radio Button {#custom-field-radiobutton}
Radio Button works similar to a Select List which allows users to choose only one value from multiple choice. However, Radio Button makes each choice permanently visible on the form while Select List only shows one value from the list at a time.

### Associated Listing {#custom-field-associatedlisting}
[Note](http://www.mosets.com/help/kb/mosets-tree/79)

### Audio Player {#custom-field-audioplayer}
Audio Player allows users to upload an audio file along with their listing. 
 
 #### Auto Start
 Set Auto Start to "Yes" so the audio plays automatically once users enter listings details view.
 
 #### Display Filename
 It allows the audio's filename to be displayed below the player.
 
 #### Loop
 By default, Loop is set to "No" so the audio track will not start over again when it is finished. If you want the track to loop indefinitely, set it to "Yes" then.
 
### Captcha {#custom-field-captcha}
Make sure you enable [Captcha](https://docs.joomla.org/How_do_you_use_Recaptcha_in_Joomla%3F) function so that you will know whether or not your user is human.  

### Category {#custom-field-category}
Category gives additional information in listing details view to show users from which category the listing belongs to.
 ////
 #### Search Category
 
 #### Show Primary Category
 
 #### Show Secondary Categories
 
 #### Show Breadcrumbs

### Checkbox {#custom-field-checkbox}
Similar to Radio Button, Checkbox makes all choices permanently visible on the form but it allows your users to have multiple selection on the field.
   
   #### Images
   Instead of using texts to define the options for the field, you can also use images to represent the options by entering URLs of the images. Be sure to keep in mind, URLs must be separated by "|" if you have two or more checkboxes. 
   
   If you have your own site, you can use {live_site} as the replacement for your site's base URL. Below is the example of the Images content for two checkboxes:  
   {live_site}/media/images/mime-icon-32/zip.png|{live_site}/media/images/mime-icon-32/mp3.png
   
   #### Show Images
   You can decide whether or not to show your Images or you can also choose to show Images only in front-end.
   
   #### Captions
   Captions are display beside the image to provide a short description of each checkbox. Enter the captions corresponding to the elements defined for the field. Captions must also be separated by "|".
   
   #### Show Captions
   You can decide whether or not to show your Captions or you can also choose to show Captions only in Edit screen.
   
   #### Image ALTs Attribute
   ALTs attribute are included in your image for accessibility and allow user agents that cannot display images to use this as alternate text. Keep it short and precise. If you leave this empty, field elements will be used for this. Enter the ALT text corresponding to the elements defined for the field. ALT texts must be separated by "|".
   
   #### Image TITLEs Attribute
   TITLEs Attribute will be added to your images and provide additional information to each of your image. Most browsers display title text as a tooltip when it is hovered over. Enter the TITLE texts corresponding to the elements defined for the field. TITLE texts must be separated by "|". 
   
   #### Details view's output
   Choose how you want the values selected to be displayed in listing details view when the field has 2 or more values.
   
   #### Horizontal output separator
   Horizontal output separator allows you to specify the string to separate each value when the field has 2 or more values. This separator string will be used in summary view and in details view if the details view output is set to display horizontally. 
   
   #### Columns
   You can configure the number of column used to display each of the checkboxes in Edit Listing form. By default, it is set to automatically arrange itself based on available width and the size of each checkbox.
   
   #### Search Operator
   Select how results are being returned when searching against the field. Selecting "Match All" will return listings matching all selected elements/values. Selecting "Match Any" will return listings matching any one of the selected elements/values.

### Checkbox with Text {#custom-field-checkboxwithtext}
//////

### Date {#custom-field-date}
Date provides a text box for entry of a date. An icon next to the text box provides a link to a pop-up calendar, which can also be used to enter date value.

 #### Start year
 You can custom the starting year or earliest year available for selection. If left empty, it will default to 70 years ago from the current year.
 
 #### Enter year
 You can also custom the latest year that available for selection. If left empty, the current year will be used.
 
 #### Date Format
 Date Format decides how the date to be displayed for the field. By default, "Year-Month-Day"(for example, 2015-12-31) is used for the field.

### Directory {#custom-field-directory}
///////

### E-mail {#custom-field-email}
E-mail allows your users to submit an E-mail address for a new listing. Any messages related to the listing will be sent to the listing's owner through the E-mail address provided during submission of the listing. Otherwise, messages will be sent to the E-mail address of the user's account.

### File {#custom-field-file}
This provides an input field for your users to upload files along with their listings.

 #### Acceptable file extensions
 Enter the acceptable file type of extension for the field. If you have more than one extension, please separate the extension with a bar "|". For example, "gif|png|jpg|jpeg" or "pdf", without quotes. Please do not start or end the value with a bar. 
 
 #### Maximum Size (in bytes)
 It decides the maximum size for a file upload in bytes. By default, it is 10MB (10485760 bytes) for the maximum size. Enter 0 for no limit. Note that your server may have a maximum upload limit.
 
 #### Image
 You can always use an image to link to the uploaded file to be displayed in listing details view. Enter the URL to the image you would like to use to link to the file. You can use {live_site} as the replacement for the value of site's domain. For example:  
 {live_site}/images/save_f2.png
 
 #### Show Counter
 Counter will be shown besides the uploaded file to calculate the number of users who has viewed the file.
  
 #### Link Class Suffix
 Link Class Suffix sets a suffix to be applied to the CSS class of the download link.

### Image {#custom-field-image}
Image allows your users to upload image files along with their listings.

 #### Min. width & height
 Enter the size (width & height) of the image. This will also be the minimum width and height required for the images uploaded by your users for this field. Enter 0 to use the value configured for listing thumbnail's size.
 
 #### Max. File Size (in bytes)
 This is the maximum file size for the uploaded file in bytes. Default is 3MB (3145728 bytes). Enter 0 for no limit. Note that your server may have a maximum upload limit.

### Listing ID {#custom-field-listingid}
////

### Month & Year {#custom-field-monthandyear}
Mosets Tree allows you to create a field for users to enter only month and year, without day. 
 
 #### Start Year
 Set a starting year or earliest year available for selection. If left empty, it will default to 70 years ago from the current year.
 
 #### End Year
 End Year is the latest year that available for selection. If left empty, the current year will be used.
 
 #### Date Format
  Date Format decides how the date to be displayed for the field. For example, the [format](http://php.net/strftime) entered should be like "%M %Y", without quotes.

### Number {#custom-field-number}
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
 This sets the separator for the decimal point. By default, it is a dot (.). 
 
 #### Thousand Separator
 You can customize the thousand separator. By default, it is a comma (,). 

### Skype {#custom-field-skype}
Mosets Tree provides a link in listings for users to connect the listing's owners through Skype. 

 #### Action 
 You can decide which action you want the Skype link works. You can set the link as to view the Skype profile of the listing's owner, add the owner to own Skype's contact, call or start a text chat with the listing's owner or send a file to the listing's owner through Skype.

### Tags {#custom-field-tags}
//////

### Terms & Condition {#custom-field-termsandcondition}
Depending on your type of directory, you may want your users to agree on certain terms and conditions before they can add any listings. This field type provides a link so your users can read the terms and conditions prescribed.

 #### Select T&C Article
 You may select a Terms & Conditions article from the list provided. 
 
 #### Text
 You can customize the T&C text that will appear beside the checkbox. You can use {article_title} and {article_url} as a placeholder for the title and URL of the selected article from Select T&C Article section.

### Text {#custom-field-text}
Text enable the user to input text information and to be displayed in listing details later.  

 #### Input type
 For both Single and Multi-line text box, the size option is used to control the width and height of the respective textbox.
 
 #### Max. characters in Summary view
 You may show full text in Summary view regardless of the field length by enter 0 into this option.
 
 #### Max. characters in Details view
 You may show full text in Details view regardless of the field length by enter 0 into this option.
 
 #### Columns
 Columns specify the width (in columns) of multi-line textbox if it is selected from the Input type section. You can specify the height (in rows) of the textbox by using Size option at the [Basic Settings]({{version}}/fields#edit-screen).
 
 #### Preserve newline
 If you're using a Multi-line textbox, this option allow you to control where to preserve the newline in the text that is entered. You can either choose to preserve newline in Details view only or Summary view only, or you can choose to preserve newline in both of the views.
 
 #### Parse URL as link in Details view
 Sometimes, texts inserted in the field may contain URLs.Turn on this option so the URLs will parsed as link in Details view. 
 
 #### Style
 Style allows you to specify additional CSS style for the input field.

### Text Editor {#custom-field-texteditor}
Mosets Tree provides WYSIWYG editor as the text editor. Users can insert content such as texts and images into a WYSIWYG editor and the appearance of the content when it is displayed will be closely corresponding to what is inserted in the editor. 

 #### Load Buttons
 If it is set to "Yes", all editor buttons (except pagebreak and readmore) will be loaded.

### Time Zone {#custom-field-timezone}
Time Zone provides a drop down list of time zones for your users to select. 

### Vanity URL {#custom-field-vanityurl}
Mosets Tree allows you to set the vanity URL for your users so they will be able to provide a specific page of the predefined website whenever they add a new listing. 

 #### URL Format
 You may specify the URL format. Use {username} as a placeholder for the user defined name. For example:  
 http://www.twitter.com/{username}
 
 #### Display Format
 You may also specify the format in which the vanity URL is displayed. Use {username} as a placeholder for the user defined name. For exmaple:  
 @{username}
 
 #### Link Title
 This will be added to the link as Title attribute. You can use this to provide additional information about the link. Most browser display title text as a tooltip when it is hovered over. User {username} as a placeholder for the user defined name. For example:  
 Follow the user @{username}
 
 #### Link Image
 Instead of showing link in texts form, you can set to use graphics to represent every link. Enter the URL of an image. This will be used for the weblink instead of the Vanity URL text. You can use {live_site} as the replacement for the value of your site's domain. For example:  
  {live_site}/images/banners/white.png
  
 #### Max. number of characters
 This option decides the maximum number of characters that users can enter for their vanity URL username.
 
 #### Show Go button
 This Go button will be available beside Vanity URL's field of the back-end Edit Listing page to allow administrator a fast way to open the linked website.
 
 #### Enable nofollow attribute
 "nofollow" is an HTML attribute value used to instruct some search engines that a hyperlink should not influence the link target's ranking in the search engine's index. Enabling this parameter will append the nofollow attribute to all links created using Vanity URL field type.
 
 #### Use GA tracking
 If your site uses Google Analytics, this option allows you to track outbound link through Vanity URL field. Please make sure you have Google Analytics running on your site and have the latest version of the tracking code before using this.
 
 #### GA's outbound directory
 If you use Google Analytics, this parameter allows you to enter an outgoing directory where all outbound clicks through Vanity URL field will be recorded. More information is available [here](https://support.google.com/analytics/answer/1136920?cbid=1aul57ykjrzdd&src=cb&rd=1).

### Video Player {#custom-field-videoplayer}
Mosets Tree allows your users to submit video along with their new listings. You can specify the width and height of the video player and whether or not to start the video automatically. 

### Web link {#custom-field-weblink}
Web link allows your users to add a link to their listings so they can redirect their visitors whoever reading the listing to a specific website.

 #### Link Text
 Use this parameter to specify the link text. If this option is left empty, the full URL will be displayed as the link's text. If you specify an image to represent the link, link's text will be used for its ALT attribute.
 
 #### Link Title 
 This will be added to the link as Title attribute. Use this to provide additional information about the link provided by the listing's owner. Most browsers display title text as a tooltip when it is hovered over. 
 
 #### Link Image
 You can always replace texts with an image to display the link. Enter the URL of an image. This will be used for the weblink instead of the weblink URL. You can use {live_site} as the replacement for your site's base URL. For example:  
 {live_site}/images/banners/white.png
 
 #### Max. URL Length
 Enter the maximum URL's length before it is clipped.
 
 #### Use internal redirect
 Using internal redirect will hide the actual destination URL and use an internal URL to redirect users to the actual URL. This option also allows you to track the number of visits which the link gets. The number of visits can be shown in front-end interface when "Show Counter" option is set to "Yes".
 
 #### Show counter
 This option shows the number of visits the link has been clicked in front-end interface. Tracking the number of visits is only available when you use internal redirect.
 
 #### Clipped symbol
 Clipped symbol represents the remaining characters of a URL which exceeds maximum URL's length.
 
 #### Show Go button
 Go button will be available beside Web link's field of the back-end Edit Listing page to allow administrator a fast way to open the linked website.
 
 #### Accept FTP links
 Setting this option to "Yes" will enable Web link field to accept links with ftp:// protocol.
 
 #### Use nofollow attribute
  "nofollow" is an HTML attribute value used to instruct some search engines that a hyperlink should not influence the link target's ranking in the search engine's index. Enabling this parameter will append the nofollow attribute to all links created using Web link field type.
 
 #### Use GA tracking
 If your site uses Google Analytics, this option allows you to track outbound link through Web link field. Please make sure you have Google Analytics running on your site and have the latest version of the tracking code before using this.
  
 #### GA's outbound directory
 If you use Google Analytics, this parameter allows you to enter an outgoing directory where all outbound clicks through Web link field will be recorded. More information is available [here](https://support.google.com/analytics/answer/1136920?cbid=1aul57ykjrzdd&src=cb&rd=1).

### Year {#custom-field-year}
Sometimes, you only want the information about years and nothing else. Mosets Tree provides you this field for your users to enter only year, without month and day.

 #### Start year
 Enter the starting year or earliest year available for the selection. If this parameter is left empty, it will default to 70 years ago from the current year.
 
 #### End year
 Enter the latest year that available for selection. If this is left empty, the current year will be used.

### Youtube {#custom-field-youtube}
If you want your users to showcase a video, just use Youtube field type. Your users will be requested to enter a Youtube video link and Mosets Tree will display the Youtube video player inside the listing page.

 #### Search's checkbox label
 If you enabling searchable option, you can always search for the listings which contain video by clicking the checkbox field provided. This parameter allows you to define the checkbox element to be displayed to your users..
 
 #### Video player's width
 This parameter let you set the width of the video player to be displayed in Details view. If this parameter is left empty, default value will be set as width of the video player.
 
 #### Video player's height
 This parameter let you set the height of the video player to be displayed in Details view. Leave this parameter empty for default value.
 
 #### Parameter
 Mosets Tree allows you to enter additional Youtube parameters. Separate each parameter by comma. This allows you to control how Youtube is presented to your visitors. Visit [here](https://developers.google.com/youtube/player_parameters#Parameters) for more information.
 
 #### Youtube's Input description
 You can set an explanation for your Youtube field. You can tell your users what to insert into this field and guide your users by providing an example along with the description.

## Edit Screen Basic Settings {#edit-screen}

### Fieldtype

@TODO: ...

### Caption




