---
title: Relatório de atividades do usuário do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
description: Saiba como usar o relatório Teams atividade do usuário no centro de administração Microsoft Teams para ver como os usuários em sua organização estão usando Teams.
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-apr2020
---

# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O Teams de atividades do usuário fornece informações sobre os tipos de atividades que os usuários em sua organização fazem Teams. Você pode ver quantos usuários se comunicam de forma não planejada por meio de reuniões não agendadas (1:1 e chamadas de grupo). Veja quantas reuniões um Teams usuário organizou e reuniões em que um usuário Teams participou. Confira detalhes sobre minutos de tela, vídeo e áudio e estatísticas de comunicação de chat, como quantos usuários respondem e postam mensagens de canal e quantos usuários se envolvem em mensagens de chat 1:1 ou de grupo.

> [!NOTE]
> A capacidade de agendar um relatório de atividades do usuário não está disponível no momento.

## <a name="view-the-user-activity-report"></a>Exibir o relatório de atividades do usuário

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Análise &** **relatóriosUsuário** > . Na guia **Exibir relatórios**, em **Relatório**, selecione **Teams do usuário**.
2. Em **Intervalo de datas**, selecione um intervalo e selecione **Executar relatório**.

    ![Captura de tela do relatório Teams atividade do usuário no centro de administração Teams com explicações explicativas.](../media/teams-reports-user-activity-with-callouts.png "Captura de tela do relatório de Teams de atividades do usuário no centro de administração Teams com callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

| Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O Teams de atividades do usuário pode ser exibido para tendências nos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |Os pontos de dados da série de tempo no gráfico mostram diferentes métricas de uso agregadas no locatário. |
|**4**   |Os dados tabular representam diferentes métricas de uso agregadas por usuário. |
|**5**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**6**   | Cada uma das métricas representadas no gráfico no nível do locatário. Filtre o que você vê no gráfico selecionando um item na legenda. Selecione **Mensagens de canal**, **mensagens de resposta**,  **mensagens de chat** ou Reuniões **Organizadas** para ver informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**7**   |A tabela fornece uma divisão do uso pelo usuário.   <ul><li>**Nome para** exibição é o nome de exibição do usuário. Selecione o nome de exibição para ir para a página de detalhes do usuário no centro de Microsoft Teams de administração.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de** resposta é o número de mensagens de resposta exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li> <li>**Mensagens de** postagem é o número de mensagens postadas exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>**Mensagens urgentes** é o número de mensagens urgentes que o usuário postou em um chat durante o período de tempo especificado.</li><li>**Total de Reuniões organizadas** é a soma de uma vez agendadas, recorrentes, não planejadas e não <em>classificadas</em> que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas agendadas uma vez** é o número de reuniões agendadas uma vez que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões agendadas organizadas recorrentes** é o número de reuniões recorrentes que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas adhoc** é o número de reuniões não planejadas que um usuário organizou durante o período de tempo especificado.</li><li>**Total de** Reuniões participadas é a soma das reuniões agendadas, recorrentes, não planejadas e não <em>classificadas</em> em que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participadas agendadas uma vez** é o número da única vez em que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões agendadas participadas recorrentes** é o número de reuniões recorrentes das que um usuário participou durante o período de tempo especificado.</li><li>**A adesão de reuniões participadas** é o número de reuniões não planejadas que um usuário participou durante o período de tempo especificado.</li><li>**As chamadas 1:1** são o número de chamadas 1:1 das que o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** áudio é o tempo total de áudio (minutos) em que o usuário participou durante o período de tempo especificado.</li><li>**Tempo de** vídeo é o tempo total de vídeo (minutos) em que o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** compartilhamento de tela é o tempo total de compartilhamento de tela (minutos) em que o usuário participou durante o período de tempo especificado.</li>  <li>**A última** atividade é a última data (UTC) que o usuário participou de uma atividade Teams.</li><li>**Outras atividades** acompanham quando o usuário é considerado ativo, mas tem um valor zero para mensagens de chat, chamadas 1:1, mensagens de canal, total de reuniões e reuniões organizadas. Exemplos de ações são quando um usuário abre uma postagem de mensagem de canal, mas não responde a ela ou quando um usuário recebe uma mensagem privada e a lê, mas não responde a ela.</li> <li>**Reuniões não classificadas** são aquelas que não podem ser identificadas como agendadas, recorrentes ou não planejadas. Eles são poucos em número e, muitas vezes, não podem ser identificados devido a informações de telemetria imperfeitas.</li> </ul>**As chamadas** de grupo foram substituídas pelo **adhoc de** Reuniões organizadas e **as Reuniões participaram do adhoc**. A soma desses dois valores é igual ao que foi medido por chamadas **de grupo**.
|**8**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**9**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, em seguida, a guia **Downloads**, selecione **Baixar** para baixar o relatório quando estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados para download.](../media/teams-reports-export-to-csv.png) <br>Quando você exibir o relatório Excel, você também verá uma coluna **ID**, que representa a ID do usuário. Uma ID de usuário é normalmente uma cadeia de caracteres alfanumérico. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados Teams relatório de atividades do usuário anônimos, você precisa ser um administrador global. Isso ocultará informações identificáveis (usando hashes MD5), como nome de exibição, email e AAD ID no relatório e sua exportação.

1. Em Centro de administração do Microsoft 365, vá **para a Configurações** \> **Org Configurações** e, em **Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365 e Teams de administração.
  
3. Selecione **Salvar alterações**.

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
