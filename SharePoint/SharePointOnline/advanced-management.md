---
ms.date: 11/20/2024
title: "Microsoft SharePoint Premium - SharePoint Advanced Management overview"
ms.reviewer: daminasy
ms.author: mactra
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- ContentEnagagementFY24
search.appverid:
- MET150
recommendations: false
description: "Learn about Microsoft SharePoint Premium - SharePoint Advanced Management and how you can use its features before and after deploying Copilot."
---

# Microsoft SharePoint Premium - SharePoint Advanced Management overview

Microsoft SharePoint Premium - SharePoint Advanced Management is an essential add-on for Microsoft 365 that equips IT administrators with a powerful suite of tools to bolster content governance throughout the Microsoft Copilot deployment journey.

Whether preparing for [Copilot deployment](/copilot/microsoft-365/microsoft-365-copilot-setup) or managing content post-implementation, this solution offers capabilities to:

- prevent content sprawl,
- streamline access management for SharePoint and OneDrive sites, and
- analyze usage patterns through comprehensive reporting.

:::image type="content" source="media/sam-overview/0-sam-overview-pillars-new.png" alt-text="Screenshot of SharePoint Advanced Management pillars." lightbox="media/sam-overview/0-sam-overview-pillars-new.png":::

We recommend utilizing SharePoint Advanced Management features along with our [best practices for Microsoft 365 Copilot](/sharepoint/sharepoint-copilot-best-practices) to reduce the risk of oversharing, control content sprawl, and manage content lifecycle.

SharePoint Advanced Management features are managed by [IT administrators](/microsoft-365/admin/add-users/about-admin-roles) with access to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). Some features can be used by site owners.

:::image type="content" source="media/sam-overview/1-sam-feature-list.png" alt-text="Screenshot of SharePoint Advanced Management features dashboard." lightbox="media/sam-overview/1-sam-feature-list.png":::

SharePoint Advanced Management helps you identify, manage, and resolve common content governance issues such as:

## Manage content sprawl

**What is content sprawl?** Content sprawl occurs when digital content accumulates without proper management across various storage locations in an organization. This leads to difficulties in accessing information, higher storage expenses, security vulnerabilities, and compliance complexities. You can tackle content sprawl by implementing governance strategies and utilizing tools that centralize control, optimize storage efficiency, and uphold secure data management practices.

### Site ownership policy

The site lifecycle management feature from Microsoft SharePoint Premium - SharePoint Advanced Management lets you improve site governance by having automated policies configured in the SharePoint admin center.

**[Site ownership policies](create-sharepoint-site-ownership-policy.md)** are a part of site lifecycle management and help effectively manage ownership of SharePoint sites in your organization.

### AI Insights

The **[AI insights](ai-insights.md)** feature for [SharePoint Advanced Management](advanced-management.md) uses a language model to identify patterns and potential issues from reporting and receive actionable recommendations to solve issues.

You can find the **Get AI insights** button next to various reports in the SharePoint admin center. Once selected, the AI insights feature extracts patterns from the report and offers a list of potential actions.

:::image type="content" alt-text="Screenshot of site lifecycle management insights dashboard in SharePoint admin center." source="media/ai-insights/0-ai-insights-inactive-sites.png" lightbox="media/ai-insights/0-ai-insights-inactive-sites.png":::

### Inactive sites policy

You can run automated, rule-based policies to manage and reduce inactive sites with the [**Inactive SharePoint sites policy**](site-lifecycle-management.md) feature from SharePoint Advanced Management.

:::image type="content" source="media/sam-overview/2-inactive-sites-policy.png" alt-text="Screenshot of inactive sites policy." lightbox="media/sam-overview/2-inactive-sites-policy.png":::

The inactive sites policy combats content sprawl by automatically identifying and managing inactive SharePoint sites. It operates by defining inactivity criteria, such as lack of updates or user activity over a set period. Once identified, site owners receive email notifications to confirm the active/inactive state of the site.

## Manage content lifecycle

You can manage the content lifecycle for SharePoint and OneDrive sites with SharePoint advanced management features that streamline content creation, organization, and retention through automated workflows, detailed reporting, and robust compliance settings.

Effective lifecycle management not only ensures streamlined governance and enhanced collaboration but also optimizes storage, maintains data integrity, and supports regulatory compliance, ultimately improving efficiency and security.

### Site change history reports

The **[Site change history report](change-history-report.md)** feature lets you create change history reports in the SharePoint admin center to review SharePoint site property changes made within the last 180 days. Create up to five reports for a given date range and filter by sites and users. You can download the report as a .csv file to view the site property changes.

:::image type="content" source="media/sam-overview/6-change-history-report.png" alt-text="Screenshot of change history report dashboard." lightbox="media/sam-overview/6-change-history-report.png":::

### Recent site actions

 The **[Recent SharePoint admin actions](recent-actions-panel.md)** policy lets you review and monitor the last 30 changes you've made to a SharePoint site's properties within the last 30 days in the SharePoint admin center. This feature only shows changes made by you and not other administrators.

:::image type="content" source="media/sam-overview/5-recent-admin-actions-panel.png" alt-text="Screenshot of restricted access control for SharePoint sites." lightbox="media/sam-overview/5-recent-admin-actions-panel.png":::

