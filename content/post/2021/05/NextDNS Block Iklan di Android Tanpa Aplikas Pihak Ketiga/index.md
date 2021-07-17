---
title: "Cara Menginstall NextDNS di Semua Perangkat"
date: 2021-05-30T00:30:13+07:00
description: "Cara Menginstall NextDNS di Semua Perangkat, Cara Block Iklan di Android Tanpa root tanpa aplikasi pihak ketiga"
categories: ["Tutorial","Android"]
tags: ["Tutorial","Android"]
keywords:
  [
    "NextDNS Block Iklan di Android Tanpa Aplikasi Pihak Ketiga",
    "Cara Block Iklan di Android Tanpa root",
    "Block Iklan di Android",
    "Block Iklan di Android Tanpa Aplikasi Pihak Ketiga",
    "Cara Menginstall NextDNS di Semua Perangkat",
    "Cara Menginstall NextDNS di Windows",
    "Cara Menginstall NextDNS di Linux",
    "Cara Menginstall NextDNS di Android"
  ]
image: nextdns.svg
---

![NextDNS](rmdhnreza.my.id.next.dns.webp)

## NextDNS The new firewall for the modern Internet.
NextDNS melindungi Anda dari semua jenis ancaman keamanan (*malware*), memblokir iklan dan pelacak di situs web dan aplikasi (*ads & trackers*), serta menyediakan Internet yang aman dan terawasi untuk anak-anak (*Family Protection*) — di semua perangkat dan di semua jaringan.

## Settings NextDNS di
- [Android](#settings-nextdns-di-android)
- [Linux](#settings-nextdns-di-linux)
- [Windows](#settings-nextdns-di-windows)


## Mendaftar dan Setting NextDNS
1. Kalian kunjungi halaman [NextDNS.io](https://my.nextdns.io/signup)
2. Daftar Menggunakan alamat E-Mail

![Mendaftar NextDNS](rmdhnreza.my.id.next.dns.1.webp)

3. Setelah mendaftar maka akan muncul tampilan seperti ini, **dan kalian ingat-ingat ID Next DNS kalian, karena ini akan dipakai saat nanti dipasang ke perangkat kalian.** Tapi sebelum memulai pemasangan NextDNS ke perangkat kalian, lebih baik kalian setting-setting dulu NextDNS nya.


![NextDNS ID](rmdhnreza.my.id.next.dns.id.webp) ![NextDNS](rmdhnreza.my.id.next.dns.2.webp)

  * **Tab Security**
    * Pada bagian ini kalian bisa enable Google Safesearch, Block Domain yang baru saja didaftarkan, dll.

{{< spoiler text="Klik Untuk Melihat Gambar" >}}

![Tab Security](rmdhnreza.my.id.next.dns.3.webp)

{{< /spoiler >}}

  * **Tab Privacy**
    * Pada bagian blocklist, kalian klik **ADD A BLOCKLIST**, dan kalian add filters yang kalian butuhkan, disini saya menambahkan filter
      * ABPindo
      * AdAway
      * AdGuard DNS filter
      * EasyList
      * EasyPrivacy
      * Energized Ultimate
      * NextDNS Ads & Trackers Blocklist (Default)
      * notracking
      * oisd
      * Steven Black
    * Pada Native Tracking Protection saya tambahkan semuanya
    * Block Disguised Third-Party Trackers - On
    * Allow Affiliate & Tracking Links - Off

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Tab Privacy](rmdhnreza.my.id.next.dns.4.webp)
{{< /spoiler >}}

  * **Tab Parental Control**
    * Jika kalian ingin block situs porno, judi, social media, dll. Ada pada bagian ini, silahkan tinggal add saja filter nya sesuai yang kalian butuhkan

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Parental Control](rmdhnreza.my.id.next.dns.5.webp)
{{< /spoiler >}}

  * **Tab Denylist**
    * Di Tab ini jika kalian ingin block domain manual

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Tab Denylist](rmdhnreza.my.id.next.dns.6.webp)
{{< /spoiler >}}

  * **Tab Allowlist**
    * Di Tab ini jika kalian ingin membuka situs yang terblock

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Tab Allowlist](rmdhnreza.my.id.next.dns.7.webp)
{{< /spoiler >}}

  * **Tab Analitycs**
    * Di Tab ini berisi informasi total query yang masuk, **Untuk NextDNS Free itu dibatasi 300,000 query per bulan.**

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Tab Analitycs](rmdhnreza.my.id.next.dns.8.webp)
{{< /spoiler >}}

  * **Tab Logs**
    * Berisi domain yang di akses di perangkat yang dipasang NextDNS

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Tab Logs](rmdhnreza.my.id.next.dns.9.webp)
{{< /spoiler >}}

  * **Tab Settings**
    * Untuk settings untuk config NextDNS, seperti nama, block page, dll.

{{< spoiler text="Klik Untuk Melihat Gambar" >}}
![Tab Settings](rmdhnreza.my.id.next.dns.10.webp)
{{< /spoiler >}}

## Settings NextDNS di Android
* **Android 9 Keatas**
  - Untuk Android 9 keatas kalian bisa menggunakan **Private DNS**
    1. Masuk ke Settings → Network & internet → Advanced → Private DNS. (Atau Search Private DNS)
    2. Pilih pada Private DNS provider hostname option.
    3. Masukan ID.dns.nextdns.io
* **Android 8 Kebawah**
  - Untuk Android 8 kebawah kalian bisa menggunakan aplikasi official NextDNS bisa di undu di playstore
    1. Install app [NextDNS](https://play.google.com/store/apps/details?id=io.nextdns.NextDNS)
    2. Buka aplikasi nya
    3. Masuk ke bagian Settings (icon gear)
    4. On kan `Use Custom Configuration`
    5. Masukan ID NextDNS nya.

## Settings NextDNS di Linux
* Untuk Linux disini saya menggunakan **DNSCrypt-Proxy**, tapi jika kalian ingin menggunakan aplikasi official NextDNS nya kalian bisa lihat di [Github Wiki](https://github.com/nextdns/nextdns/wiki)
  1. Edit file **dnscrypt-proxy.toml** menggunakan editor kesukaan kalian, lokasi config berada di `/etc/dnscrypt-proxy/dnscrypt-proxy.toml`
  2. Edit bagian `server_names` ubah menjadi `server_names = ['NextDNS-ID']`, jika sebelumnya sudah kalian settings cukup tambahkan saja tanda `#` (jadi tidak perlu dihapus)
  3. Pada bagian `[Static]` tambahkan
```toml
[static]
  [static.'NextDNS-ID']
  stamp = 'sdns://AgEAAAAAAAAACjQ1LjkwLjI4LjAADmRucy5uZXh0ZG5zLmlvBy9lZjZlZDE'
```
  4. Save & Restart NextDNS nya
  5. Ubah DNS ke `127.0.0.1` di `/etc/resolv.conf`

## Settings NextDNS di Windows
1. Download installer [NextDNS](https://nextdns.io/download/windows/stable)
2. Setelah terinstall, klik kanan pada icon NextDNS di system tray, lalu buka Settings, set ID nya menggunakan ID NextDNS kalian
3. Klik kanan pada icon NextDNS di system tray, lalu klik Enable
4. Ubah DNS ke `127.0.0.1` di Network Adapter IPv4