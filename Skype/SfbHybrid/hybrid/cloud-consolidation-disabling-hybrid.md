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
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420836"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="3d070-103">Desabilitar sua configuração híbrida para concluir a migração para Teams Somente</span><span class="sxs-lookup"><span data-stu-id="3d070-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="3d070-104">Este artigo descreve como desabilitar sua configuração híbrida antes de desativar seu ambiente local Skype for Business ambiente.</span><span class="sxs-lookup"><span data-stu-id="3d070-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3d070-105">Esta é a etapa 2 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="3d070-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3d070-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3d070-106">Step 1.</span></span> <span data-ttu-id="3d070-107">[Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md).</span><span class="sxs-lookup"><span data-stu-id="3d070-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="3d070-108">**Etapa 2. Desabilite sua configuração híbrida.**</span><span class="sxs-lookup"><span data-stu-id="3d070-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="3d070-109">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="3d070-109">(This article)</span></span>

- <span data-ttu-id="3d070-110">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3d070-110">Step 3.</span></span> <span data-ttu-id="3d070-111">[Migrar pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="3d070-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3d070-112">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="3d070-112">Step 4.</span></span> <span data-ttu-id="3d070-113">[Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3d070-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3d070-114">As etapas 2 e 3 devem ser feitas na mesma janela de manutenção, pois quaisquer pontos de extremidade de aplicativo híbrido existentes não serão descobertos entre as etapas 2 e a conclusão da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3d070-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>

## <a name="overview"></a><span data-ttu-id="3d070-115">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="3d070-115">Overview</span></span>

<span data-ttu-id="3d070-116">Depois de atualizar todos os usuários do Skype for Business local para o Teams somente no Microsoft 365, você poderá desativá-la Skype for Business implantação local.</span><span class="sxs-lookup"><span data-stu-id="3d070-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="3d070-117">Antes de desativar a implantação Skype for Business local e remover qualquer hardware, você deve separar logicamente a implantação local do Microsoft 365 desabilitando o híbrido.</span><span class="sxs-lookup"><span data-stu-id="3d070-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="3d070-118">Desabilitar híbrido consiste nas quatro etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="3d070-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="3d070-119">Atualize os registros DNS para apontarem para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d070-119">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="3d070-120">Altere o modo de coexistência para sua organização para Teams Somente.</span><span class="sxs-lookup"><span data-stu-id="3d070-120">Change the coexistence mode for your organization to Teams Only.</span></span>

3. <span data-ttu-id="3d070-121">Desabilite o espaço de endereço sip compartilhado (também conhecido como "domínio dividido") na Microsoft 365 organização.</span><span class="sxs-lookup"><span data-stu-id="3d070-121">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

4. <span data-ttu-id="3d070-122">Desabilite a capacidade no local de se comunicar com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d070-122">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="3d070-123">Essas etapas separam logicamente sua implantação local do Skype for Business Server do Microsoft 365 e garantem que sua organização está totalmente Teams Somente.</span><span class="sxs-lookup"><span data-stu-id="3d070-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="3d070-124">Os detalhes de cada etapa são fornecidos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3d070-124">Details for each step are provided in this article.</span></span> <span data-ttu-id="3d070-125">Depois que isso for concluído, você poderá desativá-la Skype for Business implantação local usando um dos dois métodos referenciados abaixo.</span><span class="sxs-lookup"><span data-stu-id="3d070-125">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="3d070-126">Depois que essa separação lógica for concluída, os atributos msRTCSIP do Active Directory local ainda terão valores e continuarão a sincronizar por meio do Azure AD Conexão no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d070-126">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="3d070-127">Como você desativa o ambiente local depende se você pretende deixar esses atributos no lugar ou primeiro descompactá-los do Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3d070-127">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="3d070-128">Esteja ciente de que limpar os atributos msRTCSIP locais depois que você tiver migrado do local pode resultar em perda de serviço para os usuários!</span><span class="sxs-lookup"><span data-stu-id="3d070-128">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="3d070-129">Detalhes e trocas das duas abordagens de desativação são descritos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3d070-129">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="3d070-130">Etapas detalhadas</span><span class="sxs-lookup"><span data-stu-id="3d070-130">Detailed Steps</span></span>

