---
title: "Cloud Linux - Shared Hosting Done Safe"
date: 2021-05-26
author: FlokiNET
draft: false
---

{{< figure src="/images/cloud_linux.png" >}}

Heard about CloudLinux?

Our shared hosting servers are equipped with a Linux distribution named CloudLinux, that improves server stability, density, and security by isolating each tenant and giving them allocated server resources. Some of its main features are:

## Security (SecureLinks)

SecureLinks is a kernel-level technology that prevents all known symbolic link attacks and enhances the security level of the servers even further, preventing malicious users from creating symbolic link files (where an attacker tricks Apache Web server to read some other user’s PHP config files).

[Source](https://www.cloudlinux.com/securelinks)

## CageFS 

CageFS is a virtualized, per-user file system that uniquely encapsulates each customer, preventing users from seeing each other and viewing sensitive information. What CageFS does is that it prevents a large number of attacks, including most privilege escalation and information disclosure attacks. With the help of CageFS, users have the following benefits:

* they only have access to safe files.
* they cannot see other users and have no way to detect the presence of other users or user names on the server.
* they cannot see server configuration files, like Apache config files.
* they have a limited view of their own processing file system, and cannot see other users’ processes.

[Source](https://www.cloudlinux.com/cagefs)

## HardenedPHP

Several highly popular versions of PHP, used in nearly 85% of all PHP sites, are unsupported by the PHP.net community. HardenedPHP secures old and unsupported versions of PHP – 4.4.9, 5.1, 5.2, 5.3, 5.4, 5.5, 5.6, 7.0, 7.1, 7.2.

HardenedPHP secures old and unsupported versions of PHP. In those old versions, including the widely used 7.2, 7.1, 7.0, and 5.6, vulnerabilities, even if discovered, are not patched by the PHP.net community. HardenedPHP takes care of all this.

[Source](https://www.cloudlinux.com/hardenedphp)

## Python Selector

The Python Selector allows end-users to select the specific version of Python they need.

Each customer is different, and each has different needs. The Python Selector allows end users to choose the Python version as an application and install additional modules. Python Selector uses mod_passenger to get the best performance from Python applications.

[Source](https://www.cloudlinux.com/index.php/python-selector)

## Ruby selector

The Ruby Selector allows end-users to select the specific version of Ruby they need.

Each of your customers is different, and each has different needs. The Ruby Selector allows end-users to choose the Ruby version for applications and install additional modules (gems) to the application environment. Ruby Selector uses mod_passenger for optimum performance.

[Source](https://www.cloudlinux.com/index.php/ruby-selector)

Have any questions about CloudLinux? E-mail us at info@flokinet.is.