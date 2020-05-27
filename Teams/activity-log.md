---
title: Exibir suas atribuições de política no log de atividades no centro de administração do Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como exibir suas atividades de atribuição de política no log de atividades no centro de administração do Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374289"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Exibir suas atribuições de política no registro de atividades

Ao atribuir políticas a usuários no centro de administração do Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades. O registro de atividades mostra as atribuições de política para lotes de mais de 20 usuários por meio do centro de administração do Microsoft Teams dos últimos 30 dias. Lembre-se de que o registro de atividades não mostra as atribuições de pacotes de política, atribuições de política a lotes de menos de 20 usuários por meio do centro de administração do Microsoft Teams, ou atribuições de política por meio do PowerShell.

![Captura de tela da página log de atividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Exibir suas atividades de atribuição de política no registro de atividades

Para exibir suas atribuições de política no log de atividades:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **painel**e, em **log de atividades**, selecione **Exibir detalhes**.
2. Você pode exibir todas as atribuições de política ou filtrar a lista por status para mostrar apenas as atribuições que **não foram iniciadas**, **em andamento**ou **concluídas**. Você verá as seguintes informações sobre cada tarefa:
    - **Nome**: o nome da atribuição de política. Clique no link para ver mais detalhes. Isso inclui o número de usuários aos quais a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciada. Você também verá a lista de usuários no lote e o status e o resultado de cada usuário. Veja um exemplo:

        ![Captura de tela do](media/activity-log-policy-assignment-detail.png)

    - **Enviado**: data e hora em que a atribuição da política foi enviada.
    - **Hora da conclusão**: data e hora em que a atribuição da política foi concluída.
    - **Impacto em**: número de usuários no lote.
    - **Status geral**: status da atribuição de política.

> [!NOTE]
> Você também pode acessar o log de atividades na página **usuários** . Depois de clicar em **aplicar** para enviar uma atribuição de política em massa, você verá uma faixa na parte superior da página. Clique no link do **log de atividades** na faixa.

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas a usuários](assign-policies.md)
