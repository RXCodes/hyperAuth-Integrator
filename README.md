# Brief Introduction
This plugin integrate features of the hyperPad discord server into hyperPad projects - creating an ecosystem that promotes collaboration, innovation and fun!
Download the plugin [here](https://raw.githubusercontent.com/RXCodes/hyperAuth-Integrator/main/hypeToken%20Integrator.plugin).

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
The plugin will use the `Broadcast Message` and `Receive Message` behaviors to interact with the plugin. If you are unfamiliar with how those behaviors work, please refer to the [Broadcast Message documentation](https://hyperpad.zendesk.com/hc/en-us/articles/360016293712) and the [Receive Message documentation](https://hyperpad.zendesk.com/hc/en-us/articles/360016294052-Receive-Message). These behaviors send and receive data across objects, so it is very useful in this plugin.

You will also need to know `Dictionaries` - they serve the purpose of storing data in an intuitive manner. If you are unfamilar with how dictionaries work or how to use them, you can either watch the [hyperPad 101 Tutorial video](https://youtu.be/ln5JYzhAE9I) or read [hyperPad's documentation](https://hyperpad.zendesk.com/hc/en-us/articles/360016300172-Dictionary).

## Requesting a Purchase
When requesting a purchase, an uneditable popup will ask the user to buy an item from the seller.
![2D80E4E9-B59A-449E-9A3A-EA034033E12D](https://user-images.githubusercontent.com/61912060/174916527-f8e05954-d39a-4928-9e52-38e23f3ce420.jpeg)

