---
title: 'Lync Server 2013: planejamento para bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d9687069e82cde803f7a01873db482ea2afa2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521988"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planejamento de bypass de mídia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Desvio de mídia refere-se à remoção do Servidor de Mediação do caminho da mídia, sempre que possível para chamadas cuja sinalização percorre o Servidor de Mediação.

O desvio de mídia pode aprimorar a qualidade da voz reduzindo latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis. A escalabilidade pode ser aprimorada, porque a eliminação do processamento de mídia para chamadas desviadas reduz a carga no Servidor de Mediação. Essa redução no carregamento complementa a capacidade do servidor de mediação controlar vários gateways.

Quando um site de filial sem um servidor de mediação estiver conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduzirá a necessidade de largura de banda permitindo que a mídia de um cliente em um site de filial flua diretamente para seu gateway local sem antes ter que fluir pelo link WAN para um servidor de mediação no site central e voltar

Ao aliviar o servidor de mediação do processamento de mídia, o bypass de mídia também pode reduzir o número de servidores de mediação exigidos por uma infraestrutura do Enterprise Voice.

A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem desvio de mídia.

**Caminhos de mídia e sinalização com e sem desvio de mídia**

![Imposição de conexão de mídia do CAC de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Imposição de conexão de mídia do CAC de voz")

Como regra geral, habilite o desvio de mídia onde possível.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do bypass de mídia no Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modos de bypass de mídia no Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Bypass de mídia e controle de admissão de chamadas no Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Seções Relacionadas

[Implantando recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

