---
title: "Membuka Situs Terblokir Menggunakan DNS Over HTTPS"
date: 2021-01-08T15:33:28+07:00
Description: "Membuka Situs Terblokir Menggunakan DNS Over HTTPS"
categories: ["Android", "Linux", "Windows", "Tutorial"]
tags: ["Android", "Linux", "Windows", "Tutorial"]
image: dns.svg
---
Kali ini saya akan share cara **Membuka Situs Terblokir Menggunakan DNS Over HTTPS** atau biasa disingkat **DoH**, cara ini tidak menggunakan aplikasi pihak ketiga, seperti VPN atau yang lainnya, cara ini hanya membutuhkan **Browser Up-to-Date**. Kelebihan menggunakan **DoH** ini tidak terlalu berpengaruh pada kecepatan internet kalian, tetapi kekurangan **DoH** ini hanya bisa membuka situs terblokir yang menggunakan protokol **HTTPS**, tapi tenang saja karena tahun 2021 ini hampir semua web sudah menggunakan protokol **HTTPS**.

## Menggunakan DNS Over HTTPS Google Chrome
Untuk Google Chrome sendiri sudah support DNS Over HTTPS di sistem operasi Windows, Android, hanya saja di sistem operasi Linux belum support (teatpi bisa menggunakan policy). Untuk mengaktifkannya kalian bisa
1. Masuk ke bagian **Settings** (Klik titik 3 dibagian atas kanan lalu pilih settings)
2. Pilih **Privacy and Security** (dibagian kiri) dan kalian Klik **Security**
3. On kan **Use Secure DNS** kalian pilih **With:** lalu disana kalian pilih DNS yang kalian pakai
![Dns Over HTTPS Chrome](https://lh4.googleusercontent.com/zem6Estu-y7LDKLscD6R_08bBVr1lXNda5PjEWMi7KizMcxCs6NqyaIv0htyS-zOPnSwC1b1084HpbMo3ZsJAHwHuuuVNTl_-fbfcgJX5h-6pJzZ-ipl3gAtXCCEh9_znbg4b6FK)

Untuk sistem operasi Linux kalian bisa menggunakan policy
1. Kalian buat file **policies.json** di
   * /etc/opt/chrome/policies/managed/policies.json (Untuk Google Chrome)
   * /etc/opt/chromium/policies/managed/policies.json (Untuk Chromium Based Browser)
2. Lalu isikan
```json
{
	"DnsOverHttpsMode"      : "secure",
	"DnsOverHttpsTemplates" : "https://dns.quad9.net/dns-query",
}
```
3. Save

**Note:** DNS Over HTTPS diatas (Untuk Linux) menggunakan DNS quad9, untuk DNS lain kalian bisa ubah templatenya dengan
   *  https://dns.google/dns-query (DNS Google)
   *  https://cloudflare-dns.com/dns-query (DNS Cloudflare)

## Menggunakan DNS Over HTTPS Microsoft Edge (Chromium)
Untuk Microsoft Edge sendiri sudah support **DNS Over HTTPS** di sistem operasi Windows, Linux. Untuk mengaktifkannya kalian bisa
1. Masuk ke bagian **settings** (Klik titik 3 dibagian atas kanan lalu pilih settings)
2. Pilih **Privacy, search, and services** (dibagian kiri) dan kalian scroll kebawah sampai bagian **Security**
3. On kan **Use Secure DNS** kalian pilih **Choose a service provider** klik kolomnya lalu disana kalian pilih DNS yang kalian pakai


![Dns Over HTTPS Microsoft Edge](https://1.bp.blogspot.com/-zPY8bFYsd4o/X_gdY5FerAI/AAAAAAAAC0M/qsrQlQJuyIQcea5chT6TFFjfhCFoOgpnwCLcBGAsYHQ/s1920/doh-edge.jpg)

## Menggunakan DNS Over HTTPS Mozilla Firefox
Untuk Microsoft Edge sendiri sudah support **DNS Over HTTPS** di sistem operasi Windows, Linux. Untuk mengaktifkannya kalian bisa
1. Masuk ke bagian **Preferences** (Klik strip 3 dibagian atas kanan lalu pilih Preferences)
2. Scroll ke paling bawah sampai bagian **Network Settings** dan kalian klik **Settings**
3. Ceklis **Enable DNS over HTTPS** lalu kalian pilih **Cloudflare** atau **NextDNS**
![Dns Over HTTPS Firefox](https://1.bp.blogspot.com/-EODEbdBhGds/X_gdzpyYHwI/AAAAAAAAC0U/FJli4jERHV8dwTekdBEcveeMpR_d3uE8wCLcBGAsYHQ/s1920/doh-firefox.jpg)
## Menggunakan DNS Over HTTPS Andorid 9+
Untuk Android 9 keatas sudah support **DNS Over HTTPS** atau **Private DNS**. Untuk mengaktifkannya kalian bisa
1. Buka **Settings** ⇢ **Connections** ⇢ **Cari Private DNS** atau Jika kalian mau lebih cepat kalian search aja **“Private DNS”** dibagian settings
2. Kalian Klik **Private DNS** nya dan Pilih **Private DNS provider hostname**
3. Kalian isi
   * **dns.google** untuk DNS Google
   * **1dot1dot1dot1.cloudflare-dns.com** untuk DNS Cloudflare
4. Jika sudah klik Save, kalian sudah bisa membuka situs yang terblokir
![Dns Over HTTPS Android](https://1.bp.blogspot.com/-uiWIS2iAzYI/X_gehiS1WgI/AAAAAAAAC0g/pZ6n5ZLJa0I8MSJcunp_T31C85uPxfttACLcBGAsYHQ/s1280/doh-android.jpg)