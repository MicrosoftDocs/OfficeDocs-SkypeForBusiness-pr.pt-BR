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
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams para garantir que as associações de grupo sejam sincronizadas.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094603"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="b5ad5-103">Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5ad5-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="b5ad5-104">No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5ad5-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="b5ad5-105">No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b5ad5-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="b5ad5-106">Isso envolve a habilitação da funcionalidade de Writeback de Grupo no Azure AD Connect juntamente com vários scripts de inicialização: Configurar grupos do [Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups)com o Exchange híbrido local .</span><span class="sxs-lookup"><span data-stu-id="b5ad5-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>