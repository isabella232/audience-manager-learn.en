---
title: Using best practices on SPA pages when sending data to AAM
seo-title: Using best practices on SPA pages when sending data to AAM
description: In this document, we will describe several best practices that you should follow and be aware of as you are sending data from Single Page Applications (SPA) to Adobe Audience Manager (AAM). This doc will focus on using Launch by Adobe, which is the recommended implementation method.
seo-description: In this document, we will describe several best practices that you should follow and be aware of as you are sending data from Single Page Applications (SPA) to Adobe Audience Manager (AAM). This doc will focus on using Launch by Adobe, which is the recommended implementation method.
feature: implementation basics
topics: spa
audience: implementer
activity: implement
doc-type: technical video
author: Doug Moore
team: Technical Marketing
kt: 1390
---

# Using best practices on SPA pages when sending data to AAM {#using-best-practices-on-spa-pages-when-sending-data-to-aam}

In this document, we will describe several best practices that you should follow and be aware of as you are sending data from [!DNL Single Page Applications] (SPA) to Adobe Audience Manager (AAM). This doc will focus on using Experience Platform Launch, which is the recommended implementation method.

## Initial Notes

* The items below are going to assume that you are using [!DNL Launch] to implement on your site. The considerations would still exist if you are not using [!DNL Launch], but you would need to adapt them to your implementation method.
* All SPAs are different, so you may need to tweak some of the following items to best meet your need, but we wanted to share some best practices with you; things that you need to think about as you are sending data from SPA pages to Audience Manager.

## Simple diagram of working with SPAs and AAM in Experience Platform Launch {#simple-diagram-of-working-with-spas-and-aam-in-experience-platform-launch}

![spa for aam in [!DNL launch]](assets/spa_for_aam_in_launch.png)

>[!NOTE] As stated, this is a simplified diagram of how SPA pages are handled in an Adobe Audience Manager implementation (without Adobe Analytics) using [!DNL Launch]. As you can see, it is fairly straight-forward, with the big decision being how you are going to communicate a view change (or an action) to [!DNL Launch].

## Triggering [!DNL Launch] from the SPA page {#triggering-launch-from-the-spa-page}

Two of the more common methods for triggering a rule in [!DNL Launch] (and therefore sending data into AAM), are:

* Setting JavaScript custom events (see example [HERE](https://helpx.adobe.com/analytics/kt/using/spa-analytics-best-practices-feature-video-use.html) with Adobe Analytics)
* Using a [!UICONTROL Direct Call Rule]

In this AAM example, we are going to use a [!UICONTROL Direct Call rule] in [!DNL Launch] to trigger the hit going into AAM. As you’ll see in the next sections, this really becomes useful by setting the [!DNL data layer] to a new value, so that it can be picked up by the [!UICONTROL Data Element] in [!DNL Launch].

## Demo Page {#demo-page}

We have created a small demo page that demonstrates changing a value in the [!DNL data layer] and sending it into AAM, as you may do on a SPA page. This functionality can be modeled for more elaborate changes needed. You can find this demo page [HERE](https://aam.enablementadobe.com/SPA-Launch.html).

## Setting the [!DNL data layer] {#setting-the-data-layer}

As mentioned, when new content is loaded on the page or when someone performs an action on the site, the [!DNL data layer] needs to be set dynamically in the head of the page BEFORE [!DNL Launch] is called and runs the [!UICONTROL rules], so that [!DNL Launch] can pick up the new values from the [!DNL data layer] and push them into Audience Manager.

If you go to the demo site listed above and look at the page source, you will see:

* The [!DNL data layer] is in the head of the page, before the call to [!DNL Launch]
* The JavaScript in the simulated SPA link changes the [!DNL data layer], and THEN calls [!DNL Launch] (the _satellite.track() call). If you were using JavaScript custom events instead of this [!UICONTROL Direct Call Rule], the lesson is the same. First change the [!DNL data layer], and then call [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23322/?quality=12)

## Additional Resources {#additional-resources}

* [SPA discussion on the Adobe forums](https://forums.adobe.com/thread/2451022)
* [Reference Architecture sites to show how to implement SPA in Launch by Adobe](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html)
* [Using best practices when tracking SPA in Adobe Analytics](https://helpx.adobe.com/analytics/kt/using/spa-analytics-best-practices-feature-video-use.html)
* [Demo site used for this article](https://aam.enablementadobe.com/SPA-Launch.html)
