---
title: Desabilitar a migração híbrida para concluir a nuvem
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
description: Este artigo inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 90ec73246007542ad0215007b0da91f4fe9405e8
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874691"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a><span data-ttu-id="3f2c6-103">Desabilitar a migração híbrida para concluir a migração para a nuvem: Visão geral</span><span class="sxs-lookup"><span data-stu-id="3f2c6-103">Disable hybrid to complete migration to the cloud: Overview</span></span>

<span data-ttu-id="3f2c6-104">Depois de mover todos os usuários do local para a nuvem, você poderá desativar a implantação do Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="3f2c6-105">Além de remover qualquer hardware, uma etapa crítica é separar logicamente essa implantação local do Microsoft 365 ou do Office 365 desabilitando o híbrido.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="3f2c6-106">Para desabilitar a configuração híbrida, são necessárias três etapas:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-106">Disabling hybrid consists of three steps:</span></span>

1. <span data-ttu-id="3f2c6-107">Atualizar registros DNS para apontar para o Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="3f2c6-108">Desabilite o espaço de endereço sip compartilhado (também conhecido como "domínio dividido") na organização do Microsoft 365 ou office 365.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-108">Disable shared sip address space (also known as "split domain") in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="3f2c6-109">Desabilite a capacidade no local de se comunicar com o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="3f2c6-110">Essas etapas separam logicamente sua implantação local do Skype for Business Server do Office 365 e devem ser feitas juntas como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-110">These steps logically separate your on-premise deployment of Skype for Business Server from Office 365 and should be done together as a unit.</span></span> <span data-ttu-id="3f2c6-111">Os detalhes de cada etapa são fornecidos neste artigo abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-111">Details for each step are provided in this article below.</span></span> <span data-ttu-id="3f2c6-112">Depois que isso for concluído, você poderá desmantelar sua Implantação local do Skype for Business usando um dos dois métodos referenciados abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-112">Once that is complete, you can decommission your on-premises Skype for Business Deployment using one of two methods referenced below.</span></span>

> [!Important] 
><span data-ttu-id="3f2c6-113">Depois que essa separação lógica for concluída, os atributos msRTCSIP do Active Directory local ainda terão valores e continuarão a sincronizar por meio do Azure AD Connect no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-113">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="3f2c6-114">Como você desativa o ambiente local depende se você pretende deixar esses atributos no lugar ou primeiro descompactá-los do Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-114">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="3f2c6-115">Esteja ciente de que limpar os atributos msRTCSIP locais depois que você tiver migrado do local pode resultar em perda de serviço para os usuários!</span><span class="sxs-lookup"><span data-stu-id="3f2c6-115">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="3f2c6-116">Detalhes e trocas das duas abordagens de desativação são descritos mais adiante.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-116">Details and tradeoffs of the two decommissioning approaches are described later below.</span></span>

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a><span data-ttu-id="3f2c6-117">Desabilitar a migração híbrida para concluir a migração para a nuvem: Etapas detalhadas</span><span class="sxs-lookup"><span data-stu-id="3f2c6-117">Disable hybrid to complete migration to the cloud: Detailed Steps</span></span>

