---
title: Atribuir licenças do Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: 6917b3d47f29c10bea8b7695cfa69ace60609393
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671817"
---
# <a name="assign-skype-for-business-licenses"></a>Atribuir licenças do Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo fornece dicas de como atribuir licenças de recursos como Audioconferência, Sistema de Telefonia e Planos de Chamadas para seus usuários. Oferece também scripts para atribuir licenças em massa.

> [!IMPORTANT]
> Consulte Skype for Business licenciamento de complemento para obter informações sobre quais licenças você precisa comprar e como [comprá-las](skype-for-business-and-microsoft-teams-add-on-licensing.md) , dependendo do seu plano Microsoft 365 ou Office 365, para que os usuários obtenham Audioconferência, números de chamada gratuita e a capacidade de ligar para números de telefone fora da sua empresa.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças

O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas

- **Você está usando conectividade PSTN local para usuários híbridos?** Nesse caso, você só precisa atribuir uma **licença Sistema de Telefonia** serviço. Você NÃO **deve atribuir** um Plano de Chamada.

- **Latência** após a atribuição de licenças: devido à latência entre o Microsoft 365 ou o Office 365 e o Skype for Business Online, pode levar até 24 horas para um usuário receber um Plano de Chamada depois de atribuir uma licença. Se, após 24 horas, o usuário não receber um Plano de Chamada, entre em contato com o suporte para produtos comerciais [– Administração Ajuda](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças. Se você precisar comprar mais licenças do Plano de Chamadas, escolha **Comprar mais**.
    
- **Próximas** etapas: depois de atribuir licenças do Plano de Chamadas aos usuários, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números às pessoas em sua organização. Para obter instruções passo a passo, consulte [Configurar Planos de Chamadas](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Como atribuir uma licença Sistema de Telefonia e Plano de Chamada a um usuário

As etapas são as mesmas que atribuir uma licença Microsoft 365 ou Office 365 usuário. Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa

1. Instale o **Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW**. Não tem o módulo instalado? Consulte [o Microsoft Online Services Sign-In Assistente para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.

2. Instale o **Módulo do Windows Azure Active Directory**. Não tem o módulo instalado? Consulte [Gerenciar Azure AD usando Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) para obter instruções de download e sintaxe de cmdlet.

3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

   Este exemplo atribui uma licença **Enterprise E3** junto com um **Sistema de Telefonia** e uma licença de **Plano de Chamadas Domésticas**.

   O nome das licenças ou nomes de produtos no script são listados em texto em itálico (consulte Sistema de Telefonia e nomes de produtos ou **SKUs** do Plano de Chamada usados para scripts, após o exemplo).

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Sistema de Telefonia nomes de produtos ou SKUs de planos de chamada e de chamada usados para scripts

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Enterprise E5 (com Sistema de Telefonia)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Sistema de Telefonia  <br/> |MCOEV  <br/> |
|Plano de Chamadas Internacionais  <br/> |MCOPSTN2  <br/> |
|Plano de Chamadas Domésticas (3000 min US / 1200 min planos da UE)  <br/> |MCOPSTN1  <br/> |
|Plano de Chamadas Domésticas (plano de chamada de 120 minutos)  <br/> |MCOPSTN5  <br/> |
|Plano de Chamadas Domésticas (plano de chamada de 240 minutos)  <br/> |MCOPSTN6  <br/> |
|Créditos de Comunicação  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferência: Dicas scripts para atribuir licenças

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>O que você precisa saber antes de atribuir Audioconferência licenças

- Provedor de audioconferência de terceiros: se alguém já estiver configurado para usar um provedor de audioconferência de terceiros, quando você atribuir uma licença de **Audioconferência,** ele será alterado para usar a Microsoft como provedor de audioconferência. Você poderá mudá-lo de volta para o provedor terceirizado.

- Próximas etapas: depois de **atribuir Audioconferência** licenças, você precisará atribuir um provedor de audioconferência. Veja [Atribuir a Microsoft como provedor de audioconferência].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Como atribuir uma Audioconferência a um usuário

As etapas são as mesmas que atribuir uma licença Microsoft 365 ou Office 365 usuário. Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Como atribuir licenças Audioconferência em massa

1. Baixe e instale [o Microsoft Online Services Sign-In Assistente para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).

   Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

   [!OBSERVAçãO] O nome das licenças ou dos produtos no script são indicados em itálico. Consulte [Audioconferência nomes de produtos ou SKUs usados para scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para todos os nomes de produtos.

   Este exemplo atribui uma licença Enterprise E3 juntamente com uma licença Audioconferência cliente.

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Audioconferência nomes de produtos ou SKUs usados para scripts
<a name="sku"> </a>

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Audioconferência  <br/> |MCOMEETADV  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (sem Audioconferência)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (com Audioconferência)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Créditos de Comunicação

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>O que você precisa saber antes de atribuir licenças de Créditos de Comunicação

- **Enterprise E5**: mesmo que os usuários sejam atribuídos Enterprise licenças E5, ainda recomendamos que você atribua a eles **licenças de Créditos de** Comunicação.
    
- **Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários. Para obter instruções passo a passo, consulte [Configurar Planos de Chamadas](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Como atribuir uma licença de Créditos de Comunicação a um usuário

As etapas são as mesmas que atribuir uma licença Microsoft 365 ou Office 365 usuário. Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Como atribuir licenças de Créditos de Comunicação em massa

Dê uma olhada no script de exemplo para atribuir **Audioconferência** licenças. Atualize-o com as informações para atribuir **licenças de Créditos** de Comunicação.

## <a name="related-topics"></a>Tópicos relacionados
  
[Configurar Planos de Chamadas](/microsoftteams/set-up-calling-plans)
  
[Adicionar fundos e gerenciar Créditos de Comunicação](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
