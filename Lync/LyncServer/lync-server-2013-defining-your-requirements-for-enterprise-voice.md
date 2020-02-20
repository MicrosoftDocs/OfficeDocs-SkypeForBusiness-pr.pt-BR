---
title: 'Lync Server 2013: definindo seus requisitos para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0406286f4f9d8251743fe6ff3a4807dff277fe92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definindo seus requisitos para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-07_

Este tópico fornece uma visão geral das considerações que você precisa tomar sobre as regiões, sites e os links entre sites em sua topologia e como eles são importantes ao implantar o Enterprise Voice. Para obter detalhes para ajudá-lo a tomar essas decisões, consulte [Network Settings for the Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) na documentação de planejamento.

<div>

## <a name="sites-and-regions"></a>Sites e regiões

Primeiro, identifique os sites em sua topologia onde você implantará o Enterprise Voice e as regiões de rede às quais esses sites pertencem. Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site. Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo. Decida onde os gateways serão implantados localmente, onde os aparelhos de filial persistentes (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia da Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Links de rede entre sites

Você também precisa considerar o uso da largura de banda que você espera nos links de rede entre seu site central e seus sites de filial. Se você tem ou planeja implantar links de WAN resilientes entre sites, recomendamos que você implante um gateway em cada site de filial para fornecer finalidades de discagem direta local (DID) para usuários nesses sites. Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link. Se você não tiver links de WAN resistentes, hospede menos de 1000 usuários no seu site de filial e não tiver administradores do Lync Server treinados e locais disponíveis, recomendamos que você implante um aparelho de filial persistente no site de filial. Se você hospedar entre 1000 e 5000 usuários no seu site de filial, sem uma conexão WAN resiliente e tiver administradores treinados do Lync Server disponíveis, recomendamos implantar um servidor de filial persistente com um pequeno gateway no site de filial. Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurações de rede para os recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

