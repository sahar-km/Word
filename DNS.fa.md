<p align="center">
<a href="https://twitter.com/tomfishburne/status/1125146808882089984?s=20"><img src="https://user-images.githubusercontent.com/787301/97933370-88680c00-1dad-11eb-83d1-dc53d01c0571.jpg"></a>
</p>

# DNS

* `resolver.tiar.app`

* `IPv4: 174.138.21.128 پورت 53 یا پورت 5003`

* `IPv6: [2400:6180:0:d0::5f6e:4001] پورت 53 یا پورت 5003`

# فهرست مطالب

* [ویژگی‌ها](#ویژگی‌ها)

* [پیکربندی](#پیکربندی)

  * [پراکسی DNS اکریلیک](#پراکسی-dns-اکریلیک)
  * [Adguard dnsproxy](#adguard-dnsproxy)
  * [Adguard Home](#adguard-home)
  * [Dnsmasq](#dnsmasq)
  * [جونیپر SRX](#جونیپر-srx)
  * [میکروتیک](#میکروتیک)
  * [OpenWrt](#openwrt)
  * [pfSense/OPNsense](#pfsenseopnsense)
  * [Pi-hole](#pi-hole)
  * [systemd-resolved](#systemd-resolved)
  * [سرور DNS تکنیسیوم](#سرور-dns-تکنیسیوم)
  * [Ubnt EdgeOS](#ubnt-edgeos)
  * [Unbound](#unbound)
  * [YogaDNS](#yogadns)


# ویژگی‌ها

- [x] فیلتر: تبلیغات، ردیابی تبلیغات و بدافزار (AdBlock)
- [x] اعتبارسنجی DNSSEC
- [x] بدون زیرشبکه مشتری EDNS (ECS)
- [x] بدون لاگ
- [x] رایگان

# پیکربندی

## [پراکسی DNS اکریلیک](https://mayakron.altervista.org/support/acrylic/Home.htm)

- [ ] لینوکس
- [ ] MacOS
- [x] ویندوز
- [ ] دیگران

### راهنما:

~~~
PrimaryServerAddress=174.138.21.128
PrimaryServerPort=5003
~~~

https://mayakron.altervista.org/support/acrylic/Configuration.htm

## [Adguard dnsproxy](https://github.com/AdguardTeam/dnsproxy)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

`./dnsproxy -u 174.138.21.128:5003 -v -o log.txt`

https://github.com/AdguardTeam/dnsproxy

## [Adguard Home](https://github.com/AdguardTeam/AdguardHome)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

![adguard_home](https://user-images.githubusercontent.com/787301/97778357-a36e2c80-1bb1-11eb-9701-8079900a8fe9.png)

https://adguard.com/en/blog/in-depth-review-adguard-home.html#dns

## [Dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html)

- [x] لینوکس
- [x] MacOS
- [ ] ویندوز
- [x] دیگران

### راهنما:

ویرایش `/etc/dnsmasq.conf`

~~~
no-resolv
server=174.138.21.128#5003
cache-size=1000

~~~

ویرایش `/etc/resolv.conf`

~~~
nameserver ::1
nameserver 127.0.0.1
options trust-ad

~~~

http://www.thekelleys.org.uk/dnsmasq/docs/dnsmasq-man.html

## [جونیپر SRX](https://www.juniper.net/us/en/products-services/security/srx-series/)

- [ ] لینوکس
- [ ] MacOS
- [ ] ویندوز
- [x] دیگران

### راهنما:

~~~
[edit security nat]

destination {
    pool DNS-Tiarap {
        address 174.138.21.128/32 port 5003;
    }
    rule-set Redirect-DNS {
        from interface ge-0/0/1.0;
        rule DNS-All {
            match {
                destination-address 0.0.0.0/0;
                destination-port 53;
            }
            then {
                destination-nat pool DNS-Tiarap;
            }
        }
    }
}

~~~

## [میکروتیک](https://mikrotik.com/)

- [x] لینوکس
- [ ] MacOS
- [ ] ویندوز
- [ ] دیگران

### راهنما:

در `/ip firewall nat`

`add chain=dstnat action=dst-nat to-addresses=174.138.21.128 to-ports=5003 protocol=tcp dst-port=53`

`add chain=dstnat action=dst-nat to-addresses=174.138.21.128 to-ports=5003 protocol=tcp dst-port=53`

https://wiki.mikrotik.com/wiki/Force_users_to_use_specified_DNS_server

## [Openwrt](https://openwrt.org/)

- [x] لینوکس
- [ ] MacOS
- [ ] ویندوز
- [ ] دیگران

### راهنما:

`uci -q delete dhcp.@dnsmasq[0].server`

`uci add_list dhcp.@dnsmasq[0].server="174.138.21.128#5003"`

`uci set dhcp.@dnsmasq[0].noresolv="1"`

`uci commit dhcp`

`/etc/init.d/dnsmasq restart`

## [pfSense](https://www.pfsense.org/)/[OPNsense](https://opnsense.org/)

- [ ] لینوکس
- [ ] MacOS
- [ ] ویندوز
- [x] دیگران

### راهنما

منو > سرویس > حل‌کننده DNS

 گزینه‌های عمومی حل‌کننده DNS
 - فعال کردن `حل‌کننده DNS`
 - فعال کردن `حالت ارسال`
 - ذخیره

منو > سیستم > تنظیمات عمومی

 تنظیمات سرور DNS
 - سرور DNS `174.138.21.128`
 - ذخیره

منو > فایروال > NAT > ارسال پورت

 - رابط: `WAN`
 - پروتکل: `TCP/UDP`
 - مقصد: `میزبان یا نام مستعار تکی` `174.138.21.128`
 - محدوده پورت مقصد: از پورت: `DNS` - تا پورت: `DNS`
 - IP هدف تغییر مسیر: `174.138.21.128`
 - پورت هدف تغییر مسیر: `دیگران` `5003`
 - ذخیره

<a href="https://user-images.githubusercontent.com/787301/97931443-91a2aa00-1da8-11eb-9d38-b4db404a5d4f.png"><img src="https://user-images.githubusercontent.com/787301/97931443-91a2aa00-1da8-11eb-9d38-b4db404a5d4f.png"></a>

<a href="https://user-images.githubusercontent.com/787301/97931665-12fa3c80-1da9-11eb-8f4b-79577660c693.png"><img src="https://user-images.githubusercontent.com/787301/97931665-12fa3c80-1da9-11eb-8f4b-79577660c693.png"></a>

## [Pi-hole](https://pi-hole.net/)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

<a href="https://user-images.githubusercontent.com/787301/98156949-89b34900-1f13-11eb-8bc6-f7c3ff96ee6e.jpg"><img src="https://user-images.githubusercontent.com/787301/98156949-89b34900-1f13-11eb-8bc6-f7c3ff96ee6e.jpg"></a>

https://docs.pi-hole.net/guides/unbound/

## [systemd-resolved](https://www.freedesktop.org/software/systemd/man/systemd-resolved.service.html)

- [x] لینوکس
- [ ] MacOS
- [ ] ویندوز
- [ ] دیگران

### راهنما:

ویرایش `/etc/systemd/resolved.conf`، `DNS=` را به صورت زیر تغییر دهید:

~~~
[Resolve]
DNS=174.138.21.128:5003
~~~

راه‌اندازی مجدد systemd-resolved:

`systemctl restart systemd-resolve`

بررسی وضعیت:

`resolvectl status`

https://www.freedesktop.org/software/systemd/man/resolved.conf.html

## [سرور DNS تکنیسیوم](https://technitium.com/dns/)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

<a href="https://user-images.githubusercontent.com/787301/98113988-79817680-1edf-11eb-9701-b9518a6a4c4b.jpg"><img src="https://user-images.githubusercontent.com/787301/98113988-79817680-1edf-11eb-9701-b9518a6a4c4b.jpg"></a>

https://blog.technitium.com/2018/06/configuring-dns-server-for-privacy.html

## [Ubnt EdgeOS](https://www.ui.com/edgemax/edgerouter/)

- [ ] لینوکس
- [ ] MacOS
- [ ] ویندوز
- [x] دیگران

### راهنما:

`eth0 = رابط WAN`

`eth1 = رابط LAN`

ورود به حالت پیکربندی

`configure`

تنظیم IP `174.138.21.128` و پورت `5003` DNS

`set service dns forwarding options 'server=174.138.21.128#5003'`

گوش دادن روی رابط LAN

`set service dns forwarding listen-on eth0`

به dhcp-client بگویید سرور DNS ISP را به /etc/resolv.conf اضافه نکند

`set interfaces ethernet eth0 dhcp-options name-server no-update`

تایید و ذخیره پیکربندی

`commit; save`

https://help.ui.com/hc/en-us/articles/115010913367-EdgeRouter-DNS-Forwarding-Setup-and-Options

## [Unbound](https://www.nlnetlabs.nl/projects/unbound/about/)

- [x] لینوکس
- [x] MacOS
- [x] ویندوز
- [x] دیگران

### راهنما:

~~~
forward-zone:
        name: "."
        forward-addr: 174.138.21.128@5003
~~~

https://wiki.alpinelinux.org/wiki/Setting_up_unbound_DNS_server

## [YogaDNS](https://www.yogadns.com/)

- [ ] لینوکس
- [ ] MacOS
- [x] ویندوز
- [ ] دیگران

### راهنما:

![yogadns](https://user-images.githubusercontent.com/787301/97865114-a77e8380-1d44-11eb-9fde-b704d47dbe40.png)

https://www.yogadns.com/docs/#servers
