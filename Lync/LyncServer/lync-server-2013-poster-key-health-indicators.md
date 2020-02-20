---
title: 'Lync Server 2013: cartaz: principais indicadores de integridade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2710e85eced76241f4946ef2746e544d07be941f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Principais indicadores de integridade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-10_

Este artigo é um complemento aos [principais indicadores de integridade: a Fundação para manter](https://go.microsoft.com/fwlink/?linkid=391838) o pôster saudável dos servidores do Lync, que você pode baixar do centro de download.

![Cartaz descrevendo a solução de problemas usando dados do KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Cartaz descrevendo a solução de problemas usando dados do KHI")

Você pode usar este cartaz para saber mais sobre os principais indicadores de integridade (KHIs), contadores de desempenho com limiares destinados à revelação de problemas de experiência do usuário. Coletar dados de KHI é geralmente a primeira etapa para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.

Se você tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para o cqmfeedback@microsoft.com.

O cartaz explica as seguintes áreas:

  - Quais são os principais indicadores de integridade?

  - Para coletar dados do KHI

  - Fluxo de correção para todas as funções de servidor

  - Glossário

  - Servidores front-end

  - Servidores SQL de back-end

  - Servidores de mediação

  - Servidores de Borda

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Quais são os principais indicadores de integridade?

Os principais indicadores de integridade são contadores de desempenho com limiares destinados à revelação de problemas de experiência do usuário. Coletar dados de KHI é geralmente a primeira etapa para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.

Os KHIs são usados além das soluções de monitoramento padrão do Lync (por exemplo, o System Center Operations Manager, as transações sintéticas, o monitoramento do servidor) e não em vez dessas soluções.

Colete os contadores de desempenho do KHI e preencha a planilha KHI que acompanha o guia de rede para produzir um scorecard que o ajudará a determinar a integridade do servidor de uma implantação do Lync. Depois de preenchida, ele orienta você a reparar o ambiente e dá mais percepção a outros participantes. Avaliar o KHIs mensalmente e incorporá-los em todos os processos operacionais em andamento da implantação.

Baixe o [Guia de rede do Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) para ver a lista completa de KHIs e para obter as planilhas relacionadas.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Para coletar dados do KHI

1.  Execute o script KHI incluído no guia de rede do Lync Server em cada Lync Server. Isso criará um coletor de dados dentro do monitor de desempenho e o nomeará KHI. Por padrão, os dados serão pesquisados a cada 15 segundos.

2.  Antes do início do dia útil da sua empresa, vá para cada servidor do Lync e inicie o coletor de dados KHI.

3.  No final desse dia, interrompa o coletor de dados do KHI e copie os dados para um local central.

4.  Após usar o monitor de desempenho para preencher a planilha do KHI incluída no download do guia de rede do Lync Server, compare os resultados com os alvos recomendados.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Fluxo de correção para todas as funções de servidor

Para cada servidor em sua implementação do Lync, comece verificando se a integridade do componente do servidor e o desempenho do sistema estão no nível desejado ou acima dele. Somente depois isso deve observar os indicadores relacionados à função do servidor na implementação geral do Lync.

Comece coletando dados de desempenho do KHI para todos os servidores. Para cada uma das funções de sistema (detalhes abordados posteriormente neste documento), determine se os componentes básicos do sistema atendem aos alvos recomendados. Caso contrário, corrija o desempenho do sistema e, em seguida, colete novamente os dados do KHI e garanta a integridade do sistema antes de examinar as métricas específicas da função do servidor na implementação do Lync. A integridade do componente para todas as funções é definida como:

  - Utilização \< da CPU 80%

  - Média de gravação \< de disco 10 ms

  - Média de leitura \< de disco 10 ms

  - Memória \>disponível de 20% no total de sistema

  - Comprimento \< da fila de rede 2

  - Pacotes descartados (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossário

Os seguintes termos e acrônimos são usados neste cartaz:

Como MCU = unidade de controle de vários pontos do compartilhamento de aplicativos

AV MCU = áudio/vídeo MCU

IM MCU = mensagens instantâneas MCU

UCWA = API Web de comunicações unificadas

Borda AV = passagem de áudio/vídeo por borda

Autenticação AV = autenticação de áudio/vídeo

Pilha SIP = contém a implementação principal SIP do Lync

Proxy de dados = usado para conferência de borda

LySS = serviço de armazenamento do Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Servidores front-end

Os seguintes destinos KHI recomendados são específicos para servidores front-end, além da integridade básica do componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>Estado &lt;2 da integridade MCU</p></td>
</tr>
<tr class="even">
<td><p>Componentes Web</p></td>
<td><p>Tempos limite &lt;do AD de expansão de lista de distribuição 0</p>
<p>Falhas de ABWQ = 0</p>
<p>Falhas de LIS = 0</p>
<p>Erros &lt; de autenticação 1/seg</p>
<p>Solicitações ASP.NET v4 rejeitadas = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pilha SIP</p></td>
<td><p>Média de processamento &lt; de mensagens de entrada 1 seg</p>
<p>Respostas de entrada &lt; ignoradas 1/seg solicitações &lt; de entrada descartadas 1/s</p>
<p>Latência &lt; da fila 100 ms</p>
<p>Latência &lt; SPROC 100 ms</p>
<p>Solicitações limitadas = 0</p>
<p>Erros &lt; de autenticação 1/seg</p>
<p>Mensagens de entrada tempo limite &lt; de 2</p>
<p>Média de mensagens de entrada &lt; suspensas 1 seg</p>
<p>Conexões &lt; controladas por fluxo 2</p>
<p>Atraso &lt; médio da fila de saída 2 seg</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% de espaço usado pelo serviço de armazenamento &lt; DB 80</p>
<p>#falhas de replicação de réplica = 0</p>
<p>#eventos de perda de dados = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Expectativa de vida da &gt; página 300 seg.</p>
<p>Solicitações em lote/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Servidores SQL de back-end

Os seguintes destinos KHI recomendados são específicos para os SQL Servers, além da integridade básica do componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Expectativa de vida da &gt; página 300 seg.</p>
<p>Solicitações em lote/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Servidores de mediação

Os seguintes destinos KHI recomendados são específicos para servidores de mediação além da integridade básica do componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serviço do servidor de mediação</p></td>
<td><p>Índice de falha de chamada de carregamento = 0</p>
<p>Chamadas com falha devido ao &lt;proxy 10</p>
<p>Chamadas com falha devido ao &lt;gateway 10</p>
<p>Chamadas (in ou out) rejeitadas = 0</p>
<p>Candidatos à mídia ausentes = 0</p>
<p>Falhas de verificação de conectividade de mídia = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Servidores de Borda

Os seguintes destinos KHI recomendados são específicos para servidores de borda além da integridade básica do componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autenticação AV</p></td>
<td><p>Solicitações &lt; inválidas 20/seg</p></td>
</tr>
<tr class="even">
<td><p>Borda de AV</p></td>
<td><p>Falhas &lt;de auth. 20/seg</p>
<p>Falhas &lt;de alocação 20/seg</p>
<p>Pacotes removidos &lt;300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de dados</p></td>
<td><p>Conexões &lt; de servidor limitado 3</p>
<p>O sistema está &lt;regulando 1</p></td>
</tr>
<tr class="even">
<td><p>Pilha SIP</p></td>
<td><p>Conexões com limite ignorado &lt; 1</p>
<p>Envio do tempo limite &lt;de 10</p>
<p>Conexões &lt;de fluxo controlado 100</p>
<p>Solicitações de entrada &lt; descartadas 1/s</p>
<p>Média de processamento &lt; de mensagens 3 seg</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Guia de rede do Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Principais indicadores de integridade: a base para manter os servidores de Lync saudáveis](https://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia de qualidade de chamada do Lync](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

