---
title: Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 046b7ab0381391b16a306d36322086882c03f18a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849815"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="e1417-103">Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1417-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="e1417-104">No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1417-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="e1417-105">No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e1417-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="e1417-106">Isso envolve a habilitação da funcionalidade Group Writeback no Azure AD Connect, juntamente com vários scripts de inicialização: [Configurar o Office 365 Groups com o Exchange híbrido local](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="e1417-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
