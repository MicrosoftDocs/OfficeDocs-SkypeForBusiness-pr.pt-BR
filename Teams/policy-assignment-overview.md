---
title: Atribuir políticas em Teams
author: KarliStites
ms.author: kastites
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
description: Saiba as diferentes maneiras de atribuir políticas e pacotes de política a usuários e grupos em Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: e17b468d2c3336dd6b34d0574b7a7c4e7c069186
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731050"
---
# <a name="assign-policies-in-teams--getting-started"></a>Atribuir políticas em Teams – iniciando

Como administrador, você usa políticas para controlar os recursos Teams que estão disponíveis para os usuários em sua organização. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para nomear apenas algumas.

As organizações têm diferentes tipos de usuários com necessidades exclusivas. As políticas personalizadas que você cria e atribui permitem que você adapte as configurações de política a diferentes conjuntos de usuários com base nessas necessidades.

Para gerenciar facilmente as políticas em sua organização, Teams oferece várias maneiras de atribuir políticas aos usuários. Atribua uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lotes ou a um grupo do que os usuários são membros. Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas a usuários em sua organização que tenham funções semelhantes. A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais você está atribuindo políticas. As políticas globais (padrão em toda a organização) se aplicam ao maior número de usuários em sua organização. Você só precisa atribuir políticas a esses usuários que exigem políticas especializadas.

Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.

Para obter detalhes sobre como **atribuir políticas a usuários e grupos,** consulte [assigning policies to users and groups](assign-policies-users-and-groups.md). Para obter detalhes sobre como atribuir **pacotes de política,** consulte [assign policy packages](assign-policy-packages.md).

## <a name="which-policy-takes-precedence"></a>Qual política tem precedência?

Um usuário tem uma política efetiva para cada tipo de política. É possível, ou mesmo provável, que um usuário tenha uma política atribuída diretamente e também seja membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo. Nesses tipos de cenários, qual política tem precedência? A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.

Se um usuário for atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência. No exemplo visual a seguir, a política efetiva do usuário é a política de reunião do Quadrado do Lincoln, que é atribuída diretamente ao usuário.

![Diagrama mostrando como uma política atribuída diretamente tem precedência.](media/assign-policies-example-directly-assigned.png)

