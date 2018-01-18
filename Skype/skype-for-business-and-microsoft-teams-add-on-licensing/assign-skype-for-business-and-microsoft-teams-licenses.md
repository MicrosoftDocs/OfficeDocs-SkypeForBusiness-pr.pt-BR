---
title: "Atribuir Skype para licenças de negócios e Teams da Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Saiba como atribuir Skype para licenças de negócios para o sistema telefônico, conferência de áudio, chamar planos e créditos de comunicações. "
ms.openlocfilehash: d60d637d3b904b98ee8600647c57062927fe9afc
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Atribuir Skype para licenças de negócios e Teams da Microsoft

Este artigo fornece dicas sobre como atribuir licenças aos usuários recursos como conferência de áudio, sistema telefônico e planos de chamada. Ele também fornece scripts para atribuir licenças em massa.
  
 **Importante**: consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre as licenças que você precisará comprar e **como comprá** -los - dependendo do seu plano do Office 365 - para que os usuários obtenham audioconferências, números para ligações gratuitas, e a capacidade de chamar números de telefone fora da sua empresa.
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Telefone de sistema e chamar planos: dicas e scripts para atribuir licenças

O que você precisa saber antes de atribuir a conferência de áudio, o sistema telefônico e chamar planejar licenças

- **Usando locais conectividade PSTN para usuários híbrida?** Nesse caso, você precisará atribuir uma licença de **Sistema telefônico** . Você deve **não** atribuir um plano de chamada.
    
- **Latência após a atribuição de licenças**: devido a latência entre o Office 365 e Skype para Business Online, possivelmente pode demorar até 24 horas para um usuário a ser atribuído um plano de chamar depois que você atribuir uma licença. Se após 24 horas, o usuário não é atribuído um plano de chamar, entre [o suporte de contato para produtos de negócios - ajuda de Admin](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Mensagens de erro**: você receberá uma mensagem de erro se você ainda não comprou o número correto de licenças. Se você precisar comprar mais licenças chamar planejar, escolha **comprar mais**.
    
- **Próximas etapas**: depois de atribuir licenças chamar planejar para seus usuários, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números para as pessoas na sua organização. Para obter instruções detalhadas, consulte [Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Como atribuir uma licença de sistema telefônico e planejar a chamada para um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Como atribuir licenças do sistema telefônico e chamar planejar em massa

1. Instale o **Assistente Microsoft Online Services entrar para profissionais de TI RTW**. Você não tem o módulo instalado? Consulte [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.
    
2. Instalar o **módulo do Windows Azure Active Directory.** Você não tem o módulo instalado? Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.
    
3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:
    
  Este exemplo atribui uma **licença Enterprise E3** junto com um **Sistema telefônico** e uma licença **Domésticas chamar planejar** .
    
  O nome das licenças ou nomes de produto no script estão listados no texto itálico (consulte o **sistema telefônico e chamar planejar nomes de produtos ou SKUs usados para execução de scripts**, após o exemplo).
    
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
  #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
  International Calling.
  for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 
  ```
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomes de produto do sistema telefônico e planos de chamar ou SKUs usados para execução de scripts

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Enterprise E5 (com o sistema telefônico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefônico  <br/> |MCOEV  <br/> |
|Plano de chamadas internacionais  <br/> |MCOPSTN2  <br/> |
|Plano de Chamadas Domésticas  <br/> |MCOPSTN1  <br/> |
|Créditos de Comunicação  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Conferência de áudio: Dicas e scripts para atribuir licenças

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>O que você precisa saber antes de atribuir licenças de conferência de áudio

- **Provedor de serviços de audioconferência de terceiros**: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, quando você atribuir uma licença de **Serviços de audioconferência** , elas serão alteradas para usar o Microsoft como os serviços de audioconferência provedor. Você pode alterá-los novamente para o provedor de terceiros.
    
- Próximas etapas: depois de atribuir licenças de **Serviços de audioconferência** , você precisa atribuir a um provedor de serviços de audioconferência. Siga um destes procedimentos:
    
  - [Atribuir a Microsoft como um provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Ou, [atribua um terceiro como um provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Como atribuir uma licença de conferência de áudio a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Como atribuir licenças de conferência de áudio em massa

1. Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:
    
    O nome das licenças ou nomes de produto no script estão listados no texto itálico. Consulte [nomes de produto de conferência de áudio ou SKUs usados para o script](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) de todos os nomes dos produtos.
    
    Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomes de produto de conferência áudio ou SKUs usados para execução de scripts
<a name="sku"> </a>

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Audioconferência  <br/> |MCOMEETADV  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|E5 da empresa (sem serviços de audioconferência)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (com serviços de audioconferência)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## <a name="communications-credits"></a>Créditos de Comunicação

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>O que você precisa saber antes de atribuir licenças créditos de comunicações

- **Os clientes corporativos E5**: mesmo se os usuários recebem licenças E5 da empresa, ainda recomendamos que você atribuir-lhes **Communications créditos** licenças.
    
- **Próximas etapas**: depois de atribuir essas licenças, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números para as pessoas na sua organização. Para obter instruções detalhadas, consulte [Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Como atribuir uma licença créditos de comunicação a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Como atribuir licenças créditos de comunicações em massa

Dê uma olhada o script de exemplo para atribuir licenças de **Conferência de áudio** . Atualizá-lo com as informações para atribuir licenças **Créditos de comunicações** .
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Adicione fundos e gerencie créditos de comunicações](add-funds-and-manage-communications-credits.md)
  