---
title: 'Lync Server 2013: Definindo seus requisitos para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definindo seus requisitos para Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-07_

Este tópico fornece uma visão geral das considerações que você precisa fazer sobre as regiões, sites e os links entre sites na sua topologia e como eles são importantes ao implantar o Enterprise Voice. Para obter detalhes sobre como fazer essas decisões, consulte [configurações de rede para os recursos avançados de voz empresarial no Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) na documentação de planejamento.

<div>

## <a name="sites-and-regions"></a>Sites e regiões

Em primeiro lugar, identifique os sites na sua topologia em que você vai implantar o Enterprise Voice e as regiões de rede às quais esses sites pertencem. Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site. Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo. Decida onde os gateways serão implantados localmente, onde utensílios de ramificação sobreviventes (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia pela Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Links de rede entre sites

Você também precisa considerar o uso de largura de banda esperado nos links de rede entre o seu site central e seus sites de filiais. Se você tem, ou planeja implantar, links de WAN resistentes entre sites, recomendamos que implante um gateway em cada site de filial para fornecer cancelamento local direto do Direct Inward (DID) para usuários naqueles sites. Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link. Se você não tiver links de WAN resilientes, hospede menos de 1000 usuários no seu site da sua filial e não tiver administradores do Lync Server treinados disponíveis, recomendamos que você implante um aparelho de ramificação sobreviventes no site da filial. Se você estiver hospedando entre os usuários do 1000 e do 5000 no seu site da sua filial, sem conexão de WAN resistente e os administradores do Lync Server treinados estiverem disponíveis, recomendamos que você implante um servidor de ramificação sobreviventes com um pequeno gateway no site da filial. Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.

</div>

<div>

## <a name="see-also"></a>Confira também


[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

