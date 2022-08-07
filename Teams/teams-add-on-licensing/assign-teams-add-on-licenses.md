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
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Saiba como atribuir licenças de complemento do Teams aos usuários para recursos como Audioconferência, Sistema de Telefonia e Planos de Chamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b482781ee29094986c310158fe74f02662f790d
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268166"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Atribuir licenças de complemento do Teams aos usuários

Licenças de complemento são licenças para recursos específicos do Teams, como Audioconferência, Sistema de Telefonia e Planos de Chamadas. Este artigo descreve como atribuir licenças de complemento a usuários individuais e grandes conjuntos de usuários em massa.

> [!NOTE]
> Consulte [o licenciamento de complemento do Teams](./microsoft-teams-add-on-licensing.md) para recursos do Teams que estão disponíveis com licenças de complemento. Você também encontrará informações sobre quais licenças precisa comprar e como comprá-las, dependendo do seu plano. Depois de decidir quais recursos você deseja para seus usuários, atribua as licenças a eles.

Você pode usar o Centro de administração do Microsoft 365 ou o PowerShell para atribuir licenças aos usuários em sua organização. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>O que você precisa saber antes de atribuir licenças de Sistema de Telefonia, Plano de Chamadas e Créditos de Comunicação

Antes de começar, examine os seguintes requisitos:

- Se você estiver usando a conectividade PSTN (Rede Telefônica Pública Comunada) local para os usuários, só precisará atribuir uma licença Telefonia do Teams Padrão usuário. NÃO atribua uma licença de Plano de Chamada.

- Depois de atribuir um Plano de Chamadas da Microsoft a um usuário, pode levar até 24 horas para que ele veja o teclado de discagem no cliente do Teams. Se o teclado de discagem não for mostrado em 24 horas, verifique a configuração [do teclado de discagem](../dial-pad-configuration.md). Se necessário, você também pode entrar em [contato com o suporte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Você receberá uma mensagem de erro se não tiver comprado o número correto de licenças. Se você precisar comprar mais licenças do Plano de Chamadas, escolha a opção para comprar mais.

- Mesmo que os usuários sejam atribuídos a licenças Enterprise E5, você ainda precisará conectá-las ao PSTN. Você tem várias [opções de conectividade PSTN](../pstn-connectivity.md), incluindo Planos de Chamada do Microsoft Teams, Roteamento Direto ou Conexão de Operador.

- Depois de atribuir licenças de Plano de Chamada ou Créditos de Comunicação aos usuários, você precisará obter números de telefone para sua organização e, em seguida, atribuir esses números aos usuários. Para obter instruções passo a passo, consulte [Configurar Planos de Chamadas](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Use o Centro de administração do Microsoft 365 para atribuir licenças a usuários individuais ou pequenos conjuntos de usuários por vez.

Atribua licenças na página **Licenças** (para até 20 usuários por vez) ou na página Usuários ativos  (para até 40 usuários por vez). O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

Se você precisar atribuir licenças para um grande número de usuários, como centenas ou milhares de usuários, use o PowerShell ou o licenciamento baseado em grupo no [Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell para atribuir licenças a usuários em massa. Para saber mais, confira [Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script de exemplo

Aqui está um exemplo de como usar um script para atribuir licenças aos usuários.

1. [Instale o Microsoft Azure Active Directory módulo para Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. No prompt Windows PowerShell comando, execute o script a seguir para atribuir licenças aos usuários, `CompanyName:License` onde está o nome da sua organização e o identificador da licença que você deseja atribuir. Por exemplo, `litwareinc:MCOMEETADV`.

    O identificador é diferente do nome amigável da licença. Por exemplo, o identificador para Audioconferência é `MCOMEETADV`. Para saber mais, confira [Nomes de produtos e identificadores de SKU para licenciamento](#product-names-and-sku-identifiers-for-licensing).

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

    Por exemplo, para atribuir Microsoft 365 Enterprise E1 e licenças de Audioconferência, use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para atribuir um Telefone do Teams com licença de Plano de Chamada, use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomes de produtos e identificadores de SKU para licenciamento

Aqui está uma lista parcial de nomes de produtos e seus nomes de partes de SKU correspondentes que você pode referenciar ao usar o PowerShell para gerenciar licenças no Teams.

Para saber mais, confira [Exibir licenças](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell) e serviços com o PowerShell [, nomes](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) de produtos e identificadores de plano de serviço para licenciamento e referência de [SKU de Educação](../sku-reference-edu.md).

| Nome do produto| Nome de parte da SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (com Sistema de Telefonia) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sem Audioconferência) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (com Audioconferência) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | Spb|
| Audioconferência | MCOMEETADV |
| A audioconferência paga por minuto (paga conforme o uso) Exige que os Créditos de Comunicação sejam configurados e habilitados.* | MCOMEETACPEA |
| Telefonia do Teams Padrão | MCOEV |
| Telefonia do Teams com Plano de Chamadas | MCOTEAMS_ESSENTIALS |
| Plano de Chamadas Internacionais | MCOPSTN2 |
| Plano de Chamadas Domésticas (3000 minutos por usuário/mês para EUA/PR/AC, 1200 minutos por usuário/mês para países da UE) | MCOPSTN1 |
| Plano de Chamadas Domésticas (120 minutos por usuário/mês para cada país) </br>*Este plano não está disponível no Estados Unidos.* | MCOPSTN5 |
| Plano de Chamadas Domésticas (240 minutos por usuário/mês para cada país) </br>*Este plano não está disponível no Estados Unidos.* | MCOPSTN6 |
| Créditos de Comunicação | MCOPSTNPP |
| Planos de chamadas pagas conforme o uso (países da zona 1) | MCOPSTN_PAYG_1 |
| Planos de chamadas pagas conforme o uso (países da Zona 2) | MCOPSTN_PAYG_2 |

## <a name="related-content"></a>Conteúdo relacionado

- [Licenciamento do complemento do Teams](./microsoft-teams-add-on-licensing.md)
- [Gerenciamento do acesso de usuários ao Teams](../user-access.md)
- [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU de Educação](../sku-reference-edu.md)
