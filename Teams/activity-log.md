---
title: Exibir suas atribuições de política no log de atividades no Centro de administração do Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como exibir suas atividades de atribuição de política no log de atividades no Centro de administração do Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821311"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Exibir suas atribuições de política no log de atividades

Ao atribuir políticas aos usuários no Centro de administração do Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades. O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Centro de administração do Microsoft Teams dos últimos 30 dias. Lembre-se de que o log de atividades não mostra atribuições de pacote de política, atribuições de política para lotes com menos de 20 usuários por meio do Centro de administração do Microsoft Teams ou atribuições de política por meio do PowerShell.

![Captura de tela da página do log de atividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Exibir suas atividades de atribuição de política no log de atividades

Para exibir suas atribuições de política no log de atividades:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Painel** e, em Log de **Atividades,** selecione **Exibir detalhes.**
2. Você pode exibir todas as atribuições de política ou filtrar a lista por status para mostrar apenas as tarefas que não foram **iniciadas,** em andamento **ou** **concluídas.** Você verá as seguintes informações sobre cada tarefa:
    - **Nome:** o nome da atribuição de política. Clique no link para exibir mais detalhes. Isso inclui o número de usuários aos que a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciadas. Você também verá a lista de usuários no lote, o status e o resultado de cada usuário. Veja um exemplo:

        ![Captura de tela da](media/activity-log-policy-assignment-detail.png)

    - **Enviado:** Data e hora em que a atribuição de política foi enviada.
    - **Hora de conclusão:** data e hora em que a atribuição de política foi concluída.
    - **Impacto em:** Número de usuários no lote.
    - **Status geral:** Status da atribuição de política.

> [!NOTE]
> Você também pode acessar o log de atividades na **página** Usuários. Depois de clicar **em Aplicar** para enviar uma atribuição de política em massa, você verá uma faixa na parte superior da página. Clique no link **do log de** atividades na faixa.

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](assign-policies.md)
