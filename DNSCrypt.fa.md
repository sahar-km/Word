<p align="center">
<a href="https://xkcd.com/538/"><img src="https://user-images.githubusercontent.com/787301/97934061-843cee00-1daf-11eb-9087-8d5e37ec345a.png"></a>
</p>

# DNSCrypt

![dnscrypt](https://user-images.githubusercontent.com/787301/174648904-5fa57b79-6641-42df-8811-ee03724aa898.png)

`2.dnscrypt-cert.dns.tiar.app`

## فهرست مطالب

* [ویژگی‌ها](#ویژگی‌ها)
* [استفاده](#استفاده)
  * [نسخه ۱](#v1)
  * [نسخه ۲](#v2)
* [اندروید](#اندروید)
* [iOS (iPhone/iPad)](#ios-iphoneipad)
   * [DNSCloack](#dnscloak)
   * [Adguard Pro](#adguard-pro)
* [لینوکس](#لینوکس)
* [MacOS](#macos)
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

## استفاده

### نسخه ۱:

| پارامتر         | مقدار         |
| ------------- |-------------  |
| provider-name|`2.dnscrypt-cert.dns.tiar.app`|
| resolver-address|`174.138.21.128`|
| provider-key |`EF96:8066:E8D9:94F0:65D8:3EDD:D31A:EEED:F56D:8657:463E:4ACA:47CD:D7FE:97C3:D4F6`|

https://oldwiki.archive.openwrt.org/inbox/dnscrypt

[فایل پیکربندی](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v1)

`id-gmail,"id-gmail resolver","id-gmail content blocking","Singapore","",,2,yes,yes,no,174.138.21.128,2.dnscrypt-cert.dns.tiar.app,EF96:8066:E8D9:94F0:65D8:3EDD:D31A:EEED:F56D:8657:463E:4ACA:47CD:D7FE:97C3:D4F6,`


### نسخه ۲:


`sdns://AQMAAAAAAAAADjE3NC4xMzguMjEuMTI4IO-WgGbo2ZTwZdg-3dMa7u31bYZXRj5KykfN1_6Xw9T2HDIuZG5zY3J5cHQtY2VydC5kbnMudGlhci5hcHA`


## اندروید

### [AdGuard](https://adguard.com/en/article/adblock-for-android.html)

![Imgur](https://i.imgur.com/e5Ugxok.jpg)

#### غیرفعال کردن فیلترهای برنامه

![Imgur](https://i.imgur.com/ndQIwRs.jpg)

## iOS (iPhone/iPad)

### [DNSCloak](https://itunes.apple.com/us/app/dnscloak-dnscrypt-doh-client/id1330471557?mt=8)

![Imgur](https://i.imgur.com/hTRFfEK.jpg)

### [Adguard Pro](https://apps.apple.com/us/app/adguard-pro-adblock/id1126386264)
* از صفحه اصلی، روی تنظیمات DNS ضربه بزنید
* به انتهای سرورهای DNS رمزگذاری شده بروید
* روی افزودن سفارشی ضربه بزنید..

![Imgur](https://i.imgur.com/WaRoonE.jpg)

اطلاعات زیر را اضافه کنید:

- نام: `dnscrypt.tiar.app`
- ارائه‌دهنده: `2.dnscrypt-cert.dns.tiar.app`
- آدرس: `174.138.21.128`
- کلید عمومی: `EF96:8066:E8D9:94F0:65D8:3EDD:D31A:EEED:F56D:8657:463E:4ACA:47CD:D7FE:97C3:D4F6`

![Imgur](https://i.imgur.com/BdOexdm.jpg)

* روی انجام شد ضربه بزنید
* `dnscrypt.tiar.app` را انتخاب کنید و سپس روی `< Adguard Pro` ضربه بزنید تا به صفحه اصلی بازگردید

* روی فیلترها ضربه بزنید، سپس همه فیلترها را غیرفعال کنید
* روی `< Adguard Pro` ضربه بزنید تا به صفحه اصلی بازگردید

![Imgur](https://i.imgur.com/5FRQk5H.png)

* روی دکمه سمت راست وضعیت ضربه بزنید تا `dnscrypt.tiar.app` فعال شود

![Imgur](https://i.imgur.com/nBviftv.png)

## لینوکس
### dnscrypt-proxy
[نصب dnscrypt-proxy در لینوکس](https://github.com/jedisct1/dnscrypt-proxy/wiki/Installation-linux)

[فایل پیکربندی dnscrypt-proxy](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

## MacOS
### dnscrypt-proxy

[نصب dnscrypt-proxy در macOS](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-macOS)

[فایل پیکربندی dnscrypt-proxy](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

## OpenWrt
### dnscrypt-proxy نسخه ۱
[dnscrypt-proxy نسخه ۱](https://oldwiki.archive.openwrt.org/inbox/dnscrypt)

۱) [csv](https://github.com/pengelana/blocklist/blob/master/dnscrypt-proxy/v1/dnscrypt-resolvers.csv) را در /usr/share/dnscrypt-proxy/dnscrypt-resolvers.csv کپی کنید
۲) /etc/config/[dnscrypt-proxy](https://github.com/pengelana/blocklist/blob/master/dnscrypt-proxy/v1/dnscrypt-proxy) را به‌روزرسانی کنید
۳) /etc/[rc.local](https://github.com/pengelana/blocklist/blob/master/dnscrypt-proxy/v1/rc.local) را به‌روزرسانی کنید


### dnscrypt-proxy نسخه ۲
[dnscrypt-proxy نسخه ۲](https://github.com/jedisct1/dnscrypt-proxy/wiki/Installation-on-OpenWRT)

[فایل پیکربندی dnscrypt-proxy](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

## Pi-hole
https://github.com/pi-hole/pi-hole/wiki/DNSCrypt-2.0

https://github.com/pi-hole/pi-hole/wiki/DNSCrypt

[فایل پیکربندی dnscrypt-proxy](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)

![github](https://camo.githubusercontent.com/c8ca8e0c1b79caddac3b6bc239b9ae1ed473ac2d/68747470733a2f2f69312e77702e636f6d2f70692d686f6c652e6e65742f77702d636f6e74656e742f75706c6f6164732f323031382f30352f5265637572736976655265736f6c7665722e706e673f773d3537372673736c3d31)

## ویندوز

### dnscrypt-proxy
[نصب dnscrypt-proxy در ویندوز](https.github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-Windows#overview)

[فایل پیکربندی dnscrypt-proxy](https://github.com/pengelana/blocklist/tree/master/dnscrypt-proxy/v2)
