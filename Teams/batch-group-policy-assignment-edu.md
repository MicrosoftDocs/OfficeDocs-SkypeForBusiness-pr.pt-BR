---
title: Atribuir políticas a grandes conjuntos de usuários em sua escola
author: serdars
ms.author: serdars
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como atribuir políticas a grandes conjuntos de usuários em sua instituição educacional com base na associação ao grupo ou diretamente por meio de uma atribuição em lotes para fins de escola remota (teleescola, teleescola).
f1keywords: ''
ms.openlocfilehash: 3cd0bfd791d2416de31d998c693002cce87f6fcd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745697"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Atribuir políticas a grandes conjuntos de usuários em sua escola

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Para saber mais sobre como atribuir políticas em Microsoft Teams, consulte Atribuir políticas aos usuários [em Teams](policy-assignment-overview.md).

## <a name="overview"></a>Visão geral

Você precisa dar aos alunos e educadores acesso a diferentes recursos no Microsoft Teams? Você pode identificar rapidamente os usuários em sua organização por tipo de licença e atribuí-los a política apropriada. Este tutorial mostra como atribuir uma política de reunião a grandes conjuntos de usuários em sua escola. Você pode atribuir políticas usando o centro de administração Microsoft Teams e o PowerShell e mostraremos as duas maneiras.

Você pode atribuir uma política de reunião a um grupo de segurança de que os usuários são membros ou diretamente aos usuários em escala por meio de uma atribuição de política em lotes. Você aprenderá a:

