---
title: Mover usuários para a nuvem
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
description: Mover usuários antes de desmantelar um ambiente Skype for Business local.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420806"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="184cb-103">Mover usuários necessários antes de desmantelar seu ambiente local</span><span class="sxs-lookup"><span data-stu-id="184cb-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="184cb-104">Este artigo descreve como mover os usuários necessários para a nuvem da Microsoft antes de desativá-lo Skype for Business ambiente local.</span><span class="sxs-lookup"><span data-stu-id="184cb-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="184cb-105">Esta é a etapa 1 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="184cb-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="184cb-106">**Etapa 1. Mova todos os usuários necessários do local para o online.**</span><span class="sxs-lookup"><span data-stu-id="184cb-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="184cb-107">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="184cb-107">(This article)</span></span>

- <span data-ttu-id="184cb-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="184cb-108">Step 2.</span></span> <span data-ttu-id="184cb-109">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="184cb-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="184cb-110">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="184cb-110">Step 3.</span></span> <span data-ttu-id="184cb-111">[Migrar pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="184cb-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="184cb-112">Esteja ciente de que quaisquer pontos de extremidade de aplicativo híbrido existentes não serão descobertos entre o momento em que você executar a Etapa 2 acima até concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="184cb-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="184cb-113">Você deve planejar fazer as etapas 2 e 3 na mesma janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="184cb-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="184cb-114">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="184cb-114">Step 4.</span></span> <span data-ttu-id="184cb-115">[Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="184cb-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="184cb-116">Mover todos os usuários necessários do local para a nuvem</span><span class="sxs-lookup"><span data-stu-id="184cb-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="184cb-117">Todos os usuários que você continuará a usar depois de concluir a migração devem primeiro ser movidos do local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="184cb-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="184cb-118">Você move os usuários usando as ferramentas de administração locais.</span><span class="sxs-lookup"><span data-stu-id="184cb-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="184cb-119">Para obter detalhes, [consulte Mover usuários entre o local e a nuvem.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="184cb-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="184cb-120">Embora seja possível que os usuários com contas Skype for Business Server locais usem Teams, esses usuários não têm a funcionalidade completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="184cb-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="184cb-121">Esses usuários não podem interoperar ou federar com qualquer outro usuário que ainda esteja usando Skype for Business (online ou local).</span><span class="sxs-lookup"><span data-stu-id="184cb-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="184cb-122">Esses usuários também não podem receber chamadas PSTN em seu Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="184cb-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="184cb-123">Portanto, você deve mover esses usuários para online.</span><span class="sxs-lookup"><span data-stu-id="184cb-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="184cb-124">Esta etapa também garante que todos os contatos ou reuniões criados no Skype for Business Server sejam migrados para Teams.</span><span class="sxs-lookup"><span data-stu-id="184cb-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="184cb-125">Para verificar se há outros usuários em sua implantação local, execute o cmdlet a seguir em uma janela Skype for Business Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="184cb-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="184cb-126">Se algum usuário for retornado, revise a saída para determinar se alguma conta deve ser movida para a nuvem e, para esses usuários, siga as etapas [aqui](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="184cb-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="184cb-127">Para contas de usuário que não são mais necessárias, execute o seguinte Skype for Business Server cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="184cb-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="184cb-128">Executar Disable-CsUser removerá todos os Skype for Business para todos os usuários que atenderem aos critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="184cb-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="184cb-129">Antes de prosseguir, confirme se essas contas não são mais necessárias para avançar.</span><span class="sxs-lookup"><span data-stu-id="184cb-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="184cb-130">Agora você está pronto para [desabilitar sua configuração híbrida.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="184cb-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="184cb-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="184cb-131">See also</span></span>

- [<span data-ttu-id="184cb-132">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="184cb-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="184cb-133">Desabilitar sua configuração híbrida</span><span class="sxs-lookup"><span data-stu-id="184cb-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="184cb-134">Mover pontos de extremidade de aplicativo híbrido do local para o online</span><span class="sxs-lookup"><span data-stu-id="184cb-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="184cb-135">Remover a implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="184cb-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




