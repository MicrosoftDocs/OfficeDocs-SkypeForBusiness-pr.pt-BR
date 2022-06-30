---
title: Exibir suas atribuições de política no log de atividades no Centro de administração do Microsoft Teams
ms.author: mabond
author: mkbond007
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como exibir suas atividades de atribuição de política no log de atividades no centro de administração do Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562210"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Exibir suas atribuições de política no log de atividades

Ao atribuir políticas a usuários no Centro de administração do Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades. O log de atividades mostra atribuições de política a lotes de mais de 20 usuários por meio do Centro de administração do Microsoft Teams dos últimos 30 dias. Tenha em mente que o log de atividades não mostra atribuições de pacote de política, atribuições de política para lotes de menos de 20 usuários por meio do centro de administração do Microsoft Teams ou atribuições de política por meio do PowerShell.

![Captura de tela da página Log de atividades.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Exibir suas atividades de atribuição de política no log de atividades

Para exibir suas atribuições de política no log de atividades:

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para Página Inicial **e, em** **Log** de Atividades, selecione **Exibir detalhes**.
2. Você pode exibir todas as atribuições de política ou filtrar a lista por status para mostrar apenas as atribuições que não foram iniciadas **, em** **andamento ou** **concluídas**. Você verá as seguintes informações sobre cada atribuição:
    - **Nome**: o nome da atribuição de política. Clique no link para exibir mais detalhes. Isso inclui o número de usuários aos quais a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciadas. Você também verá a lista de usuários no lote e o status e o resultado de cada usuário. Veja um exemplo:

        ![Captura de tela do.](media/activity-log-policy-assignment-detail.png)

    - **Enviado**: data e hora em que a atribuição de política foi enviada.
    - **Hora de conclusão**: data e hora em que a atribuição de política foi concluída.
    - **Impacto em**: número de usuários no lote.
    - **Status geral**: status da atribuição de política.

> [!NOTE]
> Você também pode acessar o Log de atividades na **página** Usuários. Depois de clicar **em Aplicar** para enviar uma atribuição de política em massa, você verá uma faixa na parte superior da página. Clique no link **log de** atividades na faixa.

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](policy-assignment-overview.md)
