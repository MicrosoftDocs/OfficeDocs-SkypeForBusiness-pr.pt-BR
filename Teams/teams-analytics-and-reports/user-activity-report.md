---
title: Relatório de atividades do usuário do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como usar o relatório de atividades do usuário de equipes no Centro de administração do Microsoft Teams para ver como os usuários em sua organização estiver usando equipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcb4511463a8866448739cafb1661c55481718b2
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2019
ms.locfileid: "33495848"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividades do usuário de equipes oferece ideias sobre os tipos de atividades que os usuários em sua organização executar em equipes. Por exemplo, você pode ver quantos usuários se comunicar por meio de chamadas de 1:1, quantos usuários se comunicar por meio de mensagens de canal e quantos usuários entrem em mensagens de bate-papo privado.

![Captura de tela do relatório de atividade de usuário de equipes no Centro de administração de equipes da Microsoft] (../media/teams-reports-user-activity.png "Captura de tela do relatório de atividade de usuário de equipes no Centro de administração de equipes da Microsoft")

## <a name="view-the-report"></a>Exibir o relatório

1. Vá para o Centro de administração do Microsoft Teams, no painel de navegação esquerdo, clique em **relatórios de & de análise**e em um **relatório**, selecione **atividade do usuário de equipes**. 
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**. 

## <a name="interpret-the-report"></a>Interpretar relatório

![Captura de tela do relatório de atividade de equipes usuário no Centro de administração de equipes da Microsoft com textos explicativos numerados] (../media/teams-reports-user-activity-with-callouts.png "Captura de tela do relatório de atividade de equipes usuário no Centro de administração de equipes da Microsoft com textos explicativos numerados")

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividades do usuário de equipes pode ser exibido para tendências pela últimos 7 dias ou 28 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X nos gráficos é o intervalo de datas selecionado para o relatório específico. </li><li>O eixo Y é o número de usuários que participam da atividade.</li></ul>Passe o mouse sobre o ponto representando uma atividade em uma determinada data para ver o número de instâncias de que a atividade nessa determinada data. |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **1:1 chamadas**, **mensagens de canal**ou **mensagens de Chat** para ver apenas as informações relacionadas a cada uma delas. Alterar a seleção não altera as informações na tabela. |
|**5**   |A tabela fornece uma análise de uso por usuário.   <ul><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir à página de configuração do usuário no Centro de administração do Microsoft Teams.</li><li>**chamadas de 1:1** é o número de chamadas de 1:1 que o usuário participou durante o período de tempo especificado.</li><li>**Mensagens de canal** é o número de mensagens exclusivos que o usuário postado no chat de uma equipe durante o período de tempo especificado.</li> <li>**Mensagens de chat** é o número de mensagens exclusivos que o usuário lançado em uma privada chat durante o período de tempo especificado.</li>  <li>**Última atividade** é a última data (UTC) que o usuário participou uma atividade de equipes.</li> </ul>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **Exportar para Excel**e, em seguida, na guia **Downloads** , clique em **Baixar** para baixar o relatório quando ele estiver pronto.<br>![Captura de tela da guia Downloads mostrando exportados relatórios para baixar](../media/teams-reports-export-to-csv.png)||

## <a name="related-topics"></a>Tópicos relacionados
- [Análises e relatórios do Teams](teams-reporting-reference.md)
- [Relatório de uso do Teams](teams-usage-report.md)
- [Relatório de uso de dispositivos do Teams](device-usage-report.md)