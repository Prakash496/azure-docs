---
title: Authentication service hero sample
titleSuffix: An Azure Communication Services article
description: This article describes the authentication services hero sample using Azure Communication Services.
author: kperla97
manager: chpalm
services: azure-communication-services

ms.author: kaperla
ms.date: 06/30/2021
ms.topic: overview
ms.service: azure-communication-services
ms.subservice: identity
ms.custom: devx-track-extended-java, devx-track-js
zone_pivot_groups: acs-js-csharp
---

# Authentication service hero sample

> [!IMPORTANT]
> This sample is available on GitHub Azure Samples for [Node.js](https://github.com/Azure-Samples/communication-services-authentication-hero-nodejs) and [C#](https://github.com/Azure-Samples/communication-services-authentication-hero-csharp).

Azure Communication Services requires developers to generate user and access token credentials inside of a trusted authentication service. Azure Communication Services is identity-agnostic, to learn more check out our [conceptual documentation](../concepts/identity-model.md).

This repository provides a sample of a server implementation of an authentication service for Azure Communication Services. It uses best practices to build a trusted backend service that issues Azure Communication Services credentials and maps them to Microsoft Entra identities. 

Use this sample to help you in the following scenarios:
- As a developer, you need to enable an authentication flow to generate Azure Communication Services user identities mapped to a Microsoft Entra identity. Then use the identity to provision access tokens to be used in calling and chat experiences.
- As a developer, you need to enable an authentication flow for Azure Communication Services support Teams identities, which is done by using a Microsoft 365 Microsoft Entra identity of a Teams' user to fetch an Azure Communication Services token to be able to join Teams calling/chat.

> [!NOTE]
>If you're looking to get started with Azure Communication Services, but are still in learning / prototyping phases, check out our [quickstarts for getting started with Azure communication services users and access tokens](../quickstarts/identity/access-tokens.md?pivots=programming-language-csharp).

![Screenshot of the Azure Communication Services Authentication Server Sample Architecture](./media/auth/acs-authentication-server-sample-overview-flow.png)

Since this sample only focuses on the server APIs, the client application isn't part of it. If you want to add the client application to sign in end-users using Microsoft Entra ID, follow the [MSAL samples](https://github.com/AzureAD/microsoft-authentication-library-for-js).

## Prerequisites

To be able to run this sample, you need:

- Register a Client and Server (Web API) applications in Microsoft Entra ID as part of [On Behalf Of workflow](/entra/identity-platform/v2-oauth2-on-behalf-of-flow). Follow instructions on [registrations set up guideline](https://github.com/Azure-Samples/communication-services-authentication-hero-csharp/blob/main/docs/deployment-guides/set-up-app-registrations.md)
- A deployed Azure Communication Services resource. [Create an Azure Communication Services resource](../quickstarts/create-communication-resource.md?tabs=linux&pivots=platform-azp). 
- Update the Server (Web API) application with information from the app registrations.
 
::: zone pivot="programming-language-javascript"
[!INCLUDE [NodeJS Auth Hero](./includes/node-auth-hero.md)]
::: zone-end

::: zone pivot="programming-language-csharp"
[!INCLUDE [C# Auth hero](./includes/csharp-auth-hero.md)]
::: zone-end
