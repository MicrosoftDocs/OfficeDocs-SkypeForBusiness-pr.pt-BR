---
title: Atribuir políticas a grandes conjuntos de usuários na sua escola
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Saiba como atribuir políticas a grandes conjuntos de usuários em sua instituição educacional com base em associação a um grupo ou diretamente por meio de uma atribuição em lote para fins de escola remota (teleescolar, tele-School).
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616935"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Atribuir políticas a grandes conjuntos de usuários na sua escola

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Para obter uma história maior sobre como atribuir políticas no Microsoft Teams, consulte [atribuir políticas a seus usuários no Teams](assign-policies.md).

## <a name="overview"></a>Visão geral

Você precisa dar aos alunos e professores acesso a diferentes recursos do Microsoft Teams? Você pode identificar rapidamente os usuários da sua organização por tipo de licença e, em seguida, atribuí-los à política apropriada. Este tutorial mostra como atribuir uma política de reunião a grandes conjuntos de usuários na sua escola. Você pode atribuir políticas usando o centro de administração do Microsoft Teams e o PowerShell e mostraremos as duas maneiras.

Você pode atribuir uma política de reunião a um grupo de segurança do qual os usuários são membros ou diretamente para os usuários em escala por meio de uma atribuição de política em lotes. Você aprenderá a:

