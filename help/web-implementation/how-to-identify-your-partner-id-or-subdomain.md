---
title: How to identify your Audience Manager Partner ID or Subdomain
seo-title: How to identify your Audience Manager Partner ID or Subdomain
description: When implementing some Experience Cloud features, you need to know what your Audience Manager “Partner ID” is (also sometimes referred to as your “client ID” or “Subdomain”). In this video, we will show you two places you can get this ID in the Audience Manager UI.
seo-description: When implementing some Experience Cloud features, you need to know what your Audience Manager “Partner ID” is (also sometimes referred to as your “client ID” or “Subdomain”). In this video, we will show you two places you can get this ID in the Audience Manager UI.
feature: implementation basics
topics: 
audience: implementer
activity: implement
doc-type: technical video
author: Doug Moore
team: Technical Marketing
kt: 2359
---

# How to identify your Audience Manager Subdomain {#how-to-identify-your-audience-manager-partner-id-or-subdomain}

When implementing some Experience Cloud features, you need to know what your Audience Manager [!DNL “Subdomain”] is (also sometimes referred to as your “[!DNL client ID]” or "[!DNL Partner ID]"). In this video, we will show you two places you can get this info in the Audience Manager UI.

## Giving away the ending… {#giving-away-the-ending}

In case you would rather just jump in and find it without watching this short video, you can find your [!DNL Partner Subdomain] in two places in the UI:

1. If you have already created a [!UICONTROL rule-based] [!UICONTROL trait], click the “[!UICONTROL Get Trait URL]” button next to the [!UICONTROL trait] in the list of [!UICONTROL traits] in that folder, and the URL will include your subdomain in the URL
1. If you go into the [!UICONTROL Tools] > [!UICONTROL Tags] interface and click on the “[!UICONTROL Get code]” icon of your container, the subdomain is toward the end of the Akamai line

If you can’t quickly find it with those quick references, the video is a short time commitment. :)

>[!VIDEO](https://video.tv.adobe.com/v/25922/?quality=12)

> [!IMPORTANT] There is a numeric ID assigned to each customer of the Adobe Experience Cloud, and this is often referred to as the "PID", or Partner ID. This is not the ID we are talking about in this article and video. Instead, the "partner subdomain", which is sometimes referred to as the partner ID, is usually a version of the client name, and is the subdomain of the server to which the data is sent. For example, if your company is "Bob's Knobs" (all things doorknobs, of course, haha), then it is likely that your partner subdomain would be "bobsknobs", whereas the "PID" would be something more like "12345". You don't typically need to know your PID, but your subdomain is important to know, so that you can configure your Audience Manager implementation.
> 