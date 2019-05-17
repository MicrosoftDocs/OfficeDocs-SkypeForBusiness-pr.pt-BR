---
title: Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dstrome
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3b41f0ae30fb0c21baab1f7e01b86e79300008e
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108632"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="f804d-103">Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f804d-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="f804d-104">No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f804d-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="f804d-105">No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f804d-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="f804d-106">Isso envolve a habilitação da funcionalidade de write-back de grupo no Azure Connect AD, juntamente com diversos scripts de inicialização: [Configurar o Office 365 grupos com Exchange híbrido local](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="f804d-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
