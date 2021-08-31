---
title: Como o Microsoft Teams usa a memória
author: msdmaguire
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Saiba mais Microsoft Teams uso da memória do sistema e por que o uso da memória é o mesmo entre o aplicativo da área de trabalho e o aplicativo Web.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 70862d2d48d98517365b35d05ccd36dd9cb4ffd3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58734030"
---
# <a name="how-microsoft-teams-uses-memory"></a>Como o Microsoft Teams usa a memória

Alguns Microsoft Teams usuários têm dúvidas sobre como o Teams usa memória. Este artigo descreve como a memória é usada pelo Teams e por que o aplicativo (aplicativo) da área de trabalho Teams e o aplicativo Web do Teams não impedem que outros aplicativos e cargas de trabalho no mesmo computador tenha memória suficiente para ser executado de forma ideal. Teams é projetado para usar a tecnologia Web moderna. Para isso, o Teams da área de trabalho foi desenvolvido em Eletrônica, que usa Chromium para renderização. Esse é o mesmo mecanismo de renderização por trás de muitos dos navegadores mais populares da atualidade, incluindo o Edge e o Chrome.

## <a name="how-teams-works"></a>Como Teams funciona

Teams projetado em Eletrônica permite um desenvolvimento mais rápido e também mantém a paridade entre Teams versões em diferentes sistemas operacionais (Windows, Mac e Linux). Essa paridade é possível porque o Chromium e o Chromium mantêm uma base de código semelhante em todas as versões. Outra vantagem dessa arquitetura é que há um perfil de uso de memória semelhante entre o Teams Web e a versão da área de trabalho. Tanto o aplicativo Web quanto as versões da área de trabalho usam memória de maneira semelhante à forma como um navegador a usaria. Mais informações sobre o Eletrônica estão disponíveis em [seu site](https://electronjs.org/).

Consulte [Chromium De uso da memória](https://www.chromium.org/developers/memory-usage-backgrounder) e [conceitos principais na Memória do Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obter mais informações.

A imagem a seguir mostra usos de memória lado a lado do aplicativo de área de trabalho Teams para Windows e o aplicativo Web Teams (neste exemplo, em execução no Google Chrome).

![Teams de memória para o aplicativo da área de trabalho e o aplicativo Web.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso de memória em Teams

É importante entender  o comportamento esperado da Teams quando se trata de memória do sistema e conhecer os sintomas de problemas realmente problemáticos de memória do sistema.

### <a name="expected-memory-usage-by-teams"></a>Uso de memória esperado por Teams

Se você estiver executando o aplicativo da área de trabalho Teams ou o aplicativo Web Teams, o Chromium detecta a disponibilidade de memória do sistema e utiliza o suficiente dessa memória para otimizar a experiência de renderização. Quando outros aplicativos ou serviços exigem memória do sistema, Chromium abre mão da memória para esses processos. Chromium ajusta o Teams de memória em uma base contínua, a fim de otimizar Teams desempenho sem afetar qualquer outra coisa em execução no momento.

Dessa forma, cargas de trabalho Chromium semelhantes podem utilizar quantidades variáveis de memória, dependendo da quantidade de memória do sistema disponível.

O gráfico a seguir mostra o uso da memória por Teams em quatro sistemas separados, cada um com quantidades diferentes de memória disponíveis. Cada um dos sistemas está processamento de cargas de trabalho semelhantes (mesmos aplicativos abertos e em execução).

![Teams de memória em diferentes sistemas.](media/teams-memory-usage.png)

Quando os computadores têm mais memória, Teams usarão essa memória. Em sistemas onde a memória é rara, Teams usar menos.

### <a name="symptoms-of-system-memory-issues"></a>Sintomas de problemas de memória do sistema

Se você vir um ou mais dos seguintes sintomas em seu computador, poderá ter um problema sério de memória do sistema:

- Alto uso de memória quando vários aplicativos grandes estão sendo executados simultaneamente.
- Desempenho lento do sistema ou suspensão de aplicativos.
- Uso total de memória do sistema sustentado de 90% ou superior em todos os aplicativos. Com essa quantidade de uso de memória, Teams deve estar devolvendo memória a outros aplicativos e cargas de trabalho. O uso sustentado de memória de 90% pode significar Teams não está devolvendo memória ao sistema, o que indica um problema.

As imagens a seguir mostram exemplos de exibições no Gerenciador de Tarefas quando o uso da memória do sistema é anormalmente alto.

![Teams exibição de uso de memória no Gerenciador de Tarefas.](media/teams-memory-high-mem-process-list.png)

![Teams gráfico de uso de memória no Gerenciador de Tarefas.](media/teams-memory-high-mem-process-list2.png)