1. <span data-ttu-id="3f2c6-118">*Atualize o DNS para apontar para o Microsoft 365 ou Office 365.*</span><span class="sxs-lookup"><span data-stu-id="3f2c6-118">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span> <span data-ttu-id="3f2c6-119">O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Microsoft 365 ou o Office 365 em vez da implantação local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-119">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="3f2c6-120">Especificamente:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-120">Specifically:</span></span>

    |<span data-ttu-id="3f2c6-121">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="3f2c6-121">Record type</span></span>|<span data-ttu-id="3f2c6-122">Name</span><span class="sxs-lookup"><span data-stu-id="3f2c6-122">Name</span></span>|<span data-ttu-id="3f2c6-123">TTL</span><span class="sxs-lookup"><span data-stu-id="3f2c6-123">TTL</span></span>|<span data-ttu-id="3f2c6-124">Valor</span><span class="sxs-lookup"><span data-stu-id="3f2c6-124">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="3f2c6-125">SRV</span><span class="sxs-lookup"><span data-stu-id="3f2c6-125">SRV</span></span>|<span data-ttu-id="3f2c6-126">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3f2c6-126">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3f2c6-127">3600</span><span class="sxs-lookup"><span data-stu-id="3f2c6-127">3600</span></span>|<span data-ttu-id="3f2c6-128">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3f2c6-128">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="3f2c6-129">SRV</span><span class="sxs-lookup"><span data-stu-id="3f2c6-129">SRV</span></span>|<span data-ttu-id="3f2c6-130">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3f2c6-130">_sip._tls</span></span>|<span data-ttu-id="3f2c6-131">3600</span><span class="sxs-lookup"><span data-stu-id="3f2c6-131">3600</span></span>|<span data-ttu-id="3f2c6-132">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3f2c6-132">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="3f2c6-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="3f2c6-133">CNAME</span></span>| <span data-ttu-id="3f2c6-134">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3f2c6-134">lyncdiscover</span></span>|   <span data-ttu-id="3f2c6-135">3600</span><span class="sxs-lookup"><span data-stu-id="3f2c6-135">3600</span></span>|   <span data-ttu-id="3f2c6-136">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3f2c6-136">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="3f2c6-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="3f2c6-137">CNAME</span></span>| <span data-ttu-id="3f2c6-138">sip</span><span class="sxs-lookup"><span data-stu-id="3f2c6-138">sip</span></span>|    <span data-ttu-id="3f2c6-139">3600</span><span class="sxs-lookup"><span data-stu-id="3f2c6-139">3600</span></span>|   <span data-ttu-id="3f2c6-140">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="3f2c6-140">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="3f2c6-141">Além disso, os registros CNAME para meet ou dialin (se presente) podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-141">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="3f2c6-142">Por fim, quaisquer registros DNS do Skype for Business em sua rede interna devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-142">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="3f2c6-143">Em casos raros, a alteração do DNS de apontar para o Microsoft 365 ou Office 365 local para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-143">In rare cases, changing DNS from pointing on premises to Microsoft 365 or Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="3f2c6-144">Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN de proxy.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-144">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="3f2c6-145">Esse modelo de federação herdado não se baseia nos registros SRV DNS, portanto, essa configuração ficará desa datada quando sua organização for para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-145">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="3f2c6-146">Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync. <span> com precisará atualizar sua configuração para habilitar isso.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-146">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="3f2c6-147">Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com qualquer locatário híbrido ou online.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-147">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="3f2c6-148">Nesse caso, a federação com essas organizações não funcionará até habilitar seu provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-148">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="3f2c6-149">Se você suspeitar que qualquer um de seus parceiros federados possa estar usando Federação Direta ou não tiver federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso enquanto se prepara para concluir sua migração para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-149">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="3f2c6-150">*Desabilite o espaço de endereço sip compartilhado na organização do Microsoft 365 ou office 365.*</span><span class="sxs-lookup"><span data-stu-id="3f2c6-150">*Disable shared sip address space in Microsoft 365 or Office 365 organization.*</span></span> <span data-ttu-id="3f2c6-151">O comando abaixo precisa ser feito a partir de uma janela do PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="3f2c6-152">*Desabilite a capacidade no local de se comunicar com o Microsoft 365 ou o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="3f2c6-152">*Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span> <span data-ttu-id="3f2c6-153">O comando abaixo precisa ser feito de uma janela local do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-153">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="3f2c6-154">Gerenciando atributos após mover usuários do local para a nuvem</span><span class="sxs-lookup"><span data-stu-id="3f2c6-154">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="3f2c6-155">Por padrão, todos os usuários que foram habilitados anteriormente para o Skype for Business Server e posteriormente movidos para a nuvem ainda têm atributos msRTCSIP configurados no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-155">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="3f2c6-156">Esses atributos, em particular endereço sip (msRTCSIP-PrimaryUserAddress) e potencialmente número de telefone (msRTCSIP-Line), continuam a sincronizar com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-156">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="3f2c6-157">Se as alterações são necessárias para qualquer um dos atributos msRTCSIP, essas alterações devem ser feitas no Active Directory local e, em seguida, sincronizar com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-157">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="3f2c6-158">No entanto, depois que a implantação do Skype for Business Server tiver sido removida, as ferramentas do Skype for Business Server não estarão disponíveis para gerenciar esses atributos.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-158">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="3f2c6-159">Há duas opções disponíveis para lidar com essa situação:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-159">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="3f2c6-160">Deixe os usuários habilitados para contas de servidor do Skype for Business como estão e gerencie os atributos msRTCSIP usando ferramentas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-160">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="3f2c6-161">Isso garante nenhuma perda de serviço para usuários migrados e permite que você remova facilmente a implantação do Skype for Business Server eliminando (por exemplo, limpar) os servidores, sem um descomissionamento completo.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-161">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="3f2c6-162">No entanto, os usuários recém-licenciados não terão esses atributos preenchidos no Active Directory local e precisarão ser gerenciados online.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-162">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="3f2c6-163">Limpe todos os atributos msRTCSIP de usuários migrados no Active Directory local e gerencie esses atributos usando ferramentas online.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-163">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="3f2c6-164">Esse método permite uma abordagem de gerenciamento consistente para usuários existentes e novos, no entanto, pode resultar em uma perda temporária de serviço durante o processo de desativação local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-164">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="3f2c6-165">Método 1 - Gerenciar endereços sip e números de telefone para usuários no Active Directory</span><span class="sxs-lookup"><span data-stu-id="3f2c6-165">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="3f2c6-166">Os administradores podem gerenciar usuários que foram movidos anteriormente de um Skype for Business Server local para a nuvem, mesmo após a desativação da implantação local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-166">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="3f2c6-167">Se você quiser fazer alterações no endereço sip de um usuário ou no número de telefone de um usuário (e o endereço sip ou número de telefone já tiver um valor no Active Directory local), você deve fazer isso no Active Directory local e permitir que os valores fluam para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-167">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="3f2c6-168">Isso NÃO exige o Skype for Business Server local.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-168">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="3f2c6-169">Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in MMC de Usuários e Computadores do Active Directory (conforme mostrado abaixo) ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-169">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="3f2c6-170">Se você estiver usando o snap-in MMC, abra a página de propriedades do usuário, clique na guia Editor de Atributos e encontre os atributos apropriados para modificar:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-170">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="3f2c6-171">Para modificar o endereço sip de um usuário, modifique `msRTCSIP-PrimaryUserAddress` o .</span><span class="sxs-lookup"><span data-stu-id="3f2c6-171">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="3f2c6-172">Observação, se o `ProxyAddresses` atributo contiver um endereço sip, atualize também esse valor como uma prática prática.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-172">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="3f2c6-173">Embora o endereço sip seja ignorado pelo O365 se estiver preenchido, ele pode ser usado por outros `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` componentes locais.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-173">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="3f2c6-174">Para modificar o número de telefone de um usuário, modifique `msRTCSIP-Line` *se ele já tiver um valor*.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-174">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Ferramenta de computadores e usuários do Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="3f2c6-176">Se o usuário não tiver originalmente um valor para o local antes da movimentação, você poderá modificar o número de telefone usando o parâmetro - no `msRTCSIP-Line` `onpremLineUri` [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) no módulo do PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-176">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="3f2c6-177">Essas etapas não são necessárias para novos usuários criados após a desabilitação híbrida, e esses usuários podem ser gerenciados diretamente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-177">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="3f2c6-178">Se você estiver confortável usando a combinação desses métodos, bem como com a saída dos atributos msRTCSIP no seu Active Directory local, você pode simplesmente reimimá-los nos servidores locais do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-178">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="3f2c6-179">No entanto, se você preferir limpar todos os atributos msRTCSIP e fazer uma desinstalação tradicional do Skype for Business Server, use o Método 2.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-179">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="3f2c6-180">Método 2 - Limpar atributos do Skype for Business para todos os usuários locais no Active Directory</span><span class="sxs-lookup"><span data-stu-id="3f2c6-180">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="3f2c6-181">Essa opção requer esforço adicional e planejamento adequado, pois os usuários que foram movidos anteriormente de um Servidor do Skype for Business local para a nuvem são necessários para serem re provisionados.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-181">This option requires additional effort and proper planning because users that were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="3f2c6-182">Esses usuários podem ser categorizados em duas categorias diferentes: usuários sem Sistema de Telefonia e usuários com Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-182">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="3f2c6-183">Os usuários com o Sistema de Telefonia terão uma perda temporária do serviço de telefonia como parte da transição do número de telefone de ser gerenciado no Active Directory local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-183">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="3f2c6-184">**É recomendável executar um piloto envolvendo um pequeno número de usuários com o Sistema de Telefonia antes de iniciar operações de usuário em massa.**</span><span class="sxs-lookup"><span data-stu-id="3f2c6-184">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="3f2c6-185">Para implantações grandes, os usuários podem ser processados em grupos menores em janelas de tempo diferentes.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-185">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE]
