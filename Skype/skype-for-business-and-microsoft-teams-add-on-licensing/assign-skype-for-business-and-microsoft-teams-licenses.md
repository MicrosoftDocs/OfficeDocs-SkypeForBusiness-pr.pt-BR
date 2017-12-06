---
title: "Atribuir Skype para Business e Teams Microsoft licenças"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Atribuir Skype para Business e Teams Microsoft licenças

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/fd41934d-f2eb-4a1b-89d8-32cb37702b33). 
  
Este artigo fornece dicas sobre a atribuição de licenças aos usuários para recursos como conferências de áudio, o sistema telefônico e planos de chamada. Ele também fornece scripts para atribuição de licenças em massa.
  
 **Importante**: consulte[Skype para Business e Teams Microsoft complemento licenciamento](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre as licenças que você precisa comprar e **como comprar** -dependendo do plano do Office 365 - para que os usuários obtenham conferência de áudio, números de chamada gratuita, e a capacidade de ligar para números de telefone fora de sua empresa.
  
## Telefone de sistema e planos de chamada: dicas e scripts para atribuição de licenças

### O que você precisa saber antes de atribuir licenças de chamar planejar, sistema telefônico e conferência de áudio

- **IMPORTANTE**: para ver a opção **Voz** na navegação à esquerda no Centro de Administração do Skype for Business, você deve comprar pelo menos uma **licença Enterprise E5**, uma licença de complemento de **Sistema Telefônico** ou uma licença de complemento de **Audioconferência**.
    
- **Usando a conectividade de PSTN locais para usuários de híbrido?** Nesse caso, você só precisa atribuir uma licença de **Sistema telefônico**. Você deve **não** atribua um plano de chamada.
    
- **Latência após a atribuição de licenças**: devido a latência entre o Office 365 e Skype for Business Online, possivelmente pode levar até 24 horas para um usuário a ser atribuído um plano de chamar depois que você atribui uma licença. Caso após 24 horas, o usuário não é atribuído um plano de chamada, entre[Contatar o suporte do Office 365 para empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Mensagens de erro**: você receberá uma mensagem de erro se você ainda não comprou o número correto de licenças. Se você precisa adquirir mais licenças chamando plano, escolha **comprar mais**.
    
- **Próximas etapas**: depois de atribuir chamando planejar licenças aos usuários, você precisará obter seus números de telefone para sua organização e atribuir esses números para as pessoas em sua organização. Para obter instruções passo a passo, consulte[Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Como atribuir uma licença de sistema telefônico e chamar planejar a um usuário

As etapas são a mesma que atribuir uma licença de Office 365. Consulte [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Como atribuir licenças sistema telefônico e chamar plano em massa

1. Instale o **Assistente Microsoft Online Services entrar para profissionais de TI RTW**. Você não tem o módulo instalado? Consulte[Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.
    
2. Instalar o **módulo do Active Directory do Azure Windows.** Você não tem o módulo instalado? Consulte[Gerenciar Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe de cmdlet.
    
3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:
    
    Este exemplo atribui uma **licença Enterprise E3** juntamente com um **Sistema telefônico** e uma licença **Domésticas chamando planejar**.
    
    O nome das licenças ou nomes de produto no script são listados em texto itálico (consulte o **sistema telefônico e chamar planejar nomes de produtos ou SKUs usados para execução de scripts**, após o exemplo).
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice.
Connect-MSOLService

#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users.
$users = Get-Content $OFD.filename

#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### Nomes de produto do sistema telefônico e chamar planos ou SKUs usados para execução de scripts

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Enterprise E5 (com o sistema de telefone)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefônico  <br/> |MCOEV  <br/> |
|Plano de Chamadas Internacionais  <br/> |MCOPSTN2  <br/> |
|Plano de Chamadas Domésticas  <br/> |MCOPSTN1  <br/> |
|Créditos de comunicações  <br/> |MCOPSTNPP  <br/> |
   
## Audioconferência: Dicas e scripts para atribuição de licenças

### O que você precisa saber antes de atribuir licenças de conferência de áudio

- **Provedor de audioconferência terceirizado**: se alguém já está configurado para usar um provedor de audioconferência terceirizado, quando você atribui uma licença de **Conferência de áudio**, eles serão alterados para usar a Microsoft como a conferência de áudio provedor. Você pode alterá-los novamente para o provedor de terceiros.
    
- Próximos passos: depois de atribuir licenças de **Conferência de áudio**, você precisa atribuir um provedor de audioconferência. Siga um destes procedimentos:
    
  - [Atribuir a Microsoft como provedor de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Ou, [Atribuir um terceiro como provedor de audioconferência](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### Como atribuir uma licença de conferência de áudio a um usuário

As etapas são a mesma que atribuir uma licença de Office 365. Consulte [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Como atribuir licenças de conferência de áudio em massa

1. Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Baixe e instale o **módulo do Windows Azure Active Directory.** Consulte[Gerenciar Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe de cmdlet.
    
    Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:
    
    O nome das licenças ou nomes de produto no script são listados em texto itálico. Consulte [Nomes de produto de conferência áudio ou SKUs usados para execução de scripts](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku) para todos os nomes de produto.
    
    Este exemplo atribui uma licença Enterprise E3 junto com uma licença de conferência de áudio.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService

#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    } 

  ```

### Nomes de produto de conferência áudio ou SKUs usados para execução de scripts
<a name="sku"> </a>

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Audioconferência  <br/> |MCOMEETADV  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> | STANDARDPACK <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (sem audioconferência)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (com conferência de áudio)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## Créditos de comunicações

### O que você precisa saber antes de atribuir licenças de créditos de comunicações

- **Clientes de Enterprise E5**: mesmo se seus usuários são atribuídos Enterprise E5 licenças, ainda recomendamos que você atribuí-los licenças de **Créditos de comunicações**.
    
- **Próximas etapas**: depois de atribuir essas licenças, você precisará obter seus números de telefone para sua organização e atribuir esses números para as pessoas em sua organização. Para obter instruções passo a passo, consulte[Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Como atribuir uma licença de créditos de comunicações a um usuário

As etapas são a mesma que atribuir uma licença de Office 365. Consulte [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Como atribuir licenças de créditos de comunicações em massa

Dê uma olhada o script de exemplo para atribuição de licenças de **Conferência de áudio**. Atualize-o com as informações de atribuição de licenças de **Créditos de comunicações**.
  
## Artigos relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Adicionar fundos e gerenciar créditos de comunicações](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

