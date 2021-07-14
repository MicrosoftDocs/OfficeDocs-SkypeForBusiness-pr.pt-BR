---
title: Migrar pontos de extremidade de aplicativo híbrido para a nuvem
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
description: Migre pontos de extremidade de aplicativo hirido antes de descomissionar um ambiente Skype for Business local.
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420796"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="aefb7-103">Migrar pontos de extremidade de aplicativo híbrido antes de encerrar seu ambiente local</span><span class="sxs-lookup"><span data-stu-id="aefb7-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="aefb7-104">Este artigo descreve como mover os pontos de extremidade de aplicativo híbrido necessários para a nuvem da Microsoft antes de desativá-los Skype for Business ambiente.</span><span class="sxs-lookup"><span data-stu-id="aefb7-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="aefb7-105">Esta é a etapa 3 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="aefb7-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="aefb7-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="aefb7-106">Step 1.</span></span> [<span data-ttu-id="aefb7-107">Mover todos os usuários necessários do local para o online</span><span class="sxs-lookup"><span data-stu-id="aefb7-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="aefb7-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="aefb7-108">Step 2.</span></span> <span data-ttu-id="aefb7-109">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="aefb7-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="aefb7-110">**Etapa 3. Migrar pontos de extremidade de aplicativo híbrido do local para o online.**</span><span class="sxs-lookup"><span data-stu-id="aefb7-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="aefb7-111">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="aefb7-111">(This article)</span></span>

- <span data-ttu-id="aefb7-112">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="aefb7-112">Step 4.</span></span> <span data-ttu-id="aefb7-113">[Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="aefb7-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="aefb7-114">Migrar todos os pontos de extremidade de aplicativo híbrido necessários do local para o online</span><span class="sxs-lookup"><span data-stu-id="aefb7-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="aefb7-115">Antes de mover esses pontos de extremidade para online, você deve garantir que os registros DNS atualizados apontem para Microsoft 365 para todos os domínios sip usados pelos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="aefb7-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="aefb7-116">Esteja ciente de que, depois de atualizar o DNS para apontar para Microsoft 365, todos os pontos de extremidade de aplicativo híbrido existentes não serão mais descobertos até que você conclua esta etapa.</span><span class="sxs-lookup"><span data-stu-id="aefb7-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="aefb7-117">Como esta etapa (criar contas de recursos online) não será possível se os registros DNS apontarem para o local, você deve planejar realizar as etapas 2 e 3 na mesma janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="aefb7-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="aefb7-118">Para obter mais informações, consulte [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="aefb7-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="aefb7-119">Recupere e exporte configurações de ponto de extremidade de aplicativo híbrido local executando o seguinte comando local Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aefb7-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="aefb7-120">Crie e licencie novas [contas de](/microsoftteams/manage-resource-accounts) recursos Microsoft 365 substituir os pontos de extremidade do aplicativo híbrido local existentes.</span><span class="sxs-lookup"><span data-stu-id="aefb7-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="aefb7-121">Associe as novas Contas de Recursos aos pontos de extremidade do aplicativo híbrido existentes.</span><span class="sxs-lookup"><span data-stu-id="aefb7-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="aefb7-122">Remova números de telefone definidos nos pontos de extremidade do aplicativo híbrido local executando o seguinte comando local Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aefb7-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="aefb7-123">Como é possível que os números de telefone dessas contas fossem gerenciados no Microsoft 365 em vez de no local, execute o seguinte comando no Skype for Business PowerShell Online:</span><span class="sxs-lookup"><span data-stu-id="aefb7-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="aefb7-124">Atribua números de telefone às novas Contas de Recursos criadas na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="aefb7-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="aefb7-125">Para obter mais informações sobre como atribuir um número de telefone a uma conta de recurso, consulte o seguinte artigo: [Atribuir um número de serviço](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="aefb7-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="aefb7-126">Exclua os pontos de extremidade locais executando o seguinte comando local Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aefb7-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="aefb7-127">Agora você está pronto para remover sua implantação [local Skype for Business local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="aefb7-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aefb7-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="aefb7-128">See also</span></span>

- [<span data-ttu-id="aefb7-129">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aefb7-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="aefb7-130">Mover todos os usuários necessários do local para o online</span><span class="sxs-lookup"><span data-stu-id="aefb7-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="aefb7-131">Desabilitar sua configuração híbrida</span><span class="sxs-lookup"><span data-stu-id="aefb7-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="aefb7-132">Remover a implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aefb7-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




