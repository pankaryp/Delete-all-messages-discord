# Delete-all-messages-discord

> Delete all messages in Discord channels or DMs

In order to delete messages in bulk, you need the discord authedication token. That's why this script only works with the **web version** of Discord. 

The authedication token can be obtained with [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo), which is a browser plugin.
After installing Tampermonkey, create a new script and add the below code:

!['plugin'](img/plugin.png?raw=true)

```javascript
// ==UserScript==
// @name         Discord Token
// @namespace    http://tampermonkey.net/
// @version      0.0.1
// @description  try to take over the world!
// @author       Untitled-1#0001
// @match        https://discordapp.com/channels/*/*
// @grant        none
// @run-at       document-start
// @license      MIT License
// ==/UserScript==

(function() {
    "use strict";
    console.log("Discord Token:" + localStorage.getItem("token"));
})();
```

When this is enabled, it will log your authentication token in the console before any of Discord's generated logs at the top of the console. (You might need to refresh at least once for it to start working).

!['token'](img/token.png?raw=true)

Now open Developer Tools (Ctr+Shift+I) and copy-paste delete-all-messages.js code into the console, after replacing the 'AUTH-TOKEN' and 'LAST_MESSAGE_ID'.
_You can find user id, message id, channel id and server id by enabling discord developer mode (settings/appearance) and right clicking the user's avatar , the message, the channel or the server._

```javascript
var before = 'LAST_MESSAGE_ID';
clearMessages = function() {
    const authToken = 'AUTH_TOKEN';
    ...
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.