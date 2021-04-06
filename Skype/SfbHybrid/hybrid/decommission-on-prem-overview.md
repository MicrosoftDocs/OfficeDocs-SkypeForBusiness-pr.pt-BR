---
title: Desmantelar seu ambiente local do Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções sobre como desmantelar seu ambiente local do Skype for Business.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593869"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="6845e-103">Desmantelar seu ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6845e-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="6845e-104">Se sua organização usa o Teams ou o Skype for Business Online com uma implantação local do Skype for Business Server, você pode migrar esses ambientes totalmente para a nuvem e, em seguida, retirar sua implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6845e-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="6845e-105">Antes de desmantelar seu ambiente [](configure-hybrid-connectivity.md) local, você deve configurar a conectividade híbrida entre sua implantação local e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6845e-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="6845e-106">Depois de configurar a conectividade híbrida, você pode migrar usuários para a nuvem, ao migrar suas reuniões do local e migrar quaisquer contatos do Skype for Business Server para o Teams.</span><span class="sxs-lookup"><span data-stu-id="6845e-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="6845e-107">Configurar a conectividade híbrida é uma etapa necessária para migrar os usuários do local para a nuvem e garantir a funcionalidade completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="6845e-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="6845e-108">Para concluir sua movimentação do local para a nuvem e desmantelar seu ambiente local do Skype for Business Server, você deve concluir as seguintes etapas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="6845e-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="6845e-109">**Etapa 1.**</span><span class="sxs-lookup"><span data-stu-id="6845e-109">**Step 1.**</span></span> <span data-ttu-id="6845e-110">Mova todos os usuários e pontos de extremidade de aplicativo [necessários do local para o online](decommission-move-on-prem-users.md).</span><span class="sxs-lookup"><span data-stu-id="6845e-110">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="6845e-111">**Etapa 2.**</span><span class="sxs-lookup"><span data-stu-id="6845e-111">**Step 2.**</span></span> <span data-ttu-id="6845e-112">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="6845e-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="6845e-113">**Etapa 3.**</span><span class="sxs-lookup"><span data-stu-id="6845e-113">**Step 3.**</span></span> <span data-ttu-id="6845e-114">[Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="6845e-114">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

