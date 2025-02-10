---
ms.date: 11/14/2024
title: Get ready for Microsoft 365 Copilot with SharePoint Advanced Management
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
recommendations: true
audience: Admin
f1.keywords:
- NOCSH
ms.topic: best-practice
ms.service: sharepoint-online
ms.collection: 
- M365-collaboration
- m365copilot
- magic-ai-copilot
- Tier2

ms.localizationpriority: medium
search.appverid:
- MET150
description: "Learn how to get ready for Microsoft 365 Copilot by using SharePoint Advanced Management. Use SharePoint Advanced Management to govern your organization's data effectively by controlling content sprawl, preventing oversharing, control content access by Copilot, and manage content lifecycle."
---
# Get ready for Microsoft 365 Copilot with SharePoint Advanced Management

## Use SharePoint to govern your organization's data effectively

To ensure assistance provided by Copilot is appropriate, accurate, and compliant, as your organization’s SharePoint admin, it's crucial for you to ensure that your organization’s data in SharePoint is appropriately governed from the following three aspects:

- **Manage content sprawl**: Reduce content duplication and ensure well-planned content creation. Ensure all sites and content are well managed governed by site owners.
- **Prevent content oversharing and control content access**: Use tools available to SharePoint admins and site owners to prevent users from oversharing content. Limit content access by Copilot with user group settings, and other tools. 
- **Manage content lifecycle**: Remove inactive and outdated content and sites. Make sure the information Copilot access is accurate and up to date. 

## Use SharePoint Advanced Management to get your organization ready for Copilot

[Microsoft SharePoint Premium – SharePoint Advanced Management](/sharepoint/advanced-management) is an essential Microsoft 365 add-on that helps you, as the SharePoint admin to address these three pillars around content governance. To get ready for your organization’s Microsoft 365 Copilot adoption, there are a few highly recommended steps you can take, primarily using SharePoint Advanced Management tools. These steps reduce accidental oversharing, minimize your content governance footprint, improve Copilot response quality, control content access by Copilot, and ensure data safety specifically for business-critical sites. Let's delve into the specific steps you can take:

### Step 1: Reduce accidental oversharing with SharePoint sharing settings

To minimize accidental content oversharing via Copilot results, it's crucial to implement the best practice sharing settings. Proactive safeguards are key. To effectively prepare your organization for Copilot, set the appropriate sharing settings for end users at both the organization and site levels:  

**At the organization level**:

