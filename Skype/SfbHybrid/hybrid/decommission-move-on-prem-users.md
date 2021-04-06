---
title: Mover usuários e pontos de extremidade para a nuvem
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
description: Mova usuários e pontos de extremidade antes de descompactar um ambiente local do Skype for Business.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593871"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="c3f6d-103">Mover usuários e pontos de extremidade necessários antes de encerrar seu ambiente local</span><span class="sxs-lookup"><span data-stu-id="c3f6d-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="c3f6d-104">Este artigo descreve como mover usuários e pontos de extremidade de aplicativo necessários para a nuvem da Microsoft antes de encerrar seu ambiente local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="c3f6d-105">Esta é a etapa 1 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="c3f6d-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="c3f6d-106">**Etapa 1. Mova todos os usuários e pontos de extremidade de aplicativo necessários do local para o online.**</span><span class="sxs-lookup"><span data-stu-id="c3f6d-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="c3f6d-107">(Este artigo.)</span><span class="sxs-lookup"><span data-stu-id="c3f6d-107">(This article.)</span></span>

- <span data-ttu-id="c3f6d-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-108">Step 2.</span></span> <span data-ttu-id="c3f6d-109">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="c3f6d-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="c3f6d-110">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-110">Step 3.</span></span> <span data-ttu-id="c3f6d-111">[Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="c3f6d-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="c3f6d-112">Mover todos os usuários necessários do local para a nuvem</span><span class="sxs-lookup"><span data-stu-id="c3f6d-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="c3f6d-113">Todos os usuários que você continuará a usar depois de concluir a migração devem primeiro ser movidos do local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="c3f6d-114">Você move os usuários usando as ferramentas de administração locais.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="c3f6d-115">Para obter detalhes, [consulte Mover usuários entre o local e a nuvem.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="c3f6d-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="c3f6d-116">Embora seja possível que os usuários com contas locais do Skype for Business Server usem o Teams, esses usuários não têm a funcionalidade completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="c3f6d-117">Esses usuários não podem interoperar ou federar com qualquer outro usuário que ainda esteja usando o Skype for Business (online ou local).</span><span class="sxs-lookup"><span data-stu-id="c3f6d-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="c3f6d-118">Esses usuários também não podem receber chamadas PSTN em seu cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="c3f6d-119">Portanto, você deve mover esses usuários para online.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="c3f6d-120">Esta etapa também garante que todos os contatos ou reuniões criados no Skype for Business Server sejam migrados para o Teams.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="c3f6d-121">Para verificar se há outros usuários em sua implantação local, execute o cmdlet a seguir em uma janela do PowerShell do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="c3f6d-122">Se algum usuário for retornado, revise a saída para determinar se alguma conta deve ser movida para a nuvem e, para esses usuários, siga as etapas [aqui](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="c3f6d-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="c3f6d-123">Para contas de usuário que não são mais necessárias, execute o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c3f6d-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="c3f6d-124">Executar Disable-CsUser removerá todos os atributos do Skype for Business para todos os usuários que atenderem aos critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="c3f6d-125">Antes de prosseguir, confirme se essas contas não são mais necessárias para avançar.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="c3f6d-126">Mover pontos de extremidade de aplicativo híbrido local para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3f6d-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="c3f6d-127">Recupere e exporte configurações de ponto de extremidade de aplicativo híbrido local executando o seguinte comando local do Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3f6d-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="c3f6d-128">Crie e licencie novas Contas [de](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) Recursos no Microsoft 365 para substituir os pontos de extremidade de aplicativo híbrido locais existentes.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="c3f6d-129">Associe as novas Contas de Recursos aos pontos de extremidade do aplicativo híbrido existentes.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="c3f6d-130">Remova números de telefone definidos nos pontos de extremidade do aplicativo híbrido local executando o seguinte comando do PowerShell do Skype for Business Server local:</span><span class="sxs-lookup"><span data-stu-id="c3f6d-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="c3f6d-131">Como é possível que os números de telefone dessas contas fossem gerenciados no Microsoft 365 em vez de no local, execute o seguinte comando no Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3f6d-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="c3f6d-132">Atribua números de telefone às novas Contas de Recursos criadas na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="c3f6d-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="c3f6d-133">Para obter mais informações sobre como atribuir um número de telefone a uma conta de recurso, consulte o seguinte artigo: [Atribuir um número de serviço](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="c3f6d-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="c3f6d-134">Exclua os pontos de extremidade locais executando o seguinte comando local do Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3f6d-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="c3f6d-135">Agora você está pronto para [desabilitar sua configuração híbrida.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="c3f6d-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3f6d-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="c3f6d-136">See also</span></span>

- [<span data-ttu-id="c3f6d-137">Desmantelar seu ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c3f6d-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="c3f6d-138">Desabilitar sua configuração híbrida</span><span class="sxs-lookup"><span data-stu-id="c3f6d-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="c3f6d-139">Remover sua implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c3f6d-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