> <span data-ttu-id="3f2c6-186">O processo é mais simples para usuários que têm um endereço sip correspondente e UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-186">The process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="3f2c6-187">Para organizações que têm usuários com valores não correspondentes nesses dois atributos, é necessário ter cuidado extra, conforme abaixo, para uma transição suave.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-187">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span> 


1. <span data-ttu-id="3f2c6-188">Confirme se o seguinte cmdlet local do Skype for Business PowerShell retorna um resultado vazio.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-188">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="3f2c6-189">Um resultado vazio significa que nenhum usuário está no local e foi movido para o Office 365 ou desabilitado:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-189">An empty result means no users are homed on-premises and have either been moved to Office 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="3f2c6-190">Grave o número de telefone atual dos usuários (LineUri), UserPrincipalName e informações relacionadas, executando o seguinte cmdlet local do Skype for Business Server PowerShell para exportar dados do usuário:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-190">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="3f2c6-191">Antes de continuar SfbUserSettings.csv arquivo aberto e confirmar se todos os dados do usuário foram exportados com êxito.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-191">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="3f2c6-192">É recomendável manter uma cópia desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-192">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="3f2c6-193">Não use esse arquivo nas etapas a seguir para processar usuários.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-193">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="3f2c6-194">Crie um arquivo com um grupo de usuários a ser usado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-194">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="3f2c6-195">Depois que o primeiro grupo de usuários for concluído com êxito, prossiga com o próximo grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-195">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="3f2c6-196">No exemplo abaixo, os grupos de usuários são selecionados em ordem alfabética, mas você pode filtrar os usuários com base em critérios que corresponde a como você gostaria de processar os usuários.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-196">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="3f2c6-197">Antes de continuar SfbUsers.csv arquivo aberto e confirmar que os dados do usuário foram exportados com êxito.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-197">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="3f2c6-198">Você precisará do LineUri (número de telefone), UserPrincipalName, SamAccountName e SipAddress desse arquivo em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-198">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="3f2c6-199">Exclua as informações de atributo relacionadas ao Skype for Business Server do Active Directory para o conjunto de usuários que você está pronto para atualizar.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-199">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="3f2c6-200">Há duas etapas para esse processo, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-200">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="3f2c6-201">Após o próximo ciclo de Sincronização do AAD após executar esta etapa, os usuários com o Sistema de Telefonia que foram movidos anteriormente de um Skype for Business Server local para a nuvem perderão a capacidade de fazer e receber chamadas até que a etapa 8 seja concluída e confirmada com êxito na etapa 9.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-201">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="3f2c6-202">Além disso, certifique-se de ter salvo os números de telefone do usuário e as informações relacionadas conforme a etapa 2, já que essas informações são necessárias para essa etapa.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-202">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="3f2c6-203">Em seguida, para o mesmo conjunto de usuários, desempacote o valor de msRTCSIP-DeploymentLocator usando o PowerShell local do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-203">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="3f2c6-204">Execute o seguinte cmdlet local do Skype for Business PowerShell para adicionar o valor de endereço sip de volta ao proxy local do Active DirectoryAddresses.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-204">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="3f2c6-205">Isso impedirá problemas de interoperabilidade que dependem desse atributo.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-205">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="3f2c6-206">Executar a sincronização do Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f2c6-206">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="3f2c6-207">Aguarde o provisionamento do usuário ser concluído.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-207">Wait for user provisioning to complete.</span></span> <span data-ttu-id="3f2c6-208">Você pode monitorar o andamento do provisionamento do usuário executando o seguinte comando do PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-208">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="3f2c6-209">O seguinte comando do PowerShell do Skype for Business Online retorna um resultado vazio assim que o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-209">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="3f2c6-210">Execute o seguinte comando do PowerShell do Skype for Business Online para atribuir números de telefone e habilitar usuários para o Sistema de Telefonia:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-210">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="3f2c6-211">Se você ainda tiver pontos de extremidade do Skype for Business (clientes Skype ou telefones de terceiros), também deseja definir -HostedVoiceMail como $true.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-211">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="3f2c6-212">Se sua organização estiver usando apenas pontos de extremidade do Teams para usuários habilitados para voz, essa configuração não será aplicável aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-212">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="3f2c6-213">Confirme se os usuários com a funcionalidade do Sistema de Telefonia foram provisionados corretamente.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-213">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="3f2c6-214">O seguinte comando do PowerShell do Skype for Business Online retorna um resultado vazio assim que o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-214">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="3f2c6-215">Repita as etapas de 3 a 9 até que todos os usuários sejam processados.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-215">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="3f2c6-216">Confirme se todos os usuários foram processados com êxito executando os dois comandos do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f2c6-216">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="3f2c6-217">Comando local do PowerShell do Skype for Business Server local:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-217">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="3f2c6-218">Comando do PowerShell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="3f2c6-218">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a><span data-ttu-id="3f2c6-219">Confira também</span><span class="sxs-lookup"><span data-stu-id="3f2c6-219">See also</span></span>

[<span data-ttu-id="3f2c6-220">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3f2c6-220">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
