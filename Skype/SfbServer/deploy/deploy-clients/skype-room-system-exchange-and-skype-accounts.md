---
title: Provisionamento de contas do Exchange e do Skype do sistema de salas do Skype
ms.author: v-lanac
author: lanachin
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
description: Leia estes tópicos para saber como provisionar contas do Exchange e do Skype para o sistema de salas do Skype.
ms.openlocfilehash: be43e732a97dc81fdd2e3a6bdb355afaff4db37d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220911"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="9d2c8-103">Provisionamento de contas do Exchange e do Skype do sistema de salas do Skype</span><span class="sxs-lookup"><span data-stu-id="9d2c8-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="9d2c8-104">Leia estes tópicos para saber como provisionar contas do Exchange e do Skype para o sistema de salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="9d2c8-105">As salas do Microsoft Teams é um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="9d2c8-106">Para obter informações sobre as salas do Microsoft Teams, consulte a [visão geral da implantação](room-systems-v2.md)de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d2c8-107">O provisionamento de contas do sistema de salas do Skype depende do tipo de topologia da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="9d2c8-108">Para saber mais sobre topologias do Active Directory, consulte [Environmental Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d2c8-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="9d2c8-109">Provisionamento de contas do Exchange &amp; Skype for Business do sistema de salas do Skype</span><span class="sxs-lookup"><span data-stu-id="9d2c8-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="9d2c8-110">Os tópicos a seguir descrevem como provisionar e gerenciar as contas do Exchange e do Skype for Business do sistema de salas do Skype para:</span><span class="sxs-lookup"><span data-stu-id="9d2c8-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="9d2c8-111">Implantações locais de floresta única</span><span class="sxs-lookup"><span data-stu-id="9d2c8-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="9d2c8-112">Implantações locais de várias florestas</span><span class="sxs-lookup"><span data-stu-id="9d2c8-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="9d2c8-113">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="9d2c8-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="9d2c8-114">Implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="9d2c8-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="9d2c8-115">Parceiros federados do sistema de salas do Skype e do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9d2c8-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="9d2c8-116">Gerenciar contas do sistema de salas do Skype</span><span class="sxs-lookup"><span data-stu-id="9d2c8-116">Manage Skype Room System accounts</span></span>
    

