---
title: "Atribuir a Microsoft como provedor de audioconferência"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# Atribuir a Microsoft como provedor de audioconferência

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](d935a90d-ea61-433d-a820-b400ed9c1f5d.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/d935a90d-ea61-433d-a820-b400ed9c1f5d). 
  
Um provedor de audioconferência fornece a  *ponte de conferência*  . A ponte de conferência fornece os números de discagem, pinos e IDs de conferência para reuniões que são criados. Você só precisa atribuir um provedor de audioconferência para as pessoas que estiverem indo para agendar ou conduzir reuniões de Teams da Microsoft ou Skype for Business.
  
Se você quiser ser capaz de ver a **que Microsoft** listada como provedor de áudio, você deve atribuir uma licença de ** Conferência de áudio** para o usuário.
  
> [!NOTE]
> Se você atribuir uma licença de **Conferência de áudio** para uma pessoa que não tem um provedor de audioconferência terceirizado, Microsoft é automaticamente atribuído como o provedor de audioconferência. Você pode[Atribuir um terceiro como provedor de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md) se necessário.
  
## Atribuir a Microsoft como provedor de audioconferência

### Usar o Centro de administração do Skype for Business

1. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
    > [!NOTE]
    > Quando o provedor é alterado de outro fornecedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, Chamada Tarifada e números de chamada gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
2. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **usuários** e selecione o usuário na lista de usuários disponíveis.
    
3. No Painel de Ações, clique em **Editar**.
    
4. Na página Propriedades do usuário, em **nome do provedor**, selecione **Microsoft** na lista suspensa.
    
    > [!NOTE]
    > Porque você estiver usando o Microsoft como provedor de audioconferência e há vários números de telefone, você pode usar a lista suspensa de **número de Chamada Tarifada padrão** para selecionar um número de áudio padrão para o usuário.
  
5. Clique em **Salvar**.
    
### Usando um script do Windows PowerShell para um pequeno número de usuários

Para economizar tempo ou automatizar o processo, você pode usar o seguinte script do PowerShell para definir a Microsoft como provedor de audioconferência para um pequeno número de usuários.
  
> [!NOTE]
> Quando o provedor é alterado de outro fornecedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, Chamada Tarifada e números de chamada gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar um ou mais dos seguintes scripts como um arquivo de script do PowerShell e depois executá-lo.
  
Para alterar o provedor para a Microsoft para uma pequena quantidade de usuários, você poderá usar o [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
> **Exemplo 1:** você pode executar este script fornecendo uma lista de usuários que devem ser atualizados.
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **Exemplo 2:** você pode executar este script fornecendo um arquivo .csv com o endereço de email (alias) de cada usuário que deseja atualizar.
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### Como usar um script do Windows PowerShell para uma grande quantidade de usuários

Para economizar tempo ou automatizar o processo, você pode usar o seguinte script do PowerShell para definir a Microsoft como provedor de audioconferência para um grande número de usuários.
  
> [!NOTE]
> Quando o provedor é alterado de outro fornecedor à **Microsoft**, as informações de conferência de áudio para o usuário (ID de conferência, Chamada Tarifada e números de chamada gratuita) serão substituídas. Você deve salvar essas informações antes de alterar o provedor. 
  
Você pode salvar um ou mais dos seguintes scripts como um arquivo de script do PowerShell e depois executá-lo.
  
> **Exemplo 1:** Neste exemplo, você pode usar esse script para alterar o provedor de audioconferência de Intercall (ou outro provedor) à **Microsoft** para um grande usuários número em sua organização.
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **Veja o script:**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## O que mais devo saber?

- Um usuário pode ser atribuído a apenas um provedor de audioconferência.
    
- Você pode alterar o provedor de conferência de áudio da Microsoft para um provedor de terceiros a qualquer momento. Para saber mais, consulte [Atribuir um terceiro como provedor de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- Em sua organização, você pode ter algumas pessoas que usam a Microsoft como seu provedor de audioconferência e outras pessoas que usam um provedor de terceiros. Mas isso é mais complicado para configurar e gerenciar.
    
## Tópicos Relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

