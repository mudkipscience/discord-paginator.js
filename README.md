# discord-paginator.js
A lightweight package to paginate discord message for discord bots with ease!

# How to use? easy!
# Install using NPM
```properties
npm install discord-paginator.js
```

# Example
```js
const BasePaginator = require('discord-paginator.js')

const pages = ['foo', 'bar'] //return foo at the first page, and bar at the second page

const Paginator = new BasePaginator({
    pages: pages, //the pages
    timeout: 120000, //the timeout for the reaction collector ended (in ms)
    page: 'Page {current}/{total}', //Show the page counter to the message
    filter: (reaction, user) => user.id == message.author.id //to filter the reaction collector
})

Paginator.spawn(message.channel) //to spawn the paginator to specific text channel
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
    pageCount: String, //Show the page counter to the message
    timeout: Number, //The timeout for the reaction collector ended (in ms)
    filter: Function //An additional filter for the paginator
})

await Paginator.spawn(Discord.TextChannel) //Spawn the paginator to specific text channel
```