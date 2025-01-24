---
title: "About user profile synchronization"
ms.reviewer: amysim
ms.author: ruihu
author: maggierui
manager: jtremper
recommendations: true
ms.date: 01/15/2025
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid:
description: "This article describes the user profile sync process for SharePoint in Microsoft 365, and the properties that are synced into user profiles."
---

# User profile synchronization

Microsoft SharePoint uses the Active Directory synchronization job to import user and group attribute information into the User Profile Application (UPA). When a new user is added to Microsoft Entra ID, the user account information is sent to the SharePoint directory store and the UPA sync process creates a profile in the User Profile Application based on a predetermined set of attributes. Once the profile has been created, any modifications to these attributes will be synced as part of regularly scheduled sync process.

> [!NOTE]
> The profile properties that are synced by the UPA sync process aren't configurable. Synchronization times vary based on workloads.

## Sync process

There are four steps in the sync process.

|Step|Description|
|---|---|
|1. Active Directory to Microsoft Entra ID | [Microsoft Entra Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis) syncs data from on-premises Active Directory to Microsoft Entra ID. For more info, see [What is hybrid identity with Microsoft Entra ID?](/azure/active-directory/hybrid/whatis-hybrid-identity) and [Attributes synchronized](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#sharepoint-online).|
|2. Microsoft Entra ID to SharePoint | Microsoft Entra ID syncs data from Microsoft Entra ID to the SharePoint directory store.|
|3. SharePoint to UPA | The UPA sync process syncs user account information in SharePoint directory store to the User Profile Application (UPA).|
|4. UPA to sites|User account information from the UPA is synced to SharePoint sites (previously called "site collections").|

Typically, user profiles are created automatically for all accounts that are created in Microsoft 365. For organizations that have a Microsoft 365 Education subscription, user profiles aren't created for new accounts by default. The user must access SharePoint once, at which time a basic stub profile will be created for the user account. The stub profile will be updated with all remaining data as part of the sync process.

If block sign-in is set on the user account in Microsoft Entra ID or disabled accounts are synced from Active Directory on premises, those user accounts won't be processed as part of the UPA sync process. The user must be enabled and licensed for changes to be processed.

## Properties that are synced into SharePoint user profiles

The following Microsoft Entra user attributes are synced to the UPA.

|Microsoft Entra attribute|User profile property display names|Notes|Sync to sites|
|:-------|:-------|:-------|:-------|
|UserPrincipalName|Account Name </br> User Name </br> User Principal Name|Example: </br> `i:0#.f <|> membership <|>` gherrera@contoso.com </br> gherrera@contoso.com|Yes|
|DisplayName|Name||Yes|
|GivenName|FirstName||Yes|
|sn|LastName||Yes|
|telephoneNumber|Work phone|Example: (123) 456-7890|Yes|
|proxyAddresses|Work Email </br> SIP Address|Work Email is set to the value prefixed with SMTP. (SMTP:gherrera@contoso.com) </br> Example: gherrera@contoso.com|Yes|
|PhysicalDeliveryOfficeName|Office||Yes|
|Title|Title </br> Job Title|Job Title contains the same value as Title and is connected to a term set.|Yes|
|Department|Department|Department is connected to a term set.|Yes|
|WWWHomePage|Public site redirect||No|
|PreferredLanguage|Language Preferences|Used by SharePoint to determine language for the user when the multilingual user interface (MUI) feature is enabled.|Yes|
|msExchHideFromAddressList|SPS-HideFromAddressLists||No|
|Manager|Manager|User Manager for organization hierarchy|Yes|

> [!NOTE]
> To update more or custom properties, see [Bulk update custom user profile properties](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).
> Some property names could differ between Azure AD Graph and Microsoft Graph, see [Property differences between Azure AD Graph and Microsoft Graph](/graph/migrate-azure-ad-graph-property-differences).

## Frequently asked questions (FAQs)

### How often are changes synced into the User Profile Application?

User account attribute changes are collected in batches and processed for UPA synchronization. Times vary based on the amount of changes requested in a single batch. The UPA synchronization is schedule to run at regular intervals.

### Will UPA synchronization overwrite existing properties in SharePoint user profiles?

For the default properties that are synced by UPA synchronization, values are overwritten to align with Microsoft Entra ID.

### Does UPA synchronization update only properties that have changed?

UPA synchronization is driven primarily by changes that are made Microsoft Entra ID, including adding new users. A full import can occur under certain maintenance events.

<a name='why-isnt-it-possible-to-map-additional-properties-for-upa-synchronization-to-sync-from-azure-ad-to-the-user-profile-application'></a>

### Why isn't it possible to map additional properties for UPA synchronization to sync from Microsoft Entra ID to the User Profile Application?

UPA synchronization is limited to a preconfigured set of properties to guarantee consistent performance across the service.
