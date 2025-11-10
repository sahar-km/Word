<p align="center">
<a href="https://xkcd.com/538/"><img src="https://user-images.githubusercontent.com/787301/97934061-843cee00-1daf-11eb-9087-8d5e37ec345a.png"></a>
</p>

# Name

![dnscrypt](https://user-images.githubusercontent.com/787301/174648904-5fa57b79-6641-42df-8811-ee03724aa898.png)

`2.dnscrypt-cert.dns.tiar.app`

## Table of Contents

* [Features](#features)
* [Usage](#usage)
  * [v1](#v1)
  * [v2](#v2)
* [Android](#android)
* [iOS (iPhone/iPad)](#ios-iphoneipad) 
   * [DNSCloack](#dnscloak)
   * [Adguard Pro](#adguard-pro)
* [Linux](#linux)
* [MacOS](#macos)
* [OpenWrt](#openwrt)
* [Pi-hole](#pi-hole)
* [Windows](#windows)
  * [dnscrypt-proxy](#dnscrypt-proxy-1)

## Features

- [x] Filter: Ad, Ad-tracking and Malware (AdBlock)
- [x] DNSSEC Validation
- [x] No EDNS Client Subnet (ECS)
- [x] No logs
- [x] Free

## Usage

### v1:

| param         | value         |
| ------------- |-------------  |
| provider-name|`2.dnscrypt-cert.dns.tiar.app`|
| resolver-address|`174.138.21.128`|
| provider-key |`EF96:8066:E8D9:94F0:65D8:3EDD:D31A:EEED:F56D:8657:463E:4ACA:47CD:D7FE:97C3:D4F6`|

https://oldwiki.archive.openwrt.org/inbox/dnscrypt

[configuration file](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v1)

`id-gmail,"id-gmail resolver","id-gmail content blocking","Singapore","",,2,yes,yes,no,174.138.21.128,2.dnscrypt-cert.dns.tiar.app,EF96:8066:E8D9:94F0:65D8:3EDD:D31A:EEED:F56D:8657:463E:4ACA:47CD:D7FE:97C3:D4F6,`


### v2:


`sdns://AQMAAAAAAAAADjE3NC4xMzguMjEuMTI4IO-WgGbo2ZTwZdg-3dMa7u31bYZXRj5KykfN1_6Xw9T2HDIuZG5zY3J5cHQtY2VydC5kbnMudGlhci5hcHA`              

        
## Android

### [AdGuard](https://adguard.com/en/article/adblock-for-android.html)

![Imgur](https://i.imgur.com/e5Ugxok.jpg)

#### Disable App Filters

![Imgur](https://i.imgur.com/ndQIwRs.jpg)
       
## iOS (iPhone/iPad)

### [DNSCloak](https://itunes.apple.com/us/app/dnscloak-dnscrypt-doh-client/id1330471557?mt=8)

![Imgur](https://i.imgur.com/hTRFfEK.jpg)

### [Adguard Pro](https://apps.apple.com/us/app/adguard-pro-adblock/id1126386264)
* From main secreen, tap DNS Settings
* Scroll to the end of ENCRYPTED DNS SERVERS
* tap Add Custom..

![Imgur](https://i.imgur.com/WaRoonE.jpg)

Add below info:

- Name: `dnscrypt.tiar.app`
- Provider: `2.dnscrypt-cert.dns.tiar.app`
- Address: `174.138.21.128`
- Public Key: `EF96:8066:E8D9:94F0:65D8:3EDD:D31A:EEED:F56D:8657:463E:4ACA:47CD:D7FE:97C3:D4F6`

![Imgur](https://i.imgur.com/BdOexdm.jpg)

* tap Done
* Select `dnscrypt.tiar.app` then tap `< Adguard Pro` to go back to main screen

* tap Filters, then disable all the filters
* tap `< Adguard Pro` to go back to main screen

![Imgur](https://i.imgur.com/5FRQk5H.png)

* tap button on the right of the Status to enable `dnscrypt.tiar.app` 

![Imgur](https://i.imgur.com/nBviftv.png)

## Linux
### dnscrypt-proxy
[Installing dnscrypt-proxy on Linux](https://github.com/jedisct1/dnscrypt-proxy/wiki/Installation-linux)

[dnscrypt-proxy config file](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

## MacOS
### dnscrypt-proxy

[Installing dnscrypt-proxy on macOS](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-macOS)

[dnscrypt-proxy config file](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

## OpenWrt
### dnscrypt-proxy v1
[dnscrypt-proxy v1](https://oldwiki.archive.openwrt.org/inbox/dnscrypt)

1) copy [csv](https://github.com/pengelana/blocklist/blob/master/dnscrypt-proxy/v1/dnscrypt-resolvers.csv) to /usr/share/dnscrypt-proxy/dnscrypt-resolvers.csv
2) update /etc/config/[dnscrypt-proxy](https://github.com/pengelana/blocklist/blob/master/dnscrypt-proxy/v1/dnscrypt-proxy)
3) update /etc/[rc.local](https://github.com/pengelana/blocklist/blob/master/dnscrypt-proxy/v1/rc.local)


### dnscrypt-proxy v2
[dnscrypt-proxy v2](https://github.com/jedisct1/dnscrypt-proxy/wiki/Installation-on-OpenWRT) 

[dnscrypt-proxy config file](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

## Pi-hole
https://github.com/pi-hole/pi-hole/wiki/DNSCrypt-2.0

https://github.com/pi-hole/pi-hole/wiki/DNSCrypt

[dnscrypt-proxy config file](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

![github](https://camo.githubusercontent.com/c8ca8e0c1b79caddac3b6bc239b9ae1ed473ac2d/68747470733a2f2f69312e77702e636f6d2f70692d686f6c652e6e65742f77702d636f6e74656e742f75706c6f6164732f323031382f30352f5265637572736976655265736f6c7665722e706e673f773d3537372673736c3d31)

## Windows

### dnscrypt-proxy
[Installing dnscrypt-proxy on Windows](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-Windows#overview)

[dnscrypt-proxy config file](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

