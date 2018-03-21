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
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: d6c0f4f3a8f903ff180785214d3a4e987321a5b3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como um provedor de serviços de audioconferência

Um provedor de serviços de audioconferência fornece a *ponte de conferência*. A ponte de conferência fornece os números de telefone de discagem, PINs e IDs de conferência para reuniões que são criados. Você precisará atribuir um provedor de serviços de audioconferência para pessoas que estão indo para agendar ou liderança Skype para reuniões de negócios ou Teams da Microsoft.
  
Se você quiser poderão ver **que Microsoft** listado como um provedor de áudio, você deve atribuir uma licença de **Serviços de audioconferência** para o usuário.
  
> [!NOTE]
> Se você atribuir uma licença de **Conferência de áudio** para uma pessoa que não tem um provedor de serviços de audioconferência de terceiros, Microsoft é atribuído automaticamente como um provedor de serviços de audioconferência. Você pode [atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md) , se necessário.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como um provedor de serviços de audioconferência

### <a name="using-the-skype-for-business-admin-center"></a>Usar o Centro de administração do Skype for Business

1. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
    > [!NOTE]
    > Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
2. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.
    
3. No Painel de Ações, clique em **Editar**.
    
4. Na página de propriedades para o usuário, em **nome do provedor**, selecione **Microsoft** na lista suspensa.
    
    > [!NOTE]
    > Como você está usando o Microsoft como o provedor de serviços de audioconferência e há vários números de telefone, você pode usar a lista suspensa de **número de Chamada Tarifada padrão** para selecionar um número de áudio padrão para o usuário.
  
5. Clique em **Salvar**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Como usar um script do Windows PowerShell para uma pequena quantidade de usuários

Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir o Microsoft como um provedor de serviços de audioconferência para um pequeno número de usuários.

> [!NOTE]
> Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar um ou mais dos seguintes scripts como um arquivo de script do PowerShell e depois executá-lo.
  
Para alterar o provedor à Microsoft para um pequeno número de usuários, você pode usar o [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
**Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Como usar um script do Windows PowerShell para uma grande quantidade de usuários
Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como um provedor de serviços de audioconferência para um grande número de usuários.

Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar um ou mais dos seguintes scripts como um arquivo de script do PowerShell e depois executá-lo.

**Exemplo 1:** Neste exemplo, você pode usar esse script para alterar o provedor de serviços de audioconferência de Intercall (ou outro provedor) para a **Microsoft** para um usuários número grande em sua organização.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Aqui está o script:

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
Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Um usuário pode ser atribuído apenas um provedor de serviços de audioconferência.
    
- Você pode alterar o provedor de serviços de audioconferência da Microsoft para um provedor de terceiros a qualquer momento. Para saber mais, consulte [atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- Em sua organização, você pode ter algumas pessoas que usam o Microsoft como seu provedor de serviços de audioconferência e outras pessoas que usam um provedor de terceiros. Porém, isso é mais complicado de configurar e gerenciar.
    
## <a name="related-topics"></a>Tópicos relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)