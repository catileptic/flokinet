---
title: "Shared Hosting Improvements 2016"
date: 2016-07-08
author: FlokiNET
draft: false
---

We are always on the search to improve our services. As we added some time ago free ddos protection at our location Romania we are now taking on the shared hosting.

Within the past time we recived plenty of requests for shell access and now here we are:

**All shared hosting clients now have shell access and can login via ssh.**

**How to use shell?**

The first thing you need are a private and public key for the ssh login. Our server offer only key auth as an option for security reasons, password auth is not possible (if you try the password auth more then a few times in row your IP will get blocked)

**Windows:**

1. Open the PuTTYgen program.
2. For Type of key to generate, select SSH-2 RSA.
3. Click the Generate button.
4. Move your mouse in the area below the progress bar. …
5. Type a passphrase in the Key passphrase field. …
6. Click the Save private key button to save the private key.

You can download the tools [here](http://www.chiark.greenend.org.uk/~sgtatham/putty/).

**Linux:**

1. Open Terminal.
2. Paste the text below, substituting in your GitHub email address.

        ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
        # Creates a new ssh key, using the provided email as a label
        Generating public/private rsa key pair.

3. When you’re prompted to “Enter a file in which to save the key,” press Enter. This accepts the default file location.

        Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]

4. At the prompt, type a secure passphrase. For more information

        Enter passphrase (empty for no passphrase): [Type a passphrase]
        Enter same passphrase again: [Type passphrase again]

Login to your cpanel and click on “SSH Access”.

There you can upload your public key or also generate a pair. We recommend to generate the key localy and then only upload the public key.

Dont forget to enable your key within Cpanel.

You can watch the Cpanel how too video [here](https://www.cpanel.com/media/tutorials/ssh.htm).

**Git on shared hosting**

Git makes admin lives easier and offer a wide range of options. So we got you git too. Just login via ssh and use the git command.

Be aware that you need to provide the full path:

    /usr/local/cpanel/3rdparty/bin/git

**Webserver tuning and more ram:**

Our Cloudlinux ressources included within the packages are already quite large but we wanted to offer more. We set the php mem limit by default to 512mb and raised the max connections limit per package too.

**Nginx:**

all webserver running Nginx as proxy in front so that static and cached content can be delivered even faster.

**PHP selector:**

From time to time customers requesting special php settings and versions to get there software running. By default our php setup is optimized to secure for all user. This includes the usage of [Suhosin](https://suhosin.org/stories/index.html) and always up to date php versions.

But some customers need an own php version so we offer via PHP selector in Cpanel the option to set your php as you need it.

If you need further options please contact us.

{{< figure src="/images/shared_hosting_improvements_2016.png" >}}