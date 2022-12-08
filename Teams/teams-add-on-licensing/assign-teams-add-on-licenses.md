---
title: Atribuir licenças de complemento do Teams aos usuários
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Saiba como atribuir licenças de complemento do Teams aos usuários para recursos como Conferência de Áudio, Sistema de Telefone e Planos de Chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 635280582796f2b373efc0c763fea0887bcd6e42
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307776"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Atribuir licenças de complemento do Teams aos usuários

Licenças de complemento são licenças para recursos específicos do Teams, como Conferência de Áudio, Sistema de Telefone e Planos de Chamada. Este artigo descreve como atribuir licenças de complemento a usuários individuais e grandes conjuntos de usuários em massa.

> [!NOTE]
> Consulte Licenciamento [de complemento do Teams](./microsoft-teams-add-on-licensing.md) para recursos do Teams que estão disponíveis com licenças de complemento. Você também encontrará informações sobre quais licenças você precisa comprar e como comprá-las, dependendo do seu plano. Depois de decidir quais recursos deseja para seus usuários, atribua as licenças a eles.

Você pode usar o Centro de administração do Microsoft 365 ou o PowerShell para atribuir licenças aos usuários em sua organização. Você deve ser um administrador global ou administrador de gerenciamento de usuário para gerenciar licenças.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>O que você precisa saber antes de atribuir licenças de Sistema telefônico, plano de chamada e créditos de comunicação

Antes de começar, examine os seguintes requisitos:

- Se você estiver usando a conectividade PSTN (Rede Telefônica Pública Comutada) local para usuários, você só precisará atribuir uma licença Telefonia do Teams Padrão. NÃO atribua uma licença de Plano de Chamada.

- Depois de atribuir um plano de chamada Microsoft a um usuário, ele pode levar até 24 horas até que ele veja o bloco de discagem em seu cliente do Teams. Se o bloco de discagem não for mostrado em 24 horas, verifique a [configuração do bloco de discagem](../dial-pad-configuration.md). Se necessário, você também pode [entrar em contato com o suporte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Você receberá uma mensagem de erro se não tiver comprado o número correto de licenças. Se você precisar comprar mais licenças do Plano de Chamada, escolha a opção para comprar mais.

- Mesmo que seus usuários sejam atribuídos licenças Enterprise E5, você ainda precisa conectá-los ao PSTN. Você tem [várias opções de conectividade PSTN](../pstn-connectivity.md), incluindo Planos de Chamada do Microsoft Teams, Roteamento Direto ou Operator Connect.

- Depois de atribuir licenças de Plano de Chamada ou Créditos de Comunicação aos usuários, você precisará obter números de telefone para sua organização e atribuir esses números aos usuários. Para obter instruções passo a passo, consulte [Configurar planos de chamada](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Use o Centro de administração do Microsoft 365 para atribuir licenças a usuários individuais ou pequenos conjuntos de usuários por vez.

Você atribui licenças na página **Licenças** (para até 20 usuários por vez) ou na página **Usuários ativos** (para até 40 usuários por vez). O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

Se você precisar atribuir licenças para um grande número de usuários, como centenas ou milhares de usuários, use o PowerShell ou [o licenciamento baseado em grupo no Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell para atribuir licenças aos usuários em massa. Para saber mais, confira [Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script de exemplo

Aqui está um exemplo de como usar um script para atribuir licenças aos usuários.

1. [Instale o módulo Microsoft Azure Active Directory para Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. No prompt de comando Windows PowerShell, execute o script a seguir para atribuir licenças aos usuários, onde `CompanyName:License` está o nome da sua organização e o identificador da licença que você deseja atribuir. Por exemplo, `litwareinc:MCOMEETADV`.

    O identificador é diferente do nome amigável da licença. Por exemplo, o identificador para Conferência de Áudio é `MCOMEETADV`. Para saber mais, confira [Nomes de produtos e identificadores de SKU para licenciamento](#product-names-and-sku-identifiers-for-licensing).

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

    Por exemplo, para atribuir licenças Microsoft 365 Enterprise E1 e Audio Conferencing, use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para atribuir uma licença do Teams Phone com Plano de Chamada, use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomes de produtos e identificadores de SKU para licenciamento

Aqui está uma lista parcial de nomes de produtos e seus nomes de partes de SKU correspondentes que você pode referenciar ao usar o PowerShell para gerenciar licenças no Teams.

Para saber mais, confira [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nomes de produto e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) e [referência de SKU do Education](../sku-reference-edu.md).

| Nome do produto| Nome de parte da SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (com sistema telefônico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sem Conferência de Áudio) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (com Conferência de Áudio) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Audioconferência | MCOMEETADV |
| Pagamento por minuto de conferência de áudio (pague conforme você for) Requer que os créditos de comunicação sejam configurados e habilitados.* | MCOMEETACPEA |
| Telefonia do Teams Padrão | MCOEV |
| Telefonia do Teams com Plano de Chamadas | MCOTEAMS_ESSENTIALS |
| Plano de Chamadas Internacionais | MCOPSTN2 |
| Plano de Chamada Doméstica (3.000 minutos por usuário/mês para EUA/PR/AC, 1200 minutos por usuário/mês para países da UE) | MCOPSTN1 |
| Plano de Chamada Doméstica (120 minutos por usuário/mês para cada país) </br>*Esse plano não está disponível no Estados Unidos.* | MCOPSTN5 |
| Plano de Chamada Doméstica (240 minutos por usuário/mês para cada país) </br>*Esse plano não está disponível no Estados Unidos.* | MCOPSTN6 |
| Créditos de Comunicação | MCOPSTNPP |
| Planos de chamada pay-as-you-go (países de zona 1) | MCOPSTN_PAYG_1 |
| Planos de chamada pay-as-you-go (países de zona-2) | MCOPSTN_PAYG_2 |
| Salas do Microsoft Teams Básico | Microsoft_Teams_Rooms_Basic |
| Salas do Microsoft Teams Básico sem Conferência de Áudio | Microsoft_Teams_Rooms_Basic_without_Audio_Conferencing |
| Salas Microsoft Teams Pro | Microsoft_Teams_Rooms_Pro |
| Salas Microsoft Teams Pro sem Conferência de Áudio | Microsoft_Teams_Rooms_Pro_without_Audio_Conferencing |
| Microsoft Teams Premium | Microsoft_Teams_Premium |

## <a name="related-content"></a>Conteúdo relacionado

- [Licenciamento do complemento do Teams](./microsoft-teams-add-on-licensing.md)
- [Gerenciamento do acesso de usuários ao Teams](../user-access.md)
- [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU da Educação](../sku-reference-edu.md)