1. <span data-ttu-id="3d070-131">*Atualize o DNS para apontar para Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="3d070-131">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="3d070-132">O DNS externo da organização para a organização local precisa ser atualizado para que os registros Skype for Business apontem para Microsoft 365 em vez da implantação local.</span><span class="sxs-lookup"><span data-stu-id="3d070-132">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="3d070-133">Especificamente:</span><span class="sxs-lookup"><span data-stu-id="3d070-133">Specifically:</span></span>

    |<span data-ttu-id="3d070-134">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="3d070-134">Record type</span></span>|<span data-ttu-id="3d070-135">Nome</span><span class="sxs-lookup"><span data-stu-id="3d070-135">Name</span></span>|<span data-ttu-id="3d070-136">TTL</span><span class="sxs-lookup"><span data-stu-id="3d070-136">TTL</span></span>|<span data-ttu-id="3d070-137">Prioridade</span><span class="sxs-lookup"><span data-stu-id="3d070-137">Priority</span></span>|<span data-ttu-id="3d070-138">Peso</span><span class="sxs-lookup"><span data-stu-id="3d070-138">Weight</span></span>|<span data-ttu-id="3d070-139">Porta</span><span class="sxs-lookup"><span data-stu-id="3d070-139">Port</span></span>|<span data-ttu-id="3d070-140">Valor</span><span class="sxs-lookup"><span data-stu-id="3d070-140">Value</span></span>|
    |---|---|---|---|---|---|---|
    |<span data-ttu-id="3d070-141">SRV</span><span class="sxs-lookup"><span data-stu-id="3d070-141">SRV</span></span>|<span data-ttu-id="3d070-142">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3d070-142">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3d070-143">3600</span><span class="sxs-lookup"><span data-stu-id="3d070-143">3600</span></span>|<span data-ttu-id="3d070-144">100</span><span class="sxs-lookup"><span data-stu-id="3d070-144">100</span></span>|<span data-ttu-id="3d070-145">1</span><span class="sxs-lookup"><span data-stu-id="3d070-145">1</span></span>|<span data-ttu-id="3d070-146">5061</span><span class="sxs-lookup"><span data-stu-id="3d070-146">5061</span></span>|<span data-ttu-id="3d070-147">sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3d070-147">sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="3d070-148">SRV</span><span class="sxs-lookup"><span data-stu-id="3d070-148">SRV</span></span>|<span data-ttu-id="3d070-149">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3d070-149">_sip._tls</span></span>|<span data-ttu-id="3d070-150">3600</span><span class="sxs-lookup"><span data-stu-id="3d070-150">3600</span></span>|<span data-ttu-id="3d070-151">100</span><span class="sxs-lookup"><span data-stu-id="3d070-151">100</span></span>|<span data-ttu-id="3d070-152">1</span><span class="sxs-lookup"><span data-stu-id="3d070-152">1</span></span>|<span data-ttu-id="3d070-153">443</span><span class="sxs-lookup"><span data-stu-id="3d070-153">443</span></span>|<span data-ttu-id="3d070-154">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3d070-154">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="3d070-155">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d070-155">CNAME</span></span>| <span data-ttu-id="3d070-156">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d070-156">lyncdiscover</span></span>|   <span data-ttu-id="3d070-157">3600</span><span class="sxs-lookup"><span data-stu-id="3d070-157">3600</span></span>| | | |<span data-ttu-id="3d070-158">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3d070-158">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="3d070-159">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d070-159">CNAME</span></span>| <span data-ttu-id="3d070-160">sip</span><span class="sxs-lookup"><span data-stu-id="3d070-160">sip</span></span>|    <span data-ttu-id="3d070-161">3600</span><span class="sxs-lookup"><span data-stu-id="3d070-161">3600</span></span>| | | | <span data-ttu-id="3d070-162">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3d070-162">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="3d070-163">Além disso, os registros CNAME para meet ou dialin (se presente) podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="3d070-163">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="3d070-164">Por fim, quaisquer registros DNS para Skype for Business em sua rede interna devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="3d070-164">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="3d070-165">Em casos raros, a alteração do DNS de apontar no local para o Microsoft 365 para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:</span><span class="sxs-lookup"><span data-stu-id="3d070-165">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="3d070-166">Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN de proxy.</span><span class="sxs-lookup"><span data-stu-id="3d070-166">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="3d070-167">Esse modelo de federação herdado não se baseia nos registros SRV DNS, portanto, essa configuração ficará desa datada quando sua organização for para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3d070-167">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="3d070-168">Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync. <span> com precisará atualizar sua configuração para habilitar isso.</span><span class="sxs-lookup"><span data-stu-id="3d070-168">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="3d070-169">Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com qualquer locatário híbrido ou online.</span><span class="sxs-lookup"><span data-stu-id="3d070-169">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="3d070-170">Nesse caso, a federação com essas organizações não funcionará até habilitar seu provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="3d070-170">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="3d070-171">Se você suspeitar que qualquer um de seus parceiros federados possa estar usando Federação Direta ou não tiver federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso enquanto se prepara para concluir sua migração para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3d070-171">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="3d070-172">*Altere o modo de coexistência para sua organização para Teams Somente.*</span><span class="sxs-lookup"><span data-stu-id="3d070-172">*Change the coexistence mode for your organization to Teams Only.*</span></span> <span data-ttu-id="3d070-173">Isso garante que qualquer novo usuário em sua organização seja sempre criado como um Teams usuário único.</span><span class="sxs-lookup"><span data-stu-id="3d070-173">This ensures that any new user in your organization is always created as a Teams Only user.</span></span> <span data-ttu-id="3d070-174">Além disso, tentar alterar o modo de locatário para Teams Somente verificará automaticamente a existência de quaisquer registros DNS locais que possam ter sido perdidas na etapa 1 e identificar esses registros na saída.</span><span class="sxs-lookup"><span data-stu-id="3d070-174">In addition,  attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span>  <span data-ttu-id="3d070-175">Alterar o modo de locatário para Teams somente terá êxito até que todos os registros DNS para sua organização sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="3d070-175">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organizaiton are updated.</span></span> <span data-ttu-id="3d070-176">Para alterar o modo de locatário para Teams execute somente o seguinte comando de uma janela Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d070-176">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
