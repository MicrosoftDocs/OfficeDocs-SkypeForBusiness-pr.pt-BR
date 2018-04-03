---
title: Atribuir a Microsoft como um provedor de serviços de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
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
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="888d6-104">Atribuir a Microsoft como um provedor de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="888d6-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="888d6-105">Para usar conferência de áudio no Office 365 com Skype para negócios e Teams da Microsoft, os usuários em sua organização precisam ter uma licença de audioconferências atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="888d6-105">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="888d6-106">Para obter mais informações sobre licenciamento e quanto custa, consulte [tente ou adquirir audioconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="888d6-106">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="888d6-107">Conferência de áudio da Microsoft fornece os números de telefone de discagem, PINs e conferência IDs que podem ser usados pelos participantes da reunião para participar de reuniões da sua organização.</span><span class="sxs-lookup"><span data-stu-id="888d6-107">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="888d6-108">Você precisa atribuir Microsoft como um provedor de serviços de audioconferência para pessoas que estão indo para agendar ou liderança Skype para reuniões de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="888d6-108">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

<span data-ttu-id="888d6-109">Se uma licença de **Serviços de audioconferência Microsoft** for atribuída a um usuário que não tem um provedor de serviços de audioconferência, o provedor do usuário será automaticamente definido como o **Microsoft** e você não precisa fazer qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="888d6-109">If a **Microsoft Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to **Microsoft** and you don't have to do anything else.</span></span> <span data-ttu-id="888d6-110">Se o usuário já tiver um provedor de serviços de audioconferência, você deverá alterar o provedor do usuário à Microsoft após atribuindo a elas uma licença de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="888d6-110">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an Audio Conferencing license.</span></span>

<span data-ttu-id="888d6-111">Se você quiser poderão ver que Microsoft listado como um provedor de serviços de audioconferência, você deve atribuir uma licença de serviços de audioconferência para o usuário.</span><span class="sxs-lookup"><span data-stu-id="888d6-111">If you want to be able to see Microsoft listed as the audio conferencing provider, you must assign an Audio Conferencing license to the user.</span></span>


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="888d6-112">Atribuir a Microsoft como um provedor de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="888d6-112">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="888d6-113">Usar o Centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="888d6-113">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="888d6-114">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="888d6-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="888d6-115">Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="888d6-115">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="888d6-116">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="888d6-116">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="888d6-117">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="888d6-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="888d6-118">Se você vir um banner informando que não existem usuários que têm uma **Conferência de áudio** licença atribuída, mas não tenho o Microsoft definido como seu provedor de serviços de audioconferência ainda, clique em **clique aqui para movê-los**.</span><span class="sxs-lookup"><span data-stu-id="888d6-118">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="888d6-119">Se você não vir o banner, no **Skype para centro de administração de negócios** clique em **usuários**e, em seguida, selecione o filtro de **usuários prontos para ser movida para conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="888d6-119">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="888d6-120">Na página de propriedades para o usuário, em **nome do provedor**, selecione **Microsoft** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="888d6-120">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="888d6-121">Como você está usando o Microsoft como o provedor de serviços de audioconferência e há vários números de telefone, você pode usar a lista suspensa de **número de Chamada Tarifada padrão** para selecionar um número de áudio padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="888d6-121">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="888d6-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="888d6-122">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="888d6-123">Como usar um script do Windows PowerShell para uma pequena quantidade de usuários</span><span class="sxs-lookup"><span data-stu-id="888d6-123">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="888d6-124">Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir o Microsoft como um provedor de serviços de audioconferência para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="888d6-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="888d6-125">Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="888d6-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="888d6-126">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="888d6-126">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="888d6-127">Para alterar o provedor à Microsoft para um pequeno número de usuários, você pode usar o cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="888d6-127">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="888d6-128">Como usar um script do Windows PowerShell para uma grande quantidade de usuários</span><span class="sxs-lookup"><span data-stu-id="888d6-128">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="888d6-129">Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como um provedor de serviços de audioconferência para um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="888d6-129">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="888d6-130">Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="888d6-130">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="888d6-131">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="888d6-131">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="888d6-132">Você pode salvar o seguinte script como um arquivo de script do PowerShell e execute-o usando qualquer um dos seus parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="888d6-132">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="888d6-133">**Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="888d6-133">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="888d6-134">**Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="888d6-134">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="888d6-135">**Exemplo 3:** Neste exemplo, você pode usar esse script para alterar o provedor de serviços de audioconferência de Intercall (ou outro provedor) para a **Microsoft** para um usuários número grande em sua organização.</span><span class="sxs-lookup"><span data-stu-id="888d6-135">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="888d6-136">Aqui está o script:</span><span class="sxs-lookup"><span data-stu-id="888d6-136">Here is the script:</span></span>

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
<span data-ttu-id="888d6-137">Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="888d6-137">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="888d6-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="888d6-138">Related topics</span></span>

[<span data-ttu-id="888d6-139">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="888d6-139">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[<span data-ttu-id="888d6-140">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="888d6-140">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

