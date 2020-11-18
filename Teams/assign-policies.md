---
title: Atribuir políticas aos usuários no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda as diferentes maneiras de atribuir políticas a seus usuários no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ada58a9abf07e606f91d48b7ac71ba06d4c1496a
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085695"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Atribuir políticas aos usuários no Microsoft Teams

Como administrador, você usa políticas para controlar os recursos do teams que estão disponíveis para os usuários da sua organização. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas alguns.

As organizações têm diferentes tipos de usuários com necessidades exclusivas e políticas personalizadas que você cria e atribui permite que você ajuste as configurações de política para diferentes conjuntos de usuários com base nessas necessidades.

Para facilitar o gerenciamento de políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas a usuários. Você pode atribuir uma política diretamente aos usuários, individualmente ou em escalabilidade por meio de uma atribuição de lote ou a um grupo do qual os usuários são membros. Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas para os usuários de sua organização que têm funções semelhantes. A opção que você escolher depende do número de políticas que você está gerenciando e do número de usuários aos quais está fazendo a atribuição. Ao definir as políticas globais (padrão para toda a organização) para que elas se apliquem ao maior número de usuários em sua organização, você só precisa atribuir políticas a esses usuários que exigem políticas especializadas.

Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas a usuários e os cenários recomendados para quando usar o quê.

## <a name="which-policy-takes-precedence"></a>Qual política tem precedência?

Um usuário tem uma política em vigor para cada tipo de política. É possível ou até mesmo provável que um usuário esteja diretamente atribuído a uma política e também seja um membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo. Nesses tipos de cenários, qual política tem precedência?  A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.

Se um usuário for diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência. No exemplo a seguir, a política efetiva do usuário é a política de reunião quadrada Lincoln, que é atribuída diretamente ao usuário.

![Diagrama mostrando como uma política atribuída diretamente tem prioridade](media/assign-policies-example-directly-assigned.png)

