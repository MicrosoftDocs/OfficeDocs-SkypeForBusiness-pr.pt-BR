---
title: Desativar o ambiente local do Skype for Business
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
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656677"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="59a54-103">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59a54-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="59a54-104">Se sua organização usa o Teams ou o Skype for Business Online com uma implantação local do Skype for Business Server, você pode migrar esses ambientes totalmente para a nuvem e, em seguida, retirar sua implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59a54-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="59a54-105">Antes de desmantelar seu ambiente [](configure-hybrid-connectivity.md) local, você deve configurar a conectividade híbrida entre sua implantação local e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59a54-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="59a54-106">Depois de configurar a conectividade híbrida, você pode migrar usuários para a nuvem, ao migrar suas reuniões do local e migrar quaisquer contatos do Skype for Business Server para o Teams.</span><span class="sxs-lookup"><span data-stu-id="59a54-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="59a54-107">Configurar a conectividade híbrida é uma etapa necessária para migrar os usuários do local para a nuvem e garantir a funcionalidade completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="59a54-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="59a54-108">Para concluir sua movimentação do local para a nuvem e desmantelar seu ambiente local do Skype for Business Server, você deve concluir as seguintes etapas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="59a54-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="59a54-109">**Etapa 1.**</span><span class="sxs-lookup"><span data-stu-id="59a54-109">**Step 1.**</span></span> <span data-ttu-id="59a54-110">[Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md).</span><span class="sxs-lookup"><span data-stu-id="59a54-110">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="59a54-111">**Etapa 2.**</span><span class="sxs-lookup"><span data-stu-id="59a54-111">**Step 2.**</span></span> <span data-ttu-id="59a54-112">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="59a54-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="59a54-113">**Etapa 3.**</span><span class="sxs-lookup"><span data-stu-id="59a54-113">**Step 3.**</span></span> <span data-ttu-id="59a54-114">[Mover pontos de extremidade de aplicativo híbrido de local para online](decommission-move-on-prem-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="59a54-114">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="59a54-115">**Etapa 4.**</span><span class="sxs-lookup"><span data-stu-id="59a54-115">**Step 4.**</span></span> <span data-ttu-id="59a54-116">[Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="59a54-116">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

