---
title: Exibir suas atribuições de política no log de atividades no Microsoft Teams de administração
author: serdars
ms.author: serdars
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como exibir suas atividades de atribuição de política no log de atividades no centro Microsoft Teams administrador.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 21caf6d694c201b12527b4be3f33856b887d177b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743077"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Exibir suas atribuições de política no log de atividades

Quando você atribui políticas aos usuários no centro de administração Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades. O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Microsoft Teams de administração dos últimos 30 dias. Lembre-se de que o log de atividades não mostra atribuições de pacote de política, atribuições de política para lotes de menos de 20 usuários por meio do centro de administração do Microsoft Teams ou atribuições de política por meio do PowerShell.

![Captura de tela da página de log atividade.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Exibir suas atividades de atribuição de política no log de atividades

Para exibir suas atribuições de política no log de atividades:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Home** e, em Seguida, em **Log** de **Atividades,** selecione Exibir detalhes .
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

- [Atribuir políticas aos usuários](policy-assignment-overview.md)