- **Use [a atribuição de política](#assign-a-policy-to-a-group) a grupos para atribuir uma política de reunião a um grupo de segurança (recomendado)**. Esse método permite atribuir uma política com base na associação ao grupo. Você pode atribuir uma política a um grupo de segurança ou lista de distribuição. À medida que os membros são adicionados ou removidos do grupo, suas atribuições de política herdadas são atualizadas de acordo. Recomendamos que você use esse método porque reduz o tempo para gerenciar políticas para novos usuários ou quando as funções dos usuários mudam. Esse método funciona melhor para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

- **Use [a atribuição de política em lote](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users) para atribuir uma política de reunião diretamente aos usuários em massa.** Você pode atribuir uma política para até 5.000 usuários por vez. Se você tiver mais de 5.000 usuários, poderá enviar vários lotes. Com esse método, quando você tiver novos usuários, precisará executar a atribuição em lotes para atribuir a política a esses novos usuários.

Lembre-se de Teams, os usuários receberão automaticamente a política Global (padrão em toda a organização) para um tipo de política Teams, a menos que você crie e atribua uma política personalizada. Como a população de alunos geralmente é o maior conjunto de usuários e eles geralmente recebem as configurações mais restritivas, recomendamos que você faça o seguinte:

- Crie uma política personalizada que permita recursos fundamentais, como chat privado e agendamento de reuniões e atribua a política à sua equipe e educadores.
- Atribua a política personalizada aos seus funcionários e educadores.
- Edite e aplique a política Global (padrão em toda a organização) para restringir recursos para alunos.

Lembre-se de que a política Global será aplicada a todos os usuários em sua escola até que você crie uma política personalizada e atribua-a à sua equipe e educadores.

Neste tutorial, os alunos receberão a política de reunião global e atribuiremos uma política de reunião personalizada chamada EducatorMeetingPolicy a funcionários e educadores. Presumimos que você editou a política global para adaptar as configurações de reunião para alunos e criou uma política personalizada que define [a](policy-packages-edu.md) experiência de reunião para funcionários e educadores.

![Captura de tela da página Políticas de reunião no Teams de administração.](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

Siga estas etapas para criar um grupo de segurança para sua equipe e educadores e atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy a esse grupo de segurança.

### <a name="before-you-get-started"></a>Antes de começar

> [!IMPORTANT]
> Quando você atribui uma política a um grupo, a atribuição de política é propagada aos membros do grupo de acordo com as regras de precedência. Por exemplo, se um usuário recebe diretamente uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência sobre uma política herdada de um grupo. Isso também significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes que ele possa herdar uma política de reunião de um grupo de segurança.

Antes de começar, é importante entender as regras [de precedência](policy-assignment-overview.md#which-policy-takes-precedence) e a classificação [de atribuição de grupo.](assign-policies-users-and-groups.md#group-assignment-ranking) Leia e entenda os conceitos em O que você precisa saber sobre a atribuição de **política a [grupos.](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)**

Você precisará concluir todas essas etapas para que sua equipe e educadores herdem uma política de reunião de um grupo de segurança.

1. [Criar grupos de segurança](#create-security-groups).
2. [Atribua uma política a um grupo de segurança](#assign-a-policy-to-a-security-group).
3. [Remova uma política que foi atribuída diretamente aos usuários](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Criar grupos de segurança

Primeiro, crie um grupo de segurança para sua equipe e educadores.

Com [School Data Sync](/SchoolDataSync/) (SDS), você pode facilmente criar educadores e [alunos](/SchoolDataSync/edu-security-groups) de grupos de segurança em sua escola. Recomendamos que você use o SDS para criar os grupos de segurança necessários para gerenciar políticas para sua escola.

Se você não conseguir implantar o SDS em seu ambiente, use este script do [PowerShell](scripts/powershell-script-security-groups-edu.md) para criar dois grupos de segurança, um para todos os funcionários e educadores com uma licença de Docente atribuída e outro para todos os alunos que têm uma licença de aluno atribuída. Você precisará executar esse script rotineiramente para manter os grupos atualizados e atualizados.

### <a name="assign-a-policy-to-a-security-group"></a>Atribuir uma política a um grupo de segurança

#### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

> [!NOTE]
> Atualmente, a atribuição de política para grupos usando o centro de administração do Microsoft Teams está disponível apenas para a política de chamada do Teams, a política de estacionamento de chamada do Teams, Teams política de Teams, Teams política de eventos ao vivo, Teams política de reunião e Teams de mensagens. Para outros tipos de política, use o PowerShell.

1. Na barra de navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Reuniões** > **Políticas de Reunião**.
2. Selecione a **guia Atribuição de política de** grupo.
3. Selecione **Adicionar grupo** e, em seguida, no painel Atribuir **política** ao grupo, faça o seguinte:

    ![Captura de tela do painel Editar configurações, mostrando a política de reunião.](media/batch-group-policy-assignment-edu-group.png)
    1. Na caixa **Selecionar um grupo,** pesquise e adicione o grupo de segurança que contém sua equipe e educadores.
    2. Na caixa **Selecionar classificação,** digite **1**.
    3. Na caixa **Selecionar uma política,** selecione **EducatorMeetingPolicy**.
    4. Selecione **Aplicar**.

Para remover uma atribuição de política de grupo, na **guia** Atribuição de política de grupo da página de política, selecione a atribuição de grupo e selecione **Remover**.

Para alterar a classificação de uma atribuição de grupo, você precisa primeiro remover a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir a política a um grupo.

#### <a name="using-powershell"></a>Usando o Windows PowerShell

> [!NOTE]
> Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos Teams de política. Consulte [New-CsGroupPolicyAssignment para](/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar ao módulo Microsoft Teams PowerShell

Execute o seguinte para instalar o [Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado). Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

##### <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

Execute o seguinte para atribuir a política de reunião chamada EducatorMeetingPolicy ao grupo de segurança que contém sua equipe e educadores e definir a classificação de atribuição como 1. Você pode especificar um grupo de segurança usando a ID do objeto, o endereço SIP (Session Initiation Protocol) ou o endereço de email. Neste exemplo, usamos um endereço de email (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Remover uma política que foi atribuída diretamente aos usuários

Lembre-se de que, se um usuário tiver sido atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência. Isso significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes que ele possa herdar uma política de reunião de um grupo de segurança.

Para saber mais, confira [O que você precisa saber sobre a atribuição de política a grupos](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups).

Siga estas etapas para remover a política de reunião que foi atribuída diretamente à sua equipe e educadores.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar ao módulo Microsoft Teams PowerShell

Execute o seguinte para instalar o [Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado). Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Desaignar uma política que foi atribuída diretamente aos usuários

Execute o seguinte para remover uma política de reunião dos usuários que foram atribuídos diretamente a essa política. Você pode especificar usuários por endereço de email ou ID de objeto.

Neste exemplo, a política de reunião é removida dos usuários especificados por seu endereço de email.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

Neste exemplo, a política de reunião é removida da lista de usuários em um arquivo de texto chamado user_ids.txt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Obter atribuições de política para um grupo

Execute o seguinte para ver todas as políticas atribuídas a um grupo de segurança específico. Observe que os grupos sempre são listados pela ID do grupo, mesmo que seu endereço SIP ou endereço de email seja usado para atribuir a política.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Obter as políticas atribuídas a um usuário

Execute o seguinte para ver todas as políticas atribuídas a um usuário específico. O exemplo a seguir mostra como obter as políticas atribuídas a reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Atribuir uma política a um lote de usuários

Siga estas etapas para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy diretamente à sua equipe e educadores em massa.

### <a name="using-powershell"></a>Usando o Windows PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Conexão o módulo powershell do Azure AD para Graph e o módulo Teams PowerShell

Antes de executar as etapas deste artigo, você precisará instalar e se conectar ao módulo do Azure AD PowerShell para Graph (para identificar usuários por suas licenças atribuídas) e ao módulo do Microsoft Teams PowerShell (para atribuir as políticas a esses usuários).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Instalar e conectar-se ao Azure AD PowerShell para Graph módulo

Abra um prompt de Windows PowerShell de comando (execute o Windows PowerShell como administrador) e execute o seguinte para instalar o Azure Active Directory PowerShell para Graph módulo.

```powershell
Install-Module -Name AzureAD
```

Execute o seguinte para se conectar ao Azure AD.

```powershell
Connect-AzureAD
```

Quando for solicitado, entre usando suas credenciais de administrador.

Para saber mais, consulte [Conexão o Azure Active Directory PowerShell para Graph módulo](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar ao módulo Microsoft Teams PowerShell

Execute o seguinte para instalar o [Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado). Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.

#### <a name="identify-your-users"></a>Identificar seus usuários

Primeiro, execute o seguinte para identificar sua equipe e educadores por tipo de licença. Isso informa quais SKUs estão em uso em sua organização. Em seguida, você pode identificar funcionários e educadores que tenham um SKU docente atribuído.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Que retorna:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

Neste exemplo, a saída mostra que a licença de docente SkuId é "e97c048c-37a4-45fb-ab50-922fbf07a370".

> [!NOTE]
> Para ver uma lista de IDs education SKUs e SKU, consulte [Education SKU reference](sku-reference-edu.md).

Em seguida, executemos o seguinte para identificar os usuários que têm essa licença e colecioná-los todos juntos.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Atribuir uma política em massa

Agora, atribuímos as políticas apropriadas aos usuários em massa. O número máximo de usuários para os quais você pode atribuir ou atualizar políticas é 5.000 por vez. Por exemplo, se você tiver mais de 5.000 funcionários e educadores, precisará enviar vários lotes.

Execute o seguinte para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy à sua equipe e educadores.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Para atribuir um tipo de política diferente em massa, como TeamsMessagingPolicy, você precisará alterar para a política que você está atribuindo e para o nome ```PolicyType``` ```PolicyName``` da política.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Obter o status de uma atribuição em massa

Cada atribuição em massa retorna uma ID de operação, que você pode usar para controlar o andamento das atribuições de política ou identificar quaisquer falhas que possam ocorrer. Por exemplo, execute o seguinte:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Para exibir o status de atribuição de cada usuário na operação em lotes, execute o seguinte. Os detalhes de cada usuário estão na ```UserState``` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Atribuir uma política em massa se você tiver mais de 5.000 usuários

Primeiro, execute o seguinte para ver quantos funcionários e educadores você tem:

```powershell
$faculty.count
```

Em vez de fornecer toda a lista de IDs de usuário, execute o seguinte para especificar os primeiros 5.000 e, em seguida, os próximos 5.000 e assim por diante.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Você pode alterar o intervalo de IDs de usuário até chegar à lista completa de usuários. Por exemplo, insira o primeiro lote, use para o segundo lote, insira para o ```$faculty[0..4999``` terceiro lote e assim por ```$faculty[5000..9999``` ```$faculty[10000..14999``` diante.

#### <a name="get-the-policies-assigned-to-a-user"></a>Obter as políticas atribuídas a um usuário

Execute o seguinte para ver todas as políticas atribuídas a um usuário específico. O exemplo a seguir mostra como obter as políticas atribuídas a hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Perguntas frequentes

**Não estou familiarizado com o PowerShell para Teams. Onde posso saber mais?**

Para ver uma visão geral sobre como usar o PowerShell para gerenciar Teams, [consulte Teams visão geral do PowerShell.](teams-powershell-overview.md) Para obter mais informações sobre os cmdlets usados neste artigo, consulte:

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](policy-assignment-overview.md)
- [Políticas do Teams e pacotes de políticas para Educação](policy-packages-edu.md)
- [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)