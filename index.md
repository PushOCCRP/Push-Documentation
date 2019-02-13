---
layout: default
title: Home
---

# Introduction
---
The Push Project is an open source mobile app ecosystem for small and medium sized news organizations. If you're a news organization
that doesn't have the time or money to creat your own app but want all the functionality that you would expect, this is probably a
project you can use.

Push does *not* replace your CMS, it augments it. If you never want to just accept the default settings you should never have to do
anything to allow the Push apps to work perfectly fine.

# Parts of the Project
---
The push project consists of a couple of different portions, each of which operates as its own standalone repository (for the most part).
The full structure and its rational is described [here](/structure), but a brief summary of the big ones are below.

### The Backend [link](https://www.github.com/pushoccrp/push-backend)

This is the heart and soul of the Push ecosystem. It is the ringleader and though which all data and information flows. It handles three
things: the injestion of data from various CMS's, the administration of P=ush system, and the serving of content to the client apps. From
an administrator's point of viewl users are managed here, push notifications are sent, analytics are viewed. It's main purpose though is
to serve up a standard JSON API that the iOS and Android apps can easily pull data from.

This is the first thing you'll have to setup.

### CMS Plugins
The backend has to communicate with your company's CMS somehow, and this is how it's done. Right now there's support for the following
standard CMS's (plus a few one-offs, but that won't be discussed here.)

- [**Wordpress**](https://github.com/PushOCCRP/Push-Wordpress)
	- Support is excellent for PHP >4.3. Wordpress may support this very old version of PHP but we don't, and really, you should upgreade ASAP.
- **BLOX**
	- In development right now, but there is limited support
	- No plugin needed, since it provides its own API
- [**Joomla**](https://github.com/PushOCCRP/Push-Joomla-REST)
	- An implementation that is customized for OCCRP. It should work for most installations with a littl massaging. This is the oldest
	plugin and may not support the newest features of Push.

You can also develop your own plugin for your own CMS. Further instructions on that can be found [here](/plugin-development).

### Apps
The bread and butter, and the real reason we're all here. All the apps are at 98% feature parity and include (but are not limited) to the following:
- Reading articles
- Viewing articles by category
- Searching archives
- Push notifications
- Analytics
- Video player (supporting YouTube right now)
- Social media sharing
- Donations support
- One-off events
- Subscription login support

There are individual repositories for each of the supported platforms. These repositories, by themselves, will not compile (or even open in
their respective IDEs). First you must run the [generator](https://github.com/pushoccrp/push-generator). This will customize the code
so that it fits your organization.

#### iOS [link](https://www.github.com/pushoccrp/push-ios)
The iOS app is written in native Objective-C code and supports iOS >10. It is optimized for only the iPhone.

I addition to the features above the code contains beta-level censorship circuvention technology that auto connects to the TOR network
in the case of certain network conditions.

#### Android [link](https://www.github.com/pushoccrp/push-android)
The Android app is written in native Java code and supports Android >4.3.3.

### Generator
The generator is where customization for the apps is done. The app code itself should never be touched in production setups, and instead completely handled
through the generator.

# Setup

## Requirements

These instructions are for a production deployment of the Push software. For development instructions please see [this page](/development)

1. Make sure the Backend supports your CMS.
1. Install any appropriate plugins
	- [Wordpress instructions](https://github.com/PushOCCRP/Push-Wordpress)
	- [Joomla instructions](https://github.com/PushOCCRP/Push-Joomla-REST)
1. [Set up the backend](https://github.com/pushoccrp/push-backend)
1. [Set up and run the generator](https://github.com/pushoccrp/push-generator)
1. The generator should automatically upload your apps to the app store (FURTHER INSTRUCTIONS TBD)
