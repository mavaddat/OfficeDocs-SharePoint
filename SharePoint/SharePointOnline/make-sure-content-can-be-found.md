---
title: "Make sure content can be found"
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
recommendations: true
ms.date: 6/14/2017
audience: Admin
f1.keywords:
- NOCSH
ms.topic: overview
ms.service: sharepoint-online
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 16fb530a-ed64-4fea-ab15-adf4b5fe96e9
description: "The content must be crawled and added to the search index for your users to find what they're searching for in SharePoint."
---

# Make sure content can be found

The content must be crawled and added to the search index for your users to find what they're searching for in Microsoft SharePoint. SharePoint in Microsoft 365 has both a classic and a modern search experience, both use the same search index. [Learn about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search.md)

  
 ## Make site content searchable
  
When users search on a site, results can come from many places such as columns, libraries, and pages. A site owner can change search settings to decide whether or not content should appear in search results.
  
Users only see search results for content they have access to. Setting the right permissions for content ensure that people can see the right documents and sites in the search results. [Learn more](make-site-content-searchable.md).
  
## Crawl site content
  
In SharePoint, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index.
  
In some cases, you may want to manually request crawling and full re-indexing of a site, a document library, or a list. [Learn more](crawl-site-content.md).
  
## Search across on-premises and online content
  
[Hybrid search in SharePoint](../SharePointServer/hybrid/hybrid-search-in-sharepoint.md) lets your users search for files and documents across SharePoint Server and Microsoft 365 at the same time. With [cloud hybrid search](../SharePointServer/hybrid/learn-about-cloud-hybrid-search-for-sharepoint.md), both on-premises and online content go into the index that both the classic and Microsoft Search experiences use. 
  
## Remove search results temporarily
  
You can **temporarily** remove documents, pages and sites from search results with immediate effect. [Learn more](remove-search-results.md).
