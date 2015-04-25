---
layout: default
title: How to fix broken certificates in your operating system
permalink: /support/fixing-broken-ssl-certificates/
---

## How to fix broken certificates in your operating system.

From time to time people have SSL issues on specific operating systems.  This page
should serve as a guide to fixing your cURL and OpenSSL issues (with Ruby) if you
do not have RVM already installed.  If you do have RVM already installed you can
simply run the [RVM command to do this automatically](https://github.com/rvm/rvm/blob/master/help/osx-ssl-certs.md): `rvm osx-ssl-certs update all`.

### MacOS X

#### Extracting certificates from Apple’s Keychain

```
cert_file="$( openssl version -d | awk -F'"' '{print $2}' )/cert.pem"
mkdir -p "${cert_file%/*}"
security find-certificate -a -p /Library/Keychains/System.keychain > "$cert_file"
security find-certificate -a -p /System/Library/Keychains/SystemRootCertificates.keychain >> "$cert_file"
```

Notes:
Curl "77" Error (E77): Replace `cert_file="..."` with displayed `CAfile`

### Linux

(Exchange `<package-manager>` for `yum`, `apt-get` or `zypper`)

```
<package-manager> install ca-certificates
```
