---
title: How to change the token lifetime defaults for a custom-developed application | Microsoft Docs
description: How to update Token Lifetime policies for your application that you are developing on Azure AD
services: active-directory
documentationcenter: ''
author: CelesteDG
manager: mtillman

ms.assetid: 
ms.service: active-directory
ms.subservice: app-mgmt
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: conceptual
ms.date: 09/11/2018
ms.author: celested

ms.collection: M365-identity-device-management
---


# How to change the token lifetime defaults for a custom-developed application

Azure AD Premium allows app developers and tenant admins to configure the lifetime of tokens issued for non-confidential clients. Token lifetime policies are set on a tenant-wide basis or the resources being accessed.

1. To set a token lifetime policy, you need to download the [Azure AD PowerShell Module](https://www.powershellgallery.com/packages/AzureADPreview).
1. Run the **Connect-AzureAD -Confirm** command.

    Here’s an example policy that sets the max age single factor refresh token. Create the policy:
  ```New-AzureADPolicy -Definition @('{"TokenLifetimePolicy":{"Version":1, "MaxAgeSingleFactor":"until-revoked"}}') -DisplayName "OrganizationDefaultPolicyScenario" -IsOrganizationDefault $true -Type "TokenLifetimePolicy"```

## Next steps

* See [Configurable token lifetimes in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) to learn how to configure token lifetimes issued by Azure AD, including how to set token lifetimes for all apps in your organization, for a multi-tenant app, or for a specific service principal in your organization. 
* [Azure AD Token Reference](https://docs.microsoft.com/azure/active-directory/develop/active-directory-token-and-claims)

