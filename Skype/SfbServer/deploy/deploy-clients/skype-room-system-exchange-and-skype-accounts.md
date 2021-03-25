---
title: Provisionamento de contas do Skype Room System Exchange e Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: Leia estes tópicos para saber como provisionar contas do Exchange e do Skype para o Skype Room System.
ms.openlocfilehash: 0e8c73bc83a62465dc711b4a6f2725f1d9c576f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113057"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="8df6f-103">Provisionamento de contas do Skype Room System Exchange e Skype</span><span class="sxs-lookup"><span data-stu-id="8df6f-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="8df6f-104">Leia estes tópicos para saber como provisionar contas do Exchange e do Skype para o Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8df6f-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="8df6f-105">As Salas do Microsoft Teams são um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="8df6f-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="8df6f-106">Para obter informações sobre salas do Microsoft Teams, consulte a visão geral de implantação das Salas do Microsoft [Teams.](/MicrosoftTeams/rooms/rooms-deploy)</span><span class="sxs-lookup"><span data-stu-id="8df6f-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](/MicrosoftTeams/rooms/rooms-deploy).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8df6f-107">O provisionamento da conta do Sistema de Sala do Skype depende do tipo de topologia que sua organização tem.</span><span class="sxs-lookup"><span data-stu-id="8df6f-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="8df6f-108">Para saber mais sobre topologias do Active Directory, consulte [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8df6f-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="8df6f-109">Provisionamento de contas do Skype Room System &amp; Exchange Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8df6f-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="8df6f-110">Os tópicos a seguir descrevem como provisionar e gerenciar contas do Skype Room System Exchange e skype for Business para:</span><span class="sxs-lookup"><span data-stu-id="8df6f-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="8df6f-111">Implantação de uma única floresta no local</span><span class="sxs-lookup"><span data-stu-id="8df6f-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="8df6f-112">Implementações locais de várias florestas</span><span class="sxs-lookup"><span data-stu-id="8df6f-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="8df6f-113">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="8df6f-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="8df6f-114">Implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="8df6f-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="8df6f-115">Skype Room System e parceiros federados do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8df6f-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="8df6f-116">Gerenciar contas do Sistema de Salas Skype</span><span class="sxs-lookup"><span data-stu-id="8df6f-116">Manage Skype Room System accounts</span></span>
