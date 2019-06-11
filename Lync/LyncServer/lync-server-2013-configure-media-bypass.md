---
title: 'Lync Server 2013: Configurar bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465a949ca1581933f96f18cfe2977d400fa7a152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurar bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

Esta seção pressupõe que você já publicou e configurou pelo menos um ou mais servidores de mediação (conforme descrito em [definir um servidor de mediação no construtor de topologias no Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md)ou no [Defina e configure um pool de front-end ou um servidor Standard Edition no Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [publique a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, tudo na documentação de implantação.

Esta seção também pressupõe que você definiu pelo menos um gateway de mesmo nível de gateway para fornecer conectividade PSTN, conforme descrito em [definir um gateway no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Se o par ao qual você está se conectando for o SBC de um provedor de tronco SIP, certifique-se de que o provedor seja qualificado e suporte bypass de mídia. Por exemplo, vários provedores de tronco SIP permitirão que seu SBC receba tráfego do Servidor de Mediação. Em caso afirmativo, o bypass não deve ser habilitado para o tronco em questão. Além disso, não é possível habilitar o bypass de mídia, a não ser que sua organização revele seus endereços IP de rede internos para o provedor de tronco SIP.

<div>


> [!NOTE]  
> O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberta da comunicação <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>unificada – Lync Server em.



</div>

Esta seção descreve como habilitar o bypass de mídia para reduzir o processamento necessário para o servidor de mediação. Antes de habilitar o bypass de mídia, certifique-se de que seu ambiente atenda às condições necessárias para dar suporte ao bypass de mídia, conforme descrito em [planejamento para o bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na documentação de planejamento. Além disso, certifique-se de ter usado as informações em [planejamento para ignorar mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir se as configurações globais de bypass de mídia devem ser ignoradas para sempre ignorar o servidor de mediação ou para usar as informações do site e da região ao determinar se ignorar o servidor de mediação.

Se você já configurou opcionalmente o controle de admissão de chamada (CAC), outro recurso do Enterprise Voice avançado, observe que a reserva de largura de banda realizada pelo controle de admissão de chamada não é aplicada a qualquer chamada na qual o bypass de mídia é implantado. A verificação se a implantação do bypass de mídia é realizada primeiro, e se o bypass de mídia estiver implantado, o controle de admissão de chamada não será usado para a chamada. A verificação será realizada para o controle de admissão de chamada apenas se a verificação do bypass de mídia falhar. Os dois recursos são mutuamente exclusivos para qualquer chamada roteada para o PSTN. Esta é a lógica porque o bypass de mídia assume que as restrições de largura de banda não existem entre os pontos de extremidade de mídia em uma chamada; o bypass de mídia não pode ser realizado em links com largura de banda restrita. Como resultado, um dos seguintes serão aplicados em uma chamada PSTN: a) a mídia ignora o Servidor de Mediação e o controle de admissão de chamada não reserva largura de banda para a chamada; ou b) o controle de admissão de chamada aplica a reserva de banda larga para a chamada e a mídia é processada pelo Servidor de Mediação envolvido na chamada.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Próximas etapas: habilitar o bypass de mídia na conexão do tronco

Depois de definir as configurações iniciais para a conectividade PSTN (planos de discagem, políticas de voz, registros de uso de PSTN, roteiros de chamadas de saída e regras de tradução), comece o processo de habilitar o bypass de mídia usando as etapas em [configurar um tronco com o bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

