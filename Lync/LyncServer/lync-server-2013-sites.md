---
title: Sites do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3342fb05a0ad843be9e4b6b065507a368e1c4556
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Sites do Lync Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-16_

No Lync Server, você define *sites* em sua rede que contenham componentes do Lync Server. Um site é um conjunto de computadores bem conectados por uma rede de alta velocidade e baixa latência, como uma rede local (LAN) única ou duas redes conectadas por uma rede óptica de alta velocidade. Observe que os sites do Lync Server são um conceito separado dos sites dos serviços de domínio do Active Directory e dos sites do Microsoft Exchange Server. Seus sites do Lync Server não precisam corresponder aos sites do Active Directory.

<div>

## <a name="site-types"></a>Tipos de Site

Cada site é um *site central*, que contém pelo menos um pool de front-ends ou um servidor Standard Edition, ou um *site de filial*. Cada site de filial é associado a um site central, e os usuários no site de filial obtêm a maior parte da funcionalidade do Lync Server dos servidores no site central associado.

Cada site de filial contem ao menos um dos seguintes:

  - Um *aparelho de filial persistente (SBA)*, que é um servidor de lâmina padrão da indústria com um registrador do Lync Server e um servidor de mediação executando no Windows Server. O aparelho de filial persistente também contém um gateway PSTN (rede telefônica pública comutada). O aparelho de filial persistente foi projetado para sites de filiais com entre 25 e 1000 usuários.

  - Um *servidor de ramificação persistente (SBS)*, que é um servidor que executa o Windows Server e que atende aos requisitos de hardware especificados, e que tem o software de servidor de mediação e registrador do Lync Server instalado nele. Ele deve se conectar ao gateway PSTN ou tronco SIP para um provedor de serviço telefônico. O Servidor de Filial Sustentável foi projetado para sites de filial com 1000 a 5000 usuários.

  - Um gateway PSTN e opcionalmente um *Servidor de Mediação*. Para obter detalhes sobre esta e outras funções de servidor, consulte [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).

Uma filial com um link WAN (rede de longa distância) resistente à um site central pode usar a terceira opção, um gateway PSTN e, opcionalmente, um Servidor de Mediação. Os sites de filiais com links menos resistentes devem usar um aparelho de filial persistente ou servidor de filial persistente, que oferecem resiliência em horários de falhas de rede de longa distância. Por exemplo, em um site com um aparelho de filial persistente ou servidor de filial persistente implantado, os usuários ainda poderão fazer e receber chamadas do Enterprise Voice se a WAN conectando o site de filial ao site central estiver desativada. Para obter detalhes sobre o aparelho de filial persistente, servidor de filial persistente e resiliência, consulte [Planning for Enterprise Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) na documentação de planejamento.

</div>

<div>

## <a name="site-topologies"></a>Topologias de Site

Sua implantação deve incluir ao menos um site central e pode incluir de nenhum a muitos sites de filial. Cada site de filial é afiliado a um site central. O site central fornece os serviços do Lync Server para o site de filial que não estão hospedados localmente no site de filial, como presença e conferência.

Se você possuir vários sites, pode pareá-los juntos nos pools de Front End em diferentes sites para ativar as capacidades de recuperação de desastres. Para obter detalhes, consulte [High Availability and Disaster Recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Funções de servidor no Lync Server 2013](lync-server-2013-server-roles.md)  
[Suporte de alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planejamento para resiliência do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

