---
ms.date: 06/20/2024
title: "Recommended sync app configuration"
ms.reviewer: gacarini
ms.author: mactra
author: MachelleTranMSFT
manager: jtremper
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: conceptual
ms.service: one-drive
ms.localizationpriority: medium
ms.collection: 
- Strat_OD_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
search.appverid:
- ODB160
- ODB150
- GOB150
- GOB160
- MET150
ms.assetid: b664e743-ae8b-4a93-aefd-1b20c584a93a
description: "View our recommendations for deploying and configuring the OneDrive sync app."
---

# Recommended sync app configuration

For the best performance, reliability, and user experience, follow these "ideal state" recommendations when you configure the OneDrive sync app.

## Updates and rings

- **Allow access to oneclient.sfx.ms and g.live.com**. Computers must be able to reach these URLs to apply updates and bug fixes, and enable or disable features. Updates are installed automatically; so, you don't need to package and deploy them. Because OneDrive runs in the background, updates are also installed silently and don't impact users.
- **Use the Insiders and Production rings**. Select several people in your IT department as early adopters to join the Insiders ring and receive features early. Leave everyone else in the organization on the default Production ring to ensure they receive bug fixes and new features in a timely fashion. This recommendation applies even if you are on the Semi-Annual Enterprise Channel for Windows and Office. For more information about the rings, see [Sync app update process](sync-client-update-process.md). To set the update ring on Windows, see [Set the sync app update ring](use-group-policy.md#set-the-sync-app-update-ring). To set it on Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos.md#tier).

## Windows Notification Service
  
- **Make sure connection to the service is enabled**. Work with your network team to ensure proxies:  

  - Allow network traffic to bypass *.wns.windows.com
  - Avoid HTTPS decryption for *.wns.windows.com

    This requirement applies to both Windows and Mac. [See the complete list of required URL and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business).

## Files On-Demand and Storage Sense

- **Keep Files On-Demand enabled**. OneDrive Files On-Demand helps users access all their files (individual or shared) without having to download them and use storage space. This setting is on by default for Windows 10 and Mac. To check this setting for Windows, see [Use OneDrive Files On-Demand](use-group-policy.md#use-onedrive-files-on-demand). To check it for Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos.md).
- **Use Storage Sense policies on PCs**. These policies let you automatically clean up "locally available" files users haven't explicitly pinned as "always available". [More info about Storage policies](/windows/client-management/mdm/policy-csp-storage)

## Silent account configuration

- **Silently configure user accounts on PCs**. When you enable the silent account configuration policy, users are signed in automatically; so, they don't need to open OneDrive or enter their password. For more information, see [Use silent account configuration](use-silent-account-configuration.md).

## Application start-up

- **Always start OneDrive automatically when signing in to Windows**. When you enable the auto-start configuration policy, OneDrive will automatically start every time users sign in to Windows. For more information, see [Start OneDrive automatically when signing in to Windows](use-group-policy.md#always-start-onedrive-automatically-when-signing-in-to-windows).

## Known Folder Move

Windows users are familiar and comfortable with saving files to their Desktop, Documents, and Pictures folders from years of developing it as a habit. When you redirect and move these folders to OneDrive, users can continue saving files to these locations, and they're backed up and available from any device. For more information, see [Redirect known folders](redirect-known-folders.md).

- **On new PCs, enable the silent policy**. [Silently move Windows known folders to OneDrive](use-group-policy.md#silently-move-windows-known-folders-to-onedrive)
- **On existing PCs, gradually enable the prompt and/or silent policy**. [About the Known Folder Move Group Policy objects](redirect-known-folders.md#about-the-known-folder-move-policies)

## Office integration

- **Keep Office file collaboration enabled** Office uses differential sync to sync only changes instead of the entire file each time. This makes sync faster and reduces network bandwidth. This setting is on by default on Windows and Mac. For more info, see [Coauthor and share in Office desktop apps](use-group-policy.md#coauthor-and-share-in-office-desktop-apps). For info about this setting for Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos.md).

## Offline mode

- **Keep offline mode enabled** With offline mode, users can work with OneDrive in the web in low or no internet situations. This setting is on by default on Windows and Mac. For more info, see [Prevent users from getting silently signed in to offline experiences on the web](lists-sync-policies.md#prevent-users-from-getting-silently-signed-in-to-offline-experiences-on-the-web), [Prevent users at your organization from enabling offline mode in OneDrive on the web](use-group-policy.md#prevent-users-at-your-organization-from-enabling-offline-mode-in-onedrive-on-the-web), and [Prevent users at your organization from enabling offline mode in OneDrive on the web for libraries and folders that are shared from other organizations](use-group-policy.md#prevent-users-at-your-organization-from-enabling-offline-mode-in-onedrive-on-the-web-for-libraries-and-folders-that-are-shared-from-other-organizations). For info about this setting for Mac, see [DisableOfflineMode](deploy-and-configure-on-macos.md#disableofflinemode) and [DisableOfflineModeForExternalLibraries](deploy-and-configure-on-macos.md#disableofflinemodeforexternallibraries).

## Shortcuts to shared folders

Users have two options when syncing files in SharePoint libraries and Teams. They can

- [Add shortcuts to libraries and folders to their OneDrive](https://support.microsoft.com/office/d66b1347-99b7-4470-9360-ffc048d35a33).
- [Use the Sync button in the document library](https://support.microsoft.com/office/6de9ede8-5b6e-4503-80b2-6190f3354a88).

It is recommended to use shortcuts instead of using the Sync button. Shortcuts are more performant because rather than syncing the entire library, only the specific folder is synced. Additionally, because the shortcuts are added to a user's OneDrive rather than to the device, it is easier to access content across all devices.

If you're an admin and want to hide the Sync button in document libraries, use the following PowerShell command:

Set-SPOTenant -HideSyncButtonOnTeamSite $true

## Sync reports

The [OneDrive sync reports in the Apps Admin Center](sync-health.md) provides you with sync health reports for tracking relevant health issues and advisories, checking the sync status and app version of individual devices, and monitoring Known Folder Move roll out. You must enable this setting on the devices from which you want to get reports. For more info, see [Enable sync health reporting for OneDrive](use-group-policy.md#enable-sync-health-reporting-for-onedrive). For info about this setting for Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos.md).
