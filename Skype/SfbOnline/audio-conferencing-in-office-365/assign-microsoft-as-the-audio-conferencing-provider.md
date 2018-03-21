---
title: "Atribuir a Microsoft como um provedor de serviços de audioconferência"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/23/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: 0193743f9dd2ed6486d93d55c881f3e582e4eb04
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="e68b2-104">Atribuir a Microsoft como um provedor de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="e68b2-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="e68b2-105">Um provedor de serviços de audioconferência fornece a *ponte de conferência*.</span><span class="sxs-lookup"><span data-stu-id="e68b2-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="e68b2-106">A ponte de conferência fornece os números de telefone de discagem, PINs e IDs de conferência para reuniões que são criados.</span><span class="sxs-lookup"><span data-stu-id="e68b2-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="e68b2-107">Você precisará atribuir um provedor de serviços de audioconferência para pessoas que estão indo para agendar ou liderança Skype para reuniões de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e68b2-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="e68b2-108">Se você quiser poderão ver **que Microsoft** listado como um provedor de áudio, você deve atribuir uma licença de **Serviços de audioconferência** para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e68b2-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e68b2-109">Se você atribuir uma licença de **Conferência de áudio** para uma pessoa que não tem um provedor de serviços de audioconferência de terceiros, Microsoft é atribuído automaticamente como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e68b2-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="e68b2-110">Você pode [atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md) , se necessário.</span><span class="sxs-lookup"><span data-stu-id="e68b2-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="e68b2-111">Atribuir a Microsoft como um provedor de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="e68b2-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="e68b2-112">Usar o Centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e68b2-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="e68b2-113">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e68b2-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e68b2-114">Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="e68b2-114">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="e68b2-115">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="e68b2-115">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="e68b2-116">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e68b2-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="e68b2-117">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e68b2-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="e68b2-118">Na página de propriedades para o usuário, em **nome do provedor**, selecione **Microsoft** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e68b2-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e68b2-119">Como você está usando o Microsoft como o provedor de serviços de audioconferência e há vários números de telefone, você pode usar a lista suspensa de **número de Chamada Tarifada padrão** para selecionar um número de áudio padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e68b2-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="e68b2-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e68b2-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="e68b2-121">Como usar um script do Windows PowerShell para uma pequena quantidade de usuários</span><span class="sxs-lookup"><span data-stu-id="e68b2-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="e68b2-122">Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir o Microsoft como um provedor de serviços de audioconferência para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="e68b2-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="e68b2-123">Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="e68b2-123">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="e68b2-124">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="e68b2-124">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="e68b2-125">Você pode salvar um ou mais dos seguintes scripts como um arquivo de script do PowerShell e depois executá-lo.</span><span class="sxs-lookup"><span data-stu-id="e68b2-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="e68b2-126">Para alterar o provedor à Microsoft para um pequeno número de usuários, você pode usar o [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span><span class="sxs-lookup"><span data-stu-id="e68b2-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="e68b2-127">**Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="e68b2-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="e68b2-128">**Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e68b2-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="e68b2-129">Como usar um script do Windows PowerShell para uma grande quantidade de usuários</span><span class="sxs-lookup"><span data-stu-id="e68b2-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="e68b2-130">Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como um provedor de serviços de audioconferência para um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="e68b2-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="e68b2-131">Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="e68b2-131">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="e68b2-132">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="e68b2-132">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="e68b2-133">Você pode salvar um ou mais dos seguintes scripts como um arquivo de script do PowerShell e depois executá-lo.</span><span class="sxs-lookup"><span data-stu-id="e68b2-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="e68b2-134">**Exemplo 1:** Neste exemplo, você pode usar esse script para alterar o provedor de serviços de audioconferência de Intercall (ou outro provedor) para a **Microsoft** para um usuários número grande em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e68b2-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="e68b2-135">Aqui está o script:</span><span class="sxs-lookup"><span data-stu-id="e68b2-135">Here is the script:</span></span>

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="e68b2-136">Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="e68b2-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="e68b2-137">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="e68b2-137">What else should I know?</span></span>

- <span data-ttu-id="e68b2-138">Um usuário pode ser atribuído apenas um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e68b2-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="e68b2-139">Você pode alterar o provedor de serviços de audioconferência da Microsoft para um provedor de terceiros a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="e68b2-139">You can change the audio conferencing provider from Microsoft to a third-party provider at any time.</span></span> <span data-ttu-id="e68b2-140">Para saber mais, consulte [atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e68b2-140">To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="e68b2-141">Em sua organização, você pode ter algumas pessoas que usam o Microsoft como seu provedor de serviços de audioconferência e outras pessoas que usam um provedor de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e68b2-141">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="e68b2-142">Porém, isso é mais complicado de configurar e gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e68b2-142">But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e68b2-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e68b2-143">Related topics</span></span>

[<span data-ttu-id="e68b2-144">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e68b2-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="e68b2-145">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e68b2-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

