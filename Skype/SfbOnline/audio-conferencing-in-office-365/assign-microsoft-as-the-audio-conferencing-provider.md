---
title: Atribuir a Microsoft como provedor de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 8ce128c2fa19668ed93c6ad387feecbee2e00a8d
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164510"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="465ee-103">Atribuir a Microsoft como provedor de audioconferência</span><span class="sxs-lookup"><span data-stu-id="465ee-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="465ee-104">Para usar a Audioconferência no Microsoft 365 ou no Office 365 com o Skype for Business e o Microsoft Teams, os usuários em sua organização precisam ter uma licença de Audioconferência atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="465ee-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="465ee-105">Confira [Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obter mais informações sobre licenciamento e quanto custa.</span><span class="sxs-lookup"><span data-stu-id="465ee-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="465ee-106">A Audioconferência da Microsoft fornece números de telefone de discagem, PINs e IDs de conferência que podem ser usados pelos participantes da reunião para ingressar nas reuniões da sua organização.</span><span class="sxs-lookup"><span data-stu-id="465ee-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="465ee-107">Você só precisa atribuir a Microsoft como provedor de audioconferência às pessoas que vão agendar ou liderar reuniões do Skype for Business ou do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="465ee-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="465ee-108">Atribuir a Microsoft como provedor de audioconferência</span><span class="sxs-lookup"><span data-stu-id="465ee-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) <span data-ttu-id="465ee-110">Usar o Centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="465ee-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="465ee-111">Vá para o **portal herddo** do centro de administração do Microsoft  >  Teams.</span><span class="sxs-lookup"><span data-stu-id="465ee-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="465ee-112">No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para **Audioconferência.**</span><span class="sxs-lookup"><span data-stu-id="465ee-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="465ee-113">Se você vir uma faixa notificando que há usuários que têm uma licença de **Audioconferência** atribuída, mas ainda não têm a Microsoft definida como provedor de audioconferência, clique aqui para movê-los. </span><span class="sxs-lookup"><span data-stu-id="465ee-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="465ee-114">Se você não vir a faixa, no Centro de administração do **Skype for Business,** clique em Usuários e selecione os Usuários prontos para serem movidos para o filtro **audioconferência.**</span><span class="sxs-lookup"><span data-stu-id="465ee-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="465ee-115">Na página de propriedades do usuário, em **Nome** do provedor, selecione **Microsoft** na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="465ee-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="465ee-116">Como você está usando a Microsoft como provedor de audioconferência  e há vários números de telefone, pode usar a lista de chamada tarifada padrão para selecionar um número de áudio padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="465ee-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="465ee-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="465ee-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="465ee-118">Como usar um script do Windows PowerShell para uma pequena quantidade de usuários</span><span class="sxs-lookup"><span data-stu-id="465ee-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="465ee-119">Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como provedor de audioconferência para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="465ee-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="465ee-120">Quando o provedor for alterado de outro provedor para a **Microsoft,** as informações de audioconferência do usuário (ID de conferência, números de tarifação tarifada e gratuita) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="465ee-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="465ee-121">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="465ee-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="465ee-122">Para alterar o provedor para a Microsoft para um pequeno número de usuários, você pode usar o cmdlet [Enable-CsOnlineDialInConferencingUser.](https://technet.microsoft.com/library/mt243813.aspx)</span><span class="sxs-lookup"><span data-stu-id="465ee-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="465ee-123">Como usar um script do Windows PowerShell para uma grande quantidade de usuários</span><span class="sxs-lookup"><span data-stu-id="465ee-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="465ee-124">Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como provedor de audioconferência para um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="465ee-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="465ee-125">Quando o provedor for alterado de outro provedor para a **Microsoft,** as informações de audioconferência do usuário (ID de conferência, números de tarifação tarifada e gratuita) serão substituídas.</span><span class="sxs-lookup"><span data-stu-id="465ee-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="465ee-126">Você deve salvar essas informações antes de alterar o provedor.</span><span class="sxs-lookup"><span data-stu-id="465ee-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="465ee-127">Você pode salvar o seguinte script como um arquivo de script do PowerShell e, em seguida, execute-o usando qualquer um dos parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="465ee-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="465ee-128">**Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="465ee-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="465ee-129">**Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="465ee-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="465ee-130">**Exemplo 3:** Neste exemplo, você pode usar esse script para alterar o provedor de audioconferência de Intercall (ou outro provedor) para a **Microsoft** para um grande número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="465ee-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="465ee-131">Este é o script:</span><span class="sxs-lookup"><span data-stu-id="465ee-131">Here is the script:</span></span>

  ```PowerShell
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
<span data-ttu-id="465ee-132">Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="465ee-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="465ee-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="465ee-133">Related topics</span></span>
<span data-ttu-id="465ee-134">[Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="465ee-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

