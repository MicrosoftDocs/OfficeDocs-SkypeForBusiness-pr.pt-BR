---
title: Provisionamento de contas do Exchange e do Skype do Sistema de Sala do Skype
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
description: Leia estes tópicos para saber como provisionar contas do Exchange e do Skype para o Sistema de Sala do Skype.
ms.openlocfilehash: fb0b511d8a99d6aa9901459e1ea06d2f05ae4a42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833911"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="bc0d4-103">Provisionamento de contas do Exchange e do Skype do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="bc0d4-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="bc0d4-104">Leia estes tópicos para saber como provisionar contas do Exchange e do Skype para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="bc0d4-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc0d4-105">As Salas do Microsoft Teams são um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="bc0d4-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="bc0d4-106">Para obter informações sobre salas do Microsoft Teams, consulte a visão geral de implantação de Salas [do](room-systems-v2.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc0d4-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc0d4-107">O provisionamento da conta do Sistema de Sala do Skype depende do tipo de topologia que sua organização tem.</span><span class="sxs-lookup"><span data-stu-id="bc0d4-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="bc0d4-108">Para saber mais sobre topologias do Active Directory, consulte [Environmental requirements for Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="bc0d4-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="bc0d4-109">Provisionamento de contas do Skype for Business do Skype for Business do Sistema de Sala &amp; do Skype</span><span class="sxs-lookup"><span data-stu-id="bc0d4-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="bc0d4-110">Os tópicos a seguir descrevem como provisionar e gerenciar o Exchange do Sistema de Sala do Skype e contas do Skype for Business para:</span><span class="sxs-lookup"><span data-stu-id="bc0d4-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="bc0d4-111">Implantação de uma única floresta no local</span><span class="sxs-lookup"><span data-stu-id="bc0d4-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="bc0d4-112">Implementações locais de várias florestas</span><span class="sxs-lookup"><span data-stu-id="bc0d4-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="bc0d4-113">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="bc0d4-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="bc0d4-114">Implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="bc0d4-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="bc0d4-115">Parceiros federados do Skype Room System e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc0d4-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="bc0d4-116">Gerenciar contas do Sistema de Salas Skype</span><span class="sxs-lookup"><span data-stu-id="bc0d4-116">Manage Skype Room System accounts</span></span>
    

