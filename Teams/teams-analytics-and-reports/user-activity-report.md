---
title: Relatório de atividades do usuário do Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Saiba como usar o relatório de atividade de usuários do teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização estão usando o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 907491aab660bacd0b619b385aaef3a9309cc121
ms.sourcegitcommit: 9d60f403b42d2fdef91cdfa3caf50179a49561df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536833"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividades do usuário do teams fornece uma visão geral dos tipos de atividades que os usuários da sua organização executam no Teams. Por exemplo, uma pode ver quantos usuários se comunicam de forma ad hoc por meio de reuniões não agendadas comumente chamadas de 1:1 e chamadas em grupo, reuniões que um usuário do teams organizou e reuniões nas quais o usuário da equipe participou. Compartilhamos detalhes sobre a tela, o vídeo e os minutos de áudio e as estatísticas de comunicação de chat, como quantos usuários respondem e postam mensagens de canal e quantos usuários participam do 1:1 ou mensagens de chat em grupo.

## <a name="view-the-user-activity-report"></a>Exibir o relatório de atividade do usuário

Você deve ser um administrador de serviços do teams para fazer essas alterações. Consulte [usar funções de administrador do teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** relatórios de  >  **uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **atividade do usuário do teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de atividade do usuário do teams no centro de administração do teams com textos explicativos](../media/teams-reports-user-activity-with-callouts.png "Captura de tela do relatório de atividade do usuário do teams no centro de administração do teams com textos explicativos")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividade de usuários do teams pode ser visualizado em busca de tendências nos últimos sete dias, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de tempo de atividade de 24 horas. |
|**3**   |<ul><li>O eixo X nos gráficos representa o intervalo de datas selecionado para esse relatório específico. </li><li>O eixo Y é o número de usuários que participam da atividade.</li></ul>Passe o mouse sobre o ponto que representa uma atividade em uma determinada data para ver o número de ocorrências dessa atividade nessa determinada data. |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **1:1 chamadas**, **mensagens de canal**ou mensagens de **chat** para ver apenas as informações relacionadas a cada uma delas. Alterar a seleção não altera as informações na tabela. |
|**5**   |A tabela oferece uma divisão de uso por usuário.   <ul><li>**Nome** de usuário é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams.</li><li>**Mensagens do canal** é o número de mensagens exclusivas que o usuário publicou em um chat de equipe durante o período de tempo especificado.</li><li>**Mensagens de resposta** é o número de mensagens de resposta exclusivas que o usuário publicou em um canal de equipe durante o período de tempo especificado.</li> <li>**Postar mensagens** é o número de mensagens de postagem exclusivas que o usuário publicou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>**Mensagens urgentes** é o número de mensagens urgentes que o usuário publicou em um chat durante o período de tempo especificado.</li><li>**Total de reuniões** é o número total de reuniões programadas e ad hoc em que um usuário participou durante o período especificado.</li><li>**Reuniões organizadas** é o número de reuniões agendadas e ad hoc organizadas por um usuário durante o período de tempo especificado.</li><li>**Reuniões organizadas agendadas** é o número de reuniões agendadas organizadas por um usuário durante o período de tempo especificado.</li><li>**Reuniões organizadas como AdHoc** é o número de reuniões ad hoc organizadas por um usuário durante o período de tempo especificado.</li><li>**Reuniões participadas** é o número das reuniões agendadas e em que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões agendadas agendadas** é o número das reuniões agendadas em que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participos de adhoc** é o número de reuniões ad hoc em que um usuário participou durante o período de tempo especificado.</li><li>**chamadas 1:1** é o número de chamadas do 1:1 nas quais o usuário participou durante o período especificado.</li><li>**Tempo de áudio** é o tempo de áudio total em que o usuário participou durante o período especificado.</li><li>**Hora do vídeo** é o tempo de vídeo total em que o usuário participou durante o período especificado.</li><li>**Tempo de compartilhamento de tela** é a tela total de tempo em que o usuário participou durante o período de tempo especificado.</li>  <li>**Última atividade** é a última data (UTC) que o usuário participou em uma atividade do teams.</li><li>**Outras atividades** acompanham quando o usuário é considerado ativo, mas tem um valor igual a zero para mensagens de chat, chamadas de 1:1, mensagens de canal, reuniões totais e reuniões organizadas. Exemplos de ações são quando um usuário abre uma postagem de mensagem de canal, mas não responde a ela ou quando um usuário recebe uma mensagem particular e a lê, mas não responde a ela.</li> </ul>Observe que **as chamadas em grupo** foram substituídas por **reuniões organizadas ad hoc** e reuniões que **participou de adhoc**, em que a soma desses dois valores é igual ao que foi medido por chamadas em **grupo**.
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png) <br>Ao exibir o relatório no Excel, você também verá uma coluna de **identificação** , que representa a ID da equipe. Uma ID de equipe geralmente é uma cadeia de caracteres alfanumérica. Se a coluna **ID** aparecer como **\n**, isso significará que um usuário solicitou as informações a serem excluídas. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
