---
title: Atribuir políticas aos usuários no Microsoft Teams
author: cichur
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba as diferentes maneiras de atribuir políticas aos usuários em Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: e29ee61183b0c831fc6d638bf20e6edaab050e8e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760549"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Atribuir políticas aos usuários no Microsoft Teams

Como administrador, você usa políticas para controlar os recursos Teams que estão disponíveis para os usuários em sua organização. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para nomear apenas algumas.

As organizações têm diferentes tipos de usuários com necessidades exclusivas. As políticas personalizadas que você cria e atribui permitem que você adapte as configurações de política a diferentes conjuntos de usuários com base nessas necessidades.

Para gerenciar facilmente as políticas em sua organização, Teams oferece várias maneiras de atribuir políticas aos usuários. Atribua uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lotes ou a um grupo do que os usuários são membros. Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas a usuários em sua organização que tenham funções semelhantes. A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais você está atribuindo políticas. As políticas globais (padrão em toda a organização) se aplicam ao maior número de usuários em sua organização. Você só precisa atribuir políticas a esses usuários que exigem políticas especializadas.

Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.

## <a name="which-policy-takes-precedence"></a>Qual política tem precedência?

Um usuário tem uma política efetiva para cada tipo de política. É possível, ou mesmo provável, que um usuário tenha uma política atribuída diretamente e também seja membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo. Nesses tipos de cenários, qual política tem precedência? A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.

Se um usuário for atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência. No exemplo visual a seguir, a política efetiva do usuário é a política de reunião do Quadrado do Lincoln, que é atribuída diretamente ao usuário.

![Diagrama mostrando como uma política atribuída diretamente tem precedência.](media/assign-policies-example-directly-assigned.png)

