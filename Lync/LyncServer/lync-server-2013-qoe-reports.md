---
title: 'Lync Server 2013: relatórios de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Relatórios de QoE no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>Relatórios de resumo/tendências de QoE

Os relatórios de resumo/tendências de QoE são úteis para encontrar os períodos de pico de uso do dia e examinar a qualidade da mídia durante esses horários para ajudar a garantir que os recursos de rede da sua organização sejam suficientes. Sua organização também pode usar os vários filtros disponíveis no relatório para isolar números de desempenho de certos locais, tipos de cliente e dispositivos e servidores.

Relatórios de resumo/tendências de QoE consistem em:

  - Relatório de Resumo de UC para UC/tendências

  - Relatório de resumo/tendência PSTN

  - Relatório Resumo da Conferência/resumo de tendências

</div>

<div>

## <a name="qoe-performance-reports"></a>Relatórios de desempenho de QoE

Relatórios de desempenho de QoE fornecem detalhes sobre os três relatórios que se concentram no desempenho do QoE de servidores de mediação a/V e em locais de ponto de extremidade.

</div>

<div>

## <a name="mediation-server-performance-report"></a>Relatório de desempenho do servidor de mediação

O relatório de desempenho do servidor de mediação lista as métricas obtidas por uma ou mais mediação durante o período de tempo especificado. As métricas do trecho do servidor de comunicação unificada (UC) para o servidor de mediação e o trecho do servidor de mediação para gateway de cada chamada são reportados separadamente. Use esse relatório para comparar o volume e o desempenho dos vários servidores de mediação da sua organização.

Para cada servidor de mediação (e para cada segmento de chamada), o relatório exibe o seguinte:

  - Número de chamadas

  - Perda de pacote

  - Tempo de viagem de ida e volta

  - Tremulação

  - Pontuação média de opinião de conversa (MOS)

  - Como enviar MOS

  - MOS ouvindo

  - MOS de rede

  - Degradação de MOS de rede

  - Retorno de eco

  - Nível do sinal

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>Relatório de desempenho do servidor de conferência A/V

O relatório de desempenho do servidor de conferência A/V fornece listas de métricas obtidas por um ou mais servidores de conferência A/V durante o período de tempo especificado. Esse relatório pode ser usado para comparar o volume e o desempenho dos vários servidores de conferência A/V da sua organização. Sua organização também pode isolar o relatório para mostrar apenas a experiência de tipos específicos de cliente, como clientes do Lync ou clientes PSTN.

Para cada servidor de conferência A/V, o relatório exibe o seguinte:

  - Número de conferências

  - Perda de pacote

  - Tempo de viagem de ida e volta

  - Tremulação

  - Pontuação média de opinião de conversa (MOS)

  - Como enviar MOS

  - MOS ouvindo

  - MOS de rede

  - Degradação de MOS de rede

  - Retorno de eco

  - Nível do sinal

</div>

<div>

## <a name="location-based-performance-report"></a>Relatório de desempenho baseado em local

O relatório de desempenho baseado em local fornece uma lista de locais de rede e para cada local mostra o número de chamadas em cada intervalo predeterminado de qualidade. O objetivo deste relatório é fornecer uma visão geral da qualidade da mídia do maior volume de chamadas telefônicas da sua organização para vários locais, de modo que você possa identificar locais deficientes e ver as diferentes classificações de qualidade da mídia na sua organização locais diferentes.

Ao exibir o relatório, diferentes tabelas de métricas são exibidas — uma tabela para cada métrica à qual sua organização decide se reportar. Você pode escolher entre as seguintes métricas deste relatório:

  - Pontuação média de opinião de conversa (MOS)

  - MOS de rede

  - Degradação de MOS de rede

  - Como enviar MOS

  - MOS ouvindo

  - Perda de pacote

  - Tremulação

  - Latência

</div>

</div>

<span> </span>

</div>

</div>

</div>

