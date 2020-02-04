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
ms.openlocfilehash: f0c3d1d667847e080b47f31bb1032ff4b8ac980d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695756"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como provedor de audioconferência

Para usar a conferência de áudio no Office 365 com o Skype for Business e o Microsoft Teams, os usuários de sua organização precisam ter uma licença de audioconferência atribuída a ele. Consulte [experimentar ou comprar conferências de áudio no Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obter mais informações sobre licenciamento e quanto custam.

A conferência de áudio da Microsoft fornece números de telefone de discagem, PINs e IDs de conferência que podem ser usados pelos participantes da reunião para ingressar nas reuniões da sua organização. Você só precisa atribuir a Microsoft como provedor de serviços de audioconferência para as pessoas que vão agendar ou liderar reuniões do Skype for Business ou do Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como provedor de audioconferência

### <a name="an-icon-showing-the-skype-for-business-logoimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) Usar o Centro de administração do Skype for Business

1. Vá para o > **portal herdado**do **centro de administração do Microsoft Teams**.
    
2. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **videoconferências**.
    
3. Se você vir uma faixa notificando que há usuários que têm uma licença de **audioconferência** atribuída, mas que ainda não têm o Microsoft Set como provedor de serviços de audioconferência, clique **em clique aqui para movê-los**. Se você não vir a faixa, no **centro de administração do Skype for Business** , clique em **usuários**e selecione os **usuários prontos para serem movidos para o filtro de audioconferência** .
    
4. Na página Propriedades do usuário, em nome do **provedor**, selecione **Microsoft** na lista suspensa.
    
    > [!NOTE]
    > Como você está usando a Microsoft como provedor de serviços de audioconferência e há vários números de telefone, você pode usar a lista suspensa **número de chamada padrão** para selecionar um número de áudio padrão para o usuário.
  
5. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Como usar um script do Windows PowerShell para uma pequena quantidade de usuários

Para poupar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como o provedor de serviços de audioconferência para um pequeno número de usuários.

> [!NOTE]
> Quando o provedor for alterado de outro provedor para a **Microsoft**, as informações de audioconferência do usuário (ID de conferência, números de chamada tarifada e gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 

  
Para alterar o provedor para a Microsoft para um pequeno número de usuários, você pode usar o cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/library/mt243813.aspx) .
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Como usar um script do Windows PowerShell para uma grande quantidade de usuários
Para poupar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como o provedor de serviços de audioconferência para um grande número de usuários.

Quando o provedor for alterado de outro provedor para a **Microsoft**, as informações de audioconferência do usuário (ID de conferência, números de chamada tarifada e gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar o script a seguir como um arquivo de script do PowerShell e executá-lo usando qualquer um de seus parâmetros de entrada.

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

**Exemplo 3:** Neste exemplo, você pode usar esse script para alterar o provedor de serviços de audioconferência da InterCall (ou outro provedor) para a **Microsoft** para um grande número de usuários em sua organização.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Aqui está o script:

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
Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="related-topics"></a>Tópicos relacionados
[Experimentar ou comprar o áudio videoconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Configurar o Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

