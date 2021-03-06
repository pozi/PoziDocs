---
layout: default
title: Azure Active Directory
parent: Integrations
grand_parent: Administrator Guide
---

# Azure Active Directory

*Azure AD integration is a feature of the **Pozi Enterprise Cloud** offering.*

Pozi's [Azure Active Directory](https://azure.microsoft.com/en-au/services/active-directory/){:target="_blank"} integration enables authorised staff to access private datasets without needing to be on the client network or VPN.

Users use a separate URL that enforces a login to Azure Active Directory before the browser loads the Pozi site.

Example:

* Public URL: `https://cardinia.pozi.com/`
* Staff URL: `https://cardinia.enterprise.pozi.com/`

<img src="../img/azure-ad-login.png" alt="" style="zoom:50%;" />

Once signed in, users will have access to private datasets for as long as the user remains logged in.
