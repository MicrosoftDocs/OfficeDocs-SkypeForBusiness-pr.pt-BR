---
title: Relatório de uso do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como usar o relatório de uso do Teams no centro de administração do Microsoft Teams para obter uma visão geral das atividades to Teams na sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5fdee65771f2ac23e2cea78e54752786357405
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234765"
---
# <a name="microsoft-teams-usage-report"></a>Relatório de uso do Microsoft Teams

O relatório de uso do Teams no centro de administração do Microsoft Teams apresenta uma visão geral da atividade de uso no Teams, incluindo o número de usuários e canais ativos, para que você possa ver rapidamente quantos usuários na sua organização estão usando o Teams para se comunicar e colaborar. Você pode visualizar as informações de uso de equipes, incluindo o número de usuários e canais ativos, convidados e mensagens em cada equipe.

![Captura de tela do relatório de uso do teams no centro de administração] (../media/teams-reports-teams-usage.png "Captura de tela do relatório de uso do teams no centro de administração do Microsoft Teams")

## <a name="view-the-report"></a>Exibir o relatório

1.In o centro de administração do Microsoft Teams, no painel de navegação esquerdo, clique em **relatórios de análise &** e, em **relatório**, selecione **uso de equipes**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

## <a name="interpret-the-report"></a>Interpretar relatório

![Captura de tela do relatório de uso do teams no centro de administração] (../media/teams-reports-teams-usage-with-callouts.png "Captura de tela do relatório de uso do teams no centro de administração do Microsoft Teams com textos explicativos numerados")

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividade de uso do Teams pode ser consultado sobre tendências dos últimos 7 ou 28 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **total usuários ativos**, **equipes & canais ativos**, **canais ativos**ou **mensagens** para ver apenas as informações relacionadas a cada um deles. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**5**   |A tabela oferece um detalhamento do uso por equipe. <ul><li>**Nome da equipe** é o nome de exibição da equipe. Você pode clicar no nome da equipe para ir para a página Configurações da equipe no centro de administração do Microsoft Teams. </li> <li>**Privacidade** refere-se à equipe ser particular ou pública.</li> <li>**Usuários ativos** é o número de usuários ativos na equipe no período de tempo especificado.</li><li>**Convidados** é o número de convidados na equipe no período de tempo especificado.</li> </li> </ul>Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br>![Captura de tela da guia downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Tópicos relacionados
- [Análises e relatórios do Teams](teams-reporting-reference.md)
