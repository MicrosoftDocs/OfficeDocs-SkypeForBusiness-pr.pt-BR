---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como gerenciar o acesso do usuário às equipes ao atribuir ou remover uma licença do teams para os usuários de sua organização.
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042268"
---
# <a name="manage-user-access-to-teams"></a>Gerenciamento do acesso de usuários ao Teams

Você gerencia o acesso às equipes no nível do usuário, atribuindo ou removendo uma licença de produto do Microsoft Teams. Cada usuário da sua organização deve ter uma licença do teams para poder usar o Microsoft Teams. Você pode atribuir uma licença do teams para novos usuários quando novas contas de usuário forem criadas ou para usuários com contas existentes.

Por padrão, quando um plano de licenciamento (por exemplo, o Microsoft 365 Enterprise E3 ou o Microsoft 365 Business Premium) é atribuído a um usuário, uma licença do Team é automaticamente atribuída e o usuário é habilitado para Teams. Você pode desabilitar ou habilitar o Microsoft Teams para um usuário removendo ou atribuindo uma licença a qualquer momento.

Você gerencia as licenças do teams no centro de administração do Microsoft 365 ou usando o PowerShell. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

> [!NOTE]
> Recomendamos que você habilite o Teams para todos os usuários para que as equipes possam ser formadas de forma orgânica para projetos e outras iniciativas dinâmicas. Mesmo que você esteja executando um piloto, talvez ainda seja útil manter o Microsoft Teams habilitado para todos os usuários, mas somente as comunicações são direcionadas para o grupo piloto de usuários.

## <a name="using-the-microsoft-365-admin-center"></a>Usar o centro de administração do Microsoft 365

Use o centro de administração do Microsoft 365 para gerenciar as licenças do teams para usuários individuais ou pequenos conjuntos de usuários por vez. Você pode gerenciar as licenças do teams na página **licenças** (para até 20 usuários no momento) ou página **usuários ativos** . O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Se você precisar gerenciar as licenças do Team para um grande número de usuários, como centenas ou milhares de usuários, [use o PowerShell](#using-powershell) ou o [Licenciamento baseado em grupo no Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Atribuir uma licença do teams

As etapas são diferentes dependendo se você usa a página **licenças** ou a página **usuários ativos** .  Para obter instruções passo a passo, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

|||
|---------|---------|
|![Captura de tela da licença do teams habilitada para um usuário](media/assign-teams-licenses-1.png)    | ![Captura de tela da licença do teams habilitada para um usuário](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Remover uma licença do teams

Quando você remove uma licença do teams de um usuário, o Microsoft Teams é desabilitado para esse usuário, e ele não vê mais as equipes no inicializador de aplicativos ou na Home Page. Para obter etapas detalhadas, consulte [cancelar a atribuição de licenças dos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Captura de tela da licença do teams desabilitada para um usuário](media/remove-teams-licenses-1.png)    | ![Captura de tela da licença do teams desabilitada para um usuário](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Usando o PowerShell

Use o PowerShell para gerenciar as licenças do teams para usuários em massa. Você pode habilitar e desabilitar o Microsoft Teams pelo PowerShell da mesma forma que faria para qualquer outra licença de plano de serviço. Você precisará dos identificadores para os planos de serviço do Teams, que são os seguintes:

- Microsoft Teams: TEAMS1
- Microsoft Teams para GCC: TEAMS_GOV
- Microsoft Teams para DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Atribuir licenças de equipe em massa

Para obter etapas detalhadas, consulte [atribuir licenças a contas de usuário com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Remover licenças do Team em massa

Para obter etapas detalhadas, confira [desabilitar o acesso a serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) e [desabilitar o acesso aos serviços ao atribuir licenças de usuário](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Exemplo 

Veja a seguir um exemplo de como usar os cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) e [set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) para desabilitar o Teams para usuários que têm um plano de licenciamento específico. Por exemplo, siga estas etapas para desabilitar primeiro o Teams para todos os usuários que tenham um plano de licenciamento específico. Em seguida, habilite o Teams para cada usuário individual que deve ter acesso ao Teams.

> [!IMPORTANT]
> O cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) habilitará todos os serviços que foram desabilitados anteriormente, a menos que explicitamente identificados em seu script personalizado. Por exemplo, se você quiser deixar o Exchange e o Sway desabilitado e também desabilitar o Teams, será necessário incluir isso no script ou o Exchange e o Sway serão habilitados para os usuários que você identificou.

Execute o comando a seguir para exibir todos os planos de licenciamento disponíveis em sua organização. Para saber mais, consulte [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).

      Get-MsolAccountSku

Execute os seguintes comandos, em \<que CompanyName: License> é o nome da sua organização e o identificador para o plano de licenciamento que você recuperou na etapa anterior. Por exemplo, ContosoSchool: ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

Execute o comando a seguir para desabilitar o Microsoft Teams para todos os usuários que têm uma licença ativa para o plano de licenciamento.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>Gerenciar equipes no nível da organização

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Licenças de Complementos do teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Atribuir licenças de Complementos do teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU do Education](sku-reference-edu.md)