<span data-ttu-id="3d070-177">Como alternativa, você pode usar o Centro de Administração Teams para alterar o modo de coexistência do locatário para o TeamsOnly, em "Configurações de toda a organização" -> "atualização Teams".</span><span class="sxs-lookup"><span data-stu-id="3d070-177">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    
    
3.  <span data-ttu-id="3d070-178">*Desabilite o espaço de endereço sip compartilhado Microsoft 365 organização.*</span><span class="sxs-lookup"><span data-stu-id="3d070-178">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="3d070-179">O comando abaixo precisa ser feito de uma janela Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d070-179">The command below needs to be done from a Teams PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  <span data-ttu-id="3d070-180">*Desabilite a capacidade no local de se comunicar com Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="3d070-180">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="3d070-181">O comando abaixo precisa ser feito de uma janela local do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d070-181">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="3d070-182">Gerenciando atributos após mover usuários do local para a nuvem</span><span class="sxs-lookup"><span data-stu-id="3d070-182">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="3d070-183">Por padrão, todos os usuários que foram habilitados anteriormente para Skype for Business Server e posteriormente movidos para a nuvem ainda têm atributos msRTCSIP configurados no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3d070-183">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="3d070-184">Esses atributos, em particular endereço sip (msRTCSIP-PrimaryUserAddress) e potencialmente número de telefone (msRTCSIP-Line), continuam a sincronizar com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d070-184">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="3d070-185">Se as alterações são necessárias para qualquer um dos atributos msRTCSIP, essas alterações devem ser feitas no Active Directory local e, em seguida, sincronizar com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d070-185">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="3d070-186">No entanto, depois que Skype for Business Server implantação do Skype for Business Server for removida, as ferramentas de Skype for Business Server não estarão disponíveis para gerenciar esses atributos.</span><span class="sxs-lookup"><span data-stu-id="3d070-186">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="3d070-187">Há duas opções disponíveis para lidar com essa situação:</span><span class="sxs-lookup"><span data-stu-id="3d070-187">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="3d070-188">Deixe os usuários habilitados para Skype for Business contas de servidor como estão e gerencie os atributos msRTCSIP usando ferramentas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d070-188">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="3d070-189">Isso garante nenhuma perda de serviço para usuários migrados e permite que você remova facilmente a implantação do Skype for Business Server eliminando (por exemplo, limpar) os servidores, sem um descomissionamento completo.</span><span class="sxs-lookup"><span data-stu-id="3d070-189">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="3d070-190">No entanto, os usuários recém-licenciados não terão esses atributos preenchidos no Active Directory local e precisarão ser gerenciados online.</span><span class="sxs-lookup"><span data-stu-id="3d070-190">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="3d070-191">Limpe todos os atributos msRTCSIP de usuários migrados no Active Directory local e gerencie esses atributos usando ferramentas online.</span><span class="sxs-lookup"><span data-stu-id="3d070-191">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="3d070-192">Esse método permite uma abordagem de gerenciamento consistente para usuários existentes e novos, no entanto, pode resultar em uma perda temporária de serviço durante o processo de desativação local.</span><span class="sxs-lookup"><span data-stu-id="3d070-192">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="3d070-193">Método 1 - Gerenciar endereços sip e números de telefone para usuários no Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d070-193">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="3d070-194">Os administradores podem gerenciar usuários que foram movidos anteriormente de um local Skype for Business Server para a nuvem, mesmo após a desativação da implantação local.</span><span class="sxs-lookup"><span data-stu-id="3d070-194">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="3d070-195">Se você quiser fazer alterações no endereço sip de um usuário ou no número de telefone de um usuário (e o endereço sip ou número de telefone já tiver um valor no Active Directory local), você deve fazer isso no Active Directory local e permitir que os valores fluam para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d070-195">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="3d070-196">Isso NÃO requer Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3d070-196">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="3d070-197">Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in MMC de Usuários e Computadores do Active Directory (conforme mostrado abaixo) ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d070-197">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="3d070-198">Se você estiver usando o snap-in MMC, abra a página de propriedades do usuário, clique na guia Editor de Atributos e encontre os atributos apropriados para modificar:</span><span class="sxs-lookup"><span data-stu-id="3d070-198">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="3d070-199">Para modificar o endereço sip de um usuário, modifique `msRTCSIP-PrimaryUserAddress` o .</span><span class="sxs-lookup"><span data-stu-id="3d070-199">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d070-200">Se o `ProxyAddresses` atributo contiver um endereço sip, atualize também esse valor como uma prática prática.</span><span class="sxs-lookup"><span data-stu-id="3d070-200">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="3d070-201">Embora o endereço sip seja ignorado pelo O365 se estiver preenchido, ele pode ser usado por outros `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` componentes locais.</span><span class="sxs-lookup"><span data-stu-id="3d070-201">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="3d070-202">Para modificar o número de telefone de um usuário, modifique `msRTCSIP-Line` *se ele já tiver um valor*.</span><span class="sxs-lookup"><span data-stu-id="3d070-202">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Ferramenta de computadores e usuários do Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="3d070-204">Se o usuário não tiver originalmente um valor para o local antes da movimentação, você poderá modificar o número de telefone usando o parâmetro - no `msRTCSIP-Line` `onpremLineUri` [cmdlet Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) no módulo do PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3d070-204">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="3d070-205">Essas etapas não são necessárias para novos usuários criados após a desabilitação híbrida, e esses usuários podem ser gerenciados diretamente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3d070-205">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="3d070-206">Se você estiver confortável usando a combinação desses métodos, bem como com deixar os atributos msRTCSIP no seu Active Directory local, você pode simplesmente reimimá-los no local Skype for Business servidores.</span><span class="sxs-lookup"><span data-stu-id="3d070-206">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="3d070-207">No entanto, se você preferir limpar todos os atributos msRTCSIP e fazer uma desinstalação tradicional do Skype for Business Server, use o Método 2.</span><span class="sxs-lookup"><span data-stu-id="3d070-207">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="3d070-208">Método 2 - Limpar Skype for Business atributos para todos os usuários locais no Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d070-208">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="3d070-209">Essa opção requer esforço adicional e planejamento adequado, pois os usuários que foram movidos anteriormente de uma Skype for Business Server local para a nuvem são necessários para serem re provisionados.</span><span class="sxs-lookup"><span data-stu-id="3d070-209">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="3d070-210">Esses usuários podem ser categorizados em duas categorias diferentes: usuários sem Sistema de Telefonia e usuários com Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="3d070-210">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="3d070-211">Os usuários com Sistema de Telefonia terão uma perda temporária do serviço de telefonia como parte da transição do número de telefone de ser gerenciado no Active Directory local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3d070-211">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="3d070-212">**É recomendável executar um piloto envolvendo um pequeno número de usuários com Sistema de Telefonia antes de iniciar operações de usuário em massa.**</span><span class="sxs-lookup"><span data-stu-id="3d070-212">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="3d070-213">Para implantações grandes, os usuários podem ser processados em grupos menores em janelas de tempo diferentes.</span><span class="sxs-lookup"><span data-stu-id="3d070-213">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="3d070-214">Esse processo é mais simples para usuários que têm um endereço sip correspondente e UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="3d070-214">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="3d070-215">Para organizações que têm usuários com valores não correspondentes nesses dois atributos, é necessário ter cuidado extra, conforme abaixo, para uma transição suave.</span><span class="sxs-lookup"><span data-stu-id="3d070-215">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="3d070-216">Se você configurou pontos de extremidade de aplicativo híbrido local para Atendimento Automático ou Filas de Chamada, não deixe de mover esses pontos de extremidade para Microsoft 365 antes de desativá-los Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3d070-216">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="3d070-217">Confirme se o seguinte cmdlet local Skype for Business PowerShell retornará um resultado vazio.</span><span class="sxs-lookup"><span data-stu-id="3d070-217">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="3d070-218">Um resultado vazio significa que nenhum usuário está no local e foi movido para Microsoft 365 ou desabilitado:</span><span class="sxs-lookup"><span data-stu-id="3d070-218">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="3d070-219">Grave o número de telefone atual dos usuários (LineUri), UserPrincipalName e informações relacionadas, executando o seguinte cmdlet local Skype for Business Server PowerShell para exportar dados do usuário:</span><span class="sxs-lookup"><span data-stu-id="3d070-219">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="3d070-220">Antes de continuar SfbUserSettings.csv arquivo aberto e confirmar se todos os dados do usuário foram exportados com êxito.</span><span class="sxs-lookup"><span data-stu-id="3d070-220">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="3d070-221">É recomendável manter uma cópia desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d070-221">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="3d070-222">Não use esse arquivo nas etapas a seguir para processar usuários.</span><span class="sxs-lookup"><span data-stu-id="3d070-222">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="3d070-223">Crie um arquivo com um grupo de usuários a ser usado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d070-223">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="3d070-224">Depois que o primeiro grupo de usuários for concluído com êxito, prossiga com o próximo grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="3d070-224">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="3d070-225">No exemplo abaixo, os grupos de usuários são selecionados em ordem alfabética, mas você pode filtrar os usuários com base em critérios que corresponde a como você gostaria de processar os usuários.</span><span class="sxs-lookup"><span data-stu-id="3d070-225">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="3d070-226">Antes de continuar SfbUsers.csv arquivo aberto e confirmar que os dados do usuário foram exportados com êxito.</span><span class="sxs-lookup"><span data-stu-id="3d070-226">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="3d070-227">Você precisará do LineUri (número de telefone), UserPrincipalName, SamAccountName e SipAddress desse arquivo em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="3d070-227">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="3d070-228">Exclua as informações de atributo relacionadas Skype for Business Server do Active Directory para o conjunto de usuários que você está pronto para atualizar.</span><span class="sxs-lookup"><span data-stu-id="3d070-228">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="3d070-229">Há duas etapas para esse processo, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="3d070-229">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="3d070-230">Após o próximo ciclo de AAD Sync após executar esta etapa, os usuários com Sistema de Telefonia que foram movidos anteriormente de um Skype for Business Server local para a nuvem perderão a capacidade de fazer e receber chamadas até que a etapa 8 seja concluída e confirmada com êxito na etapa 9.</span><span class="sxs-lookup"><span data-stu-id="3d070-230">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="3d070-231">Além disso, certifique-se de ter salvo os números de telefone do usuário e as informações relacionadas conforme a etapa 2, já que essas informações são necessárias para essa etapa.</span><span class="sxs-lookup"><span data-stu-id="3d070-231">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="3d070-232">Em seguida, para o mesmo conjunto de usuários, desempacote o valor de msRTCSIP-DeploymentLocator usando o PowerShell local do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="3d070-232">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="3d070-233">Execute o seguinte Módulo local do Active Directory para Windows PowerShell cmdlet para adicionar o valor de endereço sip de volta ao proxy local do Active DirectoryAddresses.</span><span class="sxs-lookup"><span data-stu-id="3d070-233">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="3d070-234">Isso impedirá problemas de interoperabilidade que dependem desse atributo.</span><span class="sxs-lookup"><span data-stu-id="3d070-234">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="3d070-235">Executar Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="3d070-235">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="3d070-236">Aguarde o provisionamento do usuário ser concluído.</span><span class="sxs-lookup"><span data-stu-id="3d070-236">Wait for user provisioning to complete.</span></span> <span data-ttu-id="3d070-237">Você pode monitorar o andamento do provisionamento do usuário executando o seguinte comando Skype for Business PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="3d070-237">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="3d070-238">O seguinte Skype for Business comando do PowerShell Online retorna um resultado vazio assim que o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="3d070-238">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="3d070-239">Execute o seguinte comando Skype for Business PowerShell Online para atribuir números de telefone e habilitar usuários para Sistema de Telefonia:</span><span class="sxs-lookup"><span data-stu-id="3d070-239">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="3d070-240">Se você ainda tiver Skype for Business pontos de extremidade (clientes Skype ou telefones de terceiros), também deseja definir -HostedVoiceMail como $true.</span><span class="sxs-lookup"><span data-stu-id="3d070-240">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="3d070-241">Se sua organização estiver usando apenas Teams pontos de extremidade para usuários habilitados para voz, essa configuração não será aplicável aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="3d070-241">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="3d070-242">Confirme se os usuários com Sistema de Telefonia funcionalidade foram provisionados corretamente.</span><span class="sxs-lookup"><span data-stu-id="3d070-242">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="3d070-243">O seguinte Skype for Business comando do PowerShell Online retorna um resultado vazio assim que o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="3d070-243">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="3d070-244">Repita as etapas de 3 a 9 até que todos os usuários sejam processados.</span><span class="sxs-lookup"><span data-stu-id="3d070-244">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="3d070-245">Confirme se todos os usuários foram processados com êxito executando os dois comandos do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d070-245">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="3d070-246">Comando local do PowerShell Skype for Business Server local:</span><span class="sxs-lookup"><span data-stu-id="3d070-246">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="3d070-247">Skype for Business Comando do PowerShell Online:</span><span class="sxs-lookup"><span data-stu-id="3d070-247">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="3d070-248">Depois de concluir todas as etapas no Método 2, consulte [Mover](decommission-move-on-prem-endpoints.md) pontos de extremidade de aplicativo híbrido do local para online e [Remover](decommission-remove-on-prem.md) o Skype for Business Server local para obter etapas adicionais para remover sua implantação Skype for Business Server local.</span><span class="sxs-lookup"><span data-stu-id="3d070-248">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="3d070-249">Confira também</span><span class="sxs-lookup"><span data-stu-id="3d070-249">See also</span></span>

- [<span data-ttu-id="3d070-250">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d070-250">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="3d070-251">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d070-251">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

