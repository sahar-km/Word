<p align="center">
<a href="https://twitter.com/turnoff_us/status/1232371820638146560"><img src="https://pbs.twimg.com/media/ERpDnUWWoAIGijo?format=png&name=small"></a>
</p>

# DNS over QUIC (DoQ)

![quic](https://user-images.githubusercontent.com/787301/174647576-2a8bcaa0-7965-41b4-974a-d6d1f75627e1.png)

`quic://doh.tiar.app`

پورت 784
~~~
sdns://BAMAAAAAAAAAEjE3NC4xMzguMjkuMTc1Ojc4NAAMZG9oLnRpYXIuYXBw
~~~

پورت 853
~~~
sdns://BAMAAAAAAAAAEjE3NC4xMzguMjkuMTc1Ojg1MwAMZG9oLnRpYXIuYXBw
~~~

## فهرست مطالب

* [ویژگی‌ها](#ویژگی‌ها)

* [پیکربندی](#پیکربندی)

  * [Adguard dnsproxy](#adguard-dnsproxy)
  * [Adguard Home](#adguard-home)
  * [Adguard Pro/Premium](#adguard-propremium)

## ویژگی‌ها

- [x] فیلتر: تبلیغات، ردیابی تبلیغات و بدافزار (AdBlock)
- [x] اعتبارسنجی DNSSEC
- [x] بدون زیرشبکه مشتری EDNS (ECS)
- [x] بدون لاگ
- [x] رایگان


## [Adguard dnsproxy](https://github.com/AdguardTeam/dnsproxy)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

`./dnsproxy -u quic://doh.tiar.app`

DNS-over-QUIC بالادست و گوش دادن روی `127.0.0.1` پورت `53`

https://github.com/AdguardTeam/dnsproxy


## [Adguard Home](https://adguard.com/en/adguard-home/overview.html)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

`quic://doh.tiar.app`

<a href="https://user-images.githubusercontent.com/787301/108207445-b86fcb00-7162-11eb-98bb-6aafd5ef76d1.png"><img src="https://user-images.githubusercontent.com/787301/108207445-b86fcb00-7162-11eb-98bb-6aafd5ef76d1.png"></a>


## [Adguard Pro/Premium](https://adguard.com/en/adguard-ios-pro/overview.html)

- [x] iOS
- [x] iPadOS
- [x] اندروید
- [x] دیگران

### راهنما:

~~~
sdns://BAMAAAAAAAAAEjE3NC4xMzguMjkuMTc1Ojc4NAAMZG9oLnRpYXIuYXBw
~~~

![1](https://user-images.githubusercontent.com/787301/123511532-5c8af500-d6b4-11eb-8f62-1e5d81cf3bdc.jpg)


https://adguard.com/en/adguard-ios-pro/overview.html

https://adguard.com/en/adguard-android/overview.html

https://adguard.com/en/adguard-ios/overview.html
