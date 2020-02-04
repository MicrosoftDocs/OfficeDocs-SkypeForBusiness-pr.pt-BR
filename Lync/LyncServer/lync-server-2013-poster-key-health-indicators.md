---
title: 'Lync Server 2013: pôster: principais indicadores de integridade'
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
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Principais indicadores de integridade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-10_

Este artigo é um complemento dos [principais indicadores de integridade: a base para manter](http://go.microsoft.com/fwlink/?linkid=391838) o pôster saudável dos servidores do Lync, que você pode baixar no centro de download.

![Cartaz descrevendo a solução de problemas com dados do KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Cartaz descrevendo a solução de problemas com dados do KHI")

Você pode usar este pôster para saber mais sobre os principais indicadores de integridade (KHIs), contadores de desempenho com limiares que se destinam a revelar problemas da experiência do usuário. A coleta de dados de KHI geralmente é o primeiro passo para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.

Se tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para cqmfeedback@microsoft.com.

O pôster explica as seguintes áreas:

  - Quais são os principais indicadores de integridade?

  - Para coletar dados do KHI

  - Fluxo de correção para todas as funções de servidor

  - Glossário

  - Servidores front-end

  - Servidores SQL back-end

  - Servidores de Mediação

  - Servidores de Borda

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Quais são os principais indicadores de integridade?

Os principais indicadores de integridade são contadores de desempenho com limiares que se destinam a revelar problemas da experiência do usuário. A coleta de dados de KHI geralmente é o primeiro passo para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.

KHIs são usadas além das soluções de monitoramento padrão do Lync (por exemplo, System Center Operations Manager, transações sintéticas, Monitoring Server) e não em vez dessas soluções.

Colete os contadores de desempenho do KHI e preencha a planilha do KHI que acompanha o guia de rede para produzir um scorecard que ajudará você a determinar a integridade do servidor de uma implantação do Lync. Depois de preenchido, ele orienta você a reparar o ambiente e oferece uma visão adicional para outros participantes. Avalie o KHIs mensalmente e incorpore-os aos processos operacionais contínuos de toda a implantação.

Baixe o [Guia de rede do Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) para ver a lista completa de KHIs e obter as planilhas relacionadas.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Para coletar dados do KHI

1.  Execute o script KHI incluído no guia de rede do Lync Server em cada servidor do Lync. Isso criará um coletor de dados dentro do monitor de desempenho e nomeá-lo KHI. Por padrão, os dados serão sondados a cada 15 segundos.

2.  Antes do início do dia útil da sua empresa, vá para cada servidor de Lync e inicie o coletor de dados KHI.

3.  No final do dia, interrompa o coletor de dados do KHI e copie os dados em um local central.

4.  Depois de usar o monitor de desempenho para preencher a planilha do KHI incluída no download do guia de rede do Lync Server, compare os resultados com os alvos recomendados.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Fluxo de correção para todas as funções de servidor

Para cada servidor na implementação do Lync, comece verificando se o desempenho do sistema e a integridade do componente do servidor está no nível ou acima do nível desejado. Só depois disso, você deve observar os indicadores relacionados à função do servidor na implementação geral do Lync.

Comece coletando dados de desempenho do KHI para todos os servidores. Para cada uma das funções do sistema (detalhes discutidos mais adiante neste documento) determine se os componentes básicos do sistema atendem aos alvos recomendados. Se não fizerem isso, corrija o desempenho do sistema e, em seguida, colete novamente dados do KHI e garanta a integridade do sistema antes de examinar as métricas específicas da função do servidor na implementação do Lync. A integridade do componente para todas as funções é definida como:

  - Utilização \< da CPU 80%

  - Média de gravação \< em disco 10 ms

  - Média de leitura \< de disco 10 ms

  - Memória \>disponível de 20% do total de sistema em MB

  - Comprimento \< da fila de rede 2

  - Pacotes descartados (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossário

Os termos e acrônimos a seguir são usados neste cartaz:

Como MCU = unidade de controle de vários pontos do compartilhamento de aplicativos

AV MCU = áudio/vídeo MCU

MENSAGEM instantânea MCU = mensagem instantânea MCU

UCWA = API Web de comunicação unificada

Borda de AV = travessia de áudio/vídeo via Edge

Autenticação de AV auth = áudio/vídeo

Pilha SIP = contém a implementação principal SIP do Lync

Proxy de dados = usado para a conferência de borda

LySS = serviço de armazenamento do Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Servidores front-end

Os seguintes destinos de KHI recomendados são específicos para servidores front-end, além da integridade básica do componente:


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
<td><p>Estado &lt;de integridade do MCU 2</p></td>
</tr>
<tr class="even">
<td><p>Componentes da Web</p></td>
<td><p>Tempo limite &lt;do anúncio de expansão da lista de distribuição 0</p>
<p>Falhas de ABWQ = 0</p>
<p>Falhas de LIS = 0</p>
<p>Erros &lt; de autenticação 1/s</p>
<p>ASP.NET de solicitações v4 rejeitadas = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pilha SIP</p></td>
<td><p>Média de processamento &lt; de mensagens de entrada 1 s</p>
<p>Respostas de entrada &lt; ignoradas 1/s solicitações &lt; de entrada ignoradas 1/s</p>
<p>Latência &lt; da fila 100 ms</p>
<p>SPROC latência &lt; de 100 ms</p>
<p>Solicitações limitadas = 0</p>
<p>Erros &lt; de autenticação 1/s</p>
<p>O tempo limite &lt; das mensagens de entrada expirou 2</p>
<p>Média de mensagens de entrada &lt; em espera de 1 s</p>
<p>Conexões &lt; controladas de fluxo 2</p>
<p>Média de atraso &lt; da fila de out 2 segundos</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% do espaço usado pelo serviço de armazenamento &lt; DB 80</p>
<p>#de falhas de replicação de réplica = 0</p>
<p>#de eventos de perda de dados = 0</p></td>
</tr>
<tr class="odd">
<td><p>Server</p></td>
<td><p>Expectativa de vida da &gt; página de 300 segundos.</p>
<p>Solicitações em lote/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Servidores SQL back-end

Os seguintes destinos KHI recomendados são específicos dos SQL Servers, além da integridade básica do componente:


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
<td><p>Server</p></td>
<td><p>Expectativa de vida da &gt; página de 300 segundos.</p>
<p>Solicitações em lote/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Servidores de Mediação

Os seguintes destinos de KHI recomendados são específicos para servidores de mediação além da integridade básica do componente:


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
<td><p>Índice de falha na chamada de carga = 0</p>
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

Os seguintes destinos de KHI recomendados são específicos para servidores de borda além da integridade básica do componente:


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
<td><p>Autenticação por AV</p></td>
<td><p>Solicitações &lt; incorretas 20/s</p></td>
</tr>
<tr class="even">
<td><p>Borda de AV</p></td>
<td><p>Erros &lt;de autenticação 20/s</p>
<p>Falhas &lt;de alocação 20/s</p>
<p>Pacotes ignorados &lt;300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de dados</p></td>
<td><p>Conexões &lt; de servidor limitada 3</p>
<p>O sistema está &lt;limitando 1</p></td>
</tr>
<tr class="even">
<td><p>Pilha SIP</p></td>
<td><p>Conexões com limite ignorado &lt; 1</p>
<p>Envios com tempo &lt;limite de 10</p>
<p>Conexões &lt;controladas de fluxo 100</p>
<p>Solicitações de entrada &lt; ignoradas 1/s</p>
<p>Média de processamento &lt; de mensagens 3 segundos</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Guia de rede do Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Principais indicadores de integridade: a base para a manutenção de servidores de Lync saudáveis](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia de qualidade de chamada do Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

