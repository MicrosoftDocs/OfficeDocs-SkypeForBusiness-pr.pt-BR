---
title: Desabilitar a migração híbrida para concluir Teams Somente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este artigo inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação da nuvem para Teams e Skype for Business.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453640"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="8cfc1-103">Desabilitar sua configuração híbrida para concluir a migração para Teams Somente</span><span class="sxs-lookup"><span data-stu-id="8cfc1-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="8cfc1-104">Este artigo descreve como desabilitar sua configuração híbrida antes de desativar seu ambiente local Skype for Business ambiente.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="8cfc1-105">Esta é a etapa 2 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="8cfc1-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="8cfc1-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-106">Step 1.</span></span> <span data-ttu-id="8cfc1-107">[Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc1-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="8cfc1-108">**Etapa 2. Desabilite sua configuração híbrida.**</span><span class="sxs-lookup"><span data-stu-id="8cfc1-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="8cfc1-109">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="8cfc1-109">(This article)</span></span>

- <span data-ttu-id="8cfc1-110">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-110">Step 3.</span></span> <span data-ttu-id="8cfc1-111">[Migrar pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc1-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="8cfc1-112">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-112">Step 4.</span></span> <span data-ttu-id="8cfc1-113">[Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="8cfc1-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8cfc1-114">As etapas 2 e 3 devem ser feitas na mesma janela de manutenção, pois quaisquer pontos de extremidade de aplicativo híbrido existentes não serão descobertos entre as etapas 2 e a conclusão da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="8cfc1-115">Resumo</span><span class="sxs-lookup"><span data-stu-id="8cfc1-115">Summary</span></span>

<span data-ttu-id="8cfc1-116">Depois de atualizar todos os usuários do Skype for Business local para o Teams somente no Microsoft 365, você poderá desativá-la Skype for Business implantação local.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="8cfc1-117">Antes de desativar a implantação Skype for Business local e remover qualquer hardware, você deve separar logicamente a implantação local do Microsoft 365 desabilitando o híbrido.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="8cfc1-118">Desabilitar híbrido consiste nas quatro etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="8cfc1-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="8cfc1-119">[Atualizar registros DNS para apontar para Microsoft 365](#update-dns-to-point-to-microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="8cfc1-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="8cfc1-120">[Altere o modo de coexistência para sua organização para Teams Somente](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span><span class="sxs-lookup"><span data-stu-id="8cfc1-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="8cfc1-121">[Desabilitar o espaço de endereço sip compartilhado (também conhecido como "domínio dividido") na organização Microsoft 365 .](#disable-shared-sip-address-space-in-microsoft-365-organization)</span><span class="sxs-lookup"><span data-stu-id="8cfc1-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="8cfc1-122">Desabilitar a comunicação entre o local e o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cfc1-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="8cfc1-123">Essas etapas separam logicamente sua implantação local do Skype for Business Server do Microsoft 365 e garantem que sua organização está totalmente Teams Somente.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="8cfc1-124">Depois de concluir essas etapas, você pode desativá-la Skype for Business implantação local usando um dos dois métodos referenciados em Decidir como gerenciar atributos após o [descomissionamento](cloud-consolidation-managing-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc1-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="8cfc1-125">Depois que essa separação lógica for concluída, os atributos msRTCSIP do Active Directory local ainda terão valores e continuarão a sincronizar por meio do Azure AD Conexão no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="8cfc1-126">Como você desativa o ambiente local depende se você pretende deixar esses atributos no lugar ou primeiro descompactá-los do Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="8cfc1-127">Esteja ciente de que limpar os atributos msRTCSIP locais depois que você tiver migrado do local pode resultar em perda de serviço para os usuários!</span><span class="sxs-lookup"><span data-stu-id="8cfc1-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="8cfc1-128">Detalhes e trocas das duas abordagens de desativação são descritos em Decidir como gerenciar atributos [após a desativação.](cloud-consolidation-managing-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="8cfc1-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="8cfc1-129">Atualizar DNS para apontar para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cfc1-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="8cfc1-130">O DNS externo da organização para a organização local precisa ser atualizado para que os registros Skype for Business apontem para Microsoft 365 em vez da implantação local.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="8cfc1-131">Além disso, os registros CNAME para meet ou dialin (se presente) podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="8cfc1-132">Por fim, quaisquer registros DNS para Skype for Business em sua rede interna devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="8cfc1-133">Para obter detalhes sobre como atualizar registros DNS, consulte [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc1-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="8cfc1-134">Altere o modo de coexistência para que sua organização Teams Somente</span><span class="sxs-lookup"><span data-stu-id="8cfc1-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="8cfc1-135">Esta etapa garante que qualquer novo usuário em sua organização seja sempre criado como um Teams usuário único.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="8cfc1-136">Tentar alterar o modo de locatário para Teams Somente verificará automaticamente a existência de quaisquer registros DNS locais que possam ter sido perdidas na etapa 1 e identificar esses registros na saída.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="8cfc1-137">Alterar o modo de locatário para Teams somente terá êxito até que todos os registros DNS da sua organização sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="8cfc1-138">Para alterar o modo de locatário para Teams execute somente o seguinte comando de uma janela Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="8cfc1-139">Como alternativa, você pode usar o Centro de Administração Teams para alterar o modo de coexistência do locatário para o TeamsOnly, em "Configurações de toda a organização" -> "atualização Teams".</span><span class="sxs-lookup"><span data-stu-id="8cfc1-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="8cfc1-140">Desabilitar o espaço de endereço sip compartilhado Microsoft 365 organização</span><span class="sxs-lookup"><span data-stu-id="8cfc1-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="8cfc1-141">Para desabilitar o espaço de endereço sip compartilhado, execute o seguinte comando de uma Teams do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cfc1-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="8cfc1-142">Desabilitar a comunicação entre o local e o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cfc1-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="8cfc1-143">Para desabilitar a comunicação entre o ambiente local e o Microsoft 365, execute o seguinte comando de uma janela local do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8cfc1-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="8cfc1-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="8cfc1-144">See also</span></span>

- [<span data-ttu-id="8cfc1-145">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cfc1-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="8cfc1-146">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cfc1-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

