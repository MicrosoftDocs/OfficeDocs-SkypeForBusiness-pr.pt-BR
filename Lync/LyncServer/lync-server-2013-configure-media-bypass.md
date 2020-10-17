---
title: 'Lync Server 2013: configurar bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6153be57ec60e58b404370ece2c2214ae33083c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520619"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurar bypass de mídia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

Esta seção pressupõe que você já publicou e configurou pelo menos um ou mais servidores de mediação (conforme descrito em [definir um servidor de mediação no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md), ou em [definir e configurar um pool de front-ends ou servidor Standard Edition no Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, todos na documentação

Esta seção também pressupõe que você tenha definido pelo menos um ponto de gateway para fornecer conectividade PSTN, conforme descrito em [definir um gateway no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Se o ponto ao qual você se conecta for o SBC de um provedor de tronco SIP, certifique-se de que o provedor é um provedor qualificado e que o provedor oferece suporte a bypass de mídia. Por exemplo, vários provedores de tronco SIP permitirão que seu SBC receba tráfego do Servidor de Mediação. Caso sim, o bypass não deve ser habilitado para o tronco em questão. Além disso, não é possível habilitar o bypass de mídia a não ser que sua organização releve seus endereços IP de rede internos para o provedor de tronco SIP.

<div>


> [!NOTE]  
> O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações unificativas – Lync Server em <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

Esta seção descreve como habilitar o bypass de mídia para reduzir o processamento necessário do Servidor de Mediação. Antes de habilitar o bypass de mídia, certifique-se de que o ambiente atende às condições necessárias para dar suporte ao bypass de mídia, conforme descrito em [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na documentação de planejamento. Além disso, certifique-se de ter usado as informações em [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir se habilitará as configurações globais de bypass de mídia para sempre ignorar o servidor de mediação ou para usar as informações do site e da região ao determinar se deve ignorar o servidor de mediação.

Se você já configurou opcionalmente o controle de admissão de chamada (CAC), outro recurso do Enterprise Voice avançado, observe que a reserva de largura de banda realizada pelo controle de admissão de chamada não é aplicada a qualquer chamada na qual o bypass de mídia é implantado. A verificação se a implantação do bypass de mídia é realizado primeiro e se o bypass de mídia é implantado, o controle de admissão de chamada não é usado para a chamada; apenas se a verificação do bypass de mídia falhar, a verificação é realizada para o controle de admissão de chamada. Os dois recursos são mutuamente exclusivos para qualquer chamada roteada para o PSTN. Esta é a lógica porque o bypass de mídia assume que as restrições de largura de banda não existam entre os pontos de extremidade de mídia em uma chamada; o bypass de mídia não pode ser realizado em links com largura de banda restrita. Como resultado, um dos seguintes serão aplicados em uma chamada PSTN: a) a mídia ignora o Servidor de Mediação e o controle de admissão de chamada não reserva largura de banda para a chamada; ou b) o controle de admissão de chamada aplica a reserva de banda larga para a chamada e a mídia é processada pelo Servidor de Mediação envolvido na chamada.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Próximas etapas: Habilitar o bypass de mídia na conexão de tronco

Após definir as configurações iniciais para a conectividade PSTN (planos de discagem, políticas de voz, registros de uso de PSTN, rotas de chamadas de saída e regras de conversão), inicie o processo de habilitar o bypass de mídia usando as etapas em [configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar o bypass de mídia no Lync Server 2013 para sempre ignorar o servidor de mediação](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Definir as configurações globais de bypass de mídia no Lync Server 2013 para usar informações do site e da região](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

