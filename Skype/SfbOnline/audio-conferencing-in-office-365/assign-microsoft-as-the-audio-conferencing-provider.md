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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 0cbfe5fec234ab237bd0c6bf108cfaa968685f0f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229400"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como provedor de audioconferência

Para usar conferência de áudio no Office 365 com Skype para negócios e Teams da Microsoft, os usuários em sua organização precisam ter uma licença de audioconferências atribuída a eles. Para obter mais informações sobre licenciamento e quanto custa, consulte [tente ou adquirir audioconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .

Conferência de áudio da Microsoft fornece os números de telefone de discagem, PINs e conferência IDs que podem ser usados pelos participantes da reunião para participar de reuniões da sua organização. Você precisa atribuir Microsoft como um provedor de serviços de audioconferência para pessoas que estão indo para agendar ou liderança Skype para reuniões de negócios ou Teams da Microsoft.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Atribuir a Microsoft como provedor de audioconferência

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) Usar o Centro de administração do Skype for Business

1. Vá para o **Centro de administração do Microsoft equipes** > **portal herdada**.
    
2. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**.
    
3. Se você vir um banner informando que não existem usuários que têm uma **Conferência de áudio** licença atribuída, mas não tenho o Microsoft definido como seu provedor de serviços de audioconferência ainda, clique em **clique aqui para movê-los**. Se você não vir o banner, no **Skype para centro de administração de negócios** clique em **usuários**e, em seguida, selecione o filtro de **usuários prontos para ser movida para conferência de áudio** .
    
4. Na página de propriedades para o usuário, em **nome do provedor**, selecione **Microsoft** na lista suspensa.
    
    > [!NOTE]
    > Como você está usando o Microsoft como o provedor de serviços de audioconferência e há vários números de telefone, você pode usar a lista suspensa de **número de Chamada Tarifada padrão** para selecionar um número de áudio padrão para o usuário.
  
5. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Como usar um script do Windows PowerShell para uma pequena quantidade de usuários

Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir o Microsoft como um provedor de serviços de audioconferência para um pequeno número de usuários.

> [!NOTE]
> Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 

  
Para alterar o provedor à Microsoft para um pequeno número de usuários, você pode usar o cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Como usar um script do Windows PowerShell para uma grande quantidade de usuários
Para economizar tempo ou automatizar isso, você pode usar o seguinte script do PowerShell para definir a Microsoft como um provedor de serviços de audioconferência para um grande número de usuários.

Quando o provedor é alterado de outro provedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, tarifas e números para ligações gratuitas) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar o seguinte script como um arquivo de script do PowerShell e execute-o usando qualquer um dos seus parâmetros de entrada.

**Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Exemplo 3:** Neste exemplo, você pode usar esse script para alterar o provedor de serviços de audioconferência de Intercall (ou outro provedor) para a **Microsoft** para um usuários número grande em sua organização.
    
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
  
## <a name="related-topics"></a>Tópicos relacionados
[Tente ou conferência de áudio no Office 365 de compra](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Configurar Skype para negócios Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

