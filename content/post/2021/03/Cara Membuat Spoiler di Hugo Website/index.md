---
title: "Cara Membuat Spoiler Di Hugo Website"
date: 2021-03-08T23:02:16+07:00
description: Tutorial Membuat Spoiler di Website yang Menggunakan Framework Hugo
categories: ["Hugo", "Tutorial"]
tags: ["Hugo", "Tutorial"]
image: hugo.svg
keywords: ["Spoiler Hugo", "Markdown Spoiler", "Cara Membuat Spoiler di Hugo", "Cara Membuat Spoiler di Hugo Static", "Create Spoiler Hugo Website"]
---

Kalian yang suka ikut forum (seperti Kaskus, Reddit, Tenforums, MDL, dll) pasti sudah tahu apa itu spoiler. Spoiler sangat sering digunakan, bahkan dianjurkan jika kalian ingin membuat postingan gambar yang berukuran besar ataupun video.

Untuk bisa membuat spoiler pada website yang menggunakan framework hugo, kita akan menyisipkan beberapa baris kode HTML saja (terutama untuk yang temanya belum support spoiler), Kode ini tidak menggunakan Javascript ataupun JQuery, murni menggunakan HTML saja. Berikut ini adalah langkah-langkah yang bisa kalian coba jika ingin membuat spoiler pada postingan blog yang menggunakan framework hugo.

1. Buat *shortcode* dengan nama **spoiler.html** di project hugo kalian, *Shortcode* ini bisa ditempatkan di bagian Tema atau langsung di bagian layouts pada project hugo.

### Bagian Layouts (Disarankan)
```
rmdhnreza.my.id
└───layouts
    └───shortcodes
        └───spoiler.html
```
### Bagian Tema
```
rmdhnreza.my.id
└───themes
    └───nama-tema
        └───layouts
            └───shortcodes
                └───spoiler.html
```
2. Isikan kode berikut pada file **spoiler.html**. *Snippet* HTML ini diambil dari [Wowchemy Hugo Modules](https://github.com/wowchemy/wowchemy-hugo-modules/blob/5072eddcc1eb7fcb3749a61fe2e83f4e1c36c557/wowchemy/layouts/shortcodes/spoiler.html) 
```html
{{- $id := printf "spoiler-%d" .Ordinal -}}

<details class="spoiler {{ .Get "class" }}" {{ with .Get "style" }}style="{{ . | safeCSS }}"{{ end }} id="{{$id}}">
  <summary>{{ .Get "text" | markdownify | emojify }}</summary>
  <p>{{ .Inner | markdownify | emojify }}</p>
</details>
```
3. Jika sudah kalian save.
4. Untuk membuat spoiler kalian tambahkan kode berikut pada postingan kalian

![Spoiler Hugo](1.webp)

5. Jadinya seperti ini

{{< spoiler text="Test Spoiler" >}}
Test spoiler hugo rmdhnreza.my.id
{{< /spoiler >}}

6. Jika kalian ingin mengubah cursor nya menjadi pointer, kalian bisa tambahkan kode CSS berikut
```css
summary {
  cursor: pointer;
}
```
