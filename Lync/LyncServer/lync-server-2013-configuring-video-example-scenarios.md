---
title: 'Lync Server 2013: Configurando cenários de exemplo de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 128703a39563124f6abfc4ae44143d274fd3a7c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configurando cenários de exemplo de vídeo para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

O Lync 2013 adiciona novos recursos de vídeo para suportar o vídeo de 1920 x 1080 de alta definição (HD) e galeria do modo de exibição de imagem. As medições com base nos dados do cliente mostram que a largura de banda de vídeo típica aumentou apenas um pouco para o Lync 2010, mas a largura de banda máxima do fluxo de vídeo aumentou devido ao suporte total de HD (para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em [requisitos de largura de banda de rede para o tráfego de mídia no Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Portanto, os administradores podem restringir a largura de banda de vídeo para determinados usuários (como os usuários em um escritório filial com menor capacidade de rede) e ajuda a garantir a melhor qualidade de vídeo possível para outros usuários (como executivos).

A tabela a seguir oferece uma lista de configurações recomendadas para configurar vídeo para diferentes capacidades de rede. Estas configurações irão restringir alguns cenários do usuário de enviar e receber vídeos de maior resolução (consulte a coluna mais a direita). A configuração mínima resultará no Vídeo da Galeria indisponível, devido ao baixo máximo receber largura de banda de rede.

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
<th>Resolução de vídeo esperada para boa qualidade de vídeo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Melhor</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Verdadeiro</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Ponto a ponto: Resolução de vídeo de até 1920 x 1080</p>
<p>Exibição de galeria: Até dois vídeos de 1920 x 1080 ou vários vídeos de resolução menor</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Verdadeiro</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Ponto a ponto: Resolução de vídeo de até 1280 x 720</p>
<p>Exibição de galeria: Até cinco vídeos de resolução 640 x 360</p></td>
</tr>
<tr class="odd">
<td><p>Médio</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Verdadeiro</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Ponto a ponto: Resolução de vídeo de até 960 x 540</p>
<p>Exibição de galeria: Até cinco vídeos de resolução de 424 x 240</p></td>
</tr>
<tr class="even">
<td><p>Mínimo</p></td>
<td><p>True</p></td>
<td><p>Falso</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Ponto a ponto: Resolução de vídeo de até 424 x 240</p>
<p>Exibição de galeria: Indisponível</p></td>
</tr>
</tbody>
</table>


É possível usar a informação na tabela anterior para exibir o novo vídeo HD e recursos de conferência de vídeo de Exibição de Galeria para alguns usuários na organização, enquanto permite diferentes resoluções de vídeo para outros.

No exemplo a seguir, o administrador encaminha os novos recursos de vídeo com a maior qualidade de vídeo disponível apenas para executivos. Para funcionários em um escritório filial remoto que possui baixa capacidade de rede, apenas a configuração mínima da tabela anterior é implantada. Para todos os outros funcionários, a configuração "Bom" na tabela anterior é implantada.

Para destacar os novos recursos para executivos, o administrador cria uma política de conferência chamada ExecutiveVideo. Esta política de conferência possui as seguintes configurações:

  - VideoBitRateKB está definido para 8000 Kbps

  - TotalReceiveVideoBitRateKB está definido para 8000 Kbps

  - AllowMultiview está definido para True

  - EnableMultiviewJoin está definido para True

Para funcionários no escritório de filial, o administrador cria uma política de conferência chamada BranchOfficeVideo. Esta política de conferência possui as seguintes configurações:

  - VideoBitRateKB está definido para 350 Kbps

  - TotalReceiveVideoBitRateKB está definido para 350 Kbps

  - AllowMultiview está definido para True

  - EnableMultiviewJoin está definido para False

Para todos os outros funcionários, o administrador cria uma política de conferência chamada StandardVideo. Esta política de conferência possui as seguintes configurações:

  - VideoBitRateKB está definido para 2500 Kbps

  - TotalReceiveVideoBitRateKB está definido para 2500 Kbps

  - AllowMultiview está definido para True

  - EnableMultiviewJoin está definido para True

O administrador atribui a política de conferência para usuários como a seguir:

  - A política de conferência ExecutiveVideo é atribuída aos executivos.

  - A política de conferência BranchOfficeVideo é atribuída a todos os funcionários no escritório de filial.

  - A política de conferência StandardVideo é atribuída a todos os outros funcionários.

Estas atribuições de política de conferência resulta na seguinte experiência do usuário:

  - Todas as conferências organizadas por qualquer Exibição de Galeria de suporte do usuário, mas os funcionários no escritório de filial não podem utilizar a Exibição de Galeria.

  - Para qualquer conferência de várias partes ou de duas partes, executivos podem enviar vídeo HD completo 1920 x 1080, se seu hardware e link de rede suportar e pode receber vídeo de HD completo 1920 x 1080 e o outro cliente participante suporta.

  - Funcionários que não são executivos enfrentam resoluções mais baixas do que os executivos em suas conferências de duas partes ou várias partes, mas ainda têm boa resolução.

  - Os funcionários que estão na filial receberão boa qualidade de vídeo em chamadas de duas partes quando o Lync exibir o tamanho padrão da janela de vídeo; no entanto, se a janela do Lync estiver maximizada para tela inteira, a resolução de vídeo não aumentará. Para conferências com vários participantes, os funcionários no escritório de filial verão apenas um vídeo ativo.

</div>

<span> </span>

</div>

</div>

</div>

