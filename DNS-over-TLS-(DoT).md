<p align="center">
<a href="https://xkcd.com/870/"><img src="https://user-images.githubusercontent.com/787301/97933513-f6acce80-1dad-11eb-81a5-4a58e5f5802b.png"></a>
</p>

# Name

![tls](https://user-images.githubusercontent.com/787301/174648250-bd77151b-bdaf-48a1-b3cf-05ba452ce604.png)

* `dot.tiar.app` or `doh.tiar.app`
   
* `IPv4: 174.138.29.175 port 853`
   - `sdns://AwMAAAAAAAAADjE3NC4xMzguMjkuMTc1AAxkb3QudGlhci5hcHA`

* `IPv6: [2400:6180:0:d0::5f73:4001] port 853`
   - `sdns://AwMAAAAAAAAAG1syNDAwOjYxODA6MDpkMDo6NWY3Mzo0MDAxXQAMZG90LnRpYXIuYXBw`



## Table of Contents

* [Features](#features)
* [Android](#android)
  * [Android 9 (Pie)](#android-9-pie)
  * [Nebulo](#nebulo)
* [iOS (iPhone/iPad/MacOS)](#ios-iphoneipadmacos)
  * [DNSecure](#dnsecure)
  * [iOS 14/iPadOS 14/MacOS](#ios-14ipados-14macos)
  * [Adguard Pro](#adguard-pro)
* [Stubby](#Stubby)
* [Unbound](#Unbound)
* [GL.iNet](#glinet-router) Router


## Features

- [x] Filter: Ad, Ad-tracking and Malware (AdBlock)
- [x] DNSSEC Validation
- [x] No EDNS Client Subnet (ECS)
- [x] No logs
- [x] Free


## Android


### [Android 9 (Pie)](https://www.android.com/versions/pie-9-0/)

![1](https://user-images.githubusercontent.com/787301/122766910-a5b60000-d2d4-11eb-8ad9-365813639d90.jpg)

![2](https://user-images.githubusercontent.com/787301/122766918-a8185a00-d2d4-11eb-8795-475a57f33b50.jpg)


## [Nebulo](https://play.google.com/store/apps/details?id=com.frostnerd.smokescreen&hl=en_SG)

![index](https://user-images.githubusercontent.com/787301/65694058-d0dfd100-e0a7-11e9-9fd8-02849a157c09.jpg)

![index](https://user-images.githubusercontent.com/787301/65693766-629b0e80-e0a7-11e9-98e4-cb87532f01fa.jpg)

![index](https://user-images.githubusercontent.com/787301/65693810-72b2ee00-e0a7-11e9-9229-39e3b9f5d017.jpg)

![index](https://user-images.githubusercontent.com/787301/65693857-88c0ae80-e0a7-11e9-969f-4fa64ad0c3d5.jpg)


## iOS (iPhone/iPad/MacOS)


## [DNSecure](https://apps.apple.com/us/app/dnsecure/id1533413232)

* [Download `DNSecure`](https://apps.apple.com/us/app/dnsecure/id1533413232) from App Store.

* Select `+` and then select `DNS-over-TLS`

* Name: `dot.tiar.app` then select `return`

* Server URL: `dot.tiar.app` then select `return`

![1](https://user-images.githubusercontent.com/787301/120063074-fea8c480-c097-11eb-8fae-460e3f8180c0.jpg)

* Select `Use This Server`

* Go to `Settings` - `VPN & Network` - `DNS` then select `DNSecure` to activate

![2](https://user-images.githubusercontent.com/787301/120061998-60663000-c092-11eb-8eee-612a1f86c632.jpg)


### [iOS 14/iPadOS 14/MacOS](https://github.com/pengelana/blocklist/tree/master/iOS)

* Download `DNS-over-TLS` Profile from [Github](https://github.com/pengelana/blocklist/blob/master/iOS/dot.tiar.app-signed.mobileconfig)

* Select `View raw` - `Allow`

<a href="https://user-images.githubusercontent.com/787301/103453740-0d24c700-4d18-11eb-9d98-acd0f0884c73.jpg"><img src="https://user-images.githubusercontent.com/787301/103453740-0d24c700-4d18-11eb-9d98-acd0f0884c73.jpg"></a>

* Go to `Settings` - `General` - `Profile` - `Tiarap DNS over TLS` then select `Install`

<a href="https://user-images.githubusercontent.com/787301/103453785-74427b80-4d18-11eb-8b3f-ab50639aa713.png"><img src="https://user-images.githubusercontent.com/787301/103453785-74427b80-4d18-11eb-8b3f-ab50639aa713.png"></a>

* Go to `Settings` - `VPN & Network` - `DNS`

<a href="https://user-images.githubusercontent.com/787301/103453803-9936ee80-4d18-11eb-9c4f-cdcbfec587b2.png"><img src="https://user-images.githubusercontent.com/787301/103453803-9936ee80-4d18-11eb-9c4f-cdcbfec587b2.png"></a>


## [Adguard Pro](https://apps.apple.com/app/adguard-pro-adblock/id1126386264)

* Select ⚙️ Settings - DNS protection  - DNS server

* Select `+` 

* Server name: `dot.tiar.app`

* DNS server address: `sdns://AwMAAAAAAAAADjE3NC4xMzguMjkuMTc1AAxkb3QudGlhci5hcHA`

![adguard-pro](https://user-images.githubusercontent.com/787301/122768626-5ec90a00-d2d6-11eb-97ed-69a30402a070.jpg)


## [Stubby](https://dnsprivacy.org/wiki/display/DP/DNS+Privacy+Daemon+-+Stubby)


### IPv4
~~~~
- address_data: 174.138.29.175       
  tls_auth_name: "dot.tiar.app"    
  tls_port: 853`    
~~~~


### IPv6
~~~
  - address_data: 2400:6180:0:d0::5f73:4001 
    tls_auth_name: "dot.tiar.app" 
    tls_port: 853
~~~

[Stubby configuration file](https://github.com/pengelana/blocklist/blob/master/stubby/stubby.yml.example)


## [Unbound](https://nlnetlabs.nl/projects/unbound/about/)


### IPv4

~~~
 forward-zone:
   name: "."
   forward-first: yes
   forward-tls-upstream: yes
   forward-addr: 174.138.29.175@853 #dot.tiar.app
   forward-addr: 2400:6180:0:d0::5f73:4001@853 #dot.tiar.app IPv6
~~~


## [GL.iNet](https://www.gl-inet.com/products/gl-ar750s/) Router
![Imgur](https://i.imgur.com/6W5CYeL.jpg)
![Imgur](https://i.imgur.com/pD78lMX.jpg)
![Imgur](https://i.imgur.com/fvhlKGr.jpg)




