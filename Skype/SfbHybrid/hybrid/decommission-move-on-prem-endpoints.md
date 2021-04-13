---
title: Mover pontos de extremidade de aplicativo híbrido para a nuvem
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
description: Mova pontos de extremidade de aplicativo hirido antes de encerrar um ambiente local do Skype for Business.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656872"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="f43c1-103">Mover pontos de extremidade do aplicativo hirido antes de encerrar seu ambiente local</span><span class="sxs-lookup"><span data-stu-id="f43c1-103">Move hyrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="f43c1-104">Este artigo descreve como mover pontos de extremidade de aplicativo híbrido necessários para a nuvem da Microsoft antes de encerrar seu ambiente local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f43c1-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="f43c1-105">Esta é a etapa 3 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="f43c1-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="f43c1-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f43c1-106">Step 1.</span></span> [<span data-ttu-id="f43c1-107">Mover todos os usuários necessários do local para o online</span><span class="sxs-lookup"><span data-stu-id="f43c1-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="f43c1-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f43c1-108">Step 2.</span></span> <span data-ttu-id="f43c1-109">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f43c1-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="f43c1-110">**Etapa 3. Mova os pontos de extremidade do aplicativo híbrido do local para o online.**</span><span class="sxs-lookup"><span data-stu-id="f43c1-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="f43c1-111">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="f43c1-111">(This article)</span></span>

- <span data-ttu-id="f43c1-112">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="f43c1-112">Step 4.</span></span> <span data-ttu-id="f43c1-113">[Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="f43c1-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="f43c1-114">Mover todos os pontos de extremidade de aplicativo híbrido necessários do local para o online</span><span class="sxs-lookup"><span data-stu-id="f43c1-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="f43c1-115">Antes de poder mover esses pontos de extremidade para online, você deve garantir que os registros DNS atualizados apontem para o Microsoft 365 para todos os domínios sip usados pelos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f43c1-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="f43c1-116">Não é possível criar contas de recursos online se os registros DNS apontarem para o local.</span><span class="sxs-lookup"><span data-stu-id="f43c1-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="f43c1-117">Para obter mais informações, consulte [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f43c1-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="f43c1-118">Recupere e exporte configurações de ponto de extremidade de aplicativo híbrido local executando o seguinte comando local do Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f43c1-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="f43c1-119">Crie e licencie novas Contas [de](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) Recursos no Microsoft 365 para substituir os pontos de extremidade de aplicativo híbrido locais existentes.</span><span class="sxs-lookup"><span data-stu-id="f43c1-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="f43c1-120">Associe as novas Contas de Recursos aos pontos de extremidade do aplicativo híbrido existentes.</span><span class="sxs-lookup"><span data-stu-id="f43c1-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="f43c1-121">Remova números de telefone definidos nos pontos de extremidade do aplicativo híbrido local executando o seguinte comando do PowerShell do Skype for Business Server local:</span><span class="sxs-lookup"><span data-stu-id="f43c1-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="f43c1-122">Como é possível que os números de telefone dessas contas fossem gerenciados no Microsoft 365 em vez de no local, execute o seguinte comando no Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f43c1-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="f43c1-123">Atribua números de telefone às novas Contas de Recursos criadas na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f43c1-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="f43c1-124">Para obter mais informações sobre como atribuir um número de telefone a uma conta de recurso, consulte o seguinte artigo: [Atribuir um número de serviço](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="f43c1-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="f43c1-125">Exclua os pontos de extremidade locais executando o seguinte comando local do Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f43c1-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="f43c1-126">Agora você está pronto para remover sua implantação local do [Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="f43c1-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f43c1-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="f43c1-127">See also</span></span>

- [<span data-ttu-id="f43c1-128">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f43c1-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="f43c1-129">Mover todos os usuários necessários do local para o online</span><span class="sxs-lookup"><span data-stu-id="f43c1-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="f43c1-130">Desabilitar sua configuração híbrida</span><span class="sxs-lookup"><span data-stu-id="f43c1-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="f43c1-131">Remover a implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f43c1-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




