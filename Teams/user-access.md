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
description: Saiba como gerenciar o acesso do usuário ao Teams atribuindo ou removendo uma licença do Teams aos usuários em sua organização.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d49b27de8fe6c6d13ef6ac626764b13e1fe36a0
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871010"
---
# <a name="manage-user-access-to-teams"></a>Gerenciamento do acesso de usuários ao Teams

Você gerencia o acesso ao Teams no nível do usuário atribuindo ou removendo uma licença de produto do Microsoft Teams. Exceto para ingressar em reuniões do Teams anonimamente, cada usuário em sua organização deve ter uma licença do Teams antes de poder usar o Teams. Você pode atribuir uma licença do Teams para novos usuários quando novas contas de usuário são criadas ou para usuários com contas existentes.

Por padrão, quando um plano de licenciamento (por exemplo, Microsoft 365 Enterprise E3 ou Microsoft 365 Business Premium) é atribuído a um usuário, uma licença do Teams é atribuída automaticamente e o usuário é habilitado para o Teams. Você pode desabilitar ou habilitar o Teams para um usuário removendo ou atribuindo uma licença a qualquer momento.

Use políticas de mensagens, gerenciadas a partir do Centro de Administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams,</a>para controlar quais recursos de mensagens de chat e canal estão disponíveis para os usuários no Teams. Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para pessoas em sua organização. Para saber mais, leia [Gerenciar políticas de mensagens no Teams.](messaging-policies-in-teams.md)
Você gerencia licenças do Teams no centro de administração do Microsoft 365 ou usando o PowerShell. Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.

> [!NOTE]
> Recomendamos que você habilita o Teams para todos os usuários para que as equipes possam ser formadas de forma orgânica para projetos e outras iniciativas dinâmicas. Mesmo que você esteja executando um piloto, ainda pode ser útil manter o Teams habilitado para todos os usuários, mas apenas direcionar as comunicações para o grupo piloto de usuários.

## <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

As licenças de nível de usuário do Teams são gerenciadas diretamente por meio das interfaces de gerenciamento de usuários do Centro de administração do Microsoft 365. Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes. 

> [!IMPORTANT]
> O administrador deve ter privilégios de Administrador Global ou Administrador de Gerenciamento de Usuário para gerenciar licenças do Microsoft Teams.
Use o Centro de administração do Microsoft 365 para gerenciar licenças do Teams para usuários individuais ou pequenos conjuntos de usuários por vez. Você pode gerenciar licenças do Teams na página **Licenças** (para até 20 usuários por vez) ou **na página Usuários ativos.** O método escolhido depende se você deseja gerenciar licenças de produtos para usuários específicos ou gerenciar licenças de usuário para produtos específicos.

Se você precisar gerenciar licenças do Teams para um grande número de usuários, como centenas ou milhares de usuários, use o [PowerShell](#using-powershell) ou licenciamento baseado em grupo no [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Atribuir uma licença do Teams

As etapas são diferentes, dependendo se você usa a página **Licenças** ou **a página Usuários Ativos.**  Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

|||
|---------|---------|
|![Captura de tela da licença do Teams habilitada para um usuário](media/assign-teams-licenses-1.png)    | ![Captura de tela da licença do Teams habilitada para um usuário](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Remover uma licença do Teams

Quando você remove uma licença do Teams de um usuário, o Teams é desabilitado para esse usuário e ele não verá mais o Teams no início ou na página inicial do aplicativo. Para etapas detalhadas, consulte [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Captura de tela da licença do Teams desabilitada para um usuário](media/remove-teams-licenses-1.png)    | ![Captura de tela da licença do Teams desabilitada para um usuário](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell para gerenciar licenças do Teams para usuários em massa. Você habilita e desabilita o Teams por meio do PowerShell da mesma maneira que faria para qualquer outra licença de plano de serviço. Você precisará dos identificadores dos planos de serviço do Teams, que são os seguinte:

- Microsoft Teams: TEAMS1
- Microsoft Teams para GCC: TEAMS_GOV
- Microsoft Teams para DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Atribuir licenças do Teams em massa

Para etapas detalhadas, consulte [Atribuir licenças a contas de usuário com o PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Remover licenças do Teams em massa

Para etapas detalhadas, consulte [Desabilitar o acesso](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) aos serviços com o PowerShell e desabilitar o acesso aos serviços ao atribuir [licenças de usuário.](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Exemplo 

Veja a seguir um exemplo de como usar os cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) para desabilitar o Teams para usuários que têm um plano de licenciamento específico. Por exemplo, siga estas etapas para primeiro desabilitar o Teams para todos os usuários que têm um plano de licenciamento específico. Em seguida, habilita o Teams para cada usuário individual que deve ter acesso ao Teams.

> [!IMPORTANT]
> O cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) habilita todos os serviços que foram desabilitados anteriormente, a menos que seja explicitamente identificado em seu script personalizado. Por exemplo, se você quiser deixar o Exchange e o Sway desabilitados ao desabilitar o Teams, você precisará incluir isso no script ou o Exchange e o Sway serão habilitados para os usuários identificados.

Execute o seguinte comando para exibir todos os planos de licenciamento disponíveis em sua organização. Para saber mais, consulte [Exibir licenças e serviços com o PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Execute os seguintes comandos, onde está o nome da sua organização e o identificador do plano de licenciamento que \<CompanyName:License> você recuperou na etapa anterior. Por exemplo, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Execute o seguinte comando para desabilitar o Teams para todos os usuários que possuem uma licença ativa para o plano de licenciamento.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Tópicos relacionados

- [Licenças de complemento do Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Atribuir licenças de complemento do Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomes de produtos e identificadores de plano de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referência da SKU do Education](sku-reference-edu.md)
