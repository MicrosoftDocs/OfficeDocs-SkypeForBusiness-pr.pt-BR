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
description: Saiba como usar o relatório de atividades do usuário do Teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização estão usando o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85d907e527f8b957abf1a5f3b8b9f0d8c5f44443
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809191"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividades do usuário do Teams fornece informações sobre os tipos de atividades que os usuários em sua organização executam no Teams. Por exemplo, pode-se ver quantos usuários se comunicam de forma ad hoc por meio de reuniões não agendadas comumente conhecidas como 1:1 e chamadas de grupo, reuniões que um usuário do Teams organizou e reuniões em que um usuário do Teams participou. Compartilhamos detalhes sobre minutos de tela, vídeo e áudio e estatísticas de comunicação de chat, como quantos usuários respondem e postam mensagens de canal e quantos usuários se envolvem em mensagens de chat de grupo ou 1:1.

## <a name="view-the-user-activity-report"></a>Exibir o relatório de atividades do usuário

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Consulte [Usar funções de administrador do Teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter permissões e funções de administrador.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **a atividade do usuário do Teams.**
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Screenshot of the Teams user activity report in the Teams admin center with callouts](../media/teams-reports-user-activity-with-callouts.png "Screenshot of the Teams user activity report in the Teams admin center with callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividades do usuário do Teams pode ser consultado sobre tendências dos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |<ul><li>O eixo X nos gráficos representa o intervalo de datas selecionado para esse relatório específico. </li><li>O eixo Y é o número de usuários que participam da atividade.</li></ul>Passe o mouse sobre o ponto que representa uma atividade em uma determinada data para ver o número de instâncias dessa atividade nessa data determinada. |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique **em 1:1** **chamadas,** mensagens de canal ou mensagens **de Chat** para ver apenas as informações relacionadas a cada uma delas. Alterar a seleção não altera as informações na tabela. |
|**5**   |A tabela fornece uma divisão do uso por usuário.   <ul><li>**Nome** de usuário é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Centro de administração do Microsoft Teams.</li><li>**Mensagens do canal** é o número de mensagens exclusivas que o usuário publicou em um chat de equipe durante o período de tempo especificado.</li><li>**Mensagens de** resposta é o número de mensagens de resposta exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li> <li>**Mensagens de** postagem é o número de mensagens de postagem exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>**Mensagens urgentes** é o número de mensagens urgentes que o usuário postou em um chat durante o período de tempo especificado.</li><li>**O total** de reuniões é o número total de reuniões agendadas e ad hoc em que um usuário participou durante o período de tempo especificado.</li><li>**As reuniões organizadas** são o número de reuniões agendadas e ad hoc que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas agendadas** é o número de reuniões agendadas que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas adhoc** é o número de reuniões ad hoc que um usuário organizou durante o período de tempo especificado.</li><li>**As reuniões participadas** são o número de reuniões agendadas e ad hoc das que um usuário participou durante o período de tempo especificado.</li><li>**As reuniões participadas agendadas** são o número de reuniões agendadas das que um usuário participou durante o período de tempo especificado.</li><li>**A adesão às reuniões participadas** é o número de reuniões ad hoc das que um usuário participou durante o período de tempo especificado.</li><li>**1:1 chamadas** é o número de chamadas 1:1 das que o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** áudio é o tempo total de áudio em que o usuário participou durante o período de tempo especificado.</li><li>**Tempo de** vídeo é o tempo total de vídeo em que o usuário participou durante o período de tempo especificado.</li><li>**O tempo de compartilhamento** de tela é o tempo total de compartilhamento de tela em que o usuário participou durante o período de tempo especificado.</li>  <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li><li>**Outras atividades** rastreia quando o usuário é considerado ativo, mas tem um valor zero para mensagens de chat, chamadas 1:1, mensagens de canal, total de reuniões e reuniões organizadas. Exemplos de ações são quando um usuário abre uma postagem de mensagem de canal, mas não a responde ou quando um usuário recebe uma mensagem privada e a lê, mas não responde a ela.</li> </ul>Observe que **as** chamadas de grupo foram substituídas por reuniões organizadas **adhoc** e reuniões participaram **de adhoc**, em que a soma desses dois valores é igual ao que foi medido pelas chamadas de grupo **.**
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para o Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png) <br>Ao exibir o relatório no Excel, você também verá uma coluna **de ID,** que representa a ID da equipe. Uma ID de equipe é normalmente uma cadeia alfanumérico. Se a **coluna de ID** aparecer **como \n,** isso significa que um usuário solicitou que suas informações sejam excluídas. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
