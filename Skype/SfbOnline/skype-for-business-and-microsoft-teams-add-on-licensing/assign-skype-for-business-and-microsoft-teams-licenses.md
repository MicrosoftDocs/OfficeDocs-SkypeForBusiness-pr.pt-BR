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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204842"
---
# <a name="assign-skype-for-business-licenses"></a>Atribuir licenças do Skype for Business

This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.

> [!IMPORTANT]
> Confira o licenciamento de complementos do Skype for Business  para obter informações sobre quais licenças você precisa comprar e como [comprá-las](skype-for-business-and-microsoft-teams-add-on-licensing.md) , dependendo do plano do Microsoft 365 ou do Office 365, para que os usuários recebam Audioconferência, números de chamada gratuita e a capacidade de ligar para números de telefone fora da sua empresa.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças

O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas

- **Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.

- Latência após a atribuição de **licenças:** devido à latência entre o Microsoft 365 ou o Office 365 e o Skype for Business Online, pode levar até 24 horas para um usuário ter um Plano de Chamada atribuído após a atribuição de uma licença. Se, após 24 horas, o usuário não tiver um Plano de Chamada, entre em contato com o suporte para produtos comerciais – Ajuda [para Administradores.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- **Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.
    
- **Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Como atribuir uma licença do Sistema de Telefonia e do Plano de Chamada a um usuário

As etapas são as mesmas que atribuir uma licença do Microsoft 365 ou do Office 365. Consulte [Atribuir ou remover licenças do Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa

1. Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.

2. Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.

3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

   Este exemplo atribui uma licença **Enterprise E3** junto com um **Sistema de Telefonia** e uma licença de **Plano de Chamadas Domésticas**.

   O nome das licenças ou nomes de produtos no script são listados em texto em itálico (consulte os nomes de produtos ou **SKUs** do Plano de Chamada e Sistema de Chamadas usados para scripts, após o exemplo).

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomes de produtos ou SKUs do Sistema de Telefone e Planos de Chamada usados para scripts

|**Nome do produto**|**Nome de parte da SKU**|
|:-----|:-----|
|Enterprise E5 (com Sistema de Telefonia)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plano 2 Autônomo do Skype for Business Online  <br/> |MCOSTANDARD  <br/> |
|Sistema de Telefonia  <br/> |MCOEV  <br/> |
|Plano de Chamadas Internacionais  <br/> |MCOPSTN2  <br/> |
|Plano de Chamada Doméstica (3.000 min.US / 1200 min planos da UE)  <br/> |MCOPSTN1  <br/> |
|Plano de Chamada Doméstica (plano de chamada de 120 minutos)  <br/> |MCOPSTN5  <br/> |
|Plano de Chamada Doméstica (plano de chamada de 240 minutos)  <br/> |MCOPSTN6  <br/> |
|Créditos de Comunicação  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferência: dicas e scripts para a atribuição de licenças

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>O que você precisa saber antes de atribuir licenças de Audioconferência

- Provedor de **audioconferência** de terceiros: se alguém já estiver definido para usar um provedor de serviços de audioconferência de terceiros, quando você atribuir uma licença de **Audioconferência,** ele será alterado para usar a Microsoft como provedor de audioconferência. Você poderá mudá-lo de volta para o provedor terceirizado.

- Próximas etapas: depois de atribuir **licenças** de Audioconferência, você precisa atribuir um provedor de audioconferência. Veja [Atribuir a Microsoft como provedor de audioconferência].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Como atribuir uma licença de Audioconferência a um usuário

As etapas são as mesmas que atribuir uma licença do Microsoft 365 ou do Office 365. Consulte [Atribuir ou remover licenças do Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Como atribuir licenças de Audioconferência em massa

1. Baixe e instale o Assistente de Sign-In microsoft online para profissionais de TI [RTW.](https://go.microsoft.com/fwlink/?LinkId=625123)

2. Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

    [!OBSERVAçãO] O nome das licenças ou dos produtos no script são indicados em itálico. Veja [os nomes de produtos ou SKUs de](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) Audioconferência usados para scripts para todos os nomes de produtos.

    Este exemplo atribui uma licença Enterprise E3 juntamente com uma licença de Audioconferência.

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomes de produtos ou SKUs de audioconferência usados para scripts
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

- **Clientes Enterprise E5:** mesmo que seus usuários sejam atribuídos licenças Enterprise E5, ainda recomendamos que você atribua a eles licenças de **Créditos** de Comunicação.
    
- **Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários. Para obter instruções passo a passo, consulte [Configurar Planos de Chamada.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Como atribuir uma licença de Créditos de Comunicação a um usuário

As etapas são as mesmas que atribuir uma licença do Microsoft 365 ou do Office 365. Consulte [Atribuir ou remover licenças do Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Como atribuir licenças de Créditos de Comunicação em massa

Dê uma olhada no script de exemplo para atribuir licenças **de Audioconferência.** Atualize-o com as informações para atribuir **licenças de Créditos de** Comunicação.

## <a name="related-topics"></a>Tópicos relacionados
  
[Configurar Planos de Chamadas](/microsoftteams/set-up-calling-plans)
  
[Adicionar fundos e gerenciar Créditos de Comunicação](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