Se um usuário não estiver diretamente atribuído a uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro terá precedência. Se um usuário for membro de vários grupos, a política que tem a classificação de [atribuição de grupo](#group-assignment-ranking) mais alta para o tipo de política específico tem precedência.

Neste exemplo, a política efetiva do usuário é o Teams exec e a política de HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também são atribuídas uma política do mesmo tipo de política.  

![Diagrama mostrando como uma política herdada do grupo tem prioridade](media/assign-policies-example-group.png)

Se um usuário não estiver diretamente atribuído a uma política ou não for membro de nenhum grupo ao qual a política atribuiu uma política, o usuário terá a política global (padrão para toda a organização) para esse tipo de política. Aqui está um exemplo.

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

Para saber mais, consulte [regras de precedência](#precedence-rules).

## <a name="ways-to-assign-policies"></a>Maneiras de atribuir políticas

Aqui está uma visão geral de como você pode atribuir políticas a usuários e os cenários recomendados para cada um deles. Clique nos links para saber mais.

Antes de atribuir políticas a usuários ou grupos individuais, comece [definindo as políticas globais (padrão para toda](#set-the-global-policies) a organização) para que elas se apliquem ao maior número de usuários em sua organização.  Depois que as políticas globais estiverem definidas, você só precisará atribuir políticas a esses usuários que exigem políticas especializadas.

|Faça isto  |Se...  | Usar...
|---------|---------|----|
|[Atribuir uma política a usuários individuais](#assign-a-policy-to-individual-users)    | Você está começando a usar o Microsoft Teams e simplesmente está começando ou só precisa atribuir uma ou algumas políticas a um pequeno número de usuários. |O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do PowerShell do Skype for Business Online
|[Atribuir uma política a um grupo](#assign-a-policy-to-a-group) |Você precisa atribuir políticas com base nas associações de grupo de um usuário. Por exemplo, você deseja atribuir uma política a todos os usuários em um grupo de segurança ou lista de distribuição.| O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell|
|[Atribuir uma política a um lote de usuários](#assign-a-policy-to-a-batch-of-users)   | Você precisa atribuir políticas a grandes conjuntos de usuários. Por exemplo, você deseja atribuir uma política para centenas ou milhares de usuários em sua organização de cada vez.  |O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell|
| [Atribuir um pacote de política aos usuários](#assign-a-policy-package-to-users)  | Você precisa atribuir várias políticas a conjuntos específicos de usuários em sua organização que tenham funções iguais ou semelhantes. Por exemplo, atribua o pacote de política de educação (professor) a professores em sua escola para dar a eles acesso total a chats, chamadas e reuniões e ao pacote de política Education (aluno da escola secundária) para os alunos secundários limitarem determinados recursos como chamadas privadas.  |O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell|
| [Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização particular)   |Você precisa atribuir várias políticas a um grupo de usuários em sua organização que tenham funções iguais ou semelhantes. Por exemplo, você deseja atribuir um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição. |O centro de administração do Microsoft Teams (disponível em breve) ou cmdlets do PowerShell no módulo do PowerShell para Teams|
| [Atribuir um pacote de política a um lote de usuários](#assign-a-policy-package-to-a-batch-of-users)|Você precisa atribuir várias políticas a um lote de usuários em sua organização que tenham funções iguais ou semelhantes. Por exemplo, atribua o pacote de política de educação (professor) a todos os professores da sua escola usando a atribuição de lote para dar a eles acesso total a chats, chamadas e reuniões e atribuir o pacote de política de educação (aluno secundária da escola) a um lote de alunos secundários para limitar determinados recursos como chamadas privadas.|Cmdlets do PowerShell no módulo do teams PowerShell|


## <a name="set-the-global-policies"></a>Definir as políticas globais

Siga estas etapas para definir as políticas globais (padrão para toda a organização) para cada tipo de política.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política do tipo de política que você deseja atualizar. Por exemplo, políticas **Teams**  >  de **equipes** de equipe, políticas de reuniões de **reuniões**  >  **Meetings policies**, políticas de **mensagens** ou políticas de chamadas de **voz**  >  **Calling policies**.
2. Selecione a política **global (padrão para toda a organização)** para exibir as configurações atuais.
3. Atualize a política conforme necessário e selecione **aplicar**.

### <a name="using-powershell"></a>Usando o PowerShell

Para definir as políticas globais usando o PowerShell, use o identificador global.  Comece analisando a política global atual para determinar qual configuração você deseja alterar.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Em seguida, atualize a política global conforme necessário.  Você só precisa especificar valores para as configurações que você deseja alterar. 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Atribuir uma política a usuários individuais

Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Para atribuir uma política a um usuário:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Selecione a política que você deseja atribuir e clique em **aplicar**.

Ou, você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política.
2. Selecione a política que você deseja atribuir clicando à esquerda do nome da política.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, selecione **aplicar**.

### <a name="using-powershell"></a>Usando o PowerShell

Cada tipo de política tem seu próprio conjunto de cmdlets para gerenciá-lo. Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política. Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do teams aos usuários. Esses cmdlets estão incluídos no módulo do PowerShell do Skype for Business Online e são documentados na [referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

 Baixe e instale o [módulo do PowerShell do Skype for Business online](https://www.microsoft.com/download/details.aspx?id=39366) (caso ainda não tenha sido feito) e, em seguida, execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.

> [!NOTE]
> O conector do Skype for Business online atualmente faz parte do módulo do PowerShell mais recente do teams.
>
> Se você estiver usando a [versão pública do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)mais recente, não será necessário instalar o conector do Skype for Business online.

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

Neste exemplo, atribuímos uma política de reunião do teams chamada política de reunião do aluno a um usuário chamado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para saber mais, leia [gerenciar políticas pelo PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou lista de distribuição. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.

A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funciona com grupos maiores.

Quando você atribui a política, ela é imediatamente atribuída ao grupo. No entanto, observe que a propagação da atribuição da política para os membros do grupo é realizada como uma operação em segundo plano e pode demorar algum tempo, dependendo do tamanho do grupo. O mesmo é verdadeiro quando uma política é desatribuída de um grupo ou quando os membros são adicionados ou removidos de um grupo.

As atribuições de política de grupo só são propagadas para os usuários que são membros diretos do grupo. As tarefas não são propagadas para os membros de grupos aninhados.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>O que você precisa saber sobre atribuição de política a grupos

Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.

#### <a name="precedence-rules"></a>Regras de precedência

Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:

- Uma política que é atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo que esteja atribuída a um grupo. Em outras palavras, se um usuário estiver diretamente atribuído a uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo. Isso também significa que, se um usuário tiver uma política de um determinado tipo que foi atribuído diretamente a ele, será necessário remover essa política do usuário antes de poder herdar uma política do mesmo tipo de um grupo.
- Se um usuário não tiver uma política diretamente atribuída a ele e for um membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.
- Se um usuário não for membro de nenhum grupo ao qual uma política atribuiu uma política, a política global (padrão para toda a organização) para esse tipo de política se aplicará ao usuário.

A política efetiva de um usuário é atualizada de acordo com essas regras quando um usuário é adicionado ou removido de um grupo que é atribuído a uma política, uma política é desatribuída de um grupo ou uma política diretamente atribuída ao usuário é removida.

#### <a name="group-assignment-ranking"></a>Classificação de atribuição de grupo
 
Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo. Isso é usado para determinar qual política um usuário deve herdar como política efetiva se o usuário for membro de dois ou mais grupos e cada grupo tiver atribuído uma política do mesmo tipo.

A classificação da atribuição de grupo é relativa a outras tarefas de grupo do mesmo tipo. Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, defina a classificação de uma tarefa como 1 e a outra como 2, com 1 sendo a classificação mais alta. A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.
 
Digamos, por exemplo, que você tem dois grupos, armazenar funcionários e gerentes da loja. Os dois grupos recebem uma política de chamada de equipes, armazenando a política de chamadas de gerentes de loja e a política de chamadas de gerentes de loja Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que a função de um funcionário, portanto, a política de chamada atribuída ao grupo de gerentes da loja deve ter uma classificação mais alta.

|Grupos |Nome da política de chamada de equipes  |Classificação|
|---------|---------|---|
|Gerentes da loja   |Política de chamadas de gerentes de loja         |1|
|Loja de funcionários    |Política de chamadas de funcionários da loja      |2|

Se você não especificar uma classificação, a atribuição de política terá a classificação mais baixa. 

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

> [!NOTE]
> Atualmente, a atribuição de política a grupos usando o centro de administração do Microsoft Teams está disponível apenas para política de chamada de equipes, política de estacionamento de chamada de equipe, política de equipe, política de eventos do Teams, política de reunião do Teams e política de mensagens de equipe. Para outros tipos de política, use o PowerShell.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página tipo de política. Por exemplo, acesse **Meetings**  >  **políticas de reunião** de reuniões.
2. Selecione a guia **atribuição de política de grupo** .
3. Selecione **Adicionar grupo** e, em seguida, no painel **atribuir política ao grupo** , faça o seguinte:
    1. Procure e adicione o grupo ao qual você deseja atribuir a política.
    2. Defina a classificação para a atribuição de grupo.
    3. Selecione a política que você deseja atribuir. 
    4. Selecione **aplicar**.

Para remover uma atribuição de política de grupo, na guia **atribuição de política de grupo** da página política, selecione a atribuição de grupo e, em seguida, selecione **remover**.

Para alterar a classificação de uma atribuição de grupo, primeiro você precisa remover a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir a política a um grupo.

### <a name="using-powershell"></a>Usando o PowerShell

> [!NOTE]
> Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política de equipe. Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obter a lista de tipos de política com suporte.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Para obter orientação passo a passo, consulte instalar o PowerShell do Microsoft [Teams](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group-of-users"></a>Atribuir uma política a um grupo de usuários

Use o cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo. Você pode especificar um grupo usando a identificação do objeto, o endereço SIP ou o endereço de email.

Neste exemplo, atribuímos uma política de reunião do teams chamada política de reunião de gerentes de revenda a um grupo com uma classificação de atribuição de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obter atribuições de política para um grupo

Use o cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo. Observe que os grupos são sempre listados pela ID do grupo mesmo se seu endereço SIP ou endereço de email foi usado para atribuir a política.

Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

Neste exemplo, retornamos todos os grupos que recebem uma política de reunião do teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Remover uma política de um grupo

Use o cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo. Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo e que têm uma classificação mais baixa são atualizadas. Por exemplo, se você remover uma política que tem uma classificação de 2, as políticas que têm uma classificação de 3 e 4 são atualizadas para refletir a nova classificação. As duas tabelas a seguir mostram este exemplo.

Aqui está uma lista das atribuições e prioridades de política para uma política de reunião do teams.

|Nome do grupo  |Nome da política  |Classificação|
|---------|---------|---------|
|Vendas    |Política de vendas       | 1        |
|Região oeste     |Política de região oeste         |2         |
|Visões    |Política de divisão         |3         |
|Subsidiária da   |Política da subsidiária        |4         |

Se removermos a política de região oeste do grupo região oeste, as atribuições e prioridades de política serão atualizadas da maneira a seguir.

|Nome do grupo  |Nome da política  |Classificação|
|---------|---------|---------|
|Vendas    |Política de vendas       | 1        |
|Visões    |Política de divisão         |2         |
|Subsidiária da   |Política da subsidiária        |3        |

Neste exemplo, removemos a política de reunião do teams de um grupo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Alterar uma atribuição de política para um grupo

> [!NOTE]
> O cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve. Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e, em seguida, adicionar uma nova atribuição de política.

Depois de atribuir uma política a um grupo, você pode usar o cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição da política desse grupo da seguinte maneira:

- Alterar a classificação
- Alterar a política de um determinado tipo de política
- Alterar a política de um determinado tipo de política e a classificação

Neste exemplo, alteramos a política de estacionamento de chamada de equipe de um grupo para uma política chamada SupportCallPark e a classificação de atribuição para 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Alterar a política em vigor para um usuário

Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.

Primeiro, usamos o cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) em conjunto com o ```PolicySource``` parâmetro para obter detalhes das políticas de transmissão de reunião do teams associadas ao usuário. 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

A saída mostra que o usuário foi diretamente atribuído a uma política de transmissão de reunião do teams chamada eventos do funcionário, que tem precedência sobre a política denominada eventos dinâmicos do fornecedor que é atribuída a um grupo ao qual o usuário pertence.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Agora, removemos a política de eventos de funcionários do usuário. Isso significa que o usuário não tem mais uma política de transmissão de reunião do teams diretamente atribuída a elas e herdará a política de eventos dinâmicos do fornecedor que é atribuída ao grupo ao qual o usuário pertence. 

Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Você pode usar o cmdlet a seguir no módulo do PowerShell Teams para fazer isso em escala durante uma atribuição de política em lotes, onde $users é uma lista de usuários que você especifica.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Atribuir uma política a um lote de usuários

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Para atribuir uma política a usuários em massa:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários**.
2. Procure os usuários para os quais você deseja atribuir a política ou filtre o modo de exibição para mostrar os usuários que você deseja.
3. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.
4. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Para exibir o status da atribuição da política, na faixa exibida na parte superior da página **usuários** depois que você clicar em **aplicar** para enviar a atribuição de política, clique em **registro de atividades**. Ou, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá até **painel** e, em **registro de atividades**, clique em **Exibir detalhes**. O registro de atividades mostra as atribuições de política para lotes de mais de 20 usuários por meio do centro de administração do Microsoft Teams dos últimos 30 dias. Para saber mais, consulte [exibir suas atribuições de política no log de atividades](activity-log.md).

### <a name="using-powershell"></a>Usando o PowerShell

> [!NOTE]
> No momento, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos de política de equipe. Consulte [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obter a lista de tipos de política com suporte.
 
Com a atribuição de política em lotes, você pode atribuir uma política a grandes conjuntos de usuários de uma vez sem precisar usar um script. Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das tarefas em um lote.

Você pode especificar os usuários por seu ID de objeto ou endereço SIP (protocolo de iniciação de sessão). Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o nome UPN ou endereço de email, mas isso não é necessário. Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário. Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote. 

Um lote pode conter até 5.000 usuários. Para obter melhores resultados, não envie mais do que alguns lotes de cada vez. Permitir que os lotes concluam o processamento antes de enviar mais lotes.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Verifique se você instalou a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph (opcional)

Você também pode [fazer o download e instalar o módulo do Azure ad PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se ainda não tiver feito isso) e se conectar ao Azure ad para que você possa recuperar uma lista de usuários em sua organização.

Execute o seguinte para se conectar ao Azure AD.

```powershell
Connect-AzureAD
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Microsoft Teams.

#### <a name="assign-a-policy-to-a-batch-of-users"></a>Atribuir uma política a um lote de usuários

Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada política de configuração de aplicativo de RH a um lote de usuários listados no arquivo Users_ids. Text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

Neste exemplo, nós nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada novo contratar política de mensagens a um lote de usuários especificados usando o endereço SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Obter o status de uma atribuição em lote

Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-package-to-users"></a>Atribuir um pacote de política aos usuários

Um pacote de política no Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções iguais ou semelhantes em sua organização. Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades típicas para essa função. Alguns exemplos de pacotes de política são o pacote de educação (professor) e o pacote de assistência médica (funcionário clínico). Para saber mais, consulte [gerenciar pacotes de política no Microsoft Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Atribuir um pacote de política a um usuário

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Na página do usuário, clique em **políticas** e, em seguida, ao lado de **pacote de política**, clique em **Editar**.
3. No painel **atribuir pacote de política** , selecione o pacote que você deseja atribuir e clique em **salvar**.

### <a name="assign-a-policy-package-to-multiple-users"></a>Atribuir um pacote de política a vários usuários

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **pacotes de política** e, em seguida, selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.
2. Clique em **gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando tiver terminado de adicionar usuários, clique em **salvar**.

## <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

**Este recurso está na visualização particular**

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.

A atribuição de pacote de política para grupos é recomendada para grupos de até 50.000 usuários, mas também funciona com grupos maiores. 

Quando você atribui o pacote de política, ele é imediatamente atribuído ao grupo. No entanto, observe que a propagação da atribuição da política para os membros do grupo é realizada como uma operação em segundo plano e pode demorar algum tempo, dependendo do tamanho do grupo. O mesmo é verdadeiro quando uma política é desatribuída de um grupo ou quando os membros são adicionados ou removidos de um grupo.

> [!IMPORTANT]
> Antes de começar, é importante entender [as regras de precedência](#precedence-rules) e a [classificação de atribuição de grupo](#group-assignment-ranking). Certifique-se de ler e entender os conceitos do [que você precisa saber sobre a atribuição de política a grupos,](#what-you-need-to-know-about-policy-assignment-to-groups) anteriormente neste artigo.

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a>Usar o centro de administração do Microsoft Teams (disponível em breve)

A atribuição de pacote de política a grupos no centro de administração do Microsoft Teams estará disponível em breve. Verifique novamente aqui para obter as atualizações mais recentes.

### <a name="using-powershell"></a>Usando o PowerShell

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Para obter orientação passo a passo, consulte instalar o PowerShell do Microsoft [Teams](teams-powershell-install.md).

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Atribuir um pacote de política a um grupo de usuários

Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo. Você pode especificar um grupo usando a identificação do objeto, o endereço SIP ou o endereço de email. Ao atribuir o pacote de política, especifique uma [classificação de atribuição de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política. 

Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Atribuir um pacote de política a um lote de usuários

Com a atribuição de pacote de política em lotes, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem ter que usar um script. Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das tarefas em um lote.

Você pode especificar os usuários por seu ID de objeto ou endereço SIP (protocolo de iniciação de sessão). Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o nome UPN ou endereço de email, mas isso não é necessário. Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário. Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote. 

Um lote pode conter até 5.000 usuários. Para obter melhores resultados, não envie mais do que alguns lotes de cada vez. Permitir que os lotes concluam o processamento antes de enviar mais lotes.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não tiver feito isso). Verifique se você instalou a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

### <a name="assign-a-policy-package-to-a-batch-of-users"></a>Atribuir um pacote de política a um lote de usuários

Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política de Education_PrimaryStudent a um lote de usuários.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a>Obter o status de uma atribuição em lote

Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation). 

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
