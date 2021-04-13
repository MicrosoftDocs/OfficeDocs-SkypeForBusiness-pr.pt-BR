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
description: Mova os usuários antes de desmantelar um ambiente local do Skype for Business.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656667"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="d1714-103">Mover usuários necessários antes de desmantelar seu ambiente local</span><span class="sxs-lookup"><span data-stu-id="d1714-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="d1714-104">Este artigo descreve como mover os usuários necessários para a nuvem da Microsoft antes de desmantelar seu ambiente local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d1714-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="d1714-105">Esta é a etapa 1 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="d1714-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="d1714-106">**Etapa 1. Mova todos os usuários necessários do local para o online.**</span><span class="sxs-lookup"><span data-stu-id="d1714-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="d1714-107">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="d1714-107">(This article)</span></span>

- <span data-ttu-id="d1714-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="d1714-108">Step 2.</span></span> <span data-ttu-id="d1714-109">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="d1714-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="d1714-110">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="d1714-110">Step 3.</span></span> <span data-ttu-id="d1714-111">[Mover pontos de extremidade de aplicativo híbrido de local para online](decommission-move-on-prem-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="d1714-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="d1714-112">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="d1714-112">Step 4.</span></span> <span data-ttu-id="d1714-113">[Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="d1714-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="d1714-114">Mover todos os usuários necessários do local para a nuvem</span><span class="sxs-lookup"><span data-stu-id="d1714-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="d1714-115">Todos os usuários que você continuará a usar depois de concluir a migração devem primeiro ser movidos do local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="d1714-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="d1714-116">Você move os usuários usando as ferramentas de administração locais.</span><span class="sxs-lookup"><span data-stu-id="d1714-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="d1714-117">Para obter detalhes, [consulte Mover usuários entre o local e a nuvem.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="d1714-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="d1714-118">Embora seja possível que os usuários com contas locais do Skype for Business Server usem o Teams, esses usuários não têm a funcionalidade completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="d1714-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="d1714-119">Esses usuários não podem interoperar ou federar com qualquer outro usuário que ainda esteja usando o Skype for Business (online ou local).</span><span class="sxs-lookup"><span data-stu-id="d1714-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="d1714-120">Esses usuários também não podem receber chamadas PSTN em seu cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="d1714-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="d1714-121">Portanto, você deve mover esses usuários para online.</span><span class="sxs-lookup"><span data-stu-id="d1714-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="d1714-122">Esta etapa também garante que todos os contatos ou reuniões criados no Skype for Business Server sejam migrados para o Teams.</span><span class="sxs-lookup"><span data-stu-id="d1714-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="d1714-123">Para verificar se há outros usuários em sua implantação local, execute o cmdlet a seguir em uma janela do PowerShell do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d1714-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="d1714-124">Se algum usuário for retornado, revise a saída para determinar se alguma conta deve ser movida para a nuvem e, para esses usuários, siga as etapas [aqui](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="d1714-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="d1714-125">Para contas de usuário que não são mais necessárias, execute o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="d1714-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="d1714-126">Executar Disable-CsUser removerá todos os atributos do Skype for Business para todos os usuários que atenderem aos critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="d1714-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="d1714-127">Antes de prosseguir, confirme se essas contas não são mais necessárias para avançar.</span><span class="sxs-lookup"><span data-stu-id="d1714-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="d1714-128">Agora você está pronto para [desabilitar sua configuração híbrida.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="d1714-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1714-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1714-129">See also</span></span>

- [<span data-ttu-id="d1714-130">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1714-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="d1714-131">Desabilitar sua configuração híbrida</span><span class="sxs-lookup"><span data-stu-id="d1714-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="d1714-132">Mover pontos de extremidade de aplicativo híbrido do local para o online</span><span class="sxs-lookup"><span data-stu-id="d1714-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="d1714-133">Remover a implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1714-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




