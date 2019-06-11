---
title: 'Lync Server 2013: Planejamento para controle de admissão de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planejamento para controle de admissão de chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Para aplicativos de comunicação unificada (UC) com base em IP, como telefonia, vídeo e compartilhamento de aplicativos, a largura de banda disponível de redes corporativas não é geralmente considerada um fator de limitação em ambientes LAN. Entretanto, nos links WAN que interconectam locais, a largura de banda de rede pode ser limitada. Quando um influxo de tráfego de rede se inscreve em um link de WAN, mecanismos atuais, como enfileiramento, buffer e descarte de pacotes, são usados para solucionar o congestionamento. O tráfego extra costuma ser adiado até que o congestionamento da rede facilite ou, se necessário, o tráfego seja cancelado. Para tráfego de dados convencionais em tais situações, o cliente de recebimento pode recuperar. Para tráfego em tempo real, como comunicação unificada, o congestionamento da rede não pode ser resolvido dessa maneira, porque o tráfego de comunicação unificado é sensível à latência e à perda de pacotes. O congestionamento na WAN pode resultar em uma má qualidade da experiência (QoE) para os usuários. Para tráfego em tempo real em condições congestionadas, é melhor negar chamadas do que fornecer conexões com baixa qualidade.

O controle de admissão de chamadas (CAC) determina se há largura de banda de rede suficiente para estabelecer uma sessão de tempo real de qualidade aceitável. No Lync Server 2013, o CAC controla o tráfego em tempo real somente para áudio e vídeo, mas não afeta o tráfego de dados. Se o caminho de WAN padrão não tiver a largura de banda necessária, o CAC pode tentar direcionar a chamada por meio de um caminho da Internet ou da rede telefônica pública comutada (PSTN). O CAC está disponível apenas no Lync Server.

Esta seção descreve a funcionalidade de controle de admissão de chamadas e explica como planejar o CAC.

<div>


> [!NOTE]  
> O Lync Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas (CAC), serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral do planejamento de informações comuns a todos esses três recursos, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configurações de rede para os recursos avançados de voz empresarial no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do controle de admissão de chamadas no Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Exemplo: reunindo seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componentes e topologias para CAC no Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Práticas recomendadas para controle de admissão de chamada no Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lista de verificação de implantação para controle de admissão de chamada no Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

