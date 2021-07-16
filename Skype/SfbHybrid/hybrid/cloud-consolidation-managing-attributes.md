---
title: Decidir como gerenciar atributos após o descomissionamento
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
description: Este artigo descreve como gerenciar atributos após a desativação do ambiente local.
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458977"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="04f8d-103">Decidir como gerenciar atributos após o descomissionamento</span><span class="sxs-lookup"><span data-stu-id="04f8d-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="04f8d-104">Por padrão, todos os usuários que foram habilitados anteriormente para Skype for Business Server e posteriormente movidos para a nuvem ainda têm atributos msRTCSIP configurados no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="04f8d-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="04f8d-105">Esses atributos, em particular endereço sip (msRTCSIP-PrimaryUserAddress) e potencialmente número de telefone (msRTCSIP-Line), continuam a sincronizar com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04f8d-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="04f8d-106">Se as alterações são necessárias para qualquer um dos atributos msRTCSIP, essas alterações devem ser feitas no Active Directory local e, em seguida, sincronizar com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04f8d-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="04f8d-107">No entanto, depois que Skype for Business Server implantação do Skype for Business Server for removida, as ferramentas de Skype for Business Server não estarão disponíveis para gerenciar esses atributos.</span><span class="sxs-lookup"><span data-stu-id="04f8d-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="04f8d-108">Há duas opções disponíveis para lidar com essa situação:</span><span class="sxs-lookup"><span data-stu-id="04f8d-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="04f8d-109">Deixe os usuários habilitados para Skype for Business contas de servidor como estão e gerencie os atributos msRTCSIP usando ferramentas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="04f8d-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="04f8d-110">Isso garante nenhuma perda de serviço para usuários migrados e permite que você remova facilmente a implantação do Skype for Business Server eliminando (por exemplo, limpar) os servidores, sem um descomissionamento completo.</span><span class="sxs-lookup"><span data-stu-id="04f8d-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="04f8d-111">No entanto, os usuários recém-licenciados não terão esses atributos preenchidos no Active Directory local e precisarão ser gerenciados online.</span><span class="sxs-lookup"><span data-stu-id="04f8d-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="04f8d-112">Limpe todos os atributos msRTCSIP de usuários migrados no Active Directory local e gerencie esses atributos usando ferramentas online.</span><span class="sxs-lookup"><span data-stu-id="04f8d-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="04f8d-113">Esse método permite uma abordagem de gerenciamento consistente para usuários existentes e novos, no entanto, pode resultar em uma perda temporária de serviço durante o processo de desativação local.</span><span class="sxs-lookup"><span data-stu-id="04f8d-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="04f8d-114">Método 1 - Gerenciar endereços sip e números de telefone para usuários no Active Directory</span><span class="sxs-lookup"><span data-stu-id="04f8d-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="04f8d-115">Os administradores podem gerenciar usuários que foram movidos anteriormente de um local Skype for Business Server para a nuvem, mesmo após a desativação da implantação local.</span><span class="sxs-lookup"><span data-stu-id="04f8d-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="04f8d-116">Se você quiser fazer alterações no endereço sip de um usuário ou no número de telefone de um usuário (e o endereço sip ou número de telefone já tiver um valor no Active Directory local), você deve fazer isso no Active Directory local e permitir que os valores fluam para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04f8d-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="04f8d-117">Isso NÃO requer Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="04f8d-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="04f8d-118">Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in MMC de Usuários e Computadores do Active Directory (conforme mostrado abaixo) ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04f8d-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="04f8d-119">Se você estiver usando o snap-in MMC, abra a página de propriedades do usuário, clique na guia Editor de Atributos e encontre os atributos apropriados para modificar:</span><span class="sxs-lookup"><span data-stu-id="04f8d-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="04f8d-120">Para modificar o endereço sip de um usuário, modifique `msRTCSIP-PrimaryUserAddress` o .</span><span class="sxs-lookup"><span data-stu-id="04f8d-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04f8d-121">Se o `ProxyAddresses` atributo contiver um endereço sip, atualize também esse valor como uma prática prática.</span><span class="sxs-lookup"><span data-stu-id="04f8d-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="04f8d-122">Embora o endereço sip seja ignorado pelo O365 se estiver preenchido, ele pode ser usado por outros `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` componentes locais.</span><span class="sxs-lookup"><span data-stu-id="04f8d-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="04f8d-123">Para modificar o número de telefone de um usuário, modifique `msRTCSIP-Line` *se ele já tiver um valor*.</span><span class="sxs-lookup"><span data-stu-id="04f8d-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Ferramenta de computadores e usuários do Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="04f8d-125">Se o usuário não tiver originalmente um valor para o local antes da movimentação, você poderá modificar o número de telefone usando o parâmetro - no `msRTCSIP-Line` `onpremLineUri` [cmdlet Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) no módulo do PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="04f8d-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="04f8d-126">Essas etapas não são necessárias para novos usuários criados após a desabilitação híbrida, e esses usuários podem ser gerenciados diretamente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="04f8d-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="04f8d-127">Se você estiver confortável usando a combinação desses métodos, bem como com deixar os atributos msRTCSIP no seu Active Directory local, você pode simplesmente reimimá-los no local Skype for Business servidores.</span><span class="sxs-lookup"><span data-stu-id="04f8d-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="04f8d-128">No entanto, se você preferir limpar todos os atributos msRTCSIP e fazer uma desinstalação tradicional do Skype for Business Server, use o Método 2.</span><span class="sxs-lookup"><span data-stu-id="04f8d-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="04f8d-129">Método 2 - Limpar Skype for Business atributos para todos os usuários locais no Active Directory</span><span class="sxs-lookup"><span data-stu-id="04f8d-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="04f8d-130">Essa opção requer esforço adicional e planejamento adequado, pois os usuários que foram movidos anteriormente de uma Skype for Business Server local para a nuvem são necessários para serem re provisionados.</span><span class="sxs-lookup"><span data-stu-id="04f8d-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="04f8d-131">Esses usuários podem ser categorizados em duas categorias diferentes: usuários sem Sistema de Telefonia e usuários com Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="04f8d-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="04f8d-132">Os usuários com Sistema de Telefonia terão uma perda temporária do serviço de telefonia como parte da transição do número de telefone de ser gerenciado no Active Directory local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="04f8d-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="04f8d-133">**É recomendável executar um piloto envolvendo um pequeno número de usuários com Sistema de Telefonia antes de iniciar operações de usuário em massa.**</span><span class="sxs-lookup"><span data-stu-id="04f8d-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="04f8d-134">Para implantações grandes, os usuários podem ser processados em grupos menores em janelas de tempo diferentes.</span><span class="sxs-lookup"><span data-stu-id="04f8d-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="04f8d-135">Esse processo é mais simples para usuários que têm um endereço sip correspondente e UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="04f8d-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="04f8d-136">Para organizações que têm usuários com valores não correspondentes nesses dois atributos, é necessário ter cuidado extra, conforme abaixo, para uma transição suave.</span><span class="sxs-lookup"><span data-stu-id="04f8d-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="04f8d-137">Se você configurou pontos de extremidade de aplicativo híbrido local para Atendimento Automático ou Filas de Chamada, não deixe de mover esses pontos de extremidade para Microsoft 365 antes de desativá-los Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="04f8d-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="04f8d-138">Confirme se o seguinte cmdlet local Skype for Business PowerShell retornará um resultado vazio.</span><span class="sxs-lookup"><span data-stu-id="04f8d-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="04f8d-139">Um resultado vazio significa que nenhum usuário está no local e foi movido para Microsoft 365 ou desabilitado:</span><span class="sxs-lookup"><span data-stu-id="04f8d-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="04f8d-140">Grave o número de telefone atual dos usuários (LineUri), UserPrincipalName e informações relacionadas, executando o seguinte cmdlet local Skype for Business Server PowerShell para exportar dados do usuário:</span><span class="sxs-lookup"><span data-stu-id="04f8d-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="04f8d-141">Antes de continuar SfbUserSettings.csv arquivo aberto e confirmar se todos os dados do usuário foram exportados com êxito.</span><span class="sxs-lookup"><span data-stu-id="04f8d-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="04f8d-142">É recomendável manter uma cópia desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="04f8d-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="04f8d-143">Não use esse arquivo nas etapas a seguir para processar usuários.</span><span class="sxs-lookup"><span data-stu-id="04f8d-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="04f8d-144">Crie um arquivo com um grupo de usuários a ser usado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="04f8d-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="04f8d-145">Depois que o primeiro grupo de usuários for concluído com êxito, prossiga com o próximo grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="04f8d-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="04f8d-146">No exemplo abaixo, os grupos de usuários são selecionados em ordem alfabética, mas você pode filtrar os usuários com base em critérios que corresponde a como você gostaria de processar os usuários.</span><span class="sxs-lookup"><span data-stu-id="04f8d-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="04f8d-147">Antes de continuar SfbUsers.csv arquivo aberto e confirmar que os dados do usuário foram exportados com êxito.</span><span class="sxs-lookup"><span data-stu-id="04f8d-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="04f8d-148">Você precisará do LineUri (número de telefone), UserPrincipalName, SamAccountName e SipAddress desse arquivo em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="04f8d-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="04f8d-149">Exclua as informações de atributo relacionadas Skype for Business Server do Active Directory para o conjunto de usuários que você está pronto para atualizar.</span><span class="sxs-lookup"><span data-stu-id="04f8d-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="04f8d-150">Há duas etapas para esse processo, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="04f8d-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="04f8d-151">Após o próximo ciclo de AAD Sync após executar esta etapa, os usuários com Sistema de Telefonia que foram movidos anteriormente de um Skype for Business Server local para a nuvem perderão a capacidade de fazer e receber chamadas até que a etapa 8 seja concluída e confirmada com êxito na etapa 9.</span><span class="sxs-lookup"><span data-stu-id="04f8d-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="04f8d-152">Além disso, certifique-se de ter salvo os números de telefone do usuário e as informações relacionadas conforme a etapa 2, já que essas informações são necessárias para essa etapa.</span><span class="sxs-lookup"><span data-stu-id="04f8d-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="04f8d-153">Em seguida, para o mesmo conjunto de usuários, desempacote o valor de msRTCSIP-DeploymentLocator usando o PowerShell local do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="04f8d-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="04f8d-154">Execute o seguinte Módulo local do Active Directory para Windows PowerShell cmdlet para adicionar o valor de endereço sip de volta ao proxy local do Active DirectoryAddresses.</span><span class="sxs-lookup"><span data-stu-id="04f8d-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="04f8d-155">Isso impedirá problemas de interoperabilidade que dependem desse atributo.</span><span class="sxs-lookup"><span data-stu-id="04f8d-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="04f8d-156">Executar Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="04f8d-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="04f8d-157">Aguarde o provisionamento do usuário ser concluído.</span><span class="sxs-lookup"><span data-stu-id="04f8d-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="04f8d-158">Você pode monitorar o andamento do provisionamento do usuário executando o seguinte comando Skype for Business PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="04f8d-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="04f8d-159">O seguinte Skype for Business comando do PowerShell Online retorna um resultado vazio assim que o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="04f8d-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="04f8d-160">Execute o seguinte comando Skype for Business PowerShell Online para atribuir números de telefone e habilitar usuários para Sistema de Telefonia:</span><span class="sxs-lookup"><span data-stu-id="04f8d-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="04f8d-161">Se você ainda tiver Skype for Business pontos de extremidade (clientes Skype ou telefones de terceiros), também deseja definir -HostedVoiceMail como $true.</span><span class="sxs-lookup"><span data-stu-id="04f8d-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="04f8d-162">Se sua organização estiver usando apenas Teams pontos de extremidade para usuários habilitados para voz, essa configuração não será aplicável aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="04f8d-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="04f8d-163">Confirme se os usuários com Sistema de Telefonia funcionalidade foram provisionados corretamente.</span><span class="sxs-lookup"><span data-stu-id="04f8d-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="04f8d-164">O seguinte Skype for Business comando do PowerShell Online retorna um resultado vazio assim que o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="04f8d-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="04f8d-165">Repita as etapas de 3 a 9 até que todos os usuários sejam processados.</span><span class="sxs-lookup"><span data-stu-id="04f8d-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="04f8d-166">Confirme se todos os usuários foram processados com êxito executando os dois comandos do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="04f8d-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="04f8d-167">Comando local do PowerShell Skype for Business Server local:</span><span class="sxs-lookup"><span data-stu-id="04f8d-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="04f8d-168">Skype for Business Comando do PowerShell Online:</span><span class="sxs-lookup"><span data-stu-id="04f8d-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="04f8d-169">Depois de concluir todas as etapas no Método 2, consulte [Mover](decommission-move-on-prem-endpoints.md) pontos de extremidade de aplicativo híbrido do local para online e [Remover](decommission-remove-on-prem.md) o Skype for Business Server local para obter etapas adicionais para remover sua implantação Skype for Business Server local.</span><span class="sxs-lookup"><span data-stu-id="04f8d-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="04f8d-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="04f8d-170">See also</span></span>

- [<span data-ttu-id="04f8d-171">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="04f8d-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="04f8d-172">Desativar o ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="04f8d-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

