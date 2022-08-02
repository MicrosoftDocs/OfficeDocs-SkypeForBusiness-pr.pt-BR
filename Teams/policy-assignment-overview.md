---
title: Atribuir políticas no Teams
author: mkbond007
ms.author: mabond
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
description: Conheça as diferentes maneiras de atribuir políticas e pacotes de políticas a usuários e grupos no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3dec8bf23167c5166302942140fcfe49e9ea3720
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156509"
---
# <a name="assign-policies-in-teams--getting-started"></a>Atribuir políticas no Teams – introdução

Como administrador, você usa políticas para controlar os recursos do Teams que estão disponíveis para os usuários em sua organização. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para nomear apenas algumas.

As organizações têm diferentes tipos de usuários com necessidades exclusivas. As políticas personalizadas que você cria e atribui permitem personalizar as configurações de política para diferentes conjuntos de usuários com base nessas necessidades.

Para gerenciar facilmente as políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas aos usuários. Atribua uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lote ou a um grupo do qual os usuários são membros. Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas a usuários em sua organização que têm funções semelhantes. A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais você está atribuindo políticas. As políticas globais (padrão em toda a organização) se aplicam ao maior número de usuários em sua organização. Você só precisa atribuir políticas aos usuários que exigem políticas especializadas.

Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.

Para obter detalhes sobre como **atribuir políticas a usuários e grupos**, consulte [a atribuição de políticas a usuários e grupos](assign-policies-users-and-groups.md). Para obter detalhes sobre como atribuir **pacotes de política**, consulte [atribuir pacotes de política](assign-policy-packages.md).

## <a name="which-policy-takes-precedence"></a>Qual política tem precedência?

Um usuário tem uma política efetiva para cada tipo de política. É possível ou até mesmo provável que um usuário seja atribuído diretamente a uma política e também seja membro de um ou mais grupos que recebem uma política do mesmo tipo. Nesses tipos de cenários, qual política tem precedência? A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.

Se um usuário for atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lote), essa política terá precedência. No exemplo visual a seguir, a política efetiva do usuário é a política de reunião do Lincoln Square, que é atribuída diretamente ao usuário.

![Diagrama mostrando como uma política atribuída diretamente tem precedência.](media/assign-policies-example-directly-assigned.png)

