---
title: "Download from Google Drive using Command Line Interface (CLI)"
date: 2021-06-08T17:30:13+07:00
description: "Download from Google Drive using Command Line Interface (CLI), using curl, Linux, MacOS, Windows"
image: drive.svg
categories: ["Linux", "Windows", "Tutorial"]
tags: ["Linux", "Windows", "Tutorial"]
keywords:
  [
    "Download from Google Drive using Aria2",
    "Download from Google Drive using CLI",
    "Download from Google Drive using Command Line Interface (CLI)",
    "Download from Google Drive using Curl",
    "Download from Google Drive using Wget",
    "Download from Google Drive Without Limitation",
  ]
---

<svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-google-drive" width="200" height="200" viewBox="0 0 24 24" stroke-width="1.5" stroke="CurrentColor" fill="none" stroke-linecap="round" stroke-linejoin="round" style="display: block;margin: auto;">
    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
    <path d="M12 10l-6 10l-3 -5l6 -10z"></path>
    <path d="M9 15h12l-3 5h-12"></path>
    <path d="M15 15l-6 -10h6l6 10z"></path>
</svg>

In this tutorial, I will share How to Download a File in Google Drive using Command Line Interface, using this script you can download a file without file size limitation, maybe you can use **[gdown](https://github.com/wkentaro/gdown)** but **[gdown](https://github.com/wkentaro/gdown)** sometimes still error if you **[download a big file](https://github.com/wkentaro/gdown/issues/26)** from Google Drive

## Before Download a Big File, Create OAuth Authentication First
This script also same if you don't configure first, can't download a big file from Google Drive, so you must create **OAuth Credentials** first

1. Login to **[Google Developer Console](https://console.developers.google.com/)** and Create Project first 
    * Note: If you don't have project Click on **Select Project** → **New Project**

{{< spoiler text="Click to Show Image" >}}
![Create Project](rmdhnreza.my.id.google.drive.cli.1.webp) ![Create Project](rmdhnreza.my.id.google.drive.cli.2.webp)
{{< /spoiler >}}

2. Click Hamburger menu on the left → **Select API & Services** → **Select Library**

{{< spoiler text="Click to Show Image" >}}
![API & Services](rmdhnreza.my.id.google.drive.cli.3.webp)
{{< /spoiler >}}

3. Search for **Google Drive API** and **Enable Google Drive API**

{{< spoiler text="Click to Show Image" >}}
![Enable Drive API](rmdhnreza.my.id.google.drive.cli.4.webp) ![Enable Drive API](rmdhnreza.my.id.google.drive.cli.5.webp) 
{{< /spoiler >}}

4. Click Credentials on left pane and Click **+ CREATE CREDENTIALS** and select **OAuth Client ID**

{{< spoiler text="Click to Show Image" >}}
![Create Credentials](rmdhnreza.my.id.google.drive.cli.6.webp) ![Create Credentials](rmdhnreza.my.id.google.drive.cli.7.webp) 
{{< /spoiler >}}

**Note:** If you face this error, click on **CONFIGURE CONSENT SCREEN**

{{< spoiler text="Click to Show Image" >}}
![CONFIGURE CONSENT SCREEN](rmdhnreza.my.id.google.drive.cli.8.webp) 
{{< /spoiler >}}

  * Select **External** and click **CREATE**

{{< spoiler text="Click to Show Image" >}}
![CONFIGURE CONSENT SCREEN](rmdhnreza.my.id.google.drive.cli.9.webp) 
{{< /spoiler >}}

  * Just fill in the section
    * App name *
    * User support email
    * Email addresses
  * Click **SAVE AND CONTINUE** until **Step 4** and **Click Publish** in the **Production** section
  * Back to Create Credentials
5. After select **OAuth Client ID**
    * Application type select **Desktop app**
    * Name fill whatever you want
    * Click **CREATE**
6. If success, you will get Client ID and Client Secret, **Save it**.

{{< spoiler text="Click to Show Image" >}}
![Client ID and Secret ID](rmdhnreza.my.id.google.drive.cli.10.webp) 
{{< /spoiler >}}

## Download a File From Google Drive
1. This script you can find it in **[Official GitHub Repository](https://github.com/Akianonymus/gdrive-downloader/)**
2. To install this script, just execute command
```ruby
curl -Ls --compressed https://drivedl.cf | sh -s
```
alternatively, you can use the original github url instead of https://drivedl.cf
```ruby
curl -Ls --compressed  https://github.com/Akianonymus/gdrive-downloader/raw/master/install.sh | sh -s
```
3. This script installed at `${HOME}/.gdrive-downloader/`
4. To Download a File from Google Drive (Especially big file) use command
```ruby
gdl -o driveID
```

{{< spoiler text="Click to Show Image" >}}
![Download File from Google Drive](rmdhnreza.my.id.google.drive.cli.11.webp) 
{{< /spoiler >}}


5. And you will be asked to put (Only one time), and this config file saved in `${HOME}/.gdl.conf`
    * Client ID → Fill in the client ID with the one you created earlier
    * Client Secret → Fill in the client Secret with the one you created earlier
    * Refresh Token → Just blank and hit enter
    * And the link will appear, click on that link to get **authorization code**
{{< spoiler text="Click to Show Image" >}}
![Download File from Google Drive](rmdhnreza.my.id.google.drive.cli.12.webp)
{{< /spoiler >}}
      * Login with your Google Account
{{< spoiler text="Click to Show Image" >}}
![Login Google Account](rmdhnreza.my.id.google.drive.cli.13.webp)
{{< /spoiler >}}
      * **In this case** Warning like this is normal, because app we create earlier is not verified by Google, so just click **show advanced** and click Go to **yourappname (unsafe)**
{{< spoiler text="Click to Show Image" >}}
![Warning](rmdhnreza.my.id.google.drive.cli.14.webp)
{{< /spoiler >}}
      * Click Allow
{{< spoiler text="Click to Show Image" >}}
![Allow Apps](rmdhnreza.my.id.google.drive.cli.15.webp)
{{< /spoiler >}}
      * Click Allow Again
{{< spoiler text="Click to Show Image" >}}
![Allow Apps](rmdhnreza.my.id.google.drive.cli.16.webp)
{{< /spoiler >}}
      * And you get **authorization code** copy and paste to terminal console
{{< spoiler text="Click to Show Image" >}}
![Auth code](rmdhnreza.my.id.google.drive.cli.17.webp)
{{< /spoiler >}}
6. And file will be downloaded immediately

{{< spoiler text="Click to Show Image" >}}
![Download File](rmdhnreza.my.id.google.drive.cli.19.webp)
{{< /spoiler >}}

If you want to download a big file again, just use command `gdl -o driveID`  and will not be asked to enter the auth code.

For Documentation, you can see in [GitHub Repository](https://github.com/Akianonymus/gdrive-downloader/)

Special Thanks to: **[Akianonymus](https://github.com/Akianonymus)** for making a great script!