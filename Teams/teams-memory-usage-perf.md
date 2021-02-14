---
title: Como o Microsoft Teams usa a memória
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Saiba mais sobre o uso da memória do sistema Microsoft Teams e por que o uso da memória é o mesmo entre o aplicativo da área de trabalho e o aplicativo Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878715"
---
# <a name="how-microsoft-teams-uses-memory"></a>Como o Microsoft Teams usa a memória

Alguns usuários do Microsoft Teams têm dúvidas sobre como o Teams usa a memória. Este artigo descreve como a memória é usada pelo Teams e por que o aplicativo da área de trabalho do Teams (aplicativo) e o aplicativo Web do Teams não impedem que outros aplicativos e cargas de trabalho no mesmo computador tenha memória suficiente para funcionar de forma ideal. O Teams foi projetado para usar a tecnologia da Web moderna. Para isso, o cliente de área de trabalho do Teams foi desenvolvido em Eletrônica, que usa o Chromium para renderização. Esse é o mesmo mecanismo de renderização por trás de muitos dos navegadores mais populares de hoje, incluindo o Edge e o Chrome.

## <a name="how-teams-works"></a>Como o Teams funciona

As equipes projetadas em Eletrônica permitem um desenvolvimento mais rápido e também mantém a paridade entre as versões do Teams em diferentes sistemas operacionais (Windows, Mac e Linux). Essa paridade é possível porque o Electron e o Chromium mantêm uma base de código semelhante em todas as versões. Outra vantagem dessa arquitetura é que há um perfil de uso de memória semelhante entre o aplicativo Web do Teams e a versão da área de trabalho. Tanto o aplicativo Web quanto as versões da área de trabalho usam a memória de maneira semelhante à forma como um navegador a usaria. Mais informações sobre o Electron estão disponíveis em [seu site.](https://electronjs.org/)

Confira [o Uso da Memória Chromium e](https://www.chromium.org/developers/memory-usage-backgrounder) os Principais [Conceitos na Memória do Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obter mais informações.

A imagem a seguir mostra os usos de memória lado a lado do aplicativo da área de trabalho do Teams para Windows e do aplicativo Teams Web (neste exemplo, em execução no Google Chrome).

![Uso da memória do Teams para o aplicativo da área de trabalho e o aplicativo Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso da memória no Teams

É importante entender  o comportamento esperado do Teams quando se trata de memória do sistema e conhecer os sintomas de problemas realmente problemáticos de memória do sistema.

### <a name="expected-memory-usage-by-teams"></a>Uso esperado da memória pelo Teams

Se você estiver executando o aplicativo da área de trabalho do Teams ou o aplicativo Web do Teams, o Chromium detecta quanto de memória do sistema está disponível e utiliza o suficiente dessa memória para otimizar a experiência de renderização. Quando outros aplicativos ou serviços exigem memória do sistema, o Chromium concede memória a esses processos. O Chromium ajusta o uso da memória do Teams continuamente para otimizar o desempenho do Teams sem afetar nada em execução no momento.

Dessa forma, cargas de trabalho semelhantes do Chromium podem utilizar várias quantidades de memória, dependendo da quantidade de memória do sistema disponível.

O gráfico a seguir mostra o uso da memória pelo Teams em quatro sistemas separados, cada um com quantidades diferentes de memória disponíveis. Cada um dos sistemas está processando cargas de trabalho semelhantes (mesmos aplicativos abertos e em execução).

![Uso da memória do Teams em diferentes sistemas](media/teams-memory-usage.png)

Quando os computadores têm mais memória, o Teams usará essa memória. Nos sistemas em que a memória está ficando ruim, o Teams usará menos.

### <a name="symptoms-of-system-memory-issues"></a>Sintomas de problemas de memória do sistema

Se você vir um ou mais dos seguintes sintomas em seu computador, poderá ter um problema grave de memória do sistema:

- Alto uso da memória quando vários aplicativos grandes estão sendo executados simultaneamente.
- Desempenho lento do sistema ou suspensão de aplicativos.
- Uso geral de memória total do sistema de 90% ou superior em todos os aplicativos. Com essa quantidade de uso de memória, o Teams deve devolver a memória a outros aplicativos e cargas de trabalho. O uso contínuo de memória de 90% pode significar que o Teams não está dando memória de volta ao sistema, o que indica um problema.

As imagens a seguir mostram exemplos de exibições no Gerenciador de Tarefas quando o uso da memória do sistema é anormalmente alto.

![Exibição de uso da memória do Teams no Gerenciador de Tarefas](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso da memória do Teams no Gerenciador de Tarefas](media/teams-memory-high-mem-process-list2.png)
