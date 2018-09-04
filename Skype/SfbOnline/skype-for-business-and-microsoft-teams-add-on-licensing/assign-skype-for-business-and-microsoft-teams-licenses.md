---
title: Atribuir licenças do Skype for Business e do Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: 8b83286ef854518197d3b04c23f49bc00ceca2ba
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253442"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Atribuir licenças do Skype for Business e do Microsoft Teams

Este artigo fornece dicas de como atribuir licenças de recursos como Audioconferência, Sistema de Telefonia e Planos de Chamadas para seus usuários. Ele também oferece scripts para atribuir licenças em massa.

> [!IMPORTANT]
> Veja [Licenças complementares do Skype for Business e do Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisa comprar e **como comprá** -las, de acordo com o seu plano do Office 365, para que os usuários tenham acesso a Audioconferência, números para ligações gratuitas e possam ligar para números de telefone de fora da empresa.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças

O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas

- **Você usa conectividade PSTN local para usuários híbridos?** Nesse caso, precisará atribuir uma licença de **Sistema de Telefonia**. Você **NÃO** deve atribuir um Plano de Chamadas.

- **Latência após a atribuição de licenças**: Devido à latência entre o Office 365 e o Skype for Business Online, pode levar até 24 horas para um usuário ser habilitado para o Plano de Chamadas após a atribuição da licença. Se após 24 horas o Plano de Chamadas ainda não estiver habilitado para o usuário, [Entre em contato com o suporte para produtos empresariais - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensagens de erro**: Você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças. Se precisar comprar mais licenças de Planos de Chamadas, escolha **Comprar mais**.

- **Próximas etapas**: Após atribuir licenças do Plano de Chamadas aos seus usuários, você deverá obter os números de telefone para a sua organização e atribuí-los às pessoas. Para instruções passo a passo, veja [Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).

### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Como atribuir uma licença de Sistema de Telefonia e Plano de Chamadas a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa

1. Instale o **Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW**. Não tem o módulo instalado? Consulte o [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.

2. Instale o **Módulo do Active Directory do Azure para Windows**. Não tem o módulo instalado? Consulte [Gerenciar o AD do Azure usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para ver as instruções de download e a sintaxe do cmdlet.

3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças aos usuários:

  E** ste exemplo ** atribui uma licença Enterprise**  E3 junto com um Sistema de Telefonia e uma licença de Plano de Chamadas Domésticas.**** **

  Os nomes das licenças ou dos produtos no script são listados em itálico (veja **Nomes de produtos ou SKUs de Sistema de Telefonia e Plano de Chamada usados para scripts**, depois do exemplo).

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomes de produtos ou SKUs de Sistema de Telefonia e Plano de Chamada e usados para scripts

|**Nome de produto**|**Nome de parte SKU**|
|:-----|:-----|
|Enterprise E5 (com Sistema de Telefonia)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Sistema de Telefonia  <br/> |MCOEV  <br/> |
|Plano de Chamadas Internacionais  <br/> |MCOPSTN2  <br/> |
|Plano de Chamadas Domésticas  <br/> |MCOPSTN1  <br/> |
|Créditos de Comunicação  <br/> |MCOPSTNPP  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferência: Dicas e scripts para a atribuição de licenças

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>O que você precisa saber antes de atribuir licenças de Audioconferência

- **Outros provedores de serviços de Audioconferência**: Se alguém já tiver as configurações definidas para usar um outro provedor de serviços de audioconferência quando você atribuir uma licença de **Audioconferência**, elas serão alteradas para usar a Microsoft como provedor. Você pode mudá-las para usar novamente o provedor terceirizado.

- Próximas etapas: Depois de atribuir licenças de **Audioconferência**, você precisa atribuir um provedor de Audioconferência. Veja [Atribuir a Microsoft como provedor de audioconferência].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Como atribuir uma licença de Audioconferência a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Como atribuir licenças de Audioconferência em massa

1. Baixe e instale o [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Baixe e instale o **Módulo do Active Directory do Azure para Microsoft**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o AD do Azure usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças aos usuários:

    O nome das licenças ou dos produtos no script são indicados em itálico. Veja [Nomes de produtos ou SKUs de Audioconferência usados para scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para obter todos os nomes de produtos.

    Este exemplo atribui uma licença Enterprise E3 juntamente com uma licença de Audioconferência.

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomes de produtos ou SKUs de Audioconferência usados para scripts
<a name="sku"> </a>

|**Nome de produto**|**Nome de parte SKU**|
|:-----|:-----|
|Audioconferência  <br/> |MCOMEETADV  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (sem Audioconferência)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (com Audioconferência)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Créditos de Comunicação

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>O que você precisa saber antes de atribuir licenças Créditos de Comunicação

- **Clientes Enterprise E5**: Mesmo se os seus usuários já tiverem licenças Enterprise E5 atribuídas, recomendamos que você lhes atribua licenças de **Créditos de Comunicação**.

- **Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários. Para instruções passo a passo, veja [Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).

### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Como atribuir uma licença de Créditos de Comunicação a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Como atribuir licenças de Créditos de Comunicação em massa

Dê uma olhada na amostra de script para atribuição de licenças de **AudioConferência**. Atualize-o com as informações para atribuição de licenças de **Créditos de Comunicação**.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)

[Adicionar fundos e gerenciar Créditos de Comunicação](add-funds-and-manage-communications-credits.md)