- **Use [a atribuição de política para grupos](#assign-a-policy-to-a-group) para atribuir uma política de reunião a um grupo de segurança (recomendado)**. Esse método permite atribuir uma política com base em associação a um grupo. Você pode atribuir uma política a um grupo de segurança ou lista de distribuição. Conforme os membros são adicionados ou removidos do grupo, suas atribuições de política herdadas são atualizadas de acordo. Recomendamos que você use esse método, pois ele reduz o tempo para gerenciar políticas para novos usuários ou quando as funções dos usuários mudam. Esse método funciona melhor para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

- **Use a [atribuição de política em lote](assign-policies.md#assign-a-policy-to-a-batch-of-users) para atribuir uma política de reunião diretamente aos usuários em massa**. Você pode atribuir uma política de até 5.000 usuários de cada vez. Se você tiver mais de 5.000 usuários, poderá enviar vários lotes. Com esse método, quando você tiver novos usuários, será necessário executar novamente a atribuição de lote para atribuir a política a esses novos usuários.

Lembre-se de que, no Teams, os usuários obtêm automaticamente a política global (padrão para toda a organização) para um tipo de política de equipe, a menos que você crie e atribua uma política personalizada. Como a população dos alunos costuma ser o maior conjunto de usuários e muitas vezes recebem as configurações mais restritivas, recomendamos que você faça o seguinte:

- Crie uma política personalizada que permita recursos essenciais, como chat particular e agendamento de reunião e atribuir a política a seus funcionários e educadores.
- Atribua a política personalizada a seus funcionários e educadores.
- Edite e aplique a política global (padrão para toda a organização) para restringir recursos para os alunos.

Lembre-se de que a política global será aplicada a todos os usuários de sua escola até você criar uma política personalizada e atribuí-la a seus funcionários e professores.

Neste tutorial, os alunos receberão a política de reunião global e atribuiremos uma política de reunião personalizada chamada EducatorMeetingPolicy à equipe e educadores. Presumimos que você tenha editado a política global para personalizar as configurações de reunião para os alunos e [criou uma política personalizada](policy-packages-edu.md) que define a experiência da reunião para funcionários e educadores.

![Captura de tela da página políticas de reunião no centro de administração do teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

Siga estas etapas para criar um grupo de segurança para seus funcionários e professores e, em seguida, atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy a esse grupo de segurança.

### <a name="before-you-get-started"></a>Antes de começar

> [!IMPORTANT]
> Quando você atribui uma política a um grupo, a atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência. Por exemplo, se um usuário for diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência sobre uma política herdada de um grupo. Isso também significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes de poder herdar uma política de reunião de um grupo de segurança.

Antes de começar, é importante entender [as regras de precedência](assign-policies.md#precedence-rules) e a [classificação de atribuição de grupo](assign-policies.md#group-assignment-ranking). Certifique-se de **ler e entender os conceitos do [que você precisa saber sobre a atribuição de política a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.

Você precisará completar todas essas etapas para que seus funcionários e professores herdem uma política de reunião de um grupo de segurança.

1. [Criar grupos de segurança](#create-security-groups).
2. [Atribuir uma política a um grupo de segurança](#assign-a-policy-to-a-security-group).
3. [Remover uma política que foi atribuída diretamente aos usuários](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Criar grupos de segurança

Primeiro, crie um grupo de segurança para seus funcionários e educadores.

Com a [data de sincronização da escola](https://docs.microsoft.com/SchoolDataSync/) (SDS), você pode [criar facilmente grupos de segurança para professores e alunos](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) da sua escola. Recomendamos que você use o SDS para criar os grupos de segurança necessários para gerenciar políticas para sua escola.

Se não for possível implantar o SDS em seu ambiente, use [esse script do PowerShell](scripts/powershell-script-security-groups-edu.md) para criar dois grupos de segurança, um para todos os funcionários e professores que têm uma licença docente atribuída e outro para todos os alunos que têm uma licença de aluno atribuída. Você precisará executar esse script rotineiramente para manter atualizados os grupos e até o momento.

### <a name="assign-a-policy-to-a-security-group"></a>Atribuir uma política a um grupo de segurança

#### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

> [!NOTE]
> Atualmente, a atribuição de política a grupos usando o centro de administração do Microsoft Teams está disponível apenas para política de chamada de equipes, política de estacionamento de chamada de equipe, política de equipe, política de eventos do Teams, política de reunião do Teams e política de mensagens de equipe. Para outros tipos de política, use o PowerShell.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de reunião de **reuniões**  >  .
2. Selecione a guia **atribuição de política de grupo** .
3. Selecione **Adicionar grupo** e, em seguida, no painel **atribuir política ao grupo** , faça o seguinte:

    ![Captura de tela do painel Editar configurações, mostrando política de reunião](media/batch-group-policy-assignment-edu-group.png)
    1. Na caixa **selecionar um grupo** , procure e adicione o grupo de segurança que contém seus funcionários e educadores.
    2. Na caixa **selecionar classificação** , insira **1**.
    3. Na caixa **selecionar uma política** , selecione **EducatorMeetingPolicy**.
    4. Selecione **aplicar**.

Para remover uma atribuição de política de grupo, na guia **atribuição de política de grupo** da página política, selecione a atribuição de grupo e, em seguida, selecione **remover**.

Para alterar a classificação de uma atribuição de grupo, primeiro você precisa remover a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir a política a um grupo.

#### <a name="using-powershell"></a>Usando o PowerShell

> [!NOTE]
> Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política de equipe. Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obter a lista de tipos de política com suporte.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Execute o seguinte para instalar o [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado). Verifique se você instalou a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

##### <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

Execute o seguinte para atribuir a política de reunião chamada EducatorMeetingPolicy ao grupo de segurança que contém seus funcionários e educadores e defina a classificação de atribuição como 1. Você pode especificar um grupo de segurança usando a ID do objeto, o endereço SIP ou o endereço de email. Neste exemplo, usamos um endereço de email (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Remover uma política que foi diretamente atribuída aos usuários

Lembre-se de que, se um usuário foi diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência. Isso significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes de poder herdar uma política de reunião de um grupo de segurança.

Para saber mais, confira [o que você precisa saber sobre atribuição de política a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).

Siga estas etapas para remover a política de reunião atribuída diretamente a seus funcionários e professores.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Execute o seguinte para instalar o [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado). Verifique se você instalou a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Cancelar a atribuição de uma política que foi atribuída diretamente aos usuários

Execute o seguinte para remover uma política de reunião de usuários que receberam essa política diretamente. Você pode especificar os usuários por endereço de email ou ID de objeto.

Neste exemplo, a política de reunião é removida de usuários especificados pelo endereço de e-mail.

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

Execute o seguinte para ver todas as políticas atribuídas a um grupo de segurança específico. Observe que os grupos são sempre listados pela ID do grupo mesmo se seu endereço SIP ou endereço de email foi usado para atribuir a política.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Obter as políticas atribuídas a um usuário

Execute o seguinte para ver todas as políticas atribuídas a um usuário específico. O exemplo a seguir mostra como obter as políticas atribuídas ao reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Atribuir uma política a um lote de usuários

Siga estas etapas para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy diretamente a seus funcionários e professores em massa.

### <a name="using-powershell"></a>Usando o PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Conectar-se ao módulo do Azure AD PowerShell para Graph e ao módulo do PowerShell do teams

Antes de executar as etapas deste artigo, você precisará instalar e se conectar ao módulo Azure AD PowerShell para Graph (para identificar os usuários por suas licenças atribuídas) e ao módulo do Microsoft Teams PowerShell (para atribuir as políticas a esses usuários).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph

Abra um prompt de comando do Windows PowerShell com privilégios elevados (execute o Windows PowerShell como administrador) e execute o seguinte procedimento para instalar o módulo do Azure Active Directory PowerShell para Graph.

```powershell
Install-Module -Name AzureAD
```

Execute o seguinte para se conectar ao Azure AD.

```powershell
Connect-AzureAD
```

Quando for solicitado, entre usando suas credenciais de administrador.

Para saber mais, consulte [conectar-se com o módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Execute o seguinte para instalar o [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado). Verifique se você instalou a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.

#### <a name="identify-your-users"></a>Identifique seus usuários

Primeiro, execute o seguinte procedimento para identificar seus funcionários e professores por tipo de licença. Isso informa quais SKUs estão em uso em sua organização. Em seguida, você pode identificar os funcionários e professores que têm uma SKU com docente atribuída.

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

Neste exemplo, a saída mostra que a licença doce SkuId é "e97c048c-37a4-45fb-ab50-922fbf07a370".

> [!NOTE]
> Para ver uma lista de SKUs educacionais e IDs de SKU, consulte referência sobre o [SKU educacional](sku-reference-edu.md).

Em seguida, executamos o seguinte para identificar os usuários que têm essa licença e reuni-los juntos.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Atribuir uma política em massa

Agora, atribuímos as políticas adequadas aos usuários em massa. O número máximo de usuários para os quais você pode atribuir ou atualizar políticas é de 5.000 de cada vez. Por exemplo, se você tiver mais de 5.000 funcionários e professores, será necessário enviar vários lotes.

Execute o seguinte para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy à sua equipe e educadores.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Para atribuir um tipo de política diferente em massa, como TeamsMessagingPolicy, você precisará mudar ```PolicyType``` para a política que está atribuindo e ```PolicyName``` para o nome da política.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Obter o status de uma atribuição em massa

Cada atribuição em massa retorna uma ID de operação, que você pode usar para acompanhar o andamento das tarefas de política ou identificar quaisquer falhas que possam ocorrer. Por exemplo, execute o seguinte:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Para exibir o status da atribuição de cada usuário na operação em lotes, execute o seguinte. Os detalhes de cada usuário estão na ```UserState``` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Atribuir uma política em massa se você tiver mais de 5.000 usuários

Primeiro, execute o seguinte procedimento para ver quantas pessoas e professores você tem:

```powershell
$faculty.count
```

Em vez de fornecer toda a lista de IDs de usuário, execute o seguinte para especificar o primeiro 5.000 e, em seguida, o próximo 5.000 e assim por diante.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Você pode alterar o intervalo de IDs de usuário até chegar à lista completa de usuários. Por exemplo, insira ```$faculty[0..4999``` para o primeiro lote, use ```$faculty[5000..9999``` para o segundo lote, insira ```$faculty[10000..14999``` para o terceiro lote e assim por diante.

#### <a name="get-the-policies-assigned-to-a-user"></a>Obter as políticas atribuídas a um usuário

Execute o seguinte para ver todas as políticas atribuídas a um usuário específico. O exemplo a seguir mostra como obter as políticas atribuídas ao hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Perguntas frequentes

**Não estou familiarizado com o PowerShell para Teams. Onde posso saber mais?**

Para obter uma visão geral sobre como usar o PowerShell para gerenciar equipes, consulte [visão geral do teams PowerShell](teams-powershell-overview.md). Para obter mais informações sobre os cmdlets usados neste artigo, consulte:

- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](assign-policies.md)
- [Políticas de equipe e pacotes de política para educação](policy-packages-edu.md)
- [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)
