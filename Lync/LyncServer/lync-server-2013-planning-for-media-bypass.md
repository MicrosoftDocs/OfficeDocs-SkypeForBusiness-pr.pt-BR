---
title: 'Lync Server 2013: Planejamento de bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa60b6658eca7a73e509a7f6c707c3cf48c7f16e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planejamento de bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O bypass de mídia se refere a remover o servidor de mediação do caminho de mídia sempre que possível para chamadas cujo sinal percorre o servidor de mediação.

O bypass de mídia pode aprimorar a qualidade da voz reduzindo a latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis. A escalabilidade pode ser aprimorada, pois a eliminação do processamento de mídia para chamadas ignoradas reduz a carga no servidor de mediação. Essa redução na carga complementa a capacidade do servidor de mediação para controlar vários gateways.

Onde um site de filiais sem um servidor de mediação está conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduz a necessidade de largura de banda ao permitir que a mídia de um cliente em um site de filiais flua diretamente para seu gateway local sem Primeiro, é necessário fluir pelo link de WAN para um servidor de mediação no site central e para trás.

Ao enliberar o servidor de mediação do processamento de mídia, o bypass da mídia também pode reduzir o número de servidores de mediação que uma infraestrutura Enterprise Voice requer.

A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem bypass de mídia.

**Caminhos de mídia e sinalização com e sem desvio de mídia**

![Aplicação de voz do CAC ignorando] a imposição de conexão (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicação de voz do CAC ignorando") a imposição de conexão

Como regra geral, habilite o bypass de mídia sempre que possível.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do bypass de mídia no Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modos de bypass de mídia no Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Bypass de mídia e controle de admissão de chamadas no Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Seções Relacionadas

[Implantação de recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

