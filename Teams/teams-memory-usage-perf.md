---
title: Como o Microsoft Teams usa a memória
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Como o Microsoft Teams usa a memória do sistema e porque o uso da memória é o mesmo entre o aplicativo da área de trabalho e o aplicativo Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05cbd2f4b6691c873393a7ba711e03aadf70a2f2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836981"
---
# <a name="how-microsoft-teams-uses-memory"></a>Como o Microsoft Teams usa a memória

Alguns usuários do Microsoft Teams têm perguntas sobre como o Microsoft Teams usa a memória. Este artigo descreve como a memória é usada pelo Teams e por que o aplicativo da área de trabalho do Teams (aplicativo) e o aplicativo Web Teams não impedem que outros aplicativos e cargas de trabalho no mesmo computador tenham memória suficiente para serem executados de forma ideal. O Teams foi projetado para usar a tecnologia da Web moderna. Para fazer isso, o cliente da equipe de trabalho do teams foi desenvolvido em uma área de uso. Esse é o mesmo mecanismo de renderização por trás de muitos dos navegadores mais populares do dia, incluindo o Edge e o Chrome.

## <a name="how-teams-works"></a>Como as equipes funcionam

As equipes que estão sendo projetadas para o sistema de redes com o sistema de redes e do sistema operacional são mais rápidas, e também mantém a paridade entre versões do Team em diferentes sistemas operacionais (Windows, Mac e Linux). Essa paridade é possível porque a Chromium e a da digital mantêm uma base de código semelhante em todas as versões. Outra vantagem dessa arquitetura é que há um perfil de uso de memória semelhante entre o aplicativo Web Teams e a versão da área de trabalho. As versões do aplicativo Web e da área de trabalho usam memória de maneira semelhante à de um navegador usá-lo. Mais informações sobre o recurso do recurso de dados de dados do recurso de dados [do seu site](https://electronjs.org/).

Consulte [Chromium uso da memória](https://www.chromium.org/developers/memory-usage-backgrounder) e [conceitos principais na memória do Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obter mais informações.

A imagem a seguir mostra os usos de memória lado a lado do aplicativo Teams desktop para Windows e o aplicativo Web Teams (neste exemplo, em execução no Google Chrome).

![Uso da memória do aplicativo Web do Teams e do aplicativo Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso de memória no Teams

É importante entender o comportamento *esperado* do teams quando chega à memória do sistema e conhecer os sintomas de problemas de memória de sistema realmente problemáticos.

### <a name="expected-memory-usage-by-teams"></a>Uso de memória esperado por Teams

Não importa se você está executando o aplicativo da área de trabalho do teams ou o aplicativo Web do Teams, o Chromium detecta a quantidade de memória do sistema disponível e utiliza o suficiente para otimizar a experiência de renderização. Quando outros aplicativos ou serviços exigem a memória do sistema, o Chromium fornece a memória a esses processos. O Chromium ajusta o uso da memória do teams continuamente para otimizar o desempenho da equipe sem afetar mais nada em execução no momento.

Dessa forma, cargas de trabalho Chromium semelhantes podem utilizar quantidades variáveis de memória, dependendo da quantidade de memória do sistema que está disponível.

O gráfico a seguir descreve o uso da memória por equipes em quatro sistemas separados, cada um com uma quantidade de memória diferente disponível. Cada um dos sistemas está processando cargas de trabalho semelhantes (os mesmos aplicativos abertos e em execução).

![Uso de memória do Team em diferentes sistemas](media/teams-memory-usage.png)

Quando os computadores tiverem mais memória, o Microsoft Teams vai usar essa memória. Em sistemas em que a memória está escassa, as equipes usarão menos. 

### <a name="symptoms-of-system-memory-issues"></a>Sintomas de problemas de memória do sistema

Se você vir um ou mais dos seguintes sintomas em seu computador, você pode ter um problema sério de memória do sistema:

- Alta utilização de memória quando vários aplicativos grandes são executados simultaneamente.
- Baixo desempenho do sistema ou aplicativos travam.
- Uso de memória geral do sistema sustentável de 90% ou mais em todos os aplicativos. Com essa quantidade de uso de memória, as equipes devem dar memória novamente para outros aplicativos e cargas de trabalho. Uso de memória sustentada de 90% pode significar que o Microsoft Teams não está fornecendo memória de volta ao sistema, o que indica um problema.

As imagens a seguir mostram exemplos de modos de exibição no Gerenciador de tarefas quando o uso da memória do sistema é anormalmente alto.

![Modo de exibição uso de memória do teams no Gerenciador de tarefas](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso de memória do teams no Gerenciador de tarefas](media/teams-memory-high-mem-process-list2.png)
