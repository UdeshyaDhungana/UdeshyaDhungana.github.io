---
title: "The problem with tiktok"
date: 2020-06-29T18:03:00+05:45
classes: wide
header:
  teaser: ../assets/images/posts/tiktok.jpg
categories:
  - current-affairs
tags:
  - tiktok
  - data theft
  - technology
---

![Tiktok](/assets/images/posts/tiktok.jpg "Tiktok")

It was early 2018 when teens all around the world started using an app called Musically. It was a video sharing social media app founded by Alex Zhu, a Chinese entrepreneur . Mainly used for making lip sync videos, the app's popularity skyrockted within months, if not, weeks.   


Suddenly, around the August of 2018, Musically was shut down overnight. But, that wasn't the end of it. The app's users woke up to a surprise as they found their favorite app replaced with a new logo and name: Tiktok. It had been acquired by a Chinese company Bytedance much earlier, and it was then, when they officially changed the app's name and logo. It was nothing different for the users. Existing Musically accounts were automatically migrated to Tiktok, with a slight change of UI. But the core feature was same: short videos upto 15 seconds.

The app's popularity was still uprising. It only took it a few months after that to become no. 1 social media app on the Google Play Store and the iOS App Store. Users didn't seem to care who was behind the app, or the privacy issues regarding it. As of the date this article is written, Tiktok has 1B+ downloads on the Play Store alone.

## Tiktok Exposed
The app has been receiving numerous criticisms regarding its privacy and security lately. It is even rumored to be a spyware backed by the CCP. But, let's not get political and believe in rumors. Searching for the facts, I stumbled upon a reddit comment. It was by a user(link in the footer) whose job is to reverse engineer apps. He is an expert in this field. Here is a summary of his comment. I have provided the link at the end of this post. 

After reverse engineering the app, it has been found that it collects following data:
 - Phone hardware (CPU type, hardware IDs, screen dimensions, dpi, memory usage, disk space, etc)
 - Everything related to network (IP address, local IP, router MAC, wifi access point name)
 - Every photos in your gallery. <em>Started to feel a little insecure?</em>
 - Whether or not your phone is rooted/jailbroken
 - If location is enabled, it does GPS pinging every 30 seconds. In layman's terms, it keeps track of your location.
 - Information on other apps you have installed. This includes your Facebook, Instagram, shopping websites, and many more.

The company has different protections in place to prevent anyone from reverse engineering or debugging the app. The app changes its default behavior on knowing that it is being monitored. And the app has few snippets of code which allow it to download a remote zip file, extract it, and execute the binary. Not a single app needs this feature, unless it's a spyware. Do you think that's all? Nope, There's more!

The app has't been using HTTPS until recently. The company has leaked users' email addresses, as well as their secondary email, used for password recovery. The security was so weak, that even a beginner hacker could get access to every single one of the their user's profiles and their personal details effortlessly. The app also opposes free speech. Here's a <em class="font-italic">not so concrete</em> example. Upload a video of Tiananmen Square protest, and see how it gets taken down faster than you blink. Doesn't it seem like a *whispers* propaganda?

## Problems beyond screen

The app entices its new users by providing them with a sense of 'virality'. It means that one's very first video is likely to get more views and likes, regardless of its quality, keeping the user hooked to the platform, craving for more views and likes. Oh, I almost forgot this one! There are also a bunch of creepy old men trying to access the children on the app. It's been found that 40-50 year old men getting 8-10 year old to do 'duets' with them in sexually suggestive songs. I don't want to trigger anyone but, feminists, I think it's a problem when 9-10 year olds are twerking to gain views on internet. I'm mentioning this because this is not uncommon on Tiktok.

## Summary
In conclusion, Tiktok <em class="font-weight-bold">is</em> a spyware. It may be a video sharing website on the front, but it's much shady on the back. It does everything from exposing your personal information to collecting your data. I think it's time we, as a conscious consumer, and as a responsible human being, realize that this app is a big problem to us. It's time we abandon this platform. It's time we provide other app developers, even from our own country, a chance to create a Tiktok like app, which lets the users enjoy the platform without creating privacy and security issues. 

---
Reddit [comment](https://www.reddit.com/r/videos/comments/fxgi06/not_new_news_but_tbh_if_you_have_tiktiok_just_get/fmuko1m/)

Background image by [PatentlyApple's Blog](https://www.patentlyapple.com/patently-apple/2019/12/last-month-patently-apple-posted-a-report-titled-testimony-on-apple-tiktok-used-in-background-for-new-national-security-an.html)
