---
title: 'Lync Server 2013: componentes de conectividade PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 973962c7f52474f65766e6772647359c8089daee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Componentes de conectividade PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço). Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas. Da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser igual a qualquer outra sessão SIP.

Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como um link SIP direto, ou sem um PBX).

<div>

## <a name="sip-trunking"></a>Tronco SIP

Como alternativa ao uso de gateways PSTN, você pode conectar sua solução Enterprise Voice à PSTN usando o tronco SIP. O tronco SIP permite os seguintes cenários:

  - Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.

  - Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.

O uso dessa solução de implantação requer um provedor de serviços de tronco SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Gateways PSTN

Os gateways PSTN são dispositivos de terceiros que convertem a sinalização e a mídia entre a infraestrutura do Enterprise Voice e uma PSTN ou um PBX. Os gateways PSTN funcionam com o Servidor de Mediação para apresentar uma chamada PSTN ou PBX para um cliente do Enterprise Voice. O Servidor de Mediação também apresenta as chamadas dos clientes do Enterprise Voice ao gateway PSTN para roteamento para a PSTN ou o PBX. Para obter uma lista de parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionam com o Lync Server, consulte o site do Microsoft [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)Unified Communications Partners em.

</div>

<div>

## <a name="private-branch-exchanges"></a>Centrais privadas de comutação telefônica

Se você tiver uma infraestrutura de voz existente que usa um PBX (Private Branch Exchange), você pode usar seu PBX com o Lync Server Enterprise Voice.

Os cenários de integração de PBX com o Enterprise Voice aceitos são:

  - IP-PBX que oferece suporte ao desvio de mídia, com um Servidor de Mediação.

  - IP-PBX que requer um gateway PSTN autônomo.

  - Conexão PBX TDM, com um gateway PSTN autônomo.

<div>


> [!NOTE]  
> O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>unificativas – Lync Server em.



</div>

Para obter detalhes sobre parceiros que oferecem soluções do Enterprise Voice, consulte o site do Microsoft Unified Communications Partners em [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).

Para obter detalhes sobre parceiros que oferecem soluções de hardware do Enterprise Voice, incluindo gateways PSTN, consulte o site [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)de parceiros de comunicações unificadas da Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

