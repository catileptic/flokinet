---
title: "HTTP Strict Transport Security (HSTS)"
date: 2016-04-18
author: FlokiNET
draft: false
---

The **HSTS** Policy helps protect web application users against some passive (eavesdropping) and active network attacks. A man-in-the-middle attacker has a greatly reduced ability to intercept requests and responses between a user and a web application server, while the user’s browser has **HSTS** Policy in effect for that web application

So what we need?

Activate mod headers in apache:

    a2enmod headers

**HSTS** header into VirtualHost:

    Header always set Strict-Transport-Security “max-age=31536000; includeSubDomains”

max age set the Time in seconds and includeSubDomains set the **HSTS** header also into your subdomains (recommended). If you don’t want his just only let it our and close after31536000.

Done.