## Manage permissions and access

Copilot leverages the data stored in SharePoint and OneDrive sites to provide insights and automate tasks across your organization. Confidential data from content in SharePoint and OneDrive sites can populate in Copilot's generated insights, posing security and privacy risks.

SharePoint Advanced Management ensures this data is securely handled and accessed only by authorized users and/or security groups, maintaining the integrity and security of the insights generated by Copilot​.

By preventing oversharing and managing access effectively, you can ensure that Copilot's collaboration features are optimized. This leads to more efficient and secure use of Copilot across your organization.

Before enabling Copilot for your organization and tenant, you can proactively set policies to restrict access to sites and manage content discoverability during Copilot and tenant-wide search.

### Block download policy for SharePoint and OneDrive sites

**[Block download policy for SharePoint and OneDrive sites](block-download-from-sites.md)** You can block download of files from SharePoint sites or OneDrive without needing to use Microsoft Entra Conditional Access policies. Users have browser-only access with no ability to download, print, or sync files. They also won't be able to access content through apps, including the Microsoft Office desktop apps.

:::image type="content" source="media/sam-overview/9-block-download-policy-sharepoint-onedrive.png" alt-text="Screenshot of block download policy for SharePoint and OneDrive sites.":::

**[Data access governance reports](data-access-governance-reports.md)** lets you view reports that identify sites that contain potentially overshared or sensitive content. You can use these reports to assess and apply appropriate security and compliance policies.

:::image type="content" source="media/sam-overview/7-data-access-governance.png" alt-text="Screenshot of data access governance reports dashboard." lightbox="media/sam-overview/7-data-access-governance.png":::

### Enterprise app insight reports

**[App insights](app-insights.md)** is a SharePoint Advanced Management feature that lets you gain insights on the various non-Microsoft applications registered to your Microsoft Entra admin center and how they access your SharePoint content. This report can help you maintain and protect the integrity of your content.

### Site access reviews

**[Site access review](site-access-review.md)** feature in the SharePoint admin center lets you delegate the review process of [data access governance reports](data-access-governance-reports.md) to the site owners of overshared sites.

Site access review involves site owners in the review process so they can address the concern of overshared sites identified in data access governance reports.

### Data access governance management via PowerShell

While Data access governance is available in SharePoint admin center portal, large organizations usually look for **[PowerShell support](powershell-for-data-access-governance.md)** in order to manage scale via scripting and automation.

This document discusses all appropriate PowerShell commands available via SharePoint Online PowerShell module to manage reports from Data access governance.

### Conditional access policy for SharePoint and OneDrive sites

**[Conditional access policy for SharePoint and OneDrive sites](authentication-context-example.md)** lets you enforce stringent access conditions when users access SharePoint sites. Authentication contexts can be directly applied to sites or used with sensitivity labels to connect Microsoft Entra Conditional Access policies to labeled sites.

:::image type="content" source="media/sam-overview/8-conditional-access-policies.png" alt-text="Screenshot of conditional access policy dashboard." lightbox="media/sam-overview/8-conditional-access-policies.png":::

### Restricted access control for SharePoint

You can prevent sites and content from being discovered at the site-level by enabling **[Restricted access control for SharePoint sites](restricted-access-control.md)**. Site access restriction allows only users in the specified security group or Microsoft 365 group to access content. This policy can be used with Microsoft 365 group-connected, Teams-connected, and non-group connected sites.

:::image type="content" source="media/sam-overview/3-restricted-access-control-sharepoint-sites.png" alt-text="Screenshot of saved changes for restricted access control for SharePoint sites." lightbox="media/sam-overview/3-restricted-access-control-sharepoint-sites.png":::

### Restricted access control for OneDrive

You can limit access to shared content of a user's OneDrive to only people in a security group with the **[Restricted access control for OneDrive](onedrive-site-access-restriction.md)** policy.

Once the policy is enabled, anyone who is not in the designated security group won't be able to access content in that OneDrive even if it was previously shared with them. To block users from accessing OneDrive as a service, you can enable the [Restrict OneDrive service access](limit-access.md) feature.

:::image type="content" source="media/sam-overview/4-restricted-access-control-onedrive.png" alt-text="Screenshot of restricted access control for OneDrive." lightbox="media/sam-overview/4-restricted-access-control-onedrive.png":::

## Licensing

SharePoint Advanced Management is a per-user license. To use SharePoint Advanced Management, you must have a license for each user in your organization. (It's not required for guests.) Users must also be licensed for SharePoint K, P1, or P2 via standalone or a Microsoft 365 suite.

You can purchase the *SharePoint Advanced Management Plan 1* add-on in the Microsoft 365 admin center, through a Cloud Solution Provider (CSP), or through volume licensing enrollment. Contact your Microsoft account manager for further information.

SharePoint Advanced Management is available for Commercial, WW Commercial Public Sector, Education, Charity, and US GCC, GCC-High, and DoD customers.

SharePoint Advanced Management is $3 per user per month for commercial customers. For more details on licensing, please contact your account manager.

Licensing details for each feature listed above are included in those articles.

## Related topics

[Microsoft Syntex documentation](/microsoft-365/syntex)

[Microsoft 365 Government - how to buy](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)

[Get started with Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-setup)
