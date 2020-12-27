# discordjs-menus
A lightweight package to paginate discord message for discord bots with ease!

# How to use? easy!
# Install using NPM
```properties
npm install discordjs-menus
```

# Example
```js
const BasePaginator = require('discordjs-menus')

const pages = ['foo', 'bar'] //return foo at the first page, and bar at the second page

const paginator = new BasePaginator({
    pages: pages, //the pages
    timeout: 120000, //the timeout for the reaction collector ended (in ms)
    filter: (reaction, user) => user.id == message.author.id //to filter the reaction collector
})

paginator.spawn(message.channel) //to spawn the paginator to specific text channel
```

# Explanation
```js
const Paginator = new BasePaginator({
    pages: Array<String || Discord.MessageEmbed>, //The pages, can contain string or message embed
    remove: String, //The emoji to despawn the paginator
    reset: String, //The emoji to reset the paginator to first page
    reaction: [String, String], //The emoji to move previous or next page
    removeReaction: Boolean, //Remove the user reaction when used
    removeAtEnd: Boolean, //Remove the reactions when the reaction collector is ended
    pageCount: Boolean, //Show the page counter to the message
    timeout: Number, //The timeout for the reaction collector ended (in ms)
    filter: Function //An additional filter for the paginator
})

await Paginator.spawn(Discord.TextChannel) //Spawn the paginator to specific text channel
```