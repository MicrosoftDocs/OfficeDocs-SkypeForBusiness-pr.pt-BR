---
title: 'Lync Server 2013: Sites'
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
ms.openlocfilehash: f2e5dc3323ad14f02a5b24258878512707f66f19
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Sites do Lync Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-16_

No Lync Server, você define *sites* em sua rede que contenham componentes do Lync Server. Um site é um conjunto de computadores conectados por meio de uma rede de alta velocidade e baixa latência, como uma rede local (LAN), ou de duas redes conectadas por uma rede de fibra ótica de alta velocidade. Observe que os sites do Lync Server são um conceito separado dos sites dos serviços de domínio Active Directory e dos sites do Microsoft Exchange Server. Seus sites do Lync Server não precisam corresponder a seus sites do Active Directory.

<div>

## <a name="site-types"></a>Tipos de site

Cada site é um *site central*, que contém pelo menos um pool de front-end ou um servidor Standard Edition, ou um *site de filial*. Cada site de filial está associado a exatamente um site central, e os usuários no site de filial obtêm a maior parte da funcionalidade do Lync Server dos servidores no site central associado.

Cada site de filial contém um dos seguintes:

  - Um *aparelho de ramificação sobreviventes (SBA)*, que é um servidor blade padrão do setor com um registrador do Lync Server e um servidor de mediação em execução no Windows Server. O aparelho de ramificação sobreviventes também contém um gateway PSTN (rede telefônica pública comutada). O aparelho de ramificação sobreviventes foi projetado para sites de filiais com entre 25 e 1000 usuários.

  - Um *servidor de ramificação sobreviventes (SBS)*, que é um servidor que executa o Windows Server e atende aos requisitos de hardware especificado e que tem o software do Lync Server registrador e do servidor de mediação instalado nele. Ele deve estar conectado a um provedor de serviços telefônicos por meio de um gateway PSTN ou de um tronco SIP. O servidor de ramificação sobreviventes foi projetado para sites de filiais com os usuários do 1000 e do 5000.

  - Um gateway PSTN e, opcionalmente, um *servidor de mediação*. Para obter detalhes sobre essa e outras funções de servidor, consulte [funções de servidor no Lync server 2013](lync-server-2013-server-roles.md).

Uma filial com um link de rede de longa distância (WAN) resistente para um site central pode usar a terceira opção, um gateway PSTN e, opcionalmente, um servidor de mediação. Os sites de filiais com links menos resistentes devem usar um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes, que fornecem resiliência em casos de falha de rede de longa distância. Por exemplo, em um site com um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes implantado, os usuários ainda poderão fazer e receber chamadas de voz corporativa se a WAN que estiver conectando o site de filial ao site central estiver inativa. Para obter detalhes sobre o dispositivo de ramificação sobreviventes, servidor de ramificação sobreviventes e resiliência, consulte [planejando a resiliência do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) na documentação de planejamento.

</div>

<div>

## <a name="site-topologies"></a>Topologias de site

Sua implantação deve incluir pelo menos um site central e pode incluir zero em muitos sites de filiais. Cada site de filial está associado a um site central. O site central fornece os serviços do Lync Server para o site de ramificação que não são hospedados localmente no site da filial, como presença e conferência.

Se você tiver vários sites, poderá emparelhar os pools de front-ends em sites diferentes para permitir recursos de recuperação de desastres. Para obter detalhes, consulte [suporte de alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Funções do servidor no Lync Server 2013](lync-server-2013-server-roles.md)  
[Suporte à alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planejamento para resiliência do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

