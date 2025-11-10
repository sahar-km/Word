<p alignt="center">
<a href="https://twitter.com/tomfishburne/status/1125146808882089984?s=20"><img src="https://user-images.githubusercontent.com/787301/97933370-88680c00-1dad-11eb-83d1-dc53d01c0571.jpg"></a>
</p>

# Name

* `resolver.tiar.app`

* `IPv4: 174.138.21.128 port 53 or port 5003`

* `IPv6: [2400:6180:0:d0::5f6e:4001] port 53 or port 5003`

# Table of Contents

* [Features](#features)

* [Configuration](#configuration)

  * [Acrylic DNS Proxy](#acrylic-dns-proxy)
  * [Adguard dnsproxy](#adguard-dnsproxy)
  * [Adguard Home](#adguard-home)
  * [Dnsmasq](#dnsmasq)
  * [Juniper SRX](#juniper-srx)
  * [Mikrotik](#mikrotik)
  * [OpenWrt](#openwrt)
  * [pfSense/OPNsense](#pfsenseopnsense)
  * [Pi-hole](#pi-hole)
  * [systemd-resolved](#systemd-resolved)
  * [Technitium DNS Server](#technitium-dns-server)
  * [Ubnt EdgeOS](#ubnt-edgeos)
  * [Unbound](#unbound)
  * [YogaDNS](#yogadns)


# Features

- [x] Filter: Ad, Ad-tracking and Malware (AdBlock)
- [x] DNSSEC Validation
- [x] No EDNS Client Subnet (ECS)
- [x] No logs
- [x] Free

# Configuration

## [Acrylic DNS Proxy](https://mayakron.altervista.org/support/acrylic/Home.htm)

- [ ] Linux
- [ ] MacOS
- [x] Windows
- [ ] Others

### Howto:

~~~
PrimaryServerAddress=174.138.21.128
PrimaryServerPort=5003
~~~

https://mayakron.altervista.org/support/acrylic/Configuration.htm

## [Adguard dnsproxy](https://github.com/AdguardTeam/dnsproxy)

- [x] Linux
- [x] MacOS
- [x] Windows
- [x] Others

### Howto:

`./dnsproxy -u 174.138.21.128:5003 -v -o log.txt`

https://github.com/AdguardTeam/dnsproxy

## [Adguard Home](https://github.com/AdguardTeam/AdguardHome)

- [x] Linux
- [x] MacOS
- [x] Windows
- [x] Others

### Howto:

![adguard_home](https://user-images.githubusercontent.com/787301/97778357-a36e2c80-1bb1-11eb-9701-8079900a8fe9.png)

https://adguard.com/en/blog/in-depth-review-adguard-home.html#dns

## [Dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html)

- [x] Linux
- [x] MacOS
- [ ] Windows
- [x] Others

### Howto:

Edit `/etc/dnsmasq.conf`

~~~
no-resolv
server=174.138.21.128#5003
cache-size=1000

~~~

Edit `/etc/resolv.conf`

~~~
nameserver ::1
nameserver 127.0.0.1
options trust-ad

~~~

http://www.thekelleys.org.uk/dnsmasq/docs/dnsmasq-man.html

## [Juniper SRX](https://www.juniper.net/us/en/products-services/security/srx-series/)

- [ ] Linux
- [ ] MacOS
- [ ] Windows
- [x] Others

### Howto:

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

## [Mikrotik](https://mikrotik.com/)

- [x] Linux
- [ ] MacOS
- [ ] Windows
- [ ] Others

### Howto:

In `/ip firewall nat`

`add chain=dstnat action=dst-nat to-addresses=174.138.21.128 to-ports=5003 protocol=tcp dst-port=53`

`add chain=dstnat action=dst-nat to-addresses=174.138.21.128 to-ports=5003 protocol=tcp dst-port=53`

https://wiki.mikrotik.com/wiki/Force_users_to_use_specified_DNS_server

## [Openwrt](https://openwrt.org/)

- [x] Linux
- [ ] MacOS
- [ ] Windows
- [ ] Others

### Howto:

`uci -q delete dhcp.@dnsmasq[0].server`

`uci add_list dhcp.@dnsmasq[0].server="174.138.21.128#5003"`

`uci set dhcp.@dnsmasq[0].noresolv="1"`

`uci commit dhcp`

`/etc/init.d/dnsmasq restart`

## [pfSense](https://www.pfsense.org/)/[OPNsense](https://opnsense.org/)

- [ ] Linux
- [ ] MacOS
- [ ] Windows
- [x] Others

### Howto

Menu > Service > DNS Resolver

 General DNS Resolver Options
 - Enable `DNS Resolver`
 - Enable `Forwarding Mode`
 - Save

Menu > System > General Setup

 DNS Server Settings
 - DNS Server `174.138.21.128`
 - Save

Menu > Firewall > NAT > Port Forward

 - Interface: `WAN`
 - Protocol: `TCP/UDP`
 - Destination: `Single host or alias` `174.138.21.128`
 - Destination Port range: From port: `DNS` - To port: `DNS`
 - Redirect target IP: `174.138.21.128`
 - Redirect target port: `Others` `5003`
 - Save

<a href="https://user-images.githubusercontent.com/787301/97931443-91a2aa00-1da8-11eb-9d38-b4db404a5d4f.png"><img src="https://user-images.githubusercontent.com/787301/97931443-91a2aa00-1da8-11eb-9d38-b4db404a5d4f.png"></a>

<a href="https://user-images.githubusercontent.com/787301/97931665-12fa3c80-1da9-11eb-8f4b-79577660c693.png"><img src="https://user-images.githubusercontent.com/787301/97931665-12fa3c80-1da9-11eb-8f4b-79577660c693.png"></a>

## [Pi-hole](https://pi-hole.net/)

- [x] Linux
- [x] MacOS
- [x] Windows
- [x] Others

### Howto:

<a href="https://user-images.githubusercontent.com/787301/98156949-89b34900-1f13-11eb-8bc6-f7c3ff96ee6e.jpg"><img src="https://user-images.githubusercontent.com/787301/98156949-89b34900-1f13-11eb-8bc6-f7c3ff96ee6e.jpg"></a>

https://docs.pi-hole.net/guides/unbound/

## [systemd-resolved](https://www.freedesktop.org/software/systemd/man/systemd-resolved.service.html)

- [x] Linux
- [ ] MacOS
- [ ] Windows
- [ ] Others

### Howto:

edit `/etc/systemd/resolved.conf`, change `DNS=` as below:

~~~
[Resolve]
DNS=174.138.21.128:5003
~~~

Restart systemd-resolved:

`systemctl restart systemd-resolve`

Check status:

`resolvectl status`

https://www.freedesktop.org/software/systemd/man/resolved.conf.html

## [Technitium DNS Server](https://technitium.com/dns/)

- [x] Linux
- [x] MacOS
- [x] Windows
- [x] Others

### Howto:

<a href="https://user-images.githubusercontent.com/787301/98113988-79817680-1edf-11eb-9701-b9518a6a4c4b.jpg"><img src="https://user-images.githubusercontent.com/787301/98113988-79817680-1edf-11eb-9701-b9518a6a4c4b.jpg"></a>

https://blog.technitium.com/2018/06/configuring-dns-server-for-privacy.html

## [Ubnt EdgeOS](https://www.ui.com/edgemax/edgerouter/)

- [ ] Linux
- [ ] MacOS
- [ ] Windows
- [x] Others

### Howto:

`eth0 = WAN interface`

`eth1 = LAN interface`

Enter configuration mode

`configure`

Set DNS IP `174.138.21.128` and Port `5003`

`set service dns forwarding options 'server=174.138.21.128#5003'`

Listen on LAN interface

`set service dns forwarding listen-on eth0`

tell dhcp-client not to add the ISP DNS server to /etc/resolv.conf

`set interfaces ethernet eth0 dhcp-options name-server no-update`

commit & save configuration

`commit; save`

https://help.ui.com/hc/en-us/articles/115010913367-EdgeRouter-DNS-Forwarding-Setup-and-Options

## [Unbound](https://www.nlnetlabs.nl/projects/unbound/about/)

- [x] Linux
- [x] MacOS
- [x] Windows
- [x] Others

### Howto:

~~~
forward-zone:
        name: "."
        forward-addr: 174.138.21.128@5003
~~~

https://wiki.alpinelinux.org/wiki/Setting_up_unbound_DNS_server

## [YogaDNS](https://www.yogadns.com/)

- [ ] Linux
- [ ] MacOS
- [x] Windows
- [ ] Others

### Howto:

![yogadns](https://user-images.githubusercontent.com/787301/97865114-a77e8380-1d44-11eb-9fde-b704d47dbe40.png)

https://www.yogadns.com/docs/#servers

