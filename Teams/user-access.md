---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como gerenciar o acesso do usuário ao Teams atribuindo ou removendo uma licença Teams aos usuários em sua organização.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4a83d0da32c11406f76b9bc355ceb666d4ea308
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728060"
---
# <a name="manage-user-access-to-teams"></a>Gerenciamento do acesso de usuários ao Teams

Você gerencia o acesso Teams no nível do usuário atribuindo ou removendo uma licença Microsoft Teams produto. Com exceção de Teams reuniões anônimas, cada usuário em sua organização deve ter uma licença Teams para poder usar Teams. Você pode atribuir uma Teams para novos usuários quando novas contas de usuário são criadas ou para usuários com contas existentes.

Por padrão, quando um plano de licenciamento (por exemplo, Microsoft 365 Enterprise E3 ou Microsoft 365 Business Premium) é atribuído a um usuário, uma licença Teams é atribuída automaticamente e o usuário está habilitado para Teams. Você pode desabilitar ou habilitar Teams para um usuário removendo ou atribuindo uma licença a qualquer momento.

Use políticas de mensagens, gerenciadas <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Centro</a>de Administração, para controlar quais recursos de mensagens de chat e canal estão disponíveis para os usuários no Teams. Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para pessoas em sua organização. Para saber mais, leia [Gerenciar políticas de mensagens em Teams](messaging-policies-in-teams.md).
Você gerencia Teams licenças no Centro de administração do Microsoft 365 ou usando o PowerShell. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

> [!NOTE]
> Recomendamos que você habilita Teams para todos os usuários para que as equipes possam ser formadas organicamente para projetos e outras iniciativas dinâmicas. Mesmo que você esteja executando um piloto, ainda pode ser útil manter a Teams habilitada para todos os usuários, mas apenas direcionar as comunicações para o grupo piloto de usuários.

## <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Teams licenças no nível do usuário são gerenciadas diretamente por meio das interfaces Centro de administração do Microsoft 365 de gerenciamento de usuários. Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes. 

> [!IMPORTANT]
> O administrador deve ter privilégios de Administrador Global ou Administrador de Gerenciamento de Usuários para gerenciar Microsoft Teams licenças.
Use a Centro de administração do Microsoft 365 para gerenciar Teams licenças para usuários individuais ou pequenos conjuntos de usuários por vez. Você pode gerenciar Teams licenças na página **Licenças** (para até 20 usuários no momento) ou **página Usuários ativos.** O método escolhido depende se você deseja gerenciar licenças de produtos para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Se você precisar gerenciar Teams licenças para um grande número de usuários, como centenas ou milhares de usuários, use o [PowerShell](#using-powershell) ou o licenciamento baseado em grupo no [Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Atribuir uma Teams de usuário

As etapas são diferentes, dependendo de você usar a página **Licenças** ou **a página Usuários ativos.**  Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Captura de tela 1 de Teams licença habilitada para um usuário.](media/assign-teams-licenses-1.png)    | ![Captura de tela 2 de Teams habilitada para um usuário](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Remover uma Teams de Teams

> [!IMPORTANT]
> Leva cerca de 24 horas para desabilitar uma Teams SKU para fazer efeito.

Quando você remove uma Teams de um usuário, o Teams está desabilitado para esse usuário, e ele não verá mais Teams no launcher de aplicativos ou na homepage. Para etapas detalhadas, consulte [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Captura de tela 1 da licença Teams desabilitada para um usuário.](media/remove-teams-licenses-1.png)    | ![Captura de tela 2 da licença Teams desabilitada para um usuário](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell para gerenciar Teams para usuários em massa. Você habilita e desabilita Teams através do PowerShell da mesma forma que faria para qualquer outra licença de plano de serviço. Você precisará dos identificadores para os planos de serviço para Teams, que são os seguinte:

- Microsoft Teams: TEAMS1
- Microsoft Teams para GCC: TEAMS_GOV
- Microsoft Teams para DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Atribuir Teams licenças em massa

Para etapas detalhadas, consulte [Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Remover Teams licenças em massa

Para etapas detalhadas, consulte [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and Disable access to services while [assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Exemplo 

Veja a seguir um exemplo de como usar os [cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) para desabilitar o Teams para usuários que têm um plano de licenciamento específico. Por exemplo, siga estas etapas para primeiro desabilitar Teams para todos os usuários que têm um plano de licenciamento específico. Em seguida, Teams para cada usuário individual que deve ter acesso a Teams.

> [!IMPORTANT]
> O cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) habilita todos os serviços que foram desabilitados anteriormente, a menos que explicitamente identificado em seu script personalizado. Por exemplo, se você quiser deixar o Exchange e o Sway desabilitados enquanto também desabilita o Teams, você precisará incluir isso no script ou o Exchange e o Sway estarão habilitados para os usuários identificados.

Execute o seguinte comando para exibir todos os planos de licenciamento disponíveis em sua organização. Para saber mais, confira [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Execute os comandos a seguir, onde está o nome da sua organização e o identificador do plano de licenciamento que \<CompanyName:License> você recuperou na etapa anterior. Por exemplo, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Execute o seguinte comando para desabilitar Teams para todos os usuários que têm uma licença ativa para o plano de licenciamento.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Tópicos relacionados

- [Teams licenças de complemento](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Atribuir Teams licenças de complemento](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência de SKU do Education](sku-reference-edu.md)
