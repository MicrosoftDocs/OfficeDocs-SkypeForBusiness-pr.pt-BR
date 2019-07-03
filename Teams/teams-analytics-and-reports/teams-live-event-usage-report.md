---
title: Relatório de uso de eventos ao vivo do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como usar o relatório de uso de eventos Team Live no centro de administração do Microsoft Teams para obter uma visão geral da atividade de eventos do teams Live em sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9faa11aafa2c5b22bae0f1a77b436047adddaa24
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35420528"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Relatório de uso de eventos ao vivo do Microsoft Teams

O relatório de uso de eventos Team Live no centro de administração do Microsoft Teams mostra a visão geral de atividade para eventos dinâmicos mantidos em sua organização. Você pode exibir informações de uso, incluindo status do evento, hora de início, exibições e tipo de produção para cada evento. Você pode obter informações sobre as tendências de uso e ver quem em sua organização agenda, apresenta e produz eventos ao vivo. 

![Captura de tela do relatório de uso de eventos do teams Live no centro de administração do Microsoft Teams] (../media/teams-live-event-usage-report.png "Captura de tela do relatório de uso do teams no centro de administração")

## <a name="view-the-report"></a>Exibir o relatório

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **relatórios de análise &** e, em **relatório**, selecione o **uso de eventos do teams Live**.
2. Em **intervalo de datas**, selecione um intervalo predefinido ou defina um intervalo personalizado. Você pode definir um intervalo para mostrar dados de até um ano, seis meses antes e depois da data atual.
3. Adicionais Em **organizador**, você pode optar por mostrar apenas eventos dinâmicos organizados por um usuário específico.
4. Clique em **executar relatório**.  

## <a name="interpret-the-report"></a>Interpretar relatório

![Captura de tela do relatório de uso de eventos do teams Live no centro de administração do Microsoft Teams] (../media/teams-live-event-usage-report-with-callouts.png "Captura de tela do relatório de uso de eventos do teams Live no centro de administração com textos explicativos numerados")

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de eventos do teams Live pode ser exibido para obter tendências nos últimos sete dias, 28 dias ou um intervalo de datas personalizado que você definiu. |
|**2**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório reflete a atividade próxima do tempo real quando a página é atualizada. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y é a contagem total de modo de exibição.</li> </ul>Passe o mouse sobre o ponto em uma determinada data para ver o número de exibições em todos os eventos dinâmicos nessa data.|
|**4**   |A tabela oferece uma divisão de cada evento ao vivo. <ul><li>**Evento** é o nome de exibição do evento ao vivo. Clique no nome do evento para [obter mais detalhes](#view-event-details) sobre o evento. </li> <li>**Hora de início** refere-se à data de início e hora do evento.</li> <li>**Status do evento** mostra se o evento foi colocado.  </li><li>**Organizador** é o nome do organizador de eventos.</li> <li>**Apresentadores** são os nomes dos apresentadores de eventos.</li><li>**Produtores** são os nomes dos produtores de eventos.</li><li>**Modos** de exibição é o número de modos de exibição exclusivos.</li><li>A **gravação** mostra se a configuração de gravação está ativada ou desativada.</li><li>**Tipo de produção** mostra se o evento é produzido em Teams ou por um dispositivo ou aplicativo externo.</li></li> </ul>Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|

## <a name="view-event-details"></a>Exibir detalhes do evento

A página detalhes do evento ao vivo fornece um resumo dos detalhes de um evento ao vivo e lista todos os arquivos, incluindo transcrições e gravações, associados ao evento. Clique em um nome de arquivo para exibir ou baixar o arquivo.

![Captura de tela mostrando detalhes de um evento ao vivo](../media/teams-live-event-usage-report-event-detail.png)

Se a sua organização estiver habilitada para [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ECDN ou [Kollective](https://kollective.com) eCDN, você poderá obter outras análises de participantes clicando no link relatório de parceiro.

## <a name="related-topics"></a>Tópicos relacionados
- [Análises e relatórios do Teams](teams-reporting-reference.md)
- [O que são os eventos ao vivo do Teams?](../teams-live-events/what-are-teams-live-events.md)