---
title: Atribuir Teams licenças de complemento a usuários
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Saiba como atribuir Teams licenças de complemento aos usuários para recursos como Audioconferência, Sistema de Telefonia e Planos de Chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0a83c30a4ea0fd4f907fd192b3f6dac455fc4d1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387589"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Atribuir Teams licenças de complemento a usuários

Licenças de complemento são licenças para recursos de Teams específicos, como Audioconferência, Sistema de Telefonia e Planos de Chamada. Este artigo descreve como atribuir licenças de complemento a usuários individuais e a grandes conjuntos de usuários em massa.

> [!NOTE]
> Consulte [Teams licenciamento de complemento](./microsoft-teams-add-on-licensing.md) para Teams recursos disponíveis com licenças de complemento. Você também encontrará informações sobre quais licenças você precisa comprar e como comprá-las (dependendo do seu plano), para que os usuários possam obter recursos como Audioconferência, números de chamada gratuita e a capacidade de chamar números de telefone fora da sua organização. Depois de decidir quais recursos você deseja para seus usuários, atribua as licenças a eles.

Você pode usar o Centro de administração do Microsoft 365 ou o PowerShell para atribuir licenças aos usuários em sua organização. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>O que você precisa saber antes de atribuir Sistema de Telefonia, Plano de Chamada e Créditos de Comunicação

Antes de começar, revise os seguintes requisitos:

- Se você estiver usando a conectividade PSTN (Rede Telefônica Pública Comutado) local para usuários híbridos, você só precisará atribuir uma licença Sistema de Telefonia local. Não atribua uma licença de Plano de Chamada.

- Devido à latência entre Microsoft 365 e Microsoft Teams, pode levar até 24 horas para que um usuário seja atribuído um Plano de Chamada depois de atribuir uma licença. Se o usuário não tiver um Plano de Chamada após 24 horas, contate o suporte para produtos comerciais [- ajuda do administrador](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Você receberá uma mensagem de erro se não tiver comprado o número correto de licenças. Se você precisar comprar mais licenças do Plano de Chamada, escolha a opção para comprar mais.

- Mesmo que seus usuários sejam atribuídos Enterprise licenças do E5, você ainda precisará atribuir [licenças de Créditos](../what-are-communications-credits.md) de Comunicação a eles se eles quiserem fazer ou receber chamadas da PSTN.

- Depois de atribuir licenças de Plano de Chamadas ou Créditos de Comunicação aos usuários, você precisará obter números de telefone para sua organização e atribuir esses números aos usuários. Para obter instruções passo a passo, consulte [Configurar Planos de Chamada](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Use o Centro de administração do Microsoft 365 para atribuir licenças a usuários individuais ou pequenos conjuntos de usuários por vez. Você atribui licenças na página **Licenças** (para até 20 usuários por vez) ou na página Usuários ativos  (para até 40 usuários por vez). O método escolhido depende se você deseja gerenciar licenças de produtos para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

Se você precisar atribuir licenças para um grande número de usuários, como centenas ou milhares de usuários, use o Powershell ou licenciamento baseado em [grupo no Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell para atribuir licenças a usuários em massa.  Para saber mais, confira [Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script de exemplo

Veja um exemplo de como usar um script para atribuir licenças aos usuários.

1. Instale a versão de 64 bits do [assistente Microsoft Online Services entrada para profissionais de TI RTW](/collaborate/connect-redirect?DownloadID=59185).
2. Instale o módulo Microsoft Azure Active Directory para Windows PowerShell:
    1. Abra um prompt de Windows PowerShell de comando com privilégios elevados (execute Windows PowerShell como administrador).
    2. Execute o seguinte comando:
        ```powershell
        Install-Module MSOnline
        ```
    3. Se você for solicitado a instalar o provedor NuGet, digite **Y** e pressione Enter.
    4. Se você for solicitado a instalar o módulo do PSGallery, digite **Y** e pressione Enter.
3. No prompt Windows PowerShell de comando, execute o seguinte script para atribuir licenças aos usuários, \<CompanyName:License> onde está o nome da sua organização e o identificador da licença que você deseja atribuir. Por exemplo, litwareinc:MCOMEETADV.

    O identificador é diferente do nome amigável da licença. Por exemplo, o identificador para Audioconferência é MCOMEETADV. Para saber mais, confira [Nomes de produto e identificadores SKU para licenciamento](#product-names-and-sku-identifiers-for-licensing).

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    Por exemplo, para atribuir Microsoft 365 Enterprise 1 e licenças de Audioconferência, use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para atribuir uma licença do Microsoft Business Voice (sem Plano de Chamadas), use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomes de produtos e identificadores SKU para licenciamento

Aqui está uma lista parcial de nomes de produtos e seus nomes de partes SKU correspondentes que você pode usar como referência ao usar o PowerShell para gerenciar licenças em Teams.

Para saber mais, confira [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), nomes de produtos e [identificadores](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) de plano de serviço para licenciamento e referência [de SKU do Education](../sku-reference-edu.md).

| Nome do produto| Nome de parte da SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (com Sistema de Telefonia) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sem Audioconferência) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (com Audioconferência) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Canadá)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Reino Unido) | BUSINESS_VOICE  |
| Microsoft Business Voice (Estados Unidos) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (sem Plano de Chamadas) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (sem Plano de Chamadas) para os Estados Unidos| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconferência | MCOMEETADV | 
| Pagamento de audioconferência por minuto (pagar conforme você vai)</br>*Exige que os Créditos de Comunicações sejam definidos e habilitados.* | MCOMEETACPEA |
| Sistema de Telefonia | MCOEV |
| Plano de Chamada Doméstica e Internacional | MCOPSTN2 |
| Plano de Chamada Doméstica (3000 minutos por usuário/mês para US/PR/CA, 1200 minutos por usuário/mês para países da UE) | MCOPSTN1 |
| Plano de Chamada Doméstica (120 minutos por usuário/mês para cada país) </br>*Este plano não está disponível nos Estados Unidos.* | MCOPSTN5 |
| Plano de Chamada Doméstica (240 minutos por usuário/mês para cada país) </br>*Este plano não está disponível nos Estados Unidos.* | MCOPSTN6 |
| Créditos de Comunicação | MCOPSTNPP |

## <a name="related-topics"></a>Tópicos relacionados

- [Licenciamento do complemento do Teams](./microsoft-teams-add-on-licensing.md)
- [Gerenciamento do acesso de usuários ao Teams](../user-access.md)
- [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU do Education](../sku-reference-edu.md)
