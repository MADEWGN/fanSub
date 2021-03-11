---
title: "Mengatasi Windows 10 Tidak Add Bisa Account Di Windows Mail"
date: 2021-01-31T00:42:03+07:00
categories: ["Tutorial", "Windows 10"]
tags: ["Tutorial", "Windows 10"]
image: mail.svg
---

Biasanya ini terjadi ketika kalian sudah menghapus `bloatware` di windows 10 kalian, Jadinya ada software core yang terhapus.

Untuk mengatasi tidak bisa menambahkan akun di aplikasi Mail Windows 10 caranya cukup mudah

1. Kalian buka `Windows Powershell (Admin)`

![Mengatasi Windows 10 Tidak Bisa Add Account di Windows Mail](1.jpg)

2. Masukan perintah berikut
```powershell
dism /online /add-capability /capabilityname:OneCoreUAP.OneSync~~~~0.0.1.0
```

![Mengatasi Windows 10 Tidak Bisa Add Account di Windows Mail](2.jpg)

3. Tunggu sampai selesai (_This operation completed successfully_), biasanya tidak sampai 5 menit

![Mengatasi Windows 10 Tidak Bisa Add Account di Windows Mail](3.jpg)

4. Setelah selesai kalian coba add akun di Windows Mail tanpa perlu restart windows kalian