Se um usuário não receber diretamente uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro tem precedência. Se um usuário for membro de vários grupos, [](#group-assignment-ranking) a política com a classificação de atribuição de grupo mais alta para o tipo de política determinado terá precedência.

Neste exemplo visual, a política efetiva do usuário é a política Teams e HD do Exec, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.  

![Diagrama mostrando como uma política herdada do grupo tem precedência.](media/assign-policies-example-group.png)

Se um usuário não recebe uma política diretamente ou não é membro de nenhum grupo atribuído a uma política, o usuário obtém a política global (padrão em toda a organização) para esse tipo de política. Veja um exemplo visual.

![Diagrama mostrando como uma política global tem precedência.](media/assign-policies-example-global.png)

Para saber mais, confira [Regras de precedência.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Maneiras de atribuir políticas

Aqui está uma visão geral das maneiras pelas quais você pode atribuir políticas aos usuários e aos cenários recomendados para cada um. Selecione os links para saber mais.

Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas [globais (padrão](#set-the-global-policies) em toda a organização) para que elas se apliquem ao maior número de usuários em sua organização.  Depois que as políticas globais são definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.

|Faça isso  |Se...  | Usando...
|---------|---------|----|
|[Atribuir uma política a usuários individuais](#assign-a-policy-to-individual-users)    | Você é novo no Teams e apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários. |O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell
|[Atribuir uma política a um grupo](#assign-a-policy-to-a-group) |Atribua políticas com base na associação de grupo de um usuário. Por exemplo, atribua uma política a todos os usuários em um grupo de segurança ou lista de distribuição.| O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell|
|[Atribuir uma política a um lote de usuários](#assign-a-policy-to-a-batch-of-users)   | Atribua políticas a grandes conjuntos de usuários. Por exemplo, atribua uma política a centenas ou milhares de usuários em sua organização por vez. |O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell|
| [Atribuir um pacote de política aos usuários](#assign-a-policy-package-to-users)  |Atribua várias políticas a conjuntos específicos de usuários em sua organização que tenham as mesmas funções ou funções semelhantes. Por exemplo, atribua o pacote de política Educação (Professor) aos professores em sua escola para dar a eles acesso total a chats, chamada e reuniões. Atribua o pacote de política educação (estudante secundário) a alunos secundários para limitar determinados recursos, como chamada privada.  |O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell|
| [Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização privada)   |Atribua várias políticas a um grupo de usuários em sua organização que tenham as mesmas funções ou funções semelhantes. Por exemplo, atribua um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição. |O Microsoft Teams de administração (em breve) ou cmdlets do PowerShell no módulo Teams PowerShell|
| [Atribuir um pacote de política a um lote de usuários](#assign-a-policy-package-to-a-batch-of-users)|Atribua várias políticas a um lote de usuários em sua organização que tenham as mesmas funções ou funções semelhantes. Por exemplo, atribua o pacote de política Educação (Professor) a todos os professores em sua escola usando a atribuição em lotes para dar a eles acesso total a chats, chamada e reuniões. Atribua o pacote de política educação (estudante secundário) a um lote de alunos secundários para limitar determinados recursos, como chamada privada.|Cmdlets do PowerShell no módulo Teams PowerShell|

## <a name="set-the-global-policies"></a>Definir as políticas globais

Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página de política para o tipo de política que você deseja atualizar. Por exemplo, **Teams**  >  **Teams** políticas, políticas   >  **de Reuniões,** políticas **de** mensagens ou políticas **de Chamada** de  >  **Voz.**
2. Selecione a **política Global (padrão em toda** a organização) para exibir as configurações atuais.
3. Atualize a política conforme necessário e selecione **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Para definir as políticas globais usando o PowerShell, use o identificador Global.  Comece revendo a política global atual para determinar qual configuração você deseja alterar.

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

### <a name="use-the-microsoft-teams-admin-center"></a>Usar o Microsoft Teams de administração

Para atribuir uma política a um usuário:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários** e selecione o usuário.
2. Selecione o usuário clicando à esquerda do nome do usuário e selecione **Editar configurações**.
3. Selecione a política que deseja atribuir e selecione **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página de política.
2. Selecione a política que você deseja atribuir clicando à esquerda do nome da política.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **Aplicar**.

### <a name="use-powershell"></a>Usar o PowerShell

Cada tipo de política tem seu próprio conjunto de cmdlets para gere-lo. Use o `Grant-` cmdlet para um determinado tipo de política para atribuir a política. Por exemplo, use o `Grant-CsTeamsMeetingPolicy` cmdlet para atribuir uma Teams de reunião aos usuários. Esses cmdlets estão incluídos no módulo Teams PowerShell e estão documentados na referência Skype for Business [cmdlet .](/powershell/skype/intro?view=skype-ps&preserve-view=true)

Baixe e instale o Teams versão pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (caso ainda não tenha feito isso) e execute o seguinte para se conectar.

> [!NOTE]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

Neste exemplo, atribuímos uma política de reunião Teams chamada Diretiva de Reunião de Alunos a um usuário chamado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para saber mais, leia [Gerenciar políticas por meio do PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Atribuir uma política a um grupo

A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.

A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Quando você atribui a política, ela é imediatamente atribuída ao grupo. No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo. O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.

As atribuições de política de grupo são propagadas apenas para usuários que são membros diretos do grupo. As atribuições não são propagadas para membros de grupos aninhados.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>O que você precisa saber sobre a atribuição de política a grupos

Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.

#### <a name="precedence-rules"></a>Regras de precedência

Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:

- Uma política atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo atribuída a um grupo. Em outras palavras, se um usuário receber diretamente uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo. Isso também significa que, se um usuário tiver uma política de um determinado tipo atribuído diretamente a ele, você terá que remover essa política do usuário antes que ele possa herdar uma política do mesmo tipo de um grupo.

- Se um usuário não tiver uma política atribuída diretamente a ele e for membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ela, o usuário herdará a política da atribuição de grupo com a classificação mais alta.

- Se um usuário não for membro de nenhum grupo atribuído a uma política, a política global (padrão em toda a organização) para esse tipo de política se aplica ao usuário.

A política efetiva de um usuário é atualizada de acordo com estas regras:

- quando um usuário é adicionado ou removido de um grupo atribuído a uma política.
- uma política não é atribuída a partir de um grupo.
- uma política atribuída diretamente ao usuário é removida.

#### <a name="group-assignment-ranking"></a>Classificação de atribuição de grupo

Quando você atribui uma política a um grupo, especifica uma classificação para a atribuição de grupo. Isso é usado para determinar qual política um usuário deve herdar como sua política efetiva se o usuário for membro de dois ou mais grupos e cada grupo receber uma política do mesmo tipo.

A classificação de atribuição de grupo é relativa a outras atribuições de grupo do mesmo tipo. Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, de definir a classificação de uma atribuição como 1 e a outra como 2, sendo 1 a classificação mais alta. A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.

Por exemplo, você tem dois grupos, Funcionários da Loja e Gerentes da Loja. Ambos os grupos são atribuídos a uma política de Teams de chamada, a Política de Chamada de Funcionários da Loja e a Política de Chamada de Gerentes de Loja, respectivamente. Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que sua função como funcionário, portanto, a política de chamada atribuída ao grupo Gerentes de Loja deve ter uma classificação mais alta.

|Grupo |Teams nome da política de chamada  |Classificação|
|---------|---------|---|
|Gerentes da Loja   |Política de Chamada de Gerentes de Loja         |1|
|Funcionários da Loja    |Política de Chamada de Funcionários da Loja      |2|

Se você não especificar uma classificação, a atribuição de política recebe a classificação mais baixa.

### <a name="in-the-teams-admin-center"></a>No centro de Teams de administração

> [!NOTE]
> Atualmente, a atribuição de política para grupos usando o centro de administração do Microsoft Teams está disponível apenas para a política de chamada do Teams, a política de estacionamento de chamada do Teams, Teams política de Teams, Teams política de eventos ao vivo, Teams política de reunião e Teams de mensagens. Para outros tipos de política, use o PowerShell.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página tipo de política. Por exemplo, vá para **Políticas de Reunião** de  >  **Reuniões.**

2. Selecione a **guia Atribuição de política de** grupo.

3. Selecione **Adicionar grupo** e, em seguida, no painel Atribuir **política** ao grupo, faça o seguinte:
    1. Pesquise e adicione o grupo ao que você deseja atribuir a política.
    2. De definir a classificação para a atribuição de grupo.
    3. Selecione a política que você deseja atribuir.
    4. Selecione **Aplicar**.

Para remover uma atribuição de política de grupo, na **guia** Atribuição de política de grupo da página de política, selecione a atribuição de grupo e selecione **Remover**.

Para alterar a classificação de uma atribuição de grupo, você precisa primeiro remover a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir a política a um grupo.

### <a name="use-the-powershell-option"></a>Usar a opção PowerShell

> [!NOTE]
> Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos Teams de política. Consulte [New-CsGroupPolicyAssignment para](/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar ao módulo Microsoft Teams PowerShell

Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group-of-users"></a>Atribuir uma política a um grupo de usuários

Use o cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo. Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email.

Neste exemplo, atribuímos uma política de reunião Teams chamada Política de Reunião de Gerentes de Varejo a um grupo com uma classificação de atribuição de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obter atribuições de política para um grupo

Use o cmdlet [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo. Observe que os grupos sempre são listados pela ID do grupo, mesmo que seu endereço SIP ou endereço de email seja usado para atribuir a política.

Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

Neste exemplo, retornamos todos os grupos que são atribuídos a uma Teams de reunião.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Remover uma política de um grupo

Use o cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo. Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuído a esse grupo, e que têm uma classificação mais baixa, são atualizadas. Por exemplo, se você remover uma política que tenha uma classificação de 2, as políticas que têm uma classificação de 3 e 4 serão atualizadas para refletir sua nova classificação. As duas tabelas a seguir mostram este exemplo.

Aqui está uma lista das atribuições de política e prioridades para uma Teams de reunião.

|Nome do grupo  |Nome da política  |Classificação|
|---------|---------|---------|
|Vendas    |Política de vendas       | 1        |
|Região Oeste     |Política da Região Oeste         |2         |
|Division    |Política de divisão         |3         |
|Subsidiária   |Política de subsidiária        |4         |

Se removermos a política da Região Oeste do grupo da Região Oeste, as atribuições e prioridades de política serão atualizadas da seguinte forma.

|Nome do grupo  |Nome da política  |Classificação|
|---------|---------|---------|
|Vendas    |Política de vendas       | 1        |
|Division    |Política de divisão         |2         |
|Subsidiária   |Política de subsidiária        |3        |

Neste exemplo, removemos a política Teams reunião de um grupo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Alterar uma atribuição de política para um grupo

> [!NOTE]
> O cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve. Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e adicionar uma nova atribuição de política.

Depois de atribuir uma política a um grupo, você pode usar o cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição de política desse grupo da seguinte forma:

- Alterar a classificação
- Alterar a política de um determinado tipo de política
- Alterar a política de um determinado tipo de política e a classificação

Neste exemplo, alteramos a política de estacionamento de chamada Teams grupo para uma política chamada SupportCallPark e a classificação de atribuição como 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Alterar a política efetiva para um usuário

Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.

Primeiro, usamos o cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) juntamente com o parâmetro para obter detalhes das políticas de transmissão de reunião Teams associadas ao ```PolicySource``` usuário.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

A saída mostra que o usuário recebeu diretamente uma política de transmissão de reunião Teams chamada Eventos de Funcionários, que tem precedência sobre a política chamada Vendor Live Events atribuída a um grupo ao qual o usuário pertence.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Agora, removemos a política Eventos de Funcionários do usuário. Isso significa que o usuário não tem mais uma política de transmissão de reunião Teams atribuída diretamente a ele e herdará a política eventos ao vivo do fornecedor atribuída ao grupo ao que o usuário pertence.

Use o seguinte cmdlet no módulo Skype for Business PowerShell para fazer isso.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Use o seguinte cmdlet no módulo Teams PowerShell para fazer isso em escala, embora uma atribuição de política em lote, onde $users é uma lista de usuários que você especificar.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Atribuir uma política a um lote de usuários

### <a name="use-the-admin-center"></a>Usar o centro de administração

Para atribuir uma política aos usuários em massa:

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Usuários**.

2. Pesquise os usuários aos que você deseja atribuir a política ou filtre a exibição para mostrar os usuários que você deseja.

3. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.

4. Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar**.

Para exibir o status da atribuição de política, na  faixa que  aparece na parte superior da página Usuários depois de selecionar Aplicar para enviar sua atribuição de política, selecione Log **de atividades.** Ou, na navegação à esquerda do centro de administração Microsoft Teams, vá para **Painel** e, em log de **atividades,** selecione **Exibir detalhes**. O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Microsoft Teams de administração dos últimos 30 dias. Para saber mais, confira [Exibir suas atribuições de política no log de atividades](activity-log.md).

### <a name="use-powershell-method"></a>Usar o método PowerShell

> [!NOTE]
> Atualmente, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos Teams de política. Consulte [New-CsBatchPolicyAssignmentOperation para](/powershell/module/teams/new-csbatchpolicyassignmentoperation) ver a lista de tipos de política com suporte.

Com a atribuição de política em lote, você pode atribuir uma política a grandes conjuntos de usuários por vez sem precisar usar um script. Você usa o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.

Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol). O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário. Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário. Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.

Um lote pode conter até 5.000 usuários. Para obter melhores resultados, não envie mais de alguns lotes por vez. Permitir que lotes concluam o processamento antes de enviar mais lotes.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Instalar e conectar ao módulo Teams PowerShell

Execute o seguinte para instalar o [módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar e conectar ao PowerShell do Azure AD para Graph módulo (opcional)

Talvez você também queira baixar e instalar o módulo do [Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) para Graph (se ainda não o fez) e se conectar ao Azure AD para poder recuperar uma lista de usuários em sua organização.

Execute o seguinte para se conectar ao Azure AD.

```powershell
Connect-AzureAD
```

Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Atribuir uma política de instalação a um lote de usuários

Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada Política de Configuração de Aplicativo de RH a um lote de usuários listados no arquivo Users_ids.text.

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

Neste exemplo, nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada New Hire Messaging Policy a um lote de usuários especificado usando seu endereço SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Obter o status de uma atribuição em lotes

Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo `New-CsBatchPolicyAssignmentOperation` cmdlet para um determinado lote.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na `UserState` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-package-to-users"></a>Atribuir um pacote de política aos usuários

Um pacote de política no Teams é uma coleção de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm as mesmas funções ou funções semelhantes em sua organização. Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam atividades típicas para essa função. Alguns exemplos de pacotes de política são o pacote Educação (Professor) e o pacote Assistência Médica (Trabalho Médico). Para saber mais, confira [Gerenciar pacotes de política em Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Atribuir um pacote de política a um usuário

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários** e selecione o usuário.

2. Na página do usuário, selecione **Políticas** e, ao lado de **Pacote de Política,** selecione **Editar**.

3. No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e selecione **Salvar**.

### <a name="assign-a-policy-package-to-multiple-users"></a>Atribuir um pacote de política a vários usuários

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Pacotes de Política **e** selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.

2. Escolha **Gerenciar usuários**.

3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.

4. Quando terminar de adicionar usuários, selecione **Salvar**.

## <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.

A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Quando você atribui o pacote de política, ele é imediatamente atribuído ao grupo. No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo. O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.

> [!IMPORTANT]
> Antes de começar, é importante entender as regras [de precedência](#precedence-rules) e a classificação [de atribuição de grupo.](#group-assignment-ranking) Leia e entenda os conceitos em [O que você precisa](#what-you-need-to-know-about-policy-assignment-to-groups) saber sobre a atribuição de política a grupos anteriormente neste artigo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Atribuir um pacote de política a um grupo de usuários no centro de administração

1. Entre no Centro de administração do Teams.
2. Na navegação à esquerda, vá para a página pacote de política.
3. Selecione a guia Atribuição de pacote de grupo.
4. Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:

   - Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.

2. Na navegação à esquerda, vá para a página pacote de política.

3. Selecione a guia Atribuição de política de grupo.

4. Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:

    1. Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.
    
    1. Selecione um pacote de política.
    
    1. De definir a classificação para cada tipo de política.
    
    1. Selecione **Aplicar**.
    
    ![mostra a atribuição de política de grupo.](media/group-pkg-assignment.png)

5. Para gerenciar a classificação de um tipo de política específico, navegue até a página de política específica.

6. Para reatribuir um pacote de política a um grupo, primeiro remova a atribuição de política de grupo. Em seguida, siga as etapas acima para atribuir o pacote de política a um grupo.

### <a name="work-with-powershell"></a>Trabalhar com o PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obter o módulo Teams PowerShell

Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Atribuir um pacote de política a um grupo de usuários

Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo. Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email. Ao atribuir o pacote de política, especifique uma classificação de atribuição [de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política.

Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Atribuir um pacote de política a um lote de usuários

Com a atribuição de pacote de política em lote, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script. Use o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.

Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol). O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário. Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário. Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.

Um lote contém até 5.000 usuários. Para obter melhores resultados, não envie mais de alguns lotes por vez. Permitir que lotes concluam o processamento antes de enviar mais lotes.

### <a name="use-the-teams-powershell-module"></a>Usar o módulo Teams PowerShell

Execute o seguinte para instalar o [Microsoft Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (caso ainda não tenha feito isso). Instale a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Atribuir pacotes de política a um lote de usuários

Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Consulte o status de uma atribuição em lotes

Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo `New-CsBatchPolicyAssignmentOperation` cmdlet para um determinado lote.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na `UserState` propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
