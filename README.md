# Streamroller (current dev. stage: Alpha)
## Table of Contents

- [Streamroller (current dev. stage: Alpha)](#streamroller-current-dev-stage-alpha)
  - [Table of Contents](#table-of-contents)
- [Contacts: (For questions, suggestions etc.)](#contacts-for-questions-suggestions-etc)
- [Download/Installing](#downloadinstalling)
- [Videos](#videos)
  - [While streaming](#while-streaming)
  - [Streaming setup (Getting it to do fun and interesting stuff while streaming)](#streaming-setup-getting-it-to-do-fun-and-interesting-stuff-while-streaming)
- [Security](#security)
- [Some of the current extensions](#some-of-the-current-extensions)
  - [Logic/Controller/Display style extensions](#logiccontrollerdisplay-style-extensions)
  - [Webpages](#webpages)
    - [Liveportal](#liveportal)
    - [Adminpage](#adminpage)
    - [Overlay](#overlay)
  - [Feature/Datahander extensions](#featuredatahander-extensions)
    - [twitchchat](#twitchchat)
    - [Chatbot](extensions/chatbot) [README](extensions/chatbot/README.md)
    - [discordchat](#discordchat)
    - [streamlabs\_api](#streamlabs_api)
    - [twitter](#twitter)
    - [obs](#obs)
  - [Feature Extensions](#feature-extensions)
  - [In progress](#in-progress)
  - [Ideas for extensions](#ideas-for-extensions)
- [For the Dev's/Coders out there](#for-the-devscoders-out-there)
  - [Server](#server)
  - [functional extensions](#functional-extensions)
  - [Extensions can be of different types](#extensions-can-be-of-different-types)

# Contacts: (For questions, suggestions etc.)
- [Discord, (streamroller-stuff channel)](https://discord.gg/EyJy8brZ6R). 
- [twitch.tv/OldDepressedGamer](https://twitch.tv/OldDepressedGamer). 

# Download/Installing
You can find the releases on the relase page on the right of this screen or click [here](https://github.com/SilenusTA/StreamRoller/releases) to go right to them.
To run streamroller just grab the zip (or exe) and save it somewhere. Double click to run the StreamRoller server and then head to you webbrowser and enter [localhost:3000](http://localhost:3000)

In order to be useful you will need to enter your details for whatever parts of StreamRoller you wish to use. To do this click on the Admin link on the web page you loaded above. There is a list of credentials you can enter (depending on what parts of StreamRoller you want to use).

On these links there will be instruction on where to find your tokens etc for each feature.

I.e. if you only want the AI chatbot then you will need the twitchchat tokens (to enable posting into chat) and an openAI token (to perform requests for the chat messages)

# Videos
Installing StreamRoller

[![Watch the video](https://img.youtube.com/vi/nIf06vKJpBw/hqdefault.jpg)](https://youtu.be/nIf06vKJpBw)

## While streaming
StreamRoller is designed to bring all the tools needed for streaming into one web page so when streaming you have all your controls on one screen and not have to worry about swapping programs (or even running them). Eventually the you will only need StreamRoller and OBS for all your streaming needs ... if I ever get round to coding up enough extensions:D

## Streaming setup (Getting it to do fun and interesting stuff while streaming)

The Main reason I started making StreamRoller was so I could have all my streaming tools on one webpage and be able to configure them easily.

I also wanted a easier way of making things happen. i.e. triggering things from donations (post a thanks on twitter/discord) or in future (when I get round to adding the code) maybe flash your Hue LED lights/stream lights when someone subs.

The plan is to extend StreamRoller extension list to cover all the things that might be needed. 

Once an extension is made (ie the twitter one) then it is easy to do things like sending messages when something happens 'sendTwitterMessage("hi twitter")'

For now it is relativly easy for me to link together events just using simple javascript coding on the webpage. 
It is almost at the point where I can write ...

``` 
if (alert.type="donation") 
    sendtotwitter ("thanks for the donation" + alert.from)
```
Although this isn't great for people who don't code so I do plan (somewhere in the future) of trying to get the setup (ie what to do when a tweet comes in) in a more usable fashion. This will probably anothe webpage to configure what you want it do to for you (ie Flash my Philips Hugh lights when someone donates), if chat is happy (an inprogress extension to predict the mood of chat) then set the appropriate song list up to play or change the lighting etc.

# Security

At it's current stage the use case for this software to be run in a controlled environment (ie at home behind your routers firewall). 

Any tokens, passwords entered stay on your system and are encrypted.

_I would treat it like you would an encrypted password file you have on your PC. i.e you wouldn't put that text file on a public computer._

# Some of the current extensions
Still being developed so list might be out of date by now
## Logic/Controller/Display style extensions
## Webpages
### Liveportal
- The live streaming portal is a webpage that you can use on your second monitor to show all the information/settings you need on one page.
### Adminpage
- Provides a webpage to configure the system
### Overlay
- There is a very basic overlay to that gives the bare bones to allow you to create your own, only needing to focuss on the art and animation aspects and not worry about the overlay server part of it.
## Feature/Datahander extensions
### twitchchat
- Join a twitch chat channel to send receive chat messages on the main page. Also used to handle commands and post responces from the chatbot etc
### chatbot (The AI chatbot)
- Provides a chatbot using the openAI chatGPT system
- Monitors chat and occasionally pops in with messages based on the conversation
- Can be asked questions that are processed by the openAI system
- The bot can be setup with a personality of your chosing (ie happy, sad, funny etc) to match your channel ethos
### discordchat
- connects to discord to allow things like alerts to be posted when they come in
- receive messages from a given mod only discord channel (currently used in live page as a Mod messages window so mods can send easy to see messages without having to post in chat)
### streamlabs_api
- Povides alerts data from streamlabs for twitch alerts and streamlab donations
- Used with the discord chat extension to alerts them to discord
- I also run my overlay off StreamRoller so that uses these as well to trigger alerts while streaming
### twitter
- Post messages to twitter (need to add a reader output)
- Used currently to send a message when you hit the start streaming button on OBS
### obs
- Used to control OBS from the live portal page (change scenes, mute ect)
- Live portal receives status upadates from obs (stream started, scene changed etc)
## Feature Extensions
These are extension that use the data provided by the above extensions to do something usefull
## In progress
- chatmood extension to try and sense the mood of the chat and allow triggering of events (ie change the lighting, overlays, music etc when the chat's mood changes)
- more data extensions (ie youtube, specific games, home control etc)

## Ideas for extensions
The current focus in on twitch streaming (although the streamlabs api currently supports other platforms as is). Other platforms will be integrated in time (Youtube etc)
Some things I still need to get sorted are
- Twitch pub/sub: to allow twitch control (setting title, category, bannign users etc)
- moderator chatbot: one bot that will work with all the chat extension to provide a single moderator bot for all chat channels (discord/twitch/youtube/facebook etc)
- NDI stream extension to allow easy integration of external video feeds for duel streaming
- chat auto language conversion.
- TextToSpeech for chat. So us streamers don't have to focus on chat all the time :P

# For the Dev's/Coders out there
If you would like to extend the functionality of StreamRoller feel free. All the code currently is in javascript and runs on websockets. This means it should be fairly simple for anyone with web page coding skills to add features, link things together etc.

There are three areas of StreamRoller
## Server
This is simply a message handing system that all other extensions/webpages/dataprocessors connect to.
It mostly handles routing messages from one extension to another as well as storing persistant data/credentials etc.

## functional extensions
Every extension (like the live portal) sits on a websocket that connects to the server. On this socket it receives any messages it from extensions it has signed up for and can send messages to other extensions to request information or ask them to do things
## Extensions can be of different types
- A control extension that will use other extension to link functionality, The main one of these is the live portal, this listens to almost all extensions and provides the logic to do things like send a message to discord when someone donates
- simple data producers (like the factoftheday extension that you can request a fact from)
- other types might create an overlay to add to obs like the countdowntimer and setup via sending them a message, ie start a timer for 5 minutes called breaktime and it will create a breaktime.txt to add to your overlay
  
A extension simply connects to the server and request the other extensions it wants to 'listen' to. After that it simply decides what it wants to do with the data it receives (ie chat messages)

Extensions like twitch chat simply connect to the StreamRoller server, create a channel (for other to listen to), and then sends any chat messages out on that channel. It will also receive messages like SendChatMessage("user","hi) to send a twitch chat message from the user or bot that is set up.

This means that any webpage or bit of code that can use a websocket can connect to the system, use the eisting extensions functionality or provide more functionality of their own.

If you are interested in helping expand or configure these kind of things feel free to contact me. Maybe you just want to write a couple of overlay items, add some kind of LED sign extension that can display messages sent to it or even write your own live portal page that fits better for your type of streaming (ie music streamers will probabaly want an option for streamsonglist on there in place of the mod panel, currently working on that)
