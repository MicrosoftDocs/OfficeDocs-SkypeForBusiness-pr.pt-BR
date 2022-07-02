---
title: Como o Microsoft Teams usa a memória
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Saiba mais sobre o uso de memória do sistema do Microsoft Teams e por que o uso de memória é o mesmo entre o aplicativo da área de trabalho e o aplicativo Web.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 0d55caf2a1642b28ccc63e3be1cf3eccc69bb260
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605670"
---
# <a name="how-microsoft-teams-uses-memory"></a>Como o Microsoft Teams usa a memória

Alguns usuários do Microsoft Teams têm dúvidas sobre como o Teams usa memória. Este artigo descreve como a memória é usada pelo Teams e por que o aplicativo (aplicativo) da área de trabalho do Teams e o aplicativo Web do Teams não impedem que outros aplicativos e cargas de trabalho no mesmo computador tenha memória suficiente para serem executados de forma ideal. O Teams foi projetado para usar a tecnologia da Web moderna. Para fazer isso, o cliente de área de trabalho do Teams foi desenvolvido no Electron, que usa Chromium para renderização. Esse é o mesmo mecanismo de renderização por trás de muitos dos navegadores mais populares de hoje, incluindo o Edge e o Chrome.

## <a name="how-teams-works"></a>Como o Teams funciona

As equipes que estão sendo projetadas no Electron permitem um desenvolvimento mais rápido e também mantém a paridade entre versões do Teams em diferentes sistemas operacionais (Windows, Mac e Linux). Essa paridade é possível porque Electron e Chromium mantêm uma base de código semelhante em todas as versões. Outra vantagem dessa arquitetura é que há um perfil de uso de memória semelhante entre o aplicativo Web do Teams e a versão da área de trabalho. O aplicativo Web e as versões da área de trabalho usam memória de maneira semelhante à maneira como um navegador a usaria. Mais informações sobre o Electron estão disponíveis em [seu site](https://electronjs.org/).

Consulte [Chromium uso de memória](https://www.chromium.org/developers/memory-usage-backgrounder) e [principais conceitos na memória do Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obter mais informações.

A imagem a seguir mostra os usos de memória lado a lado do aplicativo da área de trabalho do Teams para Windows e do aplicativo Web do Teams (neste exemplo, em execução no Google Chrome).

![Uso de memória do Teams para o aplicativo da área de trabalho e o aplicativo Web.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso de memória no Teams

É importante entender o comportamento esperado  do Teams quando se trata de memória do sistema e conhecer os sintomas de problemas realmente problemáticos de memória do sistema.

### <a name="expected-memory-usage-by-teams"></a>Uso de memória esperado pelo Teams

Se você estiver executando o aplicativo da área de trabalho do Teams ou o aplicativo Web do Teams, o Chromium detecta a quantidade de memória do sistema disponível e utiliza o suficiente dessa memória para otimizar a experiência de renderização. Quando outros aplicativos ou serviços exigem memória do sistema, Chromium de memória para esses processos. Chromium ajusta o uso de memória do Teams continuamente para otimizar o desempenho do Teams sem afetar nada mais em execução no momento.

Dessa forma, cargas Chromium cargas de trabalho semelhantes podem utilizar quantidades variáveis de memória, dependendo da quantidade de memória do sistema disponível.

O grafo a seguir ilustra o uso de memória pelo Teams em quatro sistemas separados, cada um com diferentes quantidades de memória disponíveis. Cada um dos sistemas está processando cargas de trabalho semelhantes (os mesmos aplicativos abertos e em execução).

![Uso de memória do Teams em sistemas diferentes.](media/teams-memory-usage.png)

Quando os computadores tiverem mais memória, o Teams usará essa memória. Em sistemas em que a memória é insuficiente, o Teams usará menos.

### <a name="symptoms-of-system-memory-issues"></a>Sintomas de problemas de memória do sistema

Se você vir um ou mais dos seguintes sintomas no computador, poderá ter um problema sério de memória do sistema:

- Alto uso de memória quando vários aplicativos grandes estão sendo executados simultaneamente.
- Desempenho lento do sistema ou travamento de aplicativos.
- Uso sustentado de memória geral do sistema de 90% ou superior em todos os aplicativos. Com essa quantidade de uso de memória, o Teams deve estar dando memória de volta a outros aplicativos e cargas de trabalho. O uso sustentado de memória de 90% pode significar que o Teams não está dando memória de volta ao sistema, o que indica um problema.

As imagens a seguir mostram exemplos de exibições no Gerenciador de Tarefas quando o uso de memória do sistema é anormalmente alto.

![Exibição de uso de memória do Teams no Gerenciador de Tarefas.](media/teams-memory-high-mem-process-list.png)

![Grafo de uso de memória do Teams no Gerenciador de Tarefas.](media/teams-memory-high-mem-process-list2.png)