Se um usuário não for atribuído diretamente a uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro terá precedência. Se um usuário for membro de vários grupos, a política que tiver a [maior (classificação](assign-policies-users-and-groups.md#group-assignment-ranking) de atribuição de grupo) para o tipo de política fornecido terá precedência.

Neste exemplo visual, a política efetiva do usuário é a política exec Teams e HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.  

![Diagrama mostrando como uma política herdada do grupo tem precedência.](media/assign-policies-example-group.png)

Se um usuário não for atribuído diretamente a uma política ou não for membro de nenhum grupo atribuído a uma política, o usuário obterá a política global (padrão em toda a organização) para esse tipo de política. Aqui está um exemplo visual.

![Diagrama mostrando como uma política global tem precedência.](media/assign-policies-example-global.png)

Para saber mais, confira ([Regras de precedência](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Maneiras de atribuir políticas

Aqui está uma visão geral das maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para cada um. Selecione os links para saber mais.

Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas globais (padrão em toda a organização [)](#set-the-global-policies) para que elas se apliquem ao maior número de usuários em sua organização.  Depois que as políticas globais forem definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.

|Faça isso  |Se...  | Usando...
|---------|---------|----|
|[Atribuir uma política a usuários individuais](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Você é novo no Teams e está apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários. |O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo PowerShell do Teams
|[Atribuir uma política a um grupo](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Atribua políticas com base na associação de grupo de um usuário. Por exemplo, atribua uma política a todos os usuários em um grupo de segurança ou lista de distribuição.| O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo PowerShell do Teams|
|[Atribuir uma política a um lote de usuários](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Atribua políticas a grandes conjuntos de usuários. Por exemplo, atribua uma política a centenas ou milhares de usuários em sua organização por vez. |O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo PowerShell do Teams|
|[Atribuir um pacote de política aos usuários](assign-policy-packages.md#assign-a-policy-package-to-users)  |Atribua várias políticas a conjuntos específicos de usuários em sua organização que têm funções iguais ou semelhantes. Por exemplo, atribua o pacote de políticas de Educação (Professor) aos professores da sua escola para dar a eles acesso completo a chats, chamadas e reuniões. Atribua o pacote de políticas de Educação (estudante do ensino médio) a alunos secundários para limitar determinados recursos, como chamadas privadas.  |O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo PowerShell do Teams|
|[Atribua o pacote de política a um grupo.](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |Atribua várias políticas a um grupo de usuários em sua organização que têm funções iguais ou semelhantes. Por exemplo, atribua um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição. |O centro de administração do Microsoft Teams (em breve) ou os cmdlets do PowerShell no módulo powershell do Teams|
|[Atribuir um pacote de política a um lote de usuários](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Atribua várias políticas a um lote de usuários em sua organização que têm funções iguais ou semelhantes. Por exemplo, atribua o pacote de políticas de Educação (Professor) a todos os professores em sua escola usando a atribuição em lote para dar a eles acesso completo a chats, chamadas e reuniões. Atribua o pacote de políticas de Educação (aluno secundário) a um lote de alunos secundários para limitar determinadas funcionalidades, como chamada privada.|Cmdlets do PowerShell no módulo PowerShell do Teams|

> [!NOTE]
> Para cancelar a atribuição de políticas, você pode remover atribuições em massa para todos os usuários atribuídos diretamente a uma política. Para saber mais, leia [Cancelar a atribuição de políticas em massa](assign-policies-users-and-groups.md#unassign-policies-in-bulk).

## <a name="set-the-global-policies"></a>Definir as políticas globais

Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para a página de política do tipo de política que você deseja atualizar. Por exemplo, políticas **do Teams** > **Teams**, **políticas de Reuniões** > **,** **Políticas de mensagens** ou **políticas de Chamada** > **de Voz**.
2. Selecione a **política Global (padrão em toda a organização)** para exibir as configurações atuais.
3. Atualize a política conforme necessário e selecione **Aplicar**.

![Atualize a política global no Centro de administração do Teams.](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>Usando o Windows PowerShell

Para definir as políticas globais usando o PowerShell, use o identificador global.  Comece examinando a política global atual para determinar qual configuração você deseja alterar.

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

Em seguida, atualize a política global conforme necessário.  Você só precisa especificar valores para as configurações que deseja alterar.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Exibir suas atribuições de política no log de atividades

Ao atribuir políticas a usuários no Centro de administração do Microsoft Teams, você pode exibir o status dessas atribuições de política no [log de atividades](https://admin.teams.microsoft.com/activitylog). O log de atividades mostra informações de upload de registro de rede, operações de política de grupo do Centro de administração do Teams e do PowerShell e operações de política em lote (para mais de 20 usuários) do centro de administração do Teams, nos últimos 30 dias.

![Captura de tela da página Log de atividades.](media/Activity_Log.png)

Para exibir suas operações de política no log de atividades:

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para **Painel** e, em **Log** de Atividades, selecione **Exibir detalhes**.
2. Você verá as seguintes informações sobre cada operação de política:
    - **Atividade**: o nome da operação de política. Por exemplo: **atribuição de política de grupo**
    - **Nome do** grupo: o nome do grupo no qual a operação de política foi concluída.
    - **Tipo de** política: o tipo de política.
    - **Nome da** política: o nome da operação de política. Para atribuições de política de lote, você pode selecionar o link para exibir mais detalhes. Isso inclui o número de usuários aos quais a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciadas. Você também verá a lista de usuários no lote e o status e o resultado de cada usuário.
    - **Enviado por**: o nome do usuário que enviou a operação de política.
    - **Enviado em**: data e hora em que a operação de política foi enviada.
    - **Concluído em**: data e hora em que a operação de política foi concluída.
    - **Afetado:** número de usuários no lote ou grupo.
    - **Status geral**: status da operação de política. Uma política pode ter um dos seguintes status:
        - **Não iniciado**: a operação de política foi enviada pelo administrador.
        - **Em andamento**: a operação de política iniciou o processamento.
        - **Distribuição para usuários**: o sistema começou a aplicar a atualização de política aos usuários.
        - **Concluído**: a atualização da política foi aplicada a todos os usuários.
        - **Concluído com erros 'x'**: a operação de política foi concluída, mas há erros.

> [!NOTE]
> Você também pode acessar o Log de atividades na **página** Usuários. Depois de selecionar **Aplicar** para enviar uma atribuição de política em massa, você verá uma faixa na parte superior da página. Selecione o link **do log de** atividades na faixa.

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas a usuários e grupos](assign-policies-users-and-groups.md)
- [Atribuir pacotes de políticas a usuários e grupos](assign-policy-packages.md)
- [Gerenciar o Teams com políticas](manage-teams-with-policies.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
