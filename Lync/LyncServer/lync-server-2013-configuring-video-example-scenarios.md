---
title: 'Lync Server 2013: Configurando cenários de exemplo de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configurar cenários de exemplo de vídeo para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

O Lync 2013 adiciona novos recursos de vídeo para dar suporte a 1920 x 1080 de vídeo e galeria de visão geral de alta definição (HD) e vídeo. As medições com base nos dados do cliente mostram que a largura de banda de vídeo típica aumentou apenas um pouco em comparação com o Lync 2010, mas a largura de banda máxima do fluxo de vídeo aumentou devido ao suporte total a HD (para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em [ Requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Portanto, os administradores podem querer restringir a largura de banda do vídeo para certos usuários (como os usuários de uma filial que têm menos capacidade de rede) e ajudam a garantir a melhor qualidade de vídeo possível para outros usuários (como executivos).

A tabela a seguir fornece uma lista de configurações recomendadas para configurar o vídeo para diferentes capacidades de rede. Essas configurações impedirão que alguns cenários do usuário enviem e recebam vídeos com resolução mais alta (veja a coluna mais à direita). A configuração mínima fará com que o vídeo da Galeria fique indisponível, devido ao máximo de recebimento máximo de largura de banda de rede.

### <a name="recommended-video-settings"></a>Configurações de vídeo recomendadas

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>Resolução de vídeo esperada para vídeo de boa qualidade</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Melhor</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Ponto a ponto: até 1920 x 1080 resolução de vídeo</p>
<p>Modo de exibição de Galeria: até 2 1920 x 1080 vídeos ou vários vídeos de resolução menores</p></td>
</tr>
<tr class="even">
<td><p>Corretamente</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Ponto a ponto: até 1280 x 720 resolução de vídeo</p>
<p>Modo de exibição de Galeria: até 5 640 x 360 de resolução de vídeo</p></td>
</tr>
<tr class="odd">
<td><p>Média</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Ponto a ponto: até 960 x 540 resolução de vídeo</p>
<p>Modo de exibição de Galeria: até 5 424 x 240 de resolução de vídeo</p></td>
</tr>
<tr class="even">
<td><p>Nível</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Ponto a ponto: até 424 x 240 resolução de vídeo</p>
<p>Modo de exibição de Galeria: não disponível</p></td>
</tr>
</tbody>
</table>


Você pode usar as informações da tabela anterior para implantar o novo vídeo e a Galeria de alta definição do recurso Exibir recursos de videoconferência para alguns usuários da sua organização, ao mesmo tempo em que permite diferentes resoluções de vídeo para outras pessoas.

No exemplo a seguir, o administrador acumula os novos recursos de vídeo com a melhor qualidade de vídeo disponível somente para executivos. Para os funcionários em uma filial remota com capacidade de rede baixa, apenas a configuração mínima da tabela anterior é implantada. Para todos os outros funcionários, a configuração "bom" da tabela anterior é implantada.

Para distribuir os novos recursos para os executivos, o administrador cria uma política de conferência chamada ExecutiveVideo. Esta política de conferência tem as seguintes configurações:

  - VideoBitRateKB é definido como 8000 kbps

  - TotalReceiveVideoBitRateKB é definido como 8000 kbps

  - AllowMultiview é definido como true

  - EnableMultiviewJoin é definido como true

Para os funcionários da filial, o administrador cria uma política de conferência chamada BranchOfficeVideo. Esta política de conferência tem as seguintes configurações:

  - VideoBitRateKB é definido como 350 kbps

  - TotalReceiveVideoBitRateKB é definido como 350 kbps

  - AllowMultiview é definido como true

  - EnableMultiviewJoin é definido como false

Para todos os outros funcionários, o administrador cria uma política de conferência chamada StandardVideo. Esta política de conferência tem as seguintes configurações:

  - VideoBitRateKB é definido como 2500 kbps

  - TotalReceiveVideoBitRateKB é definido como 2500 kbps

  - AllowMultiview é definido como true

  - EnableMultiviewJoin é definido como true

O administrador atribui uma política de conferência aos usuários da seguinte maneira:

  - A política de conferência ExecutiveVideo é atribuída aos executivos.

  - A política de conferência BranchOfficeVideo é atribuída a todos os funcionários da filial do escritório.

  - A política de conferência StandardVideo é atribuída a todos os outros funcionários.

Essas atribuições de política de conferência resultam na seguinte experiência do usuário:

  - Todas as conferências organizadas por qualquer modo de exibição da Galeria de suporte do usuário, mas os funcionários da filial não podem experimentar o modo de exibição de galeria.

  - Para qualquer conferência de dois participantes ou de vários participantes, os executivos podem enviar vídeo HD de 1920 x 1080 Full HD, se o hardware e o link de rede forem compatíveis com ele e puderem receber vídeo em HD de 1920 x 1080 para os outros clientes participantes.

  - Os funcionários que não são executivos experimentam resoluções mais baixas do que os executivos em suas conferências de dois participantes ou de vários participantes, mas ainda têm uma boa resolução.

  - Os funcionários que estiverem na filial receberão uma boa qualidade de vídeo em chamadas de dois participantes quando o Lync exibir o tamanho padrão da janela de vídeo; no entanto, se a janela do Lync estiver maximizada para tela inteira, a resolução do vídeo não aumentará. Para conferências com vários participantes, os funcionários da filial verão apenas um vídeo ativo.

</div>

<span> </span>

</div>

</div>

</div>