- Update [sharing link defaults for your organization ](/sharepoint/turn-external-sharing-on-or-off#file-and-folder-links) for your organization from organization-wide sharing to specific people links.
- To reduce risks around accidental misuse, consider hiding broad-scope permissions from your end users. [This example](/powershell/module/sharepoint-online/set-spotenant) hides "Everyone Except External Users" in the People Picker control so that no end user can use it.

**At the site level**:

Consider educating site admins on the site-level controls they can use to [restrict members from sharing](/powershell/module/sharepoint-online/set-spotenant). One key setting here ensures that Site Owners are the recipients of [access requests](https://support.microsoft.com/office/set-up-and-manage-access-requests-94b26e0b-2822-49d4-929a-8455698654b3).

### Step 2: Ensure all sites have valid owners

Site owners are the critical role on point for executing governance tasks at scale. Specifically, you need site owners to:

- Help attest if inactive sites are still needed in next step - **cleaning up unused sites**. 
- Perform [Site Access Reviews](/sharepoint/site-access-review#review-everyone-except-external-users-site-access-review-requests-for-site-owners) to confirm whether potentially overshared content is indeed being overshared and take remediation to address oversharing risks in Step 4 – control access. 

It's essential to confirm all sites have valid owners before cleaning up unused sites and asking owners to take care of overshared content. SharePoint Advanced Management's [Site Ownership policy](/sharepoint/create-sharepoint-site-ownership-policy) helps identify ownerless sites and find the appropriate owners when needed.

- You can run a Site Ownership policy in Simulation mode to identify any sites that don't have a minimum of two owners.
- Set up the policy in simulation mode to identify owners based on your desired criteria. Then upgrade the policy to Active mode to enable notifications to site owner candidates.

### Step 3: Clean up unused sites

Identify inactive sites, then take action to reduce your governance footprint and improve Copilot response quality. Inactive sites often contain outdated content, cluttering Copilot’s data source and leading to less accurate responses. Removing these sites helps Copilot focus on current information for better results. Currently, you can identify unused sites by running an inactive site policy and ask site owners to attest if the site is still needed.

- With less than five minutes you can set up and run an [Inactive Site policy ](/sharepoint/site-lifecycle-management#create-an-inactive-site-policy) in Simulation mode to identify sites that haven't been accessed for an extended (configurable) period of time.
- Once the report is generated, select the Get AI insights button to [get AI insights](/sharepoint/advanced-management#ai-insights) generated for the report to help you identify issues with the sites and possible actions to address these issues.
- After identifying inactive sites, set the policy to Active mode to notify the Site Owner to attest whether the site is still needed.
- If the site owners confirm the sties aren't needed, you need to put the sites either in [read-only mode](/sharepoint/site-lifecycle-management#read-only-mode). These sites will be moved to [Microsoft 365 Archive](/microsoft-365/archive/archive-overview) after a configurable duration (3, 6, 9, or 12 months). 

> [!TIP]
> Sites moved to Microsoft 365 Archive are no longer accessible by anyone in the organization outside of Microsoft Purview or admin search. This means Copilot won't include content from these sites when responding to user prompts.

### Step 4: Identify sites with potentially overshared content

How do you quickly identify sites with potentially overshared content without looking at the actual site? You can run two sets of reports:

- The site activity based reports
- The permission based oversharing baseline report

#### The site activity based reports

Usually, if you see there's content on a site that is being shared with one of the following options: “**Everyone Except External Users**”, “**People in your organization**” and “**Anyone**”, there's a bigger chance that the content is overshared.  SharePoint Advanced Management activity based reports let you quickly identify most actively overshared sites, by running three individual reports:

- [Usage of "Everyone Except External Users"](/sharepoint/data-access-governance-reports#content-shared-with-everyone-except-external-users-eeeu-reports) 
- [Usage of “People in your organization" sharing links](/sharepoint/data-access-governance-reports#sharing-links-reports) 
- [Usage of "Anyone" sharing links](/sharepoint/data-access-governance-reports#sharing-links-reports)

Sites with these three types of usage are at a greater risk of oversharing compared to those without such usages. You can sort, filter or download the report, and identify the sites with potentially overshared content. Once the report is generated, select the Get AI insights button to [get AI insights](/sharepoint/advanced-management#ai-insights) generated for the report to help you identify issues with the sites and possible actions to address these issues. 

#### The permission based oversharing baseline report

In addition to the site activity reports, you can also run an oversharing baseline report to learn where content overexposure risk exists in all sites on your organization, regardless of site activities. This report is the "[Oversharing Baseline Report for Sites, OneDrive and Files](/sharepoint/data-access-governance-reports#setting-up-oversharing-baseline-with-permissions-based-report)” report. You can run the report using the [Data Access Governance (DAG) PowerShell commands](/sharepoint/powershell-for-data-access-governance#oversharing-baseline-report-using-permissions) in SharePoint Online PowerShell module. This report scans all sites in your organization, and lists sites that share content with more than a specified number of users (you specify the number). You [view and download this report](/sharepoint/powershell-for-data-access-governance#view-and-download-reports-using-powershell) with PowerShell commands.

### Step 5: Control access to content

When you use Microsoft Copilot, the results come from content in Microsoft Graph, based on each individual user’s profile and permissions. In Step 3, you identify sites with potentially overshared content. Next, you want to ensure Copilot only has access to content when appropriate. To do this, as the SharePoint admin, you can:

- Initiate a [Site Access Review](/sharepoint/site-access-review) for site owners to confirm overshared content and take remediation steps.
- Use the [Restricted Access Control Policy](/sharepoint/restricted-access-control) to restrict access to a site with overshared content.
- Use the [Restricted Access Control Policy](/sharepoint/restricted-access-control) to further control accidental content discovery.

#### Site access reviews by site owners

- For any site that is identified with potentially overshared content, [Site Access Review](/sharepoint/site-access-review) is needed. As the SharePoint Admin, you should [initiate the Site Access Review](/sharepoint/site-access-review/#initiate-a-site-access-review). 
- Site Owners [receive notification](/sharepoint/site-access-review#site-access-review-process-for-site-owners) for each site that requires attention. They can use the [**Site reviews page**](/sharepoint/site-access-review#manage-multiple-site-access-review-requests-for-site-owners) to track and manage multiple review requests.
- The site owner [reviews access in two main areas](/sharepoint/site-access-review#review-everyone-except-external-users-site-access-review-requests-for-site-owners): SharePoint groups and individual items to determine whether the broad sharing is appropriate, or it's indeed oversharing and requires remediation. 
- If the site owner determines that the content is indeed overshared, they can take easy remediation actions by using the Access Review dashboard to update permissions. 

#### Restrict access with the Restricted Access Control Policy

Until the Site Access Review is complete, you as the SharePoint Admin can take action to mitigate oversharing risks. To restrict access to a site with overshared content, the SharePoint Admin can set up a [Restricted Access Control Policy](/sharepoint/restricted-access-control). As a result, all access to the site is restricted to only the group of users specified in the policy. Accordingly, the content from this site is visible in Microsoft 365 Copilot *only for this restricted group of users*. You can restrict access to individual sites or OneDrive.

#### Restricted Content Discovery policy

The other policy you can set up as the SharePoint admin to mitigate oversharing risks is the [Restricted Content Discovery policy](/sharepoint/restricted-content-discovery). Unlike the Restricted Access Control policy, the Restricted Content Discovery policy *leaves site access unchanged*, but prevents the site’s content from being surfaced in Microsoft 365 Copilot or organization-wide Search. The SharePoint Admin can [set Restricted Content Discovery on a site](/sharepoint/restricted-content-discovery#configure-restricted-content-discovery).

### Step 6: Take proactive measures on business-critical sites

For business-critical sites, you want to take proactive measures to ensure the content is appropriately shared, and access to content is limited to the minimum level. You can lock down your most important sites with the following measures:

- Use [Restricted Access Control (RAC)](/sharepoint/restricted-access-control) to proactively protect against oversharing. Even better: as part of your custom site provisioning process, configure RAC policy on new sites from the get-go and proactively avoid oversharing forever.
- Use [Restricted Content Discovery](/sharepoint/restricted-content-discovery) to leave permissions in place, but prevent the content from being available to Microsoft 365 Copilot and Organization-wide search experiences.
- Consider blocking downloads from selected sites via a block download policy. Or specifically [block the download of Teams meeting recordings and transcripts](/microsoftteams/block-download-meeting-recording).
- Finally, consider applying encryption action with "extract rights" enforced on business-critical office documents. Learn more [here](/purview/ai-microsoft-purview).

## Coming up

> [!IMPORTANT]
> The following policies are currently in preview and will soon be generally available. [*Sign up to participate in the preview by following instructions here*](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbRw8ueKeaH4JIsskRInqtJE5UNjhYVkg5NDRNWkMxRlI0TFVDR0FYSUNGUi4u&route=shorturl). 

### Use AI Powered Semantic matching to find similar sites

You discovered a site containing crucial business data that lacks proper protection. Are there more sites like this one that might have similar vulnerabilities? Soon, AI Powered Semantic matching helps you locate these sites using the site you discovered as the example. The AI powered semantic matching tool reads through all the sites you have, including content, files, metadata, and give you a list of similar sites based on your example site.
