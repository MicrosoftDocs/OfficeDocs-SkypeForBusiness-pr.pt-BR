---
title: Configurar uma organização híbrida do Exchange
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 23773ac842b93067dbf3204d81e2a3ad1708a3af
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778687"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="f64f1-103">Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f64f1-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="f64f1-104">No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f64f1-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="f64f1-105">No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f64f1-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="f64f1-106">Isso envolve a habilitação da funcionalidade de write-back do grupo no Azure AD Connect juntamente com vários scripts de inicialização: [configurar os grupos do Microsoft 365 com o Exchange híbrido local](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="f64f1-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
