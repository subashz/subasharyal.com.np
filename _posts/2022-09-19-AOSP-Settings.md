---
title: Customize Settings app with overlay
author: Subash Aryal
category:
layout: post
---

The Android Open Source Project (AOSP) provides a solid foundation for building custom Android applications. One of the key components of any Android application is the Settings app, which allows users to manage various aspects of their device.

In this article, we will discuss how to modify the AOSP Settings app by changing its appearance and behavior using an overlay. Specifically, we will explore how to change the color of the Settings app’s header and how to modify the behavior of the Wi-Fi and Bluetooth toggles.

What is an overlay?

An overlay is a way to modify the appearance and behavior of an existing Android application without changing its source code. Essentially, an overlay is a set of resources, such as layouts, styles, and strings, that are applied on top of the base application.

An overlay is applied at runtime, which means that you can modify the appearance and behavior of an application without having to rebuild it. This makes overlays an ideal solution for customizing the AOSP Settings app.

Modifying the AOSP Settings app using an overlay

Let’s start by modifying the color of the Settings app’s header. To do this, we will create an overlay that changes the color of the header. Here are the steps to follow:

Create a new directory in your AOSP project’s overlay directory. For example, you can create a directory called “my_settings_overlay”.

Inside the “my_settings_overlay” directory, create a new directory called “res”.

Inside the “res” directory, create a new directory called “values”.

Inside the “values” directory, create a new file called “styles.xml”.

Open the “styles.xml” file in a text editor and add the following code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <style name="SettingsTheme" parent="@android:style/Theme.Material.Light">
        <item name="android:colorPrimary">#FF4081</item>
    </style>
</resources>
```

In this code, we are defining a new style called “SettingsTheme” that inherits from the Material Light theme. We are also setting the value of the “android:colorPrimary” attribute to “#FF4081”, which is a shade of pink.

Build your AOSP project by running the “make” command.

Flash your modified AOSP build onto your device.

Open the Settings app and verify that the color of the header has changed.

Next, let’s modify the behavior of the Wi-Fi and Bluetooth toggles in the Settings app. By default, tapping on a toggle will toggle its state. We want to modify this behavior so that tapping on a toggle will open the corresponding Wi-Fi or Bluetooth settings screen.

To do this, we will create an overlay that intercepts the tap events of the toggles and opens the appropriate settings screen. Here are the steps to follow:

Create a new directory in your AOSP project’s overlay directory. For example, you can create a directory called “my_settings_overlay”.

Inside the “my_settings_overlay” directory, create a new directory called “smali”.

Inside the “smali” directory, create a new directory structure that matches the package name of the Settings app. For example, if the package name of the Settings app is “com.android.settings”, create a directory structure like this: “com/android/settings/”.

Inside the final “settings” directory, create a new file called “Settings$1.smali”.

Open the “Settings$1.smali” file in a text editor and add the following code:

```smali

.method public onClick(Landroid/view/View;)V
    .locals 2

const-string v0,

```
