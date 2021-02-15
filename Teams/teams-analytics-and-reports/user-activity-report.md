---
title: Relatório de atividades do usuário do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de atividades do usuário do Teams no Centro de administração do Microsoft Teams para ver como os usuários em sua organização estão usando o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f02d2f8751b8059f435164158d5c97fb6766a286
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196905"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório atividade do usuário do Teams fornece informações sobre os tipos de atividades que os usuários em sua organização fazem no Teams. Você pode ver quantos usuários se comunicam de forma não planejada por meio de reuniões não agendadas (1:1 e chamadas em grupo). Veja em quantas reuniões um usuário do Teams organizou e as reuniões em que um usuário do Teams participou. Veja detalhes sobre a tela, vídeo e minutos de áudio e estatísticas de comunicação de chat, como quantos usuários respondem e postam mensagens de canal e quantos usuários se envolvem em mensagens de chat 1:1 ou em grupo.

## <a name="view-the-user-activity-report"></a>Exibir o relatório de atividades do usuário

Você deve ser um administrador do serviço do Teams para fazer essas alterações. Confira [as funções de administrador do Teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, selecione **Análise & relatórios**  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **Atividade do usuário do Teams.**
2. Em **Intervalo de datas,** selecione um intervalo e, em seguida, selecione **Executar relatório.**

    ![Captura de tela do relatório de atividade do usuário do Teams no Centro de administração do Teams com os comentários](../media/teams-reports-user-activity-with-callouts.png "Captura de tela do relatório de atividade do usuário do Teams no Centro de administração do Teams com os comentários")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividade do usuário do Teams pode ser consultado sobre tendências dos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |Pontos de dados de série de tempo no gráfico mostram diferentes métricas de uso agregadas no locatário. |
|**4**   |Os dados tabular representaram diferentes métricas de uso agregadas por usuário. |
|**5**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**6**   | Cada uma das métricas representadas no gráfico no nível do locatário. Filtre o que você vê no gráfico selecionando um item na legenda. Selecione **Mensagens de canal,** **mensagens de resposta,**  **mensagens de chat** ou Reuniões **Organizadas** para ver informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**7**   |A tabela fornece uma divisão do uso pelo usuário.   <ul><li>**Nome para** exibição é o nome de exibição do usuário. Selecione o nome de exibição para ir para a página de detalhes do usuário no Centro de administração do Microsoft Teams.</li><li>**As mensagens de** canal são o número de mensagens exclusivas que o usuário postou em um canal de Equipe durante o período de tempo especificado.</li><li>**As mensagens de** resposta são o número de mensagens de resposta exclusivas que o usuário postou em um canal de equipe durante o período especificado.</li> <li>**Postar mensagens** é o número de mensagens de postagem exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>**Mensagens urgentes** é o número de mensagens urgentes que o usuário postou em um chat durante o período especificado.</li><li>Total de Reuniões **organizadas** é a soma de reuniões agendadas, recorrentes, não planejadas e não <em>classificadas</em> que um usuário organizou durante o período especificado.</li><li>**Reuniões organizadas em um único horário** é o número de reuniões agendadas uma vez que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões agendadas recorrentes organizadas** é o número de reuniões recorrentes que um usuário organizou durante o período especificado.</li><li>**Adhoc de** reuniões organizadas é o número de reuniões não planejadas que um usuário organizou durante o período especificado.</li><li>Total de Reuniões **participadas** é a soma das reuniões agendadas, recorrentes, não planejadas e não <em>classificadas</em> em que um usuário participou durante o período especificado.</li><li>**As reuniões participadas de uma única** vez são o número de reuniões agendadas em que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participadas recorrentes** agendadas é o número de reuniões recorrentes em que um usuário participou durante o período especificado.</li><li>**Adhoc de reuniões participadas** é o número de reuniões não planejadas em que um usuário participou durante o período especificado.</li><li>**As chamadas 1:1** são o número de chamadas 1:1 em que o usuário participou durante o período especificado.</li><li>**O tempo de** áudio é o tempo total de áudio (minutos) em que o usuário participou durante o período de tempo especificado.</li><li>**Tempo de** vídeo é o tempo total de vídeo (minutos) em que o usuário participou durante o período de tempo especificado.</li><li>**O tempo de compartilhamento** de tela é o tempo total de compartilhamento de tela (minutos) em que o usuário participou durante o período especificado.</li>  <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li><li>**Outras atividades** acompanham quando o usuário é considerado ativo, mas tem um valor zero para mensagens de chat, chamadas 1:1, mensagens de canal, total de reuniões e reuniões organizadas. Exemplos de ações são quando um usuário abre uma postagem de mensagem de canal, mas não responde a ela ou quando um usuário recebe uma mensagem privada e a lê, mas não responde a ela.</li> <li>**As reuniões não classificadas** são aquelas que não podem ser classificadas como agendadas, recorrentes ou não planejadas. Eles são curtos em número e, principalmente, não podem ser identificados devido a informações de telemetria adulteradas</li> </ul>**As chamadas** em grupo foram substituídas pela **adhoc** de Reuniões organizadas e as Reuniões **participaram.** A soma desses dois valores é igual à medida medida por chamadas **em grupo.**
|**8**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**9**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para o Excel** e, em seguida, a guia **Downloads,** selecione **Baixar** para baixar o relatório quando estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png) <br>Ao exibir o relatório no Excel, você também verá uma **coluna de ID,** que representa a ID do Usuário. Uma ID de Usuário é normalmente uma cadeia de caracteres alfanumérico. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
