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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 360d580b57ca9528eddf96d80b773c04c71c361b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727710"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como provedor de audioconferência

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Para usar a Audioconferência em Microsoft 365 ou Office 365 com Skype for Business e Microsoft Teams, os usuários em sua organização precisam ter uma licença de Audioconferência atribuída a eles. Consulte [Try or purchase Audioconferncing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how it costs.

A Conferência de Áudio da Microsoft fornece números de telefone discados, PINs e IDs de conferência que podem ser usados pelos participantes da reunião para ingressar nas reuniões da sua organização. Você só precisa atribuir a Microsoft como provedor de audioconferência a pessoas que vão agendar ou conduzir Skype for Business ou Microsoft Teams reuniões.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como provedor de audioconferência

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) Usar o Centro de administração do Skype for Business

1. Vá para o **Microsoft Teams de administração portal**  >  **herdado**.
    
2. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Audioconferência**.
    
3. Se você vir um banner notificando que há usuários que têm uma licença de **Audioconferência** atribuída, mas ainda não têm a Microsoft definida como provedor de audioconferência, clique em Clique aqui para movê-los.  Se você não vir o banner, no centro de administração do Skype for Business clique em **Usuários** e selecione o filtro Usuários prontos para serem movidos para o filtro **audioconferência.** 
    
4. Na página propriedades do usuário, em Nome **do provedor,** selecione **Microsoft** na listada.
    
    > [!NOTE]
    > Como você está usando a Microsoft como provedor de audioconferência  e há vários números de telefone, você pode usar a lista de lista de espera de número de chamada de chamada padrão para selecionar um número de áudio padrão para o usuário.
  
5. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Como usar um script do Windows PowerShell para uma pequena quantidade de usuários

Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como o provedor de audioconferência para um pequeno número de usuários.

> [!NOTE]
> Quando o provedor é alterado de outro provedor para a **Microsoft**, as informações de audioconferência para o usuário (ID da conferência, números de tarifação e tarifação gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 

  
Para alterar o provedor para a Microsoft para um pequeno número de usuários, você pode usar o cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Como usar um script do Windows PowerShell para uma grande quantidade de usuários
Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como o provedor de audioconferência para um grande número de usuários.

Quando o provedor é alterado de outro provedor para a **Microsoft**, as informações de audioconferência para o usuário (ID da conferência, números de tarifação e tarifação gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar o script a seguir como um arquivo de script do PowerShell e, em seguida, execute-o usando qualquer um de seus parâmetros de entrada.

**Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Exemplo 3:** Neste exemplo, você pode usar esse script para alterar o provedor de audioconferência de Intercall (ou outro provedor) para a **Microsoft** para um grande número de usuários em sua organização.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Este é o script:

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
Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Tópicos relacionados
[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
