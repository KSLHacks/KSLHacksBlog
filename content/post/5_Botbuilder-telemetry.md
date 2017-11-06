---
title: "Botbuilder middleware package for custom analytics and telemetry"
date: 2017-11-06
thumbnailImagePosition: left
thumbnailImage: /img/posts/5_telemetryThumbnail.png
coverImage: /img/posts/5_telemetryBanner.png
coverMeta: in
coverSize: partial
coverHeight: 40
categories:
- tech
- chatbots
tags:
- Microsoft Bot Framework
- chatbots
- bots
- bot middleware
- analytics
- telemetry

draft:          false
comments:       true
showTags:       true
showPagination: true
showSocial:     true
showDate:       true
---

Microsoft Botbuilder telemetry package for analytics.

<!--more-->
Allows bot session, incoming and outgoing messages, and LUIS recognizer to be captured and consumed. This payload can be sent to any endpoint desired.
## Purpose

This middleware allows bot developers to collect telemetry on incoming user messages, outgoing bot responses, dialog, stack, response latency and cognitive services and more. No additional REST calls are made to gather these data points. On every user input, the package will create a new payload with the most recent information.

A host of data is by default already collected from the user (below), but the developer can add, manipulate and restructure the payload however they require. Once the payload contains all the telemetry required, it can be sent to any endpoint specified by the developer. This can include API calls, database connections, etc.

## Analytics and telemetry
```js
botName                 // "Test-Bot"
userName                // "Kevin L."
userMessage             // "hello"
userMessageLength       // 5
userMessageTimestamp    // 2017-10-26T20:21:54.977Z
botResponse             // string[] ["Hello! I am your friendly bot."]
botResponseLength       // 10
botResponseTimestamp    // 2017-10-26T20:21:57.424Z
botResponseLatency      // 2447
currentDialog           // Object {dialog: "*:/", step: 0}
dialogStack             // string[] ["*:/", "*:/greeting"]
luisIntent              // "greeting"
```

## Consume
```js
// from Microsoft botbuilder SDK
var bot = new builder.UniversalBot(connector) 

// Use botbuilder-telemetry package
bot = ApplyTelemetryMiddleware(bot, configObject, dataHandleFunction, dataMutationFuncOrPromise)

// ... Rest of your bot definition
```

## configObject
Any variables can be passed in using the required configObject. Such as bot version, developer, any endpoint requirements, user data, etc..

## dataHandleFunction
Define and implement the endpoint call you wish to make. Where would you like to send the payload?

## dataMutationFuncOrPromise
Define and implement any function or promise that manipulates or adds onto the payload that is created on default. This can be left undefined if no futher processing is required, but this parameter allows the developer to customize the package before sending.

## NPM Package
Check out the source code and NPM package, give it a try and let me know what you think! Github repo [/examples/app.js][github-example] has a full example of how to setup a bot using the Microsoft Bot Framework and using the middleware.

NPM package:
[botbuilder-telemetry NPM package][npm-package]

Source code in Github here:
[botbuilder-telemetry Github Repo][github]

[github-example]: https://github.com/KSLHacks/botbuilder-telemetry/blob/master/example/app.js
[github]: https://github.com/KSLHacks/botbuilder-telemetry
[npm-package]: https://www.npmjs.com/package/botbuilder-telemetry
