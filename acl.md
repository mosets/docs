# Access Control List

- [Permissions]({{version}}/acl#permissions)
- [View Access Levels]({{version}}/acl#view-access-levels)
	- [Category View Access Levels]({{version}}/acl#category-view-access-levels)
	- [Listing Details View Access Levels]({{version}}/acl#listing-details-view-access-levels)
	- [Custom Fields View & Edit Access Levels]({{version}}/acl#custom-fields-view-and-edit-access-levels)
- [Managers]({{version}}/acl#managers)

## Permissions {#permissions}

Mosets Tree has comprehensive support for [Joomla ACL](https://docs.joomla.org/J3.x:Access_Control_List_Tutorial) that gives you fine grain control on which user groups have permission to perform tasks within your Mosets Tree directory. This includes permission on creating listings & categories, rating, reviews, contact, recommend, report and claim.

It's important to note that you still need to make sure the features in Mosets Tree's Configuration are enabled or disabled when you change permission in Mosets Tree.

You can access Mosets Tree's Permissions at:

Joomla's **Global Configuration -> Mosets Tree**

You can find a link to the same page in Mosets Tree's **Configuration**, under the **Permission** tab.

## View Access Levels {#view-access-levels}

With Joomla's View Access Levels, you can specify the view level for top level categories, listing details and custom fields. For example, you can restrict your listing details page to your special group of suppliers, or allow downloads of your floor plan PDFs to a higher privileged user groups.

### Category View Access Level {#category-view-access-levels}

Category's view access level is only available to top level categories.

To access this configuration:

1. Edit a top level category in Mosets Tree's back-end.
2. Click on **Category Configuration** tab.
3. Select the **Main** panel.
4. Check the checkbox for **View access level**.
5. Select which user levels have access to the category.

Category's View access level will affect the users ability to view the top level category, including all its sub-categories and related listings pages such as _Recently Added_, _Popular_ and _Advanced Search_. Note that listings published to the category are still accessible and are not affected in any way by the category's view access level.

### Listing Details View Access Level {#listing-details-view-access-levels}

Listing details' view access level allows you to control who can click a listing to view the listing details page.

To access this configuration:

1. Edit a top level category in Mosets Tree's back-end.
2. Click on **Category Configuration** tab.
3. Select the **Listing** panel.
4. Check the checkbox for **Listing details view access level**.
5. Select which user levels has access to listing details.

This will only affect your users ability to view listing details page.

### Custom Fields View & Edit Access Levels {#custom-fields-view-and-edit-access-levels}

Custom fields' view access level allows you to control who can view a field (caption and output) in front-end. You can use this, for example, to show a basic set of listing information to _Public_ user group, while showing all listing information to logged in customers only.

Custom fields' edit access level allows you to control who can edit a field in front-end. You can use this, for example, to offer different types of listing packages to your users, such as, only _Premium_ users can upload attachments.

To access these configuration, go to:

1. Go to **Mosets Tree -> Custom Fields**
1. Edit a custom field.
3. Change the access level at **View access level** or **Edit access level**.

## Managers {#managers}

Managers are users who can create, edit or delete listings in the front-end, even when they do not own the listings. This allows you to assign user groups to manage your directory. 

To configure your managers, go to **Mosets Tree** -> **Permission**.

This will configure managers for your entire directory. You can also assign managers to manage your top level categories:

1. Edit a top level category in Mosets Tree's back-end.
2. Click on **Category Configuration** tab.
3. Select the **Permission** panel.
4. Check one or more of the permissions you want to override and then check the corresponding user group checkboxes you want to assign as the managers.

**Edit listing** and **Delete listing** permission lets you control if your managers are allowed to edit and delete listings. 

Similarly, Managers' **Create listing** permission lets you control if your managers can create listings. You may recall that the [Permissions]({{version}}/acl#permissions) has a similar permission with the same name. This is a permission configured under Joomla's Configuration and applies directory-wide to all users. When you have 2 different permissions configured to the same user group, the managers permissions will be used.

With Managers' **Create listing** permission, you setup your directory in such a way that only a particular set of user groups can submit to one or more top level categories. An example setup that achieves this is configured as follows:

1. First, disable users' permission to create a listing. This sets up a blank slate to let us choose who can create listings in which categories later on. To do this, disable all users permissions to create listing:
	1. Go to Mosets Tree's back-end **Configuration**.
    2. Click on **Permission** tab.
    3. Click on the **Edit Permissions...** button.
    4. For both **Public** and **Registered** user groups, set their **Create Listing** permission to **Denied**.
    5. Click the **Save** button to save the changes.
2. Next, edit a top level category.
3. Click on **Category Configuration** tab.
4. Select the **Permission** panel.
5. Check the checkbox for **Create listings**.
6. Finally, select one or more user groups next to the **Create listings** label. These are the user groups you want to grant permission to create listings in the front-end. Remember, we are editing a top level category's configuration, so this permission only applies to this top level category and all its sub-categories.
7. Click the **Save** button to save the changes.





