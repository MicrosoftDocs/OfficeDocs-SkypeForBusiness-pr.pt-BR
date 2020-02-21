---
title: 'Lync Server 2013: planejamento para controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5729989334297d4a6b368808079b0a7b0f4cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planejando o controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Para aplicativos UC (comunicações unificadas) que são baseados em IP, como telefonia, vídeo e compartilhamento de aplicativos, a largura de banda disponível de redes corporativas não é geralmente considerada um fator de limitação em ambientes de LAN. No entanto, nos links WAN que interconectam sites, a largura de banda da rede pode ser limitada. Quando um influxo de tráfego de rede se inscreve em um link de WAN, mecanismos atuais, como enfileiramento, armazenamento em buffer e descarte de pacotes, são usados para resolver o congestionamento. O tráfego extra costuma atrasar até que o congestionamento da rede facilite ou, se necessário, o tráfego seja Descartado. Para o tráfego de dados convencionais nessas situações, o cliente de recebimento pode se recuperar. Para tráfego em tempo real, como comunicação unificada, o congestionamento da rede não pode ser resolvido dessa maneira, porque o tráfego de comunicação unificado é confidencial para a latência e perda de pacotes. O congestionamento na WAN pode resultar em má qualidade da experiência (QoE) para os usuários. Para tráfego em tempo real em condições congestionadas, é melhor negar chamadas do que fornecer conexões com qualidade ruim.

O CAC (controle de admissão de chamadas) determina se há largura de banda de rede suficiente para estabelecer uma sessão em tempo real de qualidade aceitável. No Lync Server 2013, o CAC controla o tráfego em tempo real somente para áudio e vídeo, mas não afeta o tráfego de dados. Se o caminho de WAN padrão não tiver a largura de banda necessária, o CAC pode tentar rotear a chamada através de um caminho da Internet ou da rede telefônica pública comutada (PSTN). O CAC está disponível somente no Lync Server.

Esta seção descreve a funcionalidade de controle de admissão de chamada e explica como planejar o CAC.

<div>


> [!NOTE]  
> O Lync Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas (CAC), serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral das informações de planejamento comuns a todos os três recursos, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configurações de rede para os recursos avançados do Enterprise Voice no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do controle de admissão de chamadas no Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Exemplo: coletando seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componentes e topologias para CAC no Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Práticas recomendadas para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lista de verificação de implantação para controle de admissão de chamada no Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

