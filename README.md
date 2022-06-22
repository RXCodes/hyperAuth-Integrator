# Brief Introduction
This plugin integrate features of the hyperPad discord server into hyperPad projects - creating an ecosystem that promotes collaboration, innovation and fun!
Download the plugin [here](https://raw.githubusercontent.com/RXCodes/hyperAuth-Integrator/main/hypeToken%20Integrator.plugin).
The version of the plugin is **v2**.

Currently, all the plugin offers right now are **Hype Tokens** - a `virtual currency` used by the hyperPad discord server. Hype Tokens can be used to purchase in-game goods within a project under a Discord account.

# Setting Up the Plugin
![B6FE93B3-DB23-4155-8C23-0E58288F2294](https://user-images.githubusercontent.com/61912060/174915536-432f9976-8987-4762-bf3c-35efb5186a12.jpeg)


- 1. After installing the plugin file linked above, navigate to the [hyperPad Project Modder](https://rxcodes.github.io/hyperPad-Project-Modder/) to set up the plugin.

- 2. Import your hyperPad project file by pressing the **Import File** button. It is worth noting that the hyperPad Project Modder will only accept `.tap` files.

- 3. After importing the project, navigate to `Manage Plugins`. This is where all your plugins will be displayed. If you have not imported a plugin in your project before, the plugins list should be blank.

- 4. Press `Import Plugin` and select the plugin file to install the plugin. If you are updating from a previous version of the plugin, remove the outdated plugin *before* installing the newer version of the plugin. To delete a plugin, click on the plugin icon and confirm the deletion action.

- 5. It might take *some time* for your plugin to install - you can expect the loading animation to freeze for large plugin files. After installing / updating the plugin, navigate back to the main menu and **Download** your modified project. Compiling a project can take some time, so hang on tight!

- 6. After the project has been compiled, you can download your project and open it in hyperPad. The newly modified project will contain the plugin. You are free to delete the original project, but it is safer to have copies of your project before and after modding a project as the hyperPad Project Modder is in `beta` - hyperPad can corrupt your entire project.<br>

# Using the Plugin API
You'll know the plugin is installed when you can see the `hypeTokens Manager` icon in the **Assets** menu - it is placed in the main directory *outside all folders*. You are free to rename and move this asset somewhere else, but deleting it will cause the plugin to malfunction as of `version 2.0 and above`.

The plugin will use the `Broadcast Message` and `Receive Message` behaviors to interact with the plugin. If you are unfamiliar with how those behaviors work, please refer to the [Broadcast Message documentation](https://hyperpad.zendesk.com/hc/en-us/articles/360016293712) and the [Receive Message documentation](https://hyperpad.zendesk.com/hc/en-us/articles/360016294052-Receive-Message). These behaviors send and receive data across objects, so it is very useful in this plugin.

You will also need to know `Dictionaries` - they serve the purpose of storing data in an intuitive manner. If you are unfamilar with how dictionaries work or how to use them, you can either watch the [hyperPad 101 Tutorial video](https://youtu.be/ln5JYzhAE9I) or read [hyperPad's documentation](https://hyperpad.zendesk.com/hc/en-us/articles/360016300172-Dictionary).

## Requesting a Purchase
When requesting a purchase, an uneditable popup will ask the user to buy an item from the seller. The user has the option to cancel *or* pay the price seen on the popup using their discord account.
![BC8423ED-8AC2-4019-8C6E-0732BA12ADCB](https://user-images.githubusercontent.com/61912060/174916859-d5f8ce7c-731c-42d1-becd-e851b3e05e0e.jpeg)

Broadcast event: `hypeToken Purchase`<br><br>
Broadcast value: `{dictionary}`
  - `name`: *(required)* The name of the product being sold.
  - `cost`: *(required)* The amount of hype tokens the product should sell for.
  - `type`: *(required)* The type of product being sold. Must be one of the strings defined below.
    - **"Consumable"** - The product can be purchased multiple times.
    - **"Non-Consumable"** - The product can only be purchased once. The user will not be charged for repeat purchases.
    - **"Subscription"** *(v3)* - The user must purchases a subscription that is only valid for a limited amount of time. The user has a choice to automatically renew the subscription and can cancel it anytime.
    - **"Limited Time"** *(v3)* - The product is only available for a limited amount of time.
  - `seller`: *(required)* The discord tag of a user in the hyperPad discord server who is selling the product.
  - `icon`: *(required)* The path to your graphic asset you want to use for the icon of the purchase. 
  - `id`: The identifier of the product. The ID should be a *unique 16-character-long string* of random characters. The same ID will reference the same product, so make sure this doesn't change for your product at all. This property is only required for `Non-Consumable` and `Subscription` product type.
  **Version 2**
  - `description`: The description of the product. This will show up next to the icon in the popup.
  - `discount`: The integer percentage of the original cost to decrease the price by. *(Range: 10-90)* This also triggers a visual event to show the original price vs the discounted price to inform the user of the discount.
  **Version 3** (unreleased)
  - `subscriptionType`: The type of subscription to offer the user.
    - **"Weekly"**: The user will be charged on a weekly basis. *(Every 7 days)*
    - **Bi-Weekly**: The user will be charged once every 2 weeks. *(Every 14 days)*
    - **"Monthly"**: The user will be charged on a monthly basis. *(Every 30 days)*
  - `limitedOfferEnds`: The *UNIX timestamp* of when the limited time offer ends. If set, a countdown will be displayed on the popup. This property is required for `Limited Time` product type.

## Handling Purchase Results
When the transaction is complete and 
