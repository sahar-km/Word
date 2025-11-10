<p align="center">
<a href="https://twitter.com/tomfishburne/status/792744498551934979?s=20"><img src="https://user-images.githubusercontent.com/787301/97933825-cca7dc00-1dae-11eb-8fe6-d93204451cf0.jpg"></a>
</p>

# DNS over HTTPS (DoH)

![https](https://user-images.githubusercontent.com/787301/174648584-5ccd635f-fdb7-44f0-bc66-393ad1c0e640.png)

* `https://doh.tiarap.org/dns-query` `(کش شده از طریق Cloudflare)`

* `https://doh.tiar.app/dns-query`

* `IPv4: 174.138.29.175`

* `IPv6: 2400:6180:0:d0::5f73:4001`


## فهرست مطالب

* [ویژگی‌ها](#ویژگی‌ها)
* [اندروید](#اندروید)
  * [Intra](#intra-app)
  * [Nebulo](#nebulo)
* [iOS (iPhone/iPad/MacOS)](#ios-iphoneipadmacos)
  * [DNSecure](#dnsecure)
  * [iOS 14/iPadOS 14](#ios-14ipados-14)
  * [DNSCloack](#dnscloack)
  * [Morhill DoH Switcher](#morhill-doh-switcher)
* [کروم](#کروم)
* [فایرفاکس](#فایرفاکس)
* [لینوکس](#لینوکس)
  * [dnscrypt-proxy](#dnscrypt-proxy)
  * [~~Cloudflared~~](#cloudflared)
* [OpenWrt](#openwrt)
* [Pi-hole](#pi-hole)
* [ویندوز](#ویندوز)
  * [dnscrypt-proxy](#dnscrypt-proxy-1)


## ویژگی‌ها

- [x] فیلتر: تبلیغات، ردیابی تبلیغات و بدافزار (AdBlock)
- [x] اعتبارسنجی DNSSEC
- [x] بدون زیرشبکه مشتری EDNS (ECS)
- [x] بدون لاگ
- [x] رایگان


## اندروید

### [برنامه Intra](https://play.google.com/store/apps/details?id=app.intra&hl=en_SG)

`آدرس: https://doh.tiarap.org/dns-query`

`آدرس: https://doh.tiar.app/dns-query`

![Imgur](https://i.imgur.com/GccGCkH.jpg)

![Imgur](https://i.imgur.com/YcAVmgV.jpg)

![Imgur](https://i.imgur.com/ajiX3fb.jpg)


### [Nebulo](https://play.google.com/store/apps/details?id=com.frostnerd.smokescreen&hl=en_US)

`آدرس: https://doh.tiarap.org/dns-query`

`آدرس: https://doh.tiar.app/dns-query`

![image](https://user-images.githubusercontent.com/787301/65695717-a04d6680-e0aa-11e9-977f-cc080609ca48.png)

![image](https://user-images.githubusercontent.com/787301/65695907-f28e8780-e0aa-11e9-8bad-f3d49115411a.png)

![image](https://user-images.githubusercontent.com/787301/65696204-6892ee80-e0ab-11e9-8e3d-c54d15e9e540.png)

![image](https://user-images.githubusercontent.com/787301/65695842-d8ed4000-e0aa-11e9-9d66-521522c4ac32.png)


## iOS (iPhone/iPad/MacOS)

## [DNSecure](https://apps.apple.com/us/app/dnsecure/id1533413232)

* [دانلود `DNSecure`](https://apps.apple.com/us/app/dnsecure/id1533413232) از اپ استور.

* روی + ضربه بزنید و سپس `DNS-over-HTTPS` را انتخاب کنید

* نام: `doh.tiar.app` سپس روی `return` ضربه بزنید

* آدرس سرور: `https://doh.tiar.app/dns-query` یا `https://doh.tiarap.org/dns-query` سپس روی `return` ضربه بزنید

![1](https://user-images.githubusercontent.com/787301/120061967-3c0a5380-c092-11eb-902a-86d3e311e5e2.jpg)

* روی `استفاده از این سرور` ضربه بزنید

* به `تنظیمات` - `VPN و شبکه` - `DNS` بروید و سپس `DNSecure` را برای فعال‌سازی انتخاب کنید

![2](https://user-images.githubusercontent.com/787301/120061998-60663000-c092-11eb-8eee-612a1f86c632.jpg)


### [iOS 14/iPadOS 14](./iOS)

* پروفایل `DNS-over-HTTPS` را از [گیت‌هاب](./iOS/doh.tiar.app-signed.mobileconfig) دانلود کنید.

![1](https://user-images.githubusercontent.com/787301/95647892-c69f4200-0b05-11eb-8075-5a427ece3e2e.png)

* به `تنظیمات` - `عمومی` - `پروفایل` - `Tiarap DNS over HTTPS` بروید و سپس روی `نصب` ضربه بزنید

![2](https://user-images.githubusercontent.com/787301/95647964-51803c80-0b06-11eb-9769-32f4c035cdc6.png)

* `تنظیمات` - `VPN و شبکه` - `DNS`

![3](https://user-images.githubusercontent.com/787301/95648121-75904d80-0b07-11eb-890a-38b34bd108b1.png)


### [DNSCloack](https://itunes.apple.com/us/app/dnscloak-dnscrypt-doh-client/id1330471557?mt=8)

![Imgur](https://i.imgur.com/9grJVjA.jpg)


### [Morhill DoH Switcher](https://itunes.apple.com/us/app/morhill-doh-switcher/id1451319401)

![Imgur](https://i.imgur.com/rXLl8cd.png)


## کروم

۱) در نوار آدرس تایپ کنید `chrome://settings/security` سپس `امنیت پیشرفته - استفاده از DNS امن` را جستجو کنید و آن را فعال کنید.

۲) انتخاب کنید: `با: سفارشی` از منوی کشویی. `ارائه‌دهنده سفارشی را وارد کنید:` تایپ کنید `https://doh.tiar.app/dns-query` یا `https://doh.tiarap.org/dns-query`.

![Screen Shot 2020-07-12 at 12 09 35 PM](https://user-images.githubusercontent.com/787301/87238747-11db8300-c439-11ea-8609-5fbc08da52e4.png)


## فایرفاکس
https://wiki.mozilla.org/Trusted_Recursive_Resolver

https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https/

_**فایرفاکس 73.0b2**_

* _نوار آدرس - **about:config** - جستجو: **network.trr**_

- `network.trr.resolvers` را با این جایگزین کنید:

`[{ "name": "Cloudflare", "url": "https://mozilla.cloudflare-dns.com/dns-query" },{ "name": "NextDNS", "url": "https://trr.dns.nextdns.io/" }, {"name":"Tiarap", "url": "https://doh.tiarap.org/dns-query"}]`

- `network.trr.useGET` را به `true` تغییر دهید

* _تنظیمات_ - _تنظیمات شبکه_

از منوی کشویی، `Tiarap` را انتخاب کنید و سپس روی OK کلیک کنید.

![Screen Shot 2020-01-09 at 9 10 57 PM](https://user-images.githubusercontent.com/787301/72071077-ee1e6f80-3325-11ea-98a1-c84f3669b707.png)


## لینوکس
### dnscrypt-proxy

[نصب dnscrypt-proxy در لینوکس](https://github.com/jedisct1/dnscrypt-proxy/wiki/Installation-linux)

[فایل پیکربندی dnscrypt-proxy](./dnscrypt-proxy/v2)


### [~~Cloudflared~~](https://developers.cloudflare.com/1.1.1.1/dns-over-https/cloudflared-proxy/)

[`"Content-Type", "application/dns-message"`](https://tools.ietf.org/html/rfc8484#section-6) توسط [~~cloudflared~~](https://github.com/cloudflare/cloudflared/pull/108) پشتیبانی نمی‌شود

**[dns.google با "cloudflared" سازگار نیست #113](https://github.com/cloudflare/cloudflared/issues/113)**


## OpenWrt
### dnscrypt-proxy
[نصب در OpenWRT](https://github.com/jedisct1/dnscrypt-proxy/wiki/Installation-on-OpenWRT)

[فایل پیکربندی dnscrypt-proxy](./dnscrypt-proxy/v2)


## Pi-hole
https://github.com/pi-hole/pi-hole/wiki/DNSCrypt-2.0

https://docs.pi-hole.net/guides/dns-over-https/

[فایل پیکربندی dnscrypt-proxy](./dnscrypt-proxy/v2)

![Pi-hole](https://docs.pi-hole.net/images/DoHConfig.png)


## ویندوز

### dnscrypt-proxy
[نصب dnscrypt-proxy در ویندوز](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-Windows#overview)

[فایل پیکربندی dnscrypt-proxy](./dnscrypt-proxy/v2)
