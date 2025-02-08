---
# Required metadata
# For more information, see https://review.learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata?branch=main
# For valid values of ms.service, ms.prod, and ms.topic, see https://review.learn.microsoft.com/en-us/help/platform/metadata-taxonomies?branch=main

title: Certificate Based Authentication for migration
description: How to use Certificate Based Authentication in migration
author:      zacsun-ms # GitHub alias
ms.author:   zhaoyang.sun # Microsoft alias
ms.service: microsoft-365-admin
ms.topic: article
ms.date:     01/25/2025
---

# Migration Manager with Certificate Based Authentication

Migration Manager allows customers to use Azure App Registrations with certificate authentication as the identity model to migrate network file share to SharePoint and OneDrive.

## Preparation Steps

### 1. Register an application

Follow [the instructions](/entra/identity-platform/quickstart-register-app?tabs=certificate) to register an application in the Microsoft Entra admin center. Let's name this application 'MigApp'.

### 2. Grant permissions

In the Entra admin center, go to **Application > App registrations** and select 'MigApp' from the **All applications** tab.

Next, grant the necessary API permissions under **API Permissions** page.

To limit 'MigApp' to move content into specific SharePoint sites, grant 'Sites.Selected' permission under the SharePoint and Microsoft Graph API.

- SharePoint API:

   - 'Sites.Selected': Required for REST and CSOM (Client-Side Object Model) calls.
   
   - Microsoft Graph API:
   
      - 'Sites.Selected': Required for site-related operations.
      
To allow 'MigApp' to move content into all SharePoint sites, grant ‘Sites.FullControl.All’ permission under the SharePoint and Microsoft Graph API.

- SharePoint API:

  - 'Sites.FullControl.All': Required for full control of all site collections.
  
  - Microsoft Graph API:
  
     - 'Sites.FullControl.All': Required for full control of all site collections.
     
Grant more permissions

- Microsoft Graph API:

   - 'User.Read.All': Required for resolving user mapping.
   
      - 'Group.Read.All': Required for resolving user mapping.
      
         - 'Organization.Read.All': Required for sending telemetry to the correct Geo location.
         
### 3. Upload certificate

Go to **Certificates & secrets** page, and select **Certificates** tab.

- Upload the public key of your X.509 certificate that is issued by the Enterprise Public Key Infrastructure (PKI).

- Copy the value in 'Thumbprint' for future use.

