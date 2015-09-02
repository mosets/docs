# Access Control List

- [Permissions]({{version}}/acl#permissions)
- [View Access Levels]({{version}}/acl#view-access-levels)
	- [Category View Access Levels]({{version}}/acl#category-view-access-levels)
	- [Listing Details View Access Levels]({{version}}/acl#listing-details-view-access-levels)
	- [Custom Fields View & Edit Access Levels]({{version}}/acl#custom-fields-view-and-edit-access-levels)

## Permissions {#permissions}

Mosets Tree has comprehensive support for [Joomla ACL](https://docs.joomla.org/J3.x:Access_Control_List_Tutorial) that gives you fine grain control on which user groups has permission to perform tasks within your Mosets Tree directory. This includes permission on creating listings & categories, rating, reviews, contact, recommend, report and claim.

It's important to note that you still need to make sure the feature in Mosets Tree's Configuration are enabled or disabled when you change permission in Mosets Tree.

You can access Mosets Tree's Permissions at:

Joomla's **Global Configuration -> Mosets Tree**

You can find a link to the same page under Mosets Tree's **Configuration**.

## View Access Levels {#view-access-levels}

With Joomla's View Access Levels, you can specify the view level for top level categories, listing details and custom fields. For example, you can restrict your listing details page to your special group of suppliers or allow downloads of your floor plan PDFs to a higher privileged user groups.

### Category View Access Level {#category-view-access-levels}

Category's view access level is only available to top level categories.

To access this configuration:

1. Edit a top level category in Mosets Tree's back-end.
2. Click on **Category Configuration** tab.
3. Select the **Main** panel.
4. Check the checkbox for **View access level**.
5. Select which user levels has access to the category.

Category's View access level will affect the user ability to view the top level category, including all its sub-categories and related listings pages such as _Recently Added_, _Popular_ and _Advanced Search_. Note that listings published to the category are still accessible and not affected in any way by the category's view access level.

### Listing Details View Access Level {#listing-details-view-access-levels}

Listing details' view access level allows you to control who can click in to a listing to view the listing details page.

To access this configuration:

1. Edit a top level category in Mosets Tree's back-end.
2. Click on **Category Configuration** tab.
3. Select the **Listing** panel.
4. Check the checkbox for **Listing details view access level**.
5. Select which user levels has access to listing details.

This will only affect your users ability to view listing details page.

### Custom Fields View & Edit Access Levels {#custom-fields-view-and-edit-access-levels}

Custom fields' view access level allows you to control who can view a field (caption and output) in front-end. You can use this, for example, to show a basic set of listing information to _Public_ user group, while showing all listing information to logged in customers only.

Custom fields' edit access level allows you to control who can edit a field in front-end. You can use this, for example, to offer different types of listing package to your users, where only _Premium_ user can upload attachments.

To access these configuration, go to:

1. Go to **Mosets Tree -> Custom Fields**
1. Edit a custom field.
3. Change the access level at **View access level** or **Edit access level**.




