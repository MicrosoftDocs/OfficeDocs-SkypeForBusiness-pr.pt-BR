---
title: Relatório de atividades do usuário do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de atividades do usuário do Teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização estão usando o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 88eb4f56c6891643bd862f425821327d14b95cb4
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825705"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividades do usuário do Teams fornece informações sobre os tipos de atividades que os usuários em sua organização fazem no Teams. Você pode ver quantos usuários se comunicam de forma não planejada por meio de reuniões não agendadas (1:1 e chamadas de grupo). Veja quantas reuniões um usuário do Teams organizou e as reuniões em que um usuário do Teams participou. Veja detalhes sobre minutos de tela, vídeo e áudio e estatísticas de comunicação de chat, como quantos usuários respondem e postam mensagens de canal e quantos usuários se envolvem em mensagens de chat em grupo ou 1:1.

> [!NOTE]
> A capacidade de agendar um relatório de atividades do usuário não está disponível no momento.

## <a name="view-the-user-activity-report"></a>Exibir o relatório de atividades do usuário

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, selecione **Relatórios de uso** >  &**análise.** Na guia **Exibir relatórios** , em **Relatório**, selecione **Atividade de usuário do Teams**.
2. Em **Intervalo de datas**, selecione um intervalo e, em seguida, **selecione Executar relatório**.

    ![Captura de tela do relatório de atividades do usuário do Teams no Centro de administração do Teams com textos explicativo.](../media/teams-reports-user-activity-with-callouts.png "Captura de tela do relatório de atividades do usuário do Teams no Centro de administração do Teams com textos explicativo")

## <a name="interpret-the-report"></a>Interpretar relatório

| Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividades do usuário do Teams pode ser exibido para ver tendências nos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |Os pontos de dados de série temporal no grafo mostram diferentes métricas de uso agregadas no locatário. |
|**4**   |Os dados tabulares representaram diferentes métricas de uso agregadas por usuário. |
|**5**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**6**   | Cada uma das métricas representadas no grafo no nível do locatário. Filtre o que você vê no gráfico selecionando um item na legenda. Selecione **Mensagens de canal**, **mensagens de resposta**,  **mensagens de chat** ou **Reuniões Organizadas** para ver informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**7**   |A tabela fornece um detalhamento do uso por usuário.   <ul><li>**Nome de** exibição é o nome de exibição do usuário. Selecione o nome de exibição para ir para a página de detalhes do usuário no Centro de administração do Microsoft Teams.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**As mensagens de** resposta são o número de mensagens de resposta exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li> <li>**Mensagens de** postagem é o número de mensagens de postagem exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>**Mensagens urgentes** é o número de mensagens urgentes que o usuário postou em um chat durante o período de tempo especificado.</li><li>**Total de reuniões organizadas** é a soma de reuniões agendadas, recorrentes, não planejadas e não <em>classificadas</em> que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas únicamente agendadas** é o número de reuniões agendadas uma vez que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas recorrentes agendadas** é o número de reuniões recorrentes que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas ad hoc** é o número de reuniões não planejadas que um usuário organizou durante o período de tempo especificado.</li><li>**O total de** reuniões participadas é a soma das reuniões agendadas, recorrentes, não planejadas e não <em>classificadas</em> em que um usuário participou durante o período de tempo especificado.</li><li>**As reuniões que participaram de uma única** vez agendadas é o número de reuniões agendadas em que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participadas recorrentes agendadas** é o número de reuniões recorrentes das que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participadas ad hoc** é o número de reuniões não planejadas das que um usuário participou durante o período de tempo especificado.</li><li>**Chamadas 1:1** são o número de chamadas 1:1 das qual o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** áudio é o tempo total de áudio (minutos) do qual o usuário participou durante o período de tempo especificado.</li><li>**Tempo de** vídeo é o tempo total de vídeo (minutos) do qual o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** compartilhamento de tela é o tempo total de compartilhamento de tela (minutos) do qual o usuário participou durante o período de tempo especificado.</li>  <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li><li>**Outras atividades** acompanham quando o usuário é considerado ativo, mas tem um valor igual a zero para mensagens de chat, chamadas 1:1, mensagens de canal, total de reuniões e reuniões organizadas. Exemplos de ações são quando um usuário abre uma postagem de mensagem de canal, mas não responde a ela ou quando um usuário recebe uma mensagem privada e a lê, mas não responde a ela.</li> <li>**As reuniões não classificadas** são aquelas que não podem ser identificadas como agendadas, recorrentes ou não planejadas. Eles são poucos em número e geralmente não podem ser identificados devido a informações de telemetria imperfeitas.</li> </ul>**As chamadas** em grupo foram substituídas por **Reuniões organizadas ad hoc** e Reuniões **participaram ad hoc**. A soma desses dois valores é igual ao que foi medido por chamadas **de grupo**.
|**8**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**9**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para o Excel** e, em seguida, na guia **Downloads** , selecione **Baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando os relatórios exportados a serem baixados.](../media/teams-reports-export-to-csv.png) <br>Ao exibir o relatório no Excel, você também verá uma **coluna de ID** , que representa a ID de usuário. Uma ID de usuário normalmente é uma cadeia de caracteres alfanumérica. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório de atividades do usuário do Teams anônimos, você precisa ser um administrador global. Isso ocultará informações identificáveis (usando hashes MD5), como nome de exibição, email e ID do AAD no relatório e sua exportação.

1. No Centro de administração do Microsoft 365, vá para **As Configurações** \> da **Organização e,** na **guia Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, escolha **Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365 e no Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
