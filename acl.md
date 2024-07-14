# Access Control List

- [Permissions]({{version}}/acl#permissions)
- [View Access Levels]({{version}}/acl#view-access-levels)
	- [Category View Access Levels]({{version}}/acl#category-view-access-levels)
	- [Listing Details View Access Levels]({{version}}/acl#listing-details-view-access-levels)
	- [Custom Fields View & Edit Access Levels]({{version}}/acl#custom-fields-view-and-edit-access-levels)
- [Managers]({{version}}/acl#managers)

## Permissions {#permissions}

Mosets Tree offers comprehensive support for [Joomla's Access Control List (ACL)](https://docs.joomla.org/J3.x:Access_Control_List_Tutorial), providing granular control over which user groups can perform specific tasks within your Mosets Tree directory. This includes permissions for creating listings and categories, rating, reviewing, contacting, recommending, reporting, and claiming listings. 

Note that while you can manage permissions in Mosets Tree, remember to also ensure the features are enabled or disabled in the Mosets Tree Configuration settings.

Access Mosets Tree's Permissions through:

- Joomla's **Global Configuration -> Mosets Tree**
- Mosets Tree's **Configuration**, under the **Permission** tab.


## View Access Levels {#view-access-levels}

Joomla's View Access Levels allow you to specify view permissions for top-level categories, listing details, and custom fields. For example, restrict access to listing details pages to a specific group of suppliers or grant higher-privileged user groups access to download floor plan PDFs.

### Category View Access Level {#category-view-access-levels}

Category View Access Levels apply only to top-level categories.

To configure:

1. Edit a top-level category in the Mosets Tree back-end.
2. Click on **Category Configuration**.
3. Select the **Main** panel.
4. Check the **View access level** checkbox.
5. Choose which user levels have access to the category.


Category View Access Level affects users' ability to view the top-level category, including its subcategories and related listing pages such as _Recently Added_, _Popular_, and _Advanced Search_. Note that listings published to the category remain accessible regardless of the Category View Access Level setting.

### Listing Details View Access Level {#listing-details-view-access-levels}

Listing Details View Access Levels control who can view individual listing details pages.

To configure:

1. Edit a top-level category in the Mosets Tree back-end.
2. Click on **Category Configuration**.
3. Select the **Listing** panel.
4. Check the **Listing details view access level** checkbox.
5. Choose which user levels have access to view listing details.

### Custom Fields View & Edit Access Levels {#custom-fields-view-and-edit-access-levels}

Custom fields offer granular control over who can view and edit them on the front-end. 

The "View access level" determines who sees a field's caption and output. For example, you could display basic listing information to public users while revealing full details only to logged-in customers.

Similarly, the "Edit access level" controls who can modify a field. This enables features like tiered listing packages, where only premium users can upload attachments.

To configure these settings:

1. Navigate to **Mosets Tree -> Custom Fields**.
2. Edit an existing custom field.
3. Adjust the access level under either "View access level" or "Edit access level."

## Managers {#managers} 

Managers are users with permissions to create, edit, or delete listings in the front-end, even if they don't own them. This allows you to assign user groups to manage your directory.

To configure managers, go to **Mosets Tree** -> **Permission**. 

This configures managers for your entire directory. You can also assign managers to specific top-level categories:

1. Edit a top-level category in Mosets Tree's back-end.
2. Click the **Category Configuration** tab.
3. Select the **Permission** panel.
4. Check the permissions you want to override (e.g., **Edit listing**, **Delete listing**, **Create listing**). Then, select the corresponding user groups you want to assign as managers.

Remember that the **Create Listing** permission in Joomla's Configuration applies directory-wide. When both directory-wide and category-specific permissions exist for the same user group, the category-specific permissions take precedence. 

Use the **Create listing** permission to control which user groups can submit listings to specific top-level categories:

1. Disable the default **Create Listing** permission for all users (**Public** and **Registered**). Go to Mosets Tree's back-end **Configuration**, click the **Permission** tab, and set both user groups' **Create Listing** permission to **Denied**.
2. Edit a top-level category.
3. Click the **Category Configuration** tab.
4. Select the **Permission** panel.
5. Check the **Create listings** checkbox.
6. Select the desired user groups next to the **Create listings** label. These groups will now have permission to create listings in this top-level category and its subcategories.

Click **Save** to confirm your changes.