Se um usuário não receber diretamente uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro tem precedência. Se um usuário for membro de vários grupos, a política que tiver a maior[(](assign-policies-users-and-groups.md#group-assignment-ranking)classificação de atribuição de grupo ) para o tipo de política determinado terá precedência.

Neste exemplo visual, a política efetiva do usuário é a política Teams e HD do Exec, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.  

![Diagrama mostrando como uma política herdada do grupo tem precedência.](media/assign-policies-example-group.png)

Se um usuário não recebe uma política diretamente ou não é membro de nenhum grupo atribuído a uma política, o usuário obtém a política global (padrão em toda a organização) para esse tipo de política. Veja um exemplo visual.

![Diagrama mostrando como uma política global tem precedência.](media/assign-policies-example-global.png)

Para saber mais, confira ([Regras de precedência](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Maneiras de atribuir políticas

Aqui está uma visão geral das maneiras pelas quais você pode atribuir políticas aos usuários e aos cenários recomendados para cada um. Selecione os links para saber mais.

Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas [globais (padrão](#set-the-global-policies) em toda a organização) para que elas se apliquem ao maior número de usuários em sua organização.  Depois que as políticas globais são definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.

|Faça isso  |Se...  | Usando...
|---------|---------|----|
|[Atribuir uma política a usuários individuais](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Você é novo no Teams e apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários. |O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell
|[Atribuir uma política a um grupo](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Atribua políticas com base na associação de grupo de um usuário. Por exemplo, atribua uma política a todos os usuários em um grupo de segurança ou lista de distribuição.| O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell|
|[Atribuir uma política a um lote de usuários](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Atribua políticas a grandes conjuntos de usuários. Por exemplo, atribua uma política a centenas ou milhares de usuários em sua organização por vez. |O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell|
|[Atribuir um pacote de política aos usuários](assign-policy-packages.md#assign-a-policy-package-to-users)  |Atribua várias políticas a conjuntos específicos de usuários em sua organização que tenham as mesmas funções ou funções semelhantes. Por exemplo, atribua o pacote de política Educação (Professor) aos professores em sua escola para dar a eles acesso total a chats, chamada e reuniões. Atribua o pacote de política educação (estudante secundário) a alunos secundários para limitar determinados recursos, como chamada privada.  |O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell|
|[Atribuir um pacote de política a um grupo](assign-policy-packages.md#assign-a-policy-package-to-a-group) (em visualização privada)   |Atribua várias políticas a um grupo de usuários em sua organização que tenham as mesmas funções ou funções semelhantes. Por exemplo, atribua um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição. |O Microsoft Teams de administração (em breve) ou cmdlets do PowerShell no módulo Teams PowerShell|
|[Atribuir um pacote de política a um lote de usuários](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Atribua várias políticas a um lote de usuários em sua organização que tenham as mesmas funções ou funções semelhantes. Por exemplo, atribua o pacote de política Educação (Professor) a todos os professores em sua escola usando a atribuição em lotes para dar a eles acesso total a chats, chamada e reuniões. Atribua o pacote de política educação (estudante secundário) a um lote de alunos secundários para limitar determinados recursos, como chamada privada.|Cmdlets do PowerShell no módulo Teams PowerShell|

## <a name="set-the-global-policies"></a>Definir as políticas globais

Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página de política para o tipo de política que você deseja atualizar. Por exemplo, **Teams**  >  **Teams** políticas, políticas   >  **de Reuniões,** políticas **de** mensagens ou políticas **de Chamada** de  >  **Voz.**
2. Selecione a **política Global (padrão em toda** a organização) para exibir as configurações atuais.
3. Atualize a política conforme necessário e selecione **Aplicar**.

![Atualize a política global Teams centro de administração.](media/assign-globalpolicy.png)

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

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Exibir suas atribuições de política no log de atividades

Quando você atribui políticas aos usuários no centro de administração Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades. O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Microsoft Teams de administração dos últimos 30 dias. Lembre-se de que o log de atividades não mostra atribuições de pacote de política, atribuições de política para lotes de menos de 20 usuários por meio do centro de administração do Microsoft Teams ou atribuições de política por meio do PowerShell.

![Captura de tela da página de log atividade.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Exibir suas atividades de atribuição de política no log de atividades

Para exibir suas atribuições de política no log de atividades:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Painel** e, em Seguida, em **Log** de **Atividades,** selecione Exibir detalhes .
2. Você pode exibir todas as atribuições de política ou filtrar a lista por status para mostrar apenas as atribuições não iniciadas **,** em andamento **ou** **concluídas.** Você verá as seguintes informações sobre cada atribuição:
    - **Nome**: o nome da atribuição de política. Clique no link para exibir mais detalhes. Isso inclui o número de usuários aos que a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciadas. Você também verá a lista de usuários no lote e o status e o resultado para cada usuário. Veja um exemplo:

        ![Captura de tela do.](media/activity-log-policy-assignment-detail.png)

    - **Enviado**: Data e hora em que a atribuição de política foi enviada.
    - **Tempo de conclusão**: Data e hora em que a atribuição de política foi concluída.
    - **Impacto em**: Número de usuários no lote.
    - **Status geral**: Status da atribuição de política.

> [!NOTE]
> Você também pode acessar o log atividade na **página Usuários.** Depois de clicar **em Aplicar** para enviar uma atribuição de política em massa, você verá um banner na parte superior da página. Clique no link **Log de** atividades no banner.

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas a usuários e grupos](assign-policies-users-and-groups.md)
- [Atribuir pacotes de política a usuários e grupos](assign-policy-packages.md)
- [Gerenciar Teams com políticas](manage-teams-with-policies.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)