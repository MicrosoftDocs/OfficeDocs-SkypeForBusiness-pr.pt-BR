---
title: Atribuir políticas aos usuários no Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Conheça as diferentes maneiras de atribuir políticas aos usuários no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3a788ff2712c065d0273d4dfb6233f03e2272337
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196285"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Atribuir políticas aos usuários no Microsoft Teams

Como administrador, você usa políticas para controlar os recursos do Teams que estão disponíveis para os usuários em sua organização. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas algumas.

As organizações têm diferentes tipos de usuários com necessidades exclusivas. As políticas personalizadas que você cria e atribui permitem adaptar as configurações de política a diferentes conjuntos de usuários com base nessas necessidades.

Para gerenciar facilmente as políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas aos usuários. Atribua uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lotes, ou a um grupo do que os usuários são membros. Você também pode usar pacotes de política para atribuir um conjunto predefinido de políticas aos usuários em sua organização que têm funções semelhantes. A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais está atribuindo políticas. As políticas globais (padrão em toda a organização) se aplicam ao maior número de usuários em sua organização. Você só precisa atribuir políticas aos usuários que exigem políticas especializadas.

Este artigo descreve as diferentes maneiras de atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.

## <a name="which-policy-takes-precedence"></a>Qual política tem precedência?

Um usuário tem uma política eficaz para cada tipo de política. É possível, ou até mesmo provável, que um usuário tenha atribuído uma política diretamente e também seja membro de um ou mais grupos que recebe uma política do mesmo tipo. Nesses tipos de cenários, qual política tem precedência? A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.

Se um usuário recebe diretamente uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência. No exemplo visual a seguir, a política efetiva do usuário é a política de reunião do Square Square, que é atribuída diretamente ao usuário.

![Diagrama mostrando como uma política atribuída diretamente tem precedência](media/assign-policies-example-directly-assigned.png)

Se um usuário não receber diretamente uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro tem precedência. Se um usuário for membro de vários grupos, [](#group-assignment-ranking) a política que tem a classificação de atribuição de grupo mais alta para determinado tipo de política terá precedência.

Neste exemplo visual, a política efetiva do usuário é a política Exec Teams e HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.  

![Diagrama mostrando como uma política herdada do grupo tem precedência](media/assign-policies-example-group.png)

Se um usuário não recebe uma política diretamente ou não é membro de nenhum grupo que recebe uma política, o usuário obtém a política global (padrão de toda a organização) para esse tipo de política. Veja um exemplo visual.

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

Para saber mais, confira [as regras de Precedência.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Maneiras de atribuir políticas

Aqui está uma visão geral de como você pode atribuir políticas aos usuários e os cenários recomendados para cada um deles. Selecione os links para saber mais.

Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas [globais (padrão](#set-the-global-policies) em toda a organização) para que se apliquem ao maior número de usuários em sua organização.  Depois que as políticas globais são definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.

|Faça isto  |Se...  | Usando...
|---------|---------|----|
|[Atribuir uma política a usuários individuais](#assign-a-policy-to-individual-users)    | Você é novo no Teams e está apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários. |O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo PowerShell do Skype for Business Online
|[Atribuir uma política a um grupo](#assign-a-policy-to-a-group) |Atribua políticas com base na associação de um usuário ao grupo. Por exemplo, atribua uma política a todos os usuários em um grupo de segurança ou lista de distribuição.| O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do Teams PowerShell|
|[Atribuir uma política a um lote de usuários](#assign-a-policy-to-a-batch-of-users)   | Atribua políticas a grandes conjuntos de usuários. Por exemplo, atribua uma política a centenas ou milhares de usuários em sua organização por vez. |O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do Teams PowerShell|
| [Atribuir um pacote de política aos usuários](#assign-a-policy-package-to-users)  |Atribua várias políticas a conjuntos específicos de usuários em sua organização que tenham funções iguais ou semelhantes. Por exemplo, atribua o pacote de política Educacional (Professor) aos professores da sua escola para que eles tenham acesso total a chats, chamada e reuniões. Atribua o pacote de política Educacional (aluno do ensino médio) a alunos secundários para limitar determinados recursos, como chamada privada.  |O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do Teams PowerShell|
| [Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização privada)   |Atribua várias políticas a um grupo de usuários em sua organização que tenham funções iguais ou semelhantes. Por exemplo, atribua um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição. |O Centro de administração do Microsoft Teams (em breve) ou cmdlets do PowerShell no módulo do Teams PowerShell|
| [Atribuir um pacote de política a um lote de usuários](#assign-a-policy-package-to-a-batch-of-users)|Atribua várias políticas a um lote de usuários em sua organização que têm funções iguais ou semelhantes. Por exemplo, atribua o pacote de política Education (Professor) a todos os professores da sua escola usando atribuição em lotes para dar a eles acesso total a chats, chamada e reuniões. Atribua o pacote de política Educacional (aluno do ensino médio) a um lote de alunos secundários para limitar determinados recursos, como chamada privada.|Cmdlets do PowerShell no módulo do Teams PowerShell|

## <a name="set-the-global-policies"></a>Definir as políticas globais

Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de política do tipo de política que você deseja atualizar. Por exemplo, políticas **do Teams**  >  **Teams,** **políticas reuniões** de reuniões, políticas de  >   **mensagens** ou políticas **de Chamada** de  >  **Voz.**
2. Selecione a **política Global (padrão em toda a organização)** para exibir as configurações atuais.
3. Atualize a política conforme necessário e selecione **Aplicar.**

### <a name="using-powershell"></a>Usando o Windows PowerShell

Para definir as políticas globais usando o PowerShell, use o identificador global.  Comece revendo a política global atual para determinar qual configuração você deseja alterar.

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

Em seguida, atualize a política Global conforme necessário.  Você só precisa especificar valores para as configurações que deseja alterar.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Atribuir uma política a usuários individuais

Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.

### <a name="use-the-microsoft-teams-admin-center"></a>Usar o Centro de administração do Microsoft Teams

Para atribuir uma política a um usuário:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Usuários** e selecione o usuário.
2. Selecione o usuário clicando à esquerda do nome de usuário e, em seguida, selecione **Editar configurações.**
3. Selecione a política que você deseja atribuir e, em seguida, selecione **Aplicar.**

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de política.
2. Selecione a política que você deseja atribuir clicando à esquerda do nome da política.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **Aplicar.**

### <a name="use-powershell"></a>Usar o PowerShell

Cada tipo de política tem seu próprio conjunto de cmdlets para gereí-lo. Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política. Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do Teams aos usuários. Esses cmdlets estão incluídos no módulo powershell do Skype for Business Online e são documentados na referência [de cmdlet](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)do Skype for Business.

 Baixe e instale o módulo do [PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) do Skype for Business Online (caso ainda não tenha feito isso) e execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.

> [!NOTE]
> No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião do Aluno a um usuário chamado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para saber mais, leia [Gerenciar políticas por meio do PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.

A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Quando você atribui a política, ela é imediatamente atribuída ao grupo. No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo. O mesmo é verdadeiro quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.

As atribuições de política de grupo são propagadas apenas para usuários que são membros diretos do grupo. As tarefas não são propagadas para membros de grupos aninhados.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>O que você precisa saber sobre a atribuição de política a grupos

Antes de começar, é importante entender as regras de precedência e a classificação da atribuição de grupo.

#### <a name="precedence-rules"></a>Regras de precedência

Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:

- Uma política atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo atribuída a um grupo. Em outras palavras, se um usuário receber diretamente uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo. Isso também significa que, se um usuário tiver uma política de um determinado tipo que foi atribuído diretamente a ele, será preciso remover essa política do usuário antes que ele possa herdar uma política do mesmo tipo de um grupo.
- Se um usuário não tiver uma política atribuída diretamente a ele e for membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuída a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.
- Se um usuário não for membro de nenhum grupo que recebe uma política, a política global (padrão de toda a organização) para esse tipo de política se aplicará ao usuário.

A política efetiva de um usuário é atualizada de acordo com estas regras:

- quando um usuário é adicionado ou removido de um grupo que recebe uma política.
- uma política não é atribuída a partir de um grupo.
- uma política atribuída diretamente ao usuário é removida.

#### <a name="group-assignment-ranking"></a>Classificação de atribuições de grupo

Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo. Isso é usado para determinar qual política um usuário deve herdar como sua política efetiva se o usuário for membro de dois ou mais grupos e cada grupo receber uma política do mesmo tipo.

A classificação da atribuição de grupo é relativa a outras atribuições de grupo do mesmo tipo. Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, de definir a classificação de uma tarefa como 1 e a outra para 2, sendo 1 a classificação mais alta. A classificação da atribuição de grupo indica qual associação ao grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.

Por exemplo, você tem dois grupos: Funcionários da Loja e Gerentes de Loja. Os dois grupos têm uma política de chamada do Teams, Política de Chamada de Funcionários da Store e Política de Chamada de Gerentes de Loja, respectivamente. Para um gerente de loja que está em ambos os grupos, sua função de gerente é mais relevante do que sua função como funcionário, portanto, a política de chamada atribuída ao grupo Gerentes de Loja deve ter uma classificação mais alta.

|Grupo |Nome da política de chamada do Teams  |Classificação|
|---------|---------|---|
|Gerentes de Loja   |Política de Chamada de Gerentes de Loja         |1|
|Armazenar Funcionários    |Política de Chamada de Funcionários da Store      |2|

Se você não especificar uma classificação, a atribuição de política será dada na classificação mais baixa.

### <a name="in-the-teams-admin-center"></a>No Centro de administração do Teams

> [!NOTE]
> Atualmente, a atribuição de política a grupos que usam o Centro de administração do Microsoft Teams só está disponível para a política de chamada do Teams, a política de parque de chamada do Teams, a política de eventos ao vivo do Teams, a política de reunião do Teams e a política de mensagens do Teams. Para outros tipos de política, use o PowerShell.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de tipo de política. Por exemplo, vá para **políticas de Reunião** de  >  **Reuniões.**
2. Selecione a **guia de atribuição de política de** grupo.
3. Selecione **Adicionar grupo** e, no painel Atribuir **política** ao grupo, faça o seguinte:
    1. Pesquise e adicione o grupo ao que você deseja atribuir a política.
    2. De definir a classificação para a atribuição de grupo.
    3. Selecione a política que você deseja atribuir.
    4. Selecione **Aplicar.**

Para remover uma atribuição  de política de grupo, na guia de atribuição de política de grupo da página de política, selecione a atribuição de grupo e, em seguida, **selecione Remover.**

Para alterar a classificação de uma atribuição de grupo, primeiro é preciso remover a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir a política a um grupo.

### <a name="use-the-powershell-option"></a>Usar a opção do PowerShell

> [!NOTE]
> Atualmente, a atribuição de política a grupos que usam o PowerShell não está disponível para todos os tipos de política do Teams. Consulte [New-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Para obter orientações passo a passo, consulte [Instalar o PowerShell do Teams.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Atribuir uma política a um grupo de usuários

Use o cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo. Você pode especificar um grupo usando a ID do objeto, o endereço SIP ou o endereço de email.

Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião de Gerentes de Varejo a um grupo com uma classificação de atribuição de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obter atribuições de política para um grupo

Use o cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo. Observe que os grupos estão sempre listados por sua ID de grupo, mesmo que seu endereço sip ou endereço de email foi usado para atribuir a política.

Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

Neste exemplo, retornamos todos os grupos que têm uma política de reunião do Teams atribuída.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Remover uma política de um grupo

Use o cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo. Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo, e que têm uma classificação inferior, são atualizadas. Por exemplo, se você remover uma política que tenha uma classificação de 2, as políticas com classificação 3 e 4 serão atualizadas para refletir sua nova classificação. As duas tabelas a seguir mostram este exemplo.

Aqui está uma lista das atribuições de política e prioridades de uma política de reunião do Teams.

|Nome do grupo  |Nome da política  |Classificação|
|---------|---------|---------|
|Vendas    |Política de vendas       | 1        |
|Região Oeste     |Política da Região Oeste         |2         |
|Divisão    |Política de divisão         |3         |
|Subsidiária   |Política de subsidiária        |4         |

Se removermos a política da Região Oeste do grupo Região Oeste, as atribuições e prioridades da política serão atualizadas da seguinte forma.

|Nome do grupo  |Nome da política  |Classificação|
|---------|---------|---------|
|Vendas    |Política de vendas       | 1        |
|Divisão    |Política de divisão         |2         |
|Subsidiária   |Política de subsidiária        |3        |

Neste exemplo, removemos a política de reunião do Teams de um grupo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Alterar uma atribuição de política para um grupo

> [!NOTE]
> O cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve. Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e adicionar uma nova atribuição de política.

Depois de atribuir uma política a um grupo, você pode usar o cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição de política desse grupo da seguinte forma:

- Alterar a classificação
- Alterar a política de um determinado tipo de política
- Alterar a política de um determinado tipo de política e a classificação

Neste exemplo, alteramos a política de parque de chamadas do Teams de um grupo para uma política chamada SupportCallPark e a classificação da tarefa para 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Alterar a política efetiva de um usuário

Veja um exemplo de como alterar a política efetiva para um usuário que recebe uma política diretamente.

Em primeiro lugar, usamos o cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) juntamente com o parâmetro para obter detalhes das políticas de transmissão de reunião do Teams associadas ```PolicySource``` ao usuário.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

A saída mostra que o usuário recebeu diretamente uma política de transmissão de reunião do Teams chamada Eventos de Funcionários, que tem precedência sobre a política chamada Eventos Ao Vivo do Fornecedor atribuída a um grupo ao qual o usuário pertence.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Agora, removemos a política Eventos de Funcionários do usuário. Isso significa que o usuário não tem mais uma política de transmissão de reunião do Teams atribuída diretamente a ele e herdará a política de Eventos Ao Vivo do Fornecedor atribuída ao grupo ao que o usuário pertence.

Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Use o cmdlet a seguir no módulo do PowerShell do Teams para fazer isso em escala, embora seja uma atribuição de política em lotes, onde o $users é uma lista de usuários que você especificar.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Atribuir uma política a um lote de usuários

### <a name="use-the-admin-center"></a>Usar o centro de administração

Para atribuir uma política aos usuários em massa:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, selecione **Usuários.**
2. Pesquise os usuários aos que você deseja atribuir a política ou filtre o exibição para mostrar os usuários que você deseja.
3. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.
4. Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar.**

Para exibir o status da atribuição de política, na  faixa exibida  na parte superior da página Usuários depois que você selecionar Aplicar para enviar sua atribuição de política, selecione Log **de atividades.** Ou, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Painel** e, em log de **atividades,** selecione **Exibir detalhes.** O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Centro de administração do Microsoft Teams dos últimos 30 dias. Para saber mais, consulte [Exibir suas atribuições de política no log de atividades.](activity-log.md)

### <a name="use-powershell-method"></a>Usar o método do PowerShell

> [!NOTE]
> Atualmente, a atribuição de política em lotes usando o PowerShell não está disponível para todos os tipos de política do Teams. Consulte [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para ver a lista de tipos de política com suporte.

Com a atribuição de política em lote, você pode atribuir uma política a grandes conjuntos de usuários por vez sem precisar usar um script. Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das atribuições em um lote.

Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol). O endereço SIP de um usuário geralmente tem o mesmo valor que o nome de usuário principal (UPN) ou o endereço de email, mas isso não é necessário. Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário. Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.

Um lote pode conter até 5.000 usuários. Para obter melhores resultados, não envie mais do que alguns lotes de cada vez. Permita que os lotes concluam o processamento antes de enviar mais lotes.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Teams

Execute o seguinte para instalar o módulo [do PowerShell do Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams) Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar e conectar-se ao módulo do PowerShell do Azure AD para Graph (opcional)

Talvez você também queira baixar e instalar o módulo do PowerShell do [Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) para Graph (se ainda não tiver feito isso) e conectar-se ao Azure AD para recuperar uma lista de usuários em sua organização.

Execute o seguinte para se conectar ao Azure AD.

```powershell
Connect-AzureAD
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Atribuir uma política de configuração a um lote de usuários

Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada Política de Configuração de Aplicativo RH a um lote de usuários listados no arquivo Users_ids.text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

Neste exemplo, nos conectamos ao Azure AD para recuperar um conjunto de usuários e atribuir uma política de mensagens chamada Nova Política de Contratação de Mensagens a um lote de usuários especificados usando seu endereço SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Obter o status de uma atribuição em lotes

Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID de operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet de um determinado lote.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>Atribuir um pacote de política aos usuários

Um pacote de política no Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm funções iguais ou semelhantes em sua organização. Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas e configurações de política predefinidas que suportam atividades típicas para essa função. Alguns exemplos de pacotes de política são o pacote Education (Professor) e o pacote Saúde (Trabalhador clínico). Para saber mais, consulte [Gerenciar pacotes de política no Teams.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Atribuir um pacote de política a um usuário

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Usuários** e selecione o usuário.
2. Na página do usuário, selecione Políticas **e,** em seguida, ao lado do pacote **de Política,** selecione **Editar.**
3. No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e, em seguida, selecione **Salvar.**

### <a name="assign-a-policy-package-to-multiple-users"></a>Atribuir um pacote de política a vários usuários

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Pacotes de política e selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.
2. Escolha **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, selecione **Salvar.**

## <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

**Este recurso está na visualização particular**

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.

A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Quando você atribui o pacote de política, ele é atribuído imediatamente ao grupo. No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo. O mesmo é verdadeiro quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.

> [!IMPORTANT]
> Antes de começar, é importante entender as regras de [precedência](#precedence-rules) e a classificação [da atribuição de grupo.](#group-assignment-ranking) Leia e entenda os conceitos [](#what-you-need-to-know-about-policy-assignment-to-groups) do que você precisa saber sobre a atribuição de política a grupos anteriormente neste artigo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Atribuir um pacote de política a um grupo de usuários no centro de administração

1. Entre no Centro de administração do Teams.
2. Na navegação à esquerda, vá para a página do pacote de política.
3. Selecione a guia de atribuição de política de grupo.
4. Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:

    a. Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.

    b. Selecione um pacote de política.

    c. Definir a classificação para cada tipo de política.

    d. Selecione **Aplicar.**

    ![mostra a atribuição de política de grupo](media/group-pkg-assignment.png)

5. Para gerenciar a classificação de um tipo de política específico, navegue até a página de política específica.
6. Para reatribuir um pacote de política a um grupo, primeiro remova a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir o pacote de política a um grupo.

### <a name="work-with-powershell"></a>Trabalhar com o PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obter o módulo do PowerShell do Teams

Para obter orientações passo a passo, consulte [Instalar o PowerShell do Teams.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Atribuir um pacote de política a um grupo de usuários

Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo. Você pode especificar um grupo usando a ID do objeto, o endereço SIP ou o endereço de email. Ao atribuir o pacote de política, especifique uma classificação de atribuição [de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política.

Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Atribuir um pacote de política a um lote de usuários

Com a atribuição de pacote de política em lotes, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script. Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das atribuições em um lote.

Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol). O endereço SIP de um usuário geralmente tem o mesmo valor que o nome de usuário principal (UPN) ou o endereço de email, mas isso não é necessário. Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário. Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.

Um lote contém até 5.000 usuários. Para obter melhores resultados, não envie mais do que alguns lotes de cada vez. Permita que os lotes concluam o processamento antes de enviar mais lotes.

### <a name="use-the-teams-powershell-module"></a>Usar o módulo do PowerShell do Teams

Execute o seguinte para instalar o módulo [do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) do Microsoft Teams (caso ainda não o tenha feito). Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Atribuir pacotes de política a um lote de usuários

Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Ver o status de uma atribuição em lotes

Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID de operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet de um determinado lote.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
