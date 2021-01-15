---
title: Relatório de pools de minutos PSTN do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Como usar o relatório de pools de minutos PSTN do Teams no centro de administração do Microsoft Teams para exibir os minutos consumidos em sua organização durante o mês atual.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809341"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Relatório de pools de minutos PSTN do Microsoft Teams

O relatório de pools de minutos PSTN do Teams no centro de administração do Microsoft Teams oferece uma visão geral da atividade de audioconferência e chamada em sua organização mostrando o número de minutos consumidos durante o mês atual. Você pode ver um detalhamento da atividade, incluindo a licença usada para chamadas, o total de minutos disponíveis, os minutos usados e o uso da licença por local.

## <a name="view-the-pstn-minute-pools-report"></a>Exibir o relatório de pools de minutos PSTN

Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione pools de minutos **PSTN** e clique em **Executar relatório**.

![Captura de tela do relatório de pools de minutos PSTN do Teams no centro de administração](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot of the Teams PSTN minute pools report in the Microsoft Teams admin center with numbered callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**2**   |Clique em uma funcionalidade (licença) para exibir a atividade desse recurso. |
|**3**   |O eixo X é país ou região. O eixo Y é o número de minutos. <br>Passe o mouse sobre uma barra no gráfico para ver a atividade desse local de uso.  |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em Usuários **Não** **Utilizados**, Domésticos, Sem Dados ou **Internacional** usado para ver apenas as informações relacionadas a cada um deles. |
|**5**   |A tabela fornece uma divisão dos pools de minutos por capacidade e local de uso. <ul><li>**País ou região é** o local de uso. </li><li>**A descrição da** funcionalidade é a descrição da licença usada para a chamada.  As descrições de funcionalidade que você pode ver neste relatório incluem: <ul><li>Plano de chamada doméstica e internacional (1200 minutos domésticos)</li><li>Plano de chamada doméstica e internacional (3000 minutos domésticos)</li><li>Plano de chamada doméstica e internacional (600 minutos internacionais)</li></ul></li><br><li>**O total** de minutos é o número total de minutos disponíveis para o mês.</li><li>**Minutos usados** é o número de minutos usados por mês</li> <li>**Minutos disponíveis é** o número de minutos restantes para o mês.</li><li>**A funcionalidade** é a licença usada para a chamada. As licenças que você pode ver incluem:<ul><li>**MCOPSTNPP** - Créditos de Comunicação</li><li>**MCOPSTN1** - Plano de Chamada Doméstica (3000 min US /1200 min planos da UE)</li><li>**MCOPSTN2** - Plano de Chamada Internacional</li><li>**MCOPSTN5** - Plano de Chamada Doméstica (plano de chamada de 120 minutos)</li><li>**MCOPSTN6** - Plano de Chamada Doméstica (plano de chamada de 240 minutos)</li><li>**MCOMEETADD** - Audioconferência</li><li>**MCOMEETACPEA** - Audioconferência paga por minuto</li></ul></li> </ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira.|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)