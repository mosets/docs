# Importer

MT importer helps you to import stuff to Mosets Tree. Yay!

## Import from CSV
This Importer will import all listings from a .csv files. Download a sample and start by adding your listings to the file. Please bear in mind the following when adding listings:  
- The first line of sample.csv contains the list of column names that map to Moset Tree's database. Only the first column **- link_name** is compulsory. Other columns are optional and can be safely removed. If you're removing a column, make sure you remove the corresponding values for the listings.
- Second line and onwards is where you insert your data. One line for each listing. In sample.csv, the second line is filled with one sample listing.
- You may use Microsoft Excel or any other word processor to edit the file. Make sure you do not save the formatting when prompted.
- Enter Category ID to the **cat_id** field. This information can be found when you're browsing the category. If no cat_id is specified, Importer will import the listing to Root category (0). To import a listing to more than one category, specify the category IDs separated by command. ie: "2,6,17"
- Enter User ID to the **user_id** field. This information can be found from your database table called pklzm_users. If no user_id column is specified, the listing will be owned by you (username: **admin**) by default.
- If you want a particular listing to be featured, set **link_featured** field to 1, otherwise set it to 0.
- There is no need to enter **link_published** or **link_approved**'s value. All imported listings will be published and approved automatically.
- If you want to import a particular column to an existing custom field, use the ID of the custom field as the column name. In the sample, the last 2 columns are mapped to custom fields with ID 25 and 26. You can locate these IDs at Custom Fields page.
- Any column names that are not mapped to pklzm__mt_links table or a custom field ID will assigned to a new text-based custom field.
- If you have multiple values in a column (Checkbox or Multiple select box), separate each values with the bar character. For example - value1|value2|value3
- The field separator is comma (,) and the fields should be enclosed by double quote if the values contains comma.
- Use the Dry Run option to check if your CSV file is properly formatted. Dry run will scan your CSV file and report any errors if it finds any. Importing using the dry-run option does not write any data to your database.

What this Importer doesn't do:  
- It does not support importing files or binary based data.
- It does not create categories. You have to create the categories first before starting the import.

WARNING: **PLEASE BACKUP YOUR DATABASE BEFORE PROCEEDING TO THE NEXT STEP.** Although we have done everything possible to minimize the risk of database corruption, accident do happens once a while. Backing up your database is the best protection to this.

To import:

1. Login to your Joomla's administrator back-end.
2. Goto "**Components -> MT Importer -> Import from .csv file**".
3. Click "**Choose File**" to select .csv file from your computer.
4. Click "**Import**" to start the import process.

You will be notified and redirected to Mosets Tree main page when the import is completed. Since you're importing data from another source, you need to perform "**Recount Cats/Listings**" after the import process is complete. This function will recount the number of categories and listings you have in Mosets Tree.



## Import from Hot Property
MT Importer will import all types, companies, agents and properties from Hot Property 1.0 to Mosets Tree version 3.5. During the import, 3 new top level categories will be created, namely 'Hot Property Properties', 'Hot Property Agents' and 'Hot Property Companies' to store the imported properties, agents and companies respectively.

No data will be removed during or after the import process. Any data that you currently have in Mosets Tree will be retained.

### Requirement
This importer requires Hot Property data from version 1.0 and an installed copy of Mosets Tree 3.5.

You need to make sure the following database tables and image paths exists in order for the import to proceed:
- Database tables: pklzm_hp_agents, pklzm_hp_companies, pklzm_hp_photos, pklzm_hp_properties, pklzm_hp_properties2, pklzm_hp_prop_ef, pklzm_hp_prop_types
- Image paths:  
C:\xampp\htdocs\joomla/media/com_hotproperty/images/std,  
C:\xampp\htdocs\joomla/media/com_hotproperty/images/thb,  
C:\xampp\htdocs\joomla/media/com_hotproperty/images/ori,  
C:\xampp\htdocs\joomla/media/com_hotproperty/images/agent,  
C:\xampp\htdocs\joomla/media/com_hotproperty/images/company

To import:

1. Login to your Joomla's administrator back-end.
2. Goto "**Components -> MT Importer -> Import from Hot Property**".
3. Click "**Import**" to start the import process.

You will be notified and redirected to Mosets Tree main page once the import is complete. Since you're importing data from another component, you need to perform "**Recount Cats/Listings**" after the import process is complete to recount the number of categories and listings you have in Mosets Tree. This function is available under the "**Tools**" section in Mosets Tree back-end.