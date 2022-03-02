---
title: "Secure Your TLS With PFS"
date: 2016-04-18
author: FlokiNET
draft: false
---

Today’s mostly used SSL is broken. The reason is, RC4 is [broken](http://www.isg.rhul.ac.uk/tls/) and that is mostly used by SSL active websites. Check your SSL used website about SSL Ciphers (in FF click on the secure bar logo) – you will see for example: RSA_RC4_128_SHA

That means the server uses RSA with RC4 and SHA 128. And that is broken.

But it is getting worse. The NSA is currently building the biggest [spy center](http://www.wired.com/threatlevel/2012/03/ff_nsadatacenter/) in the US to save any data they get. Why? It may be true that you can’t break the current secure ciphers now, but what about later?

So what we need is a system which will remain secure in the future. PFS (Perfect-Forward-Secrecy) fulfills this requirement.

**How does it work?**

When two peers want to establish a TLS tunnel with PFS, after performing the server (or the mutual) authentication, they agree on an ephemeral session key.

The session keys are then used to encrypt the rest of the conversation (session). They are deleted afterwards. The goal of the key exchange phase is to enable the two parties to negotiate the keys securely; in other words, to prevent anyone else from learning these keys.

**How do we enable it?**

First: Use a long SSL Cert Key. We recommend to use RSA 4096 bits.

Also you realy should look foward to get TLS 1.2 active on your server (should be already supported by every unix on latest version)

**Activate PFS**

You will need Apache 2.3+ , earlier versions are not supporting PFS.

Replace (or add if applicable) the following configuration directives in your SSL module configuration file (most likely to be found in /etc/apache2/mods-enabled/ssl.conf).

     

    SSLProtocol +TLSv1.2
    SSLCompression off
    SSLHonorCipherOrder on
    SSLCipherSuiteECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384

Update your Dovecot mailserver:

    ssl_cipher_list=ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384
    ssl_prefer_server_ciphers = yes

How does it look later? Have a look at our billing system ([SSL labs](https://www.ssllabs.com/ssltest/analyze.html?d=billing.flokinet.com).