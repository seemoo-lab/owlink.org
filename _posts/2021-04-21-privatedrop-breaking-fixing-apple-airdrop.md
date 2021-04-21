---
layout: post
title:  "PrivateDrop: Breaking and Fixing Apple AirDrop"
date:   2021-04-21 11:00:00 +0200
---

Apple AirDrop allows users to send photos and other media over a direct Wi-Fi connection from one Apple device to another. As people typically want to share sensitive data exclusively with people they know, AirDrop only shows receiver devices from address book contacts by default. To determine whether the other party is a contact, AirDrop uses a mutual authentication mechanism that compares a user’s phone number and email address with entries in the other user’s address book.
We discovered two severe privacy leaks in this authentication mechanism. In particular, we showed that it is possible to learn the phone numbers and email addresses of AirDrop users – even as a complete stranger. **Read the [full version on the project website](https://privatedrop.github.io).**
