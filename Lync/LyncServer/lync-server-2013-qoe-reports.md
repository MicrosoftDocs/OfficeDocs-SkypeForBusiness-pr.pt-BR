---
title: 'Lync Server 2013: relatórios de QoE'
description: 'Lync Server 2013: relatórios de QoE.'
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
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571397"
---
# <a name="qoe-reports-in-lync-server-2013"></a>Relatórios de QoE no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>Relatórios de resumo/tendências de QoE

Os relatórios de resumo/tendências de QoE são úteis para encontrar os horários de pico de uso do dia e examinar a qualidade da mídia durante esses horários para ajudar a garantir que os recursos de rede da sua organização sejam suficientes. Sua organização também pode usar os vários filtros disponíveis no relatório para isolar números de desempenho de determinados locais, tipos de dispositivos e clientes e servidores.

Relatórios de resumo/tendência de QoE consistem em:

  - Relatório de resumo/tendência UC-to-UC

  - Relatório de resumo/tendência PSTN

  - Relatório de Resumo de conferências/tendências

</div>

<div>

## <a name="qoe-performance-reports"></a>Relatórios de desempenho de QoE

Relatórios de desempenho de QoE fornecem detalhes sobre os três relatórios que se concentram no desempenho de QoE de servidores de mediação, servidores de conferência A/V e locais de pontos de extremidade.

</div>

<div>

## <a name="mediation-server-performance-report"></a>Relatório de desempenho do servidor de mediação

O relatório de desempenho do servidor de mediação lista as métricas obtidas por uma ou mais mediação durante o período de tempo especificado. As métricas para o trecho do servidor de comunicações unificadas (UC) para o servidor de mediação e o trecho do servidor de mediação para gateway de cada chamada são relatados separadamente. Use este relatório para comparar o volume e o desempenho dos vários servidores de mediação da sua organização.

Para cada servidor de mediação (e para cada segmento de chamada), o relatório exibe o seguinte:

  - Número de chamadas

  - Perda de pacote

  - Tempo de ida e volta

  - Torção

  - Pontuação média de opinião da conversa (MOS)

  - MOS enviando

  - MOS ouvindo

  - MOS de rede

  - Degradação de MOS de rede

  - Retorno de eco

  - Nível do sinal

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>Relatório de desempenho de servidor de conferência A/V

O relatório de desempenho do servidor de conferência A/V fornece listas de métricas obtidas por um ou mais servidores de conferência A/V durante o período de tempo especificado. Este relatório pode ser usado para comparar o volume e o desempenho dos vários servidores de conferência A/V da sua organização. Sua organização também pode isolar o relatório para mostrar apenas a experiência de tipos específicos de clientes, como clientes do Lync ou clientes PSTN.

Para cada servidor de conferência A/V, o relatório exibe o seguinte:

  - Número de conferências

  - Perda de pacote

  - Tempo de ida e volta

  - Torção

  - Pontuação média de opinião da conversa (MOS)

  - MOS enviando

  - MOS ouvindo

  - MOS de rede

  - Degradação de MOS de rede

  - Retorno de eco

  - Nível do sinal

</div>

<div>

## <a name="location-based-performance-report"></a>Relatório de desempenho baseado em local

O Location-Based relatório de desempenho fornece uma lista de locais de rede e para cada local mostra o número de chamadas em cada intervalo de qualidade predeterminado. O objetivo deste relatório é fornecer informações sobre a qualidade da mídia do grande volume de chamadas telefônicas da sua organização para vários locais, para que você possa identificar locais com desempenho ruim e ver as diferentes pontuações de qualidade de mídia nos diferentes locais da sua organização.

Ao exibir o relatório, diferentes tabelas de métricas aparecem — uma tabela para cada métrica que sua organização decide relatar. Você pode escolher entre as seguintes métricas para este relatório:

  - Pontuação média de opinião da conversa (MOS)

  - MOS de rede

  - Degradação de MOS de rede

  - MOS enviando

  - MOS ouvindo

  - Perda de pacote

  - Torção

  - Latência

</div>

</div>

<span> </span>

</div>

</div>

</div>

