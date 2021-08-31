---
title: Microsoft Teams Relatório de pools de minutos PSTN
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Como usar o relatório Teams pools de minutos PSTN no centro de administração Microsoft Teams para exibir os minutos consumidos em sua organização durante o mês atual.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6ea18ce789ab08a92849833f72d1bf291ebaec9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730270"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams Relatório de pools de minutos PSTN

O relatório Teams pools de minutos PSTN no centro de administração do Microsoft Teams fornece uma visão geral da atividade de audioconferência e chamada em sua organização mostrando o número de minutos consumidos durante o mês atual. Você pode ver uma divisão de atividades, incluindo a licença usada para chamadas, o total de minutos disponíveis, os minutos usados e o uso da licença por local.

## <a name="view-the-pstn-minute-pools-report"></a>Exibir o relatório de pools de minutos PSTN

Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione Pools de minutos **PSTN** e clique em **Executar relatório**.

![Captura de tela do relatório Teams pools de minutos PSTN no centro de administração.](../media/teams-reports-pstn-minute-pools-with-callouts.png "Captura de tela do relatório Teams pools de minutos PSTN no centro de administração Microsoft Teams com callouts numerados")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**2**   |Clique em uma funcionalidade (licença) para exibir a atividade desse recurso. |
|**3**   |O eixo X é país ou região. O eixo Y é o número de minutos. <br>Passe o mouse sobre uma barra no gráfico para ver a atividade desse local de uso.  |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **Unused**, **Domestic users**, **No data** ou International **usado** para ver apenas as informações relacionadas a cada um. |
|**5**   |A tabela fornece uma divisão de pools de minutos por funcionalidade e local de uso. <ul><li>**País ou região é** o local de uso. </li><li>**Descrição da funcionalidade** é a descrição da licença usada para a chamada.  As descrições de funcionalidade que você pode ver neste relatório incluem: <ul><li>Plano de chamada doméstica e internacional (1200 minutos domésticos)</li><li>Plano de chamada doméstica e internacional (3.000 minutos domésticos)</li><li>Plano de chamada doméstica e internacional (600 minutos internacionais)</li></ul></li><br><li>**O total** de minutos é o número total de minutos disponíveis para o mês.</li><li>**Minutos usados** é o número de minutos usados por mês</li> <li>**Minutos disponíveis é** o número de minutos restantes para o mês.</li><li>**A funcionalidade** é a licença usada para a chamada. As licenças que você pode ver incluem:<ul><li>**MCOPSTN1** - Plano de Chamada Doméstica (3.000 min us / 1200 min planos da UE)</li><li>**MCOPSTN2** - Plano de Chamada Internacional</li><li>**MCOPSTN5** - Plano de Chamada Doméstica (plano de chamada de 120 minutos)</li><li>**MCOPSTN6** - Plano de Chamada Doméstica (plano de chamada de 240 minutos)</li><li>**MCOMEETADD -** Audioconferência</li></ul></li> </ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira.|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
