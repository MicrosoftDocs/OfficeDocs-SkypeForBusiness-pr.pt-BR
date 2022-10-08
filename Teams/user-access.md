---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
manager: SerdarSoysal
author: DaniEASmith
ms.author: danismith
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como gerenciar o acesso do usuário ao Teams atribuindo ou removendo uma licença do Teams aos usuários em sua organização.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 489378c365b691184c07d42292fbb4b0d98b663e
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377169"
---
# <a name="manage-user-access-to-teams"></a>Gerenciamento do acesso de usuários ao Teams

Você gerencia o acesso ao Teams no nível do usuário atribuindo ou removendo uma licença de produto do Microsoft Teams. Exceto para ingressar em reuniões do Teams anonimamente, cada usuário em sua organização deve ter uma licença do Teams antes de poder usar o Teams. Você pode atribuir uma licença do Teams para novos usuários quando novas contas de usuário são criadas ou para usuários com contas existentes.

Por padrão, quando um plano de licenciamento (por exemplo, Microsoft 365 Enterprise E3 ou Microsoft 365 Business Premium) é atribuído a um usuário, uma licença do Teams é atribuída automaticamente e o usuário está habilitado para o Teams. Você pode desabilitar ou habilitar o Teams para um usuário removendo ou atribuindo uma licença a qualquer momento.

Use políticas de mensagens, gerenciadas pelo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Administração Center</a>, para controlar quais recursos de mensagens de chat e canal estão disponíveis para os usuários no Teams. Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para pessoas em sua organização. Para saber mais, leia [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md).
Você gerencia licenças do Teams no Centro de administração do Microsoft 365 ou usando o PowerShell. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

> [!NOTE]
> Recomendamos que você habilite o Teams para todos os usuários para que as equipes possam ser formadas organicamente para projetos e outras iniciativas dinâmicas. Mesmo que você esteja executando um piloto, ainda pode ser útil manter o Teams habilitado para todos os usuários, mas direcionar apenas as comunicações para o grupo piloto de usuários.

## <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

As licenças de nível de usuário do Teams são gerenciadas diretamente por meio das interfaces Centro de administração do Microsoft 365 de gerenciamento de usuários. Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.

> [!IMPORTANT]
> O administrador deve ter privilégios de Administrador Global ou Administrador de Gerenciamento de Usuários para gerenciar licenças do Microsoft Teams.
Use o Centro de administração do Microsoft 365 para gerenciar licenças do Teams para usuários individuais ou pequenos conjuntos de usuários por vez. Você pode gerenciar licenças do Teams na página **Licenças** (para até 20 usuários ao mesmo tempo) ou **na página Usuários ativos** . O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Se você precisar gerenciar licenças do Teams para um grande número de usuários, como centenas ou milhares de usuários, [use o PowerShell](#using-powershell) ou o licenciamento baseado em grupo no [Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Atribuir uma licença do Teams

As etapas são diferentes dependendo se você usa a página **Licenças** ou **a página Usuários ativos** .  Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Captura de tela 1 da licença do Teams habilitada para um usuário.](media/assign-teams-licenses-1.png)    | ![Captura de tela 2 da licença do Teams habilitada para um usuário](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Remover uma licença do Teams

> [!IMPORTANT]
> Leva cerca de 24 horas para que a desabilitação de um SKU do Teams entre em vigor.

Quando você remove uma licença do Teams de um usuário, o Teams é desabilitado para esse usuário e ele não verá mais o Teams no inicializador de aplicativos ou na home page. Para obter etapas detalhadas, [consulte Cancelar a atribuição de licenças dos usuários](/microsoft-365/admin/manage/remove-licenses-from-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Captura de tela 1 da licença do Teams desabilitada para um usuário.](media/remove-teams-licenses-1.png)    | ![Captura de tela 2 da licença do Teams desabilitada para um usuário](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell para gerenciar licenças do Teams para usuários em massa. Você habilita e desabilita o Teams por meio do PowerShell da mesma maneira que faria para qualquer outra licença de plano de serviço. Você precisará dos identificadores para os planos de serviço do Teams, que são os seguintes:

- Microsoft Teams: TEAMS1
- Microsoft Teams para GCC: TEAMS_GOV
- Microsoft Teams para DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Atribuir licenças do Teams em massa

Para obter etapas detalhadas, [consulte Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Remover licenças do Teams em massa

Para obter etapas detalhadas, consulte [Desabilitar o acesso aos serviços com o PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) e desabilitar o acesso aos [serviços ao atribuir licenças de usuário](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Exemplo 

Veja a seguir um exemplo de como usar os cmdlets [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) para desabilitar o Teams para usuários que têm um plano de licenciamento específico. Por exemplo, siga estas etapas para primeiro desabilitar o Teams para todos os usuários que têm um plano de licenciamento específico. Em seguida, habilite o Teams para cada usuário individual que deve ter acesso ao Teams.

> [!IMPORTANT]
> O cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) habilitará todos os serviços que foram desabilitados anteriormente, a menos que explicitamente identificados no script personalizado. Por exemplo, se você quiser deixar o Exchange e o Sway desabilitados enquanto também desabilita o Teams, você precisará incluir isso no script ou o Exchange e o Sway serão habilitados para os usuários identificados.

Execute o comando a seguir para exibir todos os planos de licenciamento disponíveis em sua organização. Para saber mais, confira [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Execute os comandos a seguir, onde \<CompanyName:License> está o nome da sua organização e o identificador do plano de licenciamento que você recuperou na etapa anterior. Por exemplo, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Execute o comando a seguir para desabilitar o Teams para todos os usuários que têm uma licença ativa para o plano de licenciamento.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Tópicos relacionados

- [Licenças de complemento do Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Atribuir licenças de complemento do Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU de Educação](sku-reference-edu.md)
