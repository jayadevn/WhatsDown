# WhatsDown

An experiment in backing up your WhatsApp chats using the WhatsApp Web interface and a Chrome extension.

## Current state

UPDATE: A very preliminary version of the Chrome extension side of things works now. The server is being done now.

WhatsDown does not work right now. It's still in initial stages of development, and I can only spend so much time on it every month. I have no schedule on when it will be finally usable, but it will (probably) be ready some day. Feel free to raise issues if you need anything, or watch the repo to follow it.

## The idea

### i. Background

Whether you like it or not, WhatsApp is by far the most popular messaging application today. But it also requires you to keep a copy of every message you ever sent on your mobile device, indefinitely. At some point the store is going to grow large enough to fill your phone memory. I know it happened to me. WhatsApp has no solution to it. It simply grows in size until it crashes and then you're forced to let go of old messages. WhatsDown is an attempt to handle this issue.

### ii. How it works

WhatsDown is totally passive. It lives in two parts—a Chrome extension, and a Node server running locally. The Chrome extension reads messages on WhatsApp Web, and posts it to the local WhatsDown server. The server then saves it to a flatfile database. A web or desktop application can then be written to read and display these messages whenever you want, with no connection to the internet or WhatsApp on your phone.

WhatsDown is passive—it does not actively send new requests to WhatsApp, or attempt to reverse engineer the API. It simply reads messages from the browser. Hence there is no risk to your existing messages or your WhatsApp account.

WhatsDown is private—none of your messages are sent to a remote server. It all lives on your computer until you decide to backup to any destination of your choice.

### iii. Caveats

Since WhatsDown passively watches texts on WhatsApp Web, it is impossible to get messages that were never opened on the browser. As a result, WhatsDown is perfect for someone (like me) who spends most of their time on WhatsApp Web as opposed to the Android/iOS app.

### iv. Problems

There are still some unsolved problems, like how to assign a unique ID to each chat? I have worked out separating private chats from group chats, but there is no protection against two private chats with the same contact name, or two group chats with the same name and same members from messing up your chat history.

## Version History

`v. 0.2.0` : Chrome extension now works. As new messages are loaded, they are parsed and stored as objects.

`v. 0.1.1` : This entire enterprise is a wack-a-mole. Deal with one bug, two more arises. Putting the project on hold, because I have to get a life.

`v. 0.1.0` : Bug fixes

`v. 0.0.1` : Initial commit. When the extension icon is clicked, all the messages in current chat will be logged in console.
