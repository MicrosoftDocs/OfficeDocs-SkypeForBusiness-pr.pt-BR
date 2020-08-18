---
title: Atribuir licenças de Complementos do teams aos usuários
author: LanaChin
ms.author: v-lanac
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
description: Saiba como atribuir licenças de Complementos do teams a usuários para recursos como videoconferência, sistema telefônico e planos de chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788735"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Atribuir licenças de Complementos do teams aos usuários

As licenças de complemento são licenças para recursos específicos do Teams, como videoconferência, sistema telefônico e planos de chamada. Este artigo descreve como atribuir licenças de Complementos a usuários individuais e a grandes conjuntos de usuários em massa.

> [!NOTE]
> Consulte [Licenciamento do complemento do teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) para recursos do teams que estão disponíveis com licenças complementares. Você também encontrará informações sobre quais licenças precisa comprar e como comprá-las (dependendo do seu plano), para que os usuários possam obter recursos como videoconferências, números de chamada gratuita e a capacidade de fazer chamadas para números de telefone fora da sua organização. Depois de decidir quais recursos você deseja para seus usuários, atribua as licenças a eles.

Você pode usar o centro de administração do Microsoft 365 ou o PowerShell para atribuir licenças aos usuários em sua organização. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>O que você precisa saber antes de atribuir licenças de um sistema telefônico, plano de chamada e créditos de comunicação

Antes de começar, revise o seguinte:

- Se você estiver usando a conectividade PSTN (rede telefônica pública comutada) para usuários híbridos, só precisará atribuir uma licença do sistema telefônico. Não atribua uma licença de plano de chamada.

- Devido à latência entre o Microsoft 365 e o Microsoft Teams, pode levar até 24 horas para que um usuário receba um plano de chamada após a atribuição de uma licença. Se o usuário não estiver atribuído a um plano de chamadas depois de 24 horas, [entre em contato com o suporte para produtos empresariais-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Você receberá uma mensagem de erro se não tiver comprado o número correto de licenças. Se precisar comprar mais licenças do plano de chamadas, escolha a opção de comprar mais.

- Mesmo que seus usuários tenham licenças Enterprise E5 atribuídas, você ainda precisa atribuir licenças de [créditos de comunicações](../what-are-communications-credits.md) a eles se quiser fazer ou receber chamadas da PSTN.

- Depois de atribuir licenças de plano de chamada ou de crédito de comunicação aos usuários, você precisará obter números de telefone para sua organização e atribuir esses números aos usuários. Para obter instruções passo a passo, consulte [configurar planos de chamada](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Usar o centro de administração do Microsoft 365

Use o centro de administração do Microsoft 365 para atribuir licenças para usuários individuais ou pequenos conjuntos de usuários de uma só vez. Você pode atribuir licenças na página **licenças** (para até 20 usuários de uma vez) ou para a página **usuários ativos** . O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Para obter instruções passo a passo, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Se você precisar atribuir licenças para um grande número de usuários, como centenas ou milhares de usuários, use o PowerShell ou o [Licenciamento baseado em grupo no Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Usando o PowerShell

Use o PowerShell para atribuir licenças a usuários em massa.  Para saber mais, confira [atribuir licenças a contas de usuário com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script de exemplo

Veja um exemplo de como usar um script para atribuir licenças aos seus usuários.

1. Instale a versão de 64 bits do [Assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
2. Instale o módulo do Microsoft Azure Active Directory para Windows PowerShell:
    1. Abra um prompt de comando do Windows PowerShell elevado (execute o Windows PowerShell como um administrador).
    2. Execute o seguinte comando:
        ```powershell
        Install-Module MSOnline
        ```
    3. Se você for solicitado a instalar o provedor de NuGet, digite **Y**e pressione Enter.
    4. Se for solicitado a instalar o módulo do PSGallery, digite **Y**e pressione Enter.
3. No prompt de comando do Windows PowerShell, execute o seguinte script para atribuir licenças aos seus usuários, onde \<CompanyName:License> é o nome da sua organização e o identificador da licença que você deseja atribuir. Por exemplo, litwareinc: MCOMEETADV.

    O identificador é diferente do nome amigável da licença. Por exemplo, o identificador do áudio videoconferência é MCOMEETADV. Para saber mais, consulte [nomes de produtos e identificadores de SKU para licenciamento](#product-names-and-sku-identifiers-for-licensing).

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

    Por exemplo, para atribuir licenças do Microsoft 365 Enterprise 1 e do áudio referencing, use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para atribuir uma licença do Microsoft Business Voice (sem plano de chamada), use a seguinte sintaxe no script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nomes de produtos e identificadores de SKU para licenciamento

Aqui está uma lista parcial de nomes de produto e seus nomes de partes de SKU correspondentes que você pode usar como referência ao usar o PowerShell para gerenciar licenças no Microsoft Teams.

Para saber mais, consulte [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nomes de produto e identificadores de plano de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)e [referência de SKU educacional](../sku-reference-edu.md).

| Nome do produto| Nome de parte da SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (com sistema telefônico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sem conferência de áudio) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (com conferência de áudio) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SP|
| Microsoft Business Voice (Canadá)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Reino Unido) | BUSINESS_VOICE  |
| Microsoft Business Voice (Estados Unidos) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (sem plano de chamada) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (sem plano de chamada) para os Estados Unidos| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconferência | MCOMEETADV | 
| Áudio conferência paga por minuto (pré-pago)</br>*Requer que os créditos de comunicações sejam configurados e habilitados.* | MCOMEETACPEA |
| Sistema Telefônico | MCOEV |
| Plano de chamadas domésticas e internacionais | MCOPSTN2 |
| Plano de chamadas domésticas (3000 minutos por usuário/mês para EUA/PR/CA, 1200 minutos por usuário/mês para países da UE) | MCOPSTN1 |
| Plano de chamadas domésticas (120 minutos por usuário/mês para cada país) </br>*Este plano não está disponível nos Estados Unidos.* | MCOPSTN5 |
| Plano de chamadas domésticas (240 minutos por usuário/mês para cada país) </br>*Este plano não está disponível nos Estados Unidos.* | MCOPSTN6 |
| Créditos de Comunicação | MCOPSTNPP |

## <a name="related-topics"></a>Tópicos relacionados

- [Licenciamento do complemento do Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Gerenciamento do acesso de usuários ao Teams](../user-access.md)
- [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU do Education](../sku-reference-edu.md)