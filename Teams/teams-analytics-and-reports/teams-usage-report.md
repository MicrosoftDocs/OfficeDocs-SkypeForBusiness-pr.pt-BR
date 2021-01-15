---
title: Relatório de uso do Microsoft Teams
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
description: Saiba como usar o relatório de uso do Teams no centro de administração do Microsoft Teams para obter uma visão geral das atividades to Teams na sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63193b6540a40e9ad4a2171c95f638dfb7c1d112
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809261"
---
# <a name="microsoft-teams-usage-report"></a>Relatório de uso do Microsoft Teams

O relatório de uso do Teams no centro de administração do Microsoft Teams apresenta uma visão geral da atividade de uso no Teams, incluindo o número de usuários e canais ativos, para que você possa ver rapidamente quantos usuários na sua organização estão usando o Teams para se comunicar e colaborar. Você pode visualizar as informações de uso de equipes, incluindo o número de usuários e canais ativos, convidados e mensagens em cada equipe.

## <a name="view-the-usage-report"></a>Exibir o relatório de uso

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **o uso do Teams.**
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso do Teams no centro de administração do Teams com os callouts](../media/teams-reports-teams-usage-with-callouts.png "Captura de tela do relatório de uso do Teams no centro de administração do Teams com os callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividade de uso do Teams pode ser consultado sobre tendências dos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **Total** de usuários ativos, **equipes &** usuários ativos , canais **ativos** ou mensagens para ver apenas as informações relacionadas a cada um deles.  Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**5**   |A tabela oferece um detalhamento do uso por equipe. <ul><li>**Nome da** equipe é o nome para exibição da equipe. Você pode clicar no nome da equipe para ir para a página de configurações da equipe no centro de administração do Microsoft Teams. </li> <li>**Privacidade** refere-se à equipe ser particular ou pública.</li> <li>**Usuários ativos** é o número de usuários ativos na equipe no período de tempo especificado.</li><li>**Convidados** é o número de convidados na equipe no período de tempo especificado.</li> <li>**Canais ativos** é o número de canais que têm pelo menos um usuário ativo no período de tempo especificado.</li> <li>**Mensagens de** Postagem é o número de todas as mensagens de postagem em canais no período de tempo especificado.</li> <li>**Mensagens de** resposta é o número de todas as mensagens de resposta em canais no período de tempo especificado.</li> <li>**As reuniões organizadas** são o número de reuniões agendadas e ad hoc que um usuário organizou durante o período de tempo especificado. </li><li>**Mensagens urgentes** é o número de todas as mensagens urgentes no período de tempo especificado.</li><li>**Reações** é o número de todas as reações a mensagens no período de tempo especificado.</li><li>**Menções** é o número de todas as menções usadas nas mensagens no período de tempo especificado.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que os usuários da equipe publicaram em chats de equipe durante o período de tempo especificado.</li> </li> </ul>Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para o Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
