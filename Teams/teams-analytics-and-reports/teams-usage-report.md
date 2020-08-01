---
title: Relatório de uso do Microsoft Teams
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
description: Saiba como usar o relatório de uso do Teams no centro de administração do Microsoft Teams para obter uma visão geral das atividades to Teams na sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2a87894e38e0ccec04b4b088e70c03ddb5e6f967
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533868"
---
# <a name="microsoft-teams-usage-report"></a>Relatório de uso do Microsoft Teams

O relatório de uso do Teams no centro de administração do Microsoft Teams apresenta uma visão geral da atividade de uso no Teams, incluindo o número de usuários e canais ativos, para que você possa ver rapidamente quantos usuários na sua organização estão usando o Teams para se comunicar e colaborar. Você pode visualizar as informações de uso de equipes, incluindo o número de usuários e canais ativos, convidados e mensagens em cada equipe.

## <a name="view-the-usage-report"></a>Exibir o relatório de uso

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** relatórios de  >  **uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **uso do teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso do teams no centro de administração do teams com textos explicativos](../media/teams-reports-teams-usage-with-callouts.png "Captura de tela do relatório de uso do teams no centro de administração do teams com textos explicativos")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório atividade de uso do teams pode ser exibido para obter tendências nos últimos sete dias, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **total usuários ativos**, **equipes & canais ativos**, **canais ativos**ou **mensagens** para ver apenas as informações relacionadas a cada um deles. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**5**   |A tabela oferece um detalhamento do uso por equipe. <ul><li>**Nome da equipe** é o nome de exibição da equipe. Você pode clicar no nome da equipe para ir para a página Configurações da equipe no centro de administração do Microsoft Teams. </li> <li>**Privacidade** refere-se à equipe ser particular ou pública.</li> <li>**Usuários ativos** é o número de usuários ativos na equipe no período de tempo especificado.</li><li>**Convidados** é o número de convidados na equipe no período de tempo especificado.</li> <li>**Canais ativos** é o número de canais que têm pelo menos um usuário ativo no intervalo de tempo especificado.</li> <li>**Postar mensagens** é o número de todas as mensagens postadas em canais no intervalo de tempo especificado.</li> <li>**Mensagens de resposta** é o número de todas as mensagens de resposta em canais no intervalo de tempo especificado.</li> <li>**Reuniões organizadas** é o número de reuniões agendadas e ad hoc organizadas por um usuário durante o período de tempo especificado. </li><li>**Mensagens urgentes** é o número de todas as mensagens urgentes no período de tempo especificado.</li><li>**Reações** é o número de todas as reações às mensagens no período de tempo especificado.</li><li>**Menção** é o número de todas as menção usadas nas mensagens no período de tempo especificado.</li><li>**Mensagens de canal** é o número de mensagens exclusivas que os usuários da equipe lançaram em um chat de equipe durante o período de tempo especificado.</li> </li> </ul>Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
