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
ms.openlocfilehash: 22aa16c459f727b20709d71e149e216f62297f2b
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160095"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividade de usuários do teams fornece informações sobre os tipos de atividades que os usuários da sua organização executam no Teams. Por exemplo, você pode ver quantos usuários comunicam-se através de chamadas do 1:1, quantos usuários se comunicam por meio de mensagens de canal e quantos usuários participam de mensagens de chat privadas.

## <a name="view-the-report"></a>Exibir o relatório

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** > relatórios de**uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **atividade do usuário do teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de atividade do usuário do teams no centro de administração do teams com textos explicativos](../media/teams-reports-user-activity-with-callouts.png "Captura de tela do relatório de atividade do usuário do teams no centro de administração do teams com textos explicativos")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividade de usuários do teams pode ser exibido para obter tendências nos últimos sete dias ou 28 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X nos gráficos representa o intervalo de datas selecionado para esse relatório específico. </li><li>O eixo Y é o número de usuários que participam da atividade.</li></ul>Passe o mouse sobre o ponto que representa uma atividade em uma determinada data para ver o número de ocorrências dessa atividade nessa determinada data. |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **1:1 chamadas**, **mensagens de canal**ou mensagens de **chat** para ver apenas as informações relacionadas a cada uma delas. Alterar a seleção não altera as informações na tabela. |
|**5**   |A tabela oferece uma divisão de uso por usuário.   <ul><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams.</li><li>**chamadas 1:1** é o número de chamadas do 1:1 nas quais o usuário participou durante o período especificado.</li><li>**Mensagens do canal** é o número de mensagens exclusivas que o usuário publicou em um chat de equipe durante o período de tempo especificado.</li><li>**Mensagens de resposta** é o número de mensagens de resposta exclusivas que o usuário publicou em um canal de equipe durante o período de tempo especificado.</li> <li>**Postar mensagens** é o número de mensagens de postagem exclusivas que o usuário publicou em um canal de equipe durante o período de tempo especificado.</li><li>**Reuniões organizadas** é o número de reuniões agendadas organizadas por um usuário durante o período de tempo especificado.</li><li>**Reuniões participadas** é o número de reuniões agendadas em que um usuário participou durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>As **chamadas em grupo** é o número de chamadas em grupo nas quais o usuário participou durante o período de tempo especificado.</li><li>**Tempo de áudio** é o tempo de áudio total em que o usuário participou durante o período especificado.</li><li>**Hora do vídeo** é o tempo de vídeo total em que o usuário participou durante o período especificado.</li><li>**Tempo de compartilhamento de tela** é a tela total que o usuário participou durante o período de tempo especificado.</li>  <li>**Última atividade** é a última data (UTC) que o usuário participou em uma atividade do teams.</li> </ul>Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png) <br>Ao exibir o relatório no Excel, você também verá uma coluna de **identificação** , que representa a ID da equipe. Uma ID de equipe geralmente é uma cadeia de caracteres alfanumérica. Se a coluna **ID** aparecer como **\n**, isso significará que um usuário solicitou as informações a serem excluídas. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
