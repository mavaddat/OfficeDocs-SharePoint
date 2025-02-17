---
title: "Feature release rings"
ms.reviewer: 
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 09/07/2023
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-server-itpro
ms.localizationpriority: medium
ms.collection: 
- IT_Sharepoint_Server
- IT_Sharepoint_Server_Top
ms.assetid: 88317397-e0cb-47c7-9093-7872bc685213
description: "Learn about the feature release rings."
---


# Feature release rings

[!INCLUDE[appliesto-xxx-xxx-xxx-SUB-xxx-md](../includes/appliesto-xxx-xxx-xxx-SUB-xxx-md.md)]

## Overview

In previous versions of SharePoint Server, such as SharePoint Server 2019 and SharePoint Server 2016, new feature experiences were introduced at the launch of major new versions. Those versions would be serviced with new security and quality improvements via monthly Public Updates. On rare occasions, new feature experiences may be introduced via a Public Update as well. However, customers would typically have to wait for the next major version of SharePoint Server to be released to get additional feature experiences that weren't part of the initial launch.

SharePoint Server Subscription Edition brings a more agile approach to how new feature experiences are introduced to SharePoint Server customers. Instead of waiting for the next major version of SharePoint Server to be released, new feature experiences will now be introduced to SharePoint Server Subscription Edition on a regular basis via Feature Updates. Customers will have access to these new feature experiences as soon as they're ready and will have control over how they're made available in their SharePoint farm deployments.

## Introducing feature updates

Organizations often desire predictability for when new features are introduced to the products they use. Microsoft will bundle new feature experiences for SharePoint Server Subscription Edition together in **Feature Updates** so that they can be introduced on a predictable schedule. **Feature Updates** will be introduced twice a year, once in the spring and once in the autumn. Feature updates will be incorporated into the monthly **Public Updates**, alongside the typical security and quality updates that customers are used to. Once a new **Feature Update** is released, it will be included in all **Public Updates** going forward. 

Feature Updates will be named based on the calendar year and which half of the year they were released. For example, the feature update released in the autumn of calendar year 2022 is called **SharePoint Server Subscription Edition Version 22H2**. A feature update released in the spring of calendar year 2023 is called **SharePoint Server Subscription Edition Version 23H1**. 

In addition to the desire for predictability of new feature releases, organizations desire the ability to manage the introduction of those new features into their environments. This gives organizations time to train their users and support staff on any new functionality, perform compatibility testing of those new feature experiences with existing customer scenarios, and develop new business processes to take full advantage of the new feature experiences. 

To meet this need, new feature experiences introduced in Feature Updates will be grouped into the following feature release rings:  

- Early release
- Standard release

### Early release

In the **Early release** ring, new feature experiences will be enabled in your SharePoint farm as soon as they're ready. These experiences are supported for production use but may change before they're included in the Standard release ring. 

Enable **Early release** to:

- Use new feature experiences in a production environment as soon as possible.
- Perform compatibility testing and explore new feature experiences in a test environment and provide feedback to Microsoft.
- Prepare your internal help desk and user documentation for new feature experiences.

### Standard release

In the **Standard release** ring, new feature experiences are enabled in your SharePoint farm once they're ready for all customers to use by default. These feature experiences are supported for production use and have received additional validation during **Early release**. Enable **Standard release** if you prefer to minimize changes to your SharePoint experience and are willing to wait longer for new feature experiences. **Standard release** is the default feature release ring.

## Selecting feature release preference

SharePoint Server Subscription Edition farms are part of the Standard release ring by default. At any time, customers can choose to move from the Standard release ring to the Early release ring, or from the Early release ring to the Standard release ring. New feature experiences will be enabled or disabled based on the feature release selected for the SharePoint farm.

Follow these steps to select a feature release preference for your SharePoint farm using SharePoint Central Administration:

1. Browse to **SharePoint Central Administration**.
1. Click **System Settings**.
1. Click **Feature release preference**.
1. Select either **Early release** or **Standard release (Default)** and then click **OK**.
1. Run **SharePoint Products Configuration Wizard** on each server in your SharePoint farm to ensure all features recognize the new feature release preference.

Follow these steps to select a feature release preference for your SharePoint farm using Windows PowerShell:

> [!NOTE]
> To set this using Windows PowerShell, you must be running **SharePoint Server Subscription Edition Version 23H2** or a newer version.

1. Launch the **SharePoint Management Shell** or a Windows PowerShell console.
1. Run the **Set-SPFeatureReleasePreference** cmdlet with the **FeatureReleaseRing** parameter, specifying either **Early** or **Standard** for the parameter value. <br>Set-SPFeatureReleasePreference -FeatureReleaseRing {Early | Standard}
1. Run **SharePoint Products Configuration Wizard** on each server in your SharePoint farm to ensure all features recognize the new feature release preference.

