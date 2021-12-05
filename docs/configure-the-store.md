# Configure the store

Before making any configuration in the store, you must read and configure a realm or several realms.

Remember that this documentation is available at the following link <a href="/wiki/create-a-realm" target="_blank">Create a realm</a>

Within the administration menu, we have an option to configure the store. It is located in the following path: `en/admin/store`.

**In it, we will find categories, items and a section called top to highlight some of them**.

![store](https://user-images.githubusercontent.com/2810187/144719000-9b50def0-69d0-4ed4-8928-537a10d08854.png)

1. The first thing to create is a category

![category](https://user-images.githubusercontent.com/2810187/144719087-09dcb767-4849-4f36-b8f8-dbf59a7891c2.png)

- **Name:** This is the name of the category, e.g., mounts.
- **Realm:** It is a list of the kingdoms that are created, that is why they must be created first.
- **Type:** It has 2 options, normal and dropdown.
- **Child Menu:** Is it related to any other category?.
- **Route / slug:** It is used to create the URL of the category. e.g., mounts.

After we create the category, we can create the items of the store: `en/admin/store/items`

![create_item](https://user-images.githubusercontent.com/2810187/144731728-1ee55db9-6a24-494e-89f2-592a0f889cf7.png)

- **Name:** Item name.
- **Description:** Information about the item you are creating.
- **Category:** The category to which it belongs, previously created.
- **Type:** Item, Money, Level, Rename, Customize, Change Faction, Change Race.
- **Icon Name:** It is the icon of the item, you can get it at wowhead.
- **Price Type:** DP, VP or both.
- **DP Price:** Amount of Donation Points.
- **VP Price:** Amount of Vote Points.
- **Command:** In command, you must not type a command. It is only the number.

Next, we will go into detail with the information.

- In the case of the item, the item id, only the item id, must be added. Followed by the quantity, if necessary.
> Ex. 12345:2 That would send item 12345, with a quantity of 2 units.
> You can also send several items, leaving a space between them. Ex. 12345:2 54321:4
