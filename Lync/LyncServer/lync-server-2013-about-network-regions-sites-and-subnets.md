---
title: 'Lync Server 2013: sobre regiões de rede, sites e sub-redes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fe7b93f00ce7af6354fa8a1bc94c104f3af14f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523208"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Sobre regiões de rede, sites e sub-redes no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

Os recursos avançados do Enterprise Voice descritos nesta seção compartilham determinados requisitos de configuração para regiões de rede, sites de rede e sub-redes. Por exemplo, todos os três recursos avançados exigem que cada sub-rede em sua topologia seja associada a um *site de rede*específico e cada local de rede deve estar associado a uma *região de rede*.

<div>


> [!IMPORTANT]  
> Antes de iniciar a configuração de rede para controle de admissão de chamada, E9-1-1 ou desvio de mídia, verifique se você analisou informações adicionais sobre as configurações de rede nas configurações de rede do tópico <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">recursos avançados do Enterprise Voice no Lync Server 2013</A> na documentação de planejamento. Para obter detalhes sobre a configuração de rede primariamente sobre o controle de admissão de chamadas, confira a <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definição de seus requisitos para controle de admissão de chamadas no Lync Server 2013</A> na documentação de planejamento.



</div>

O controle de admissão de chamada e o E9-1-1 têm requisitos adicionais de configuração para sites de rede:

  - O controle de admissão de chamadas exige que um *perfil de política de largura de banda* seja especificado para cada site restrito por limitações de largura de banda de WAN. Se você planeja implantar o controle de admissão de chamadas, você deve [criar perfis de política de largura de banda no Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) antes de configurar seus sites de rede.

  - E9-1-1 requer que uma *política de local* seja especificada para cada site. Se você planeja implantar o E9-1-1, você deve [criar políticas de local no Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar seus sites de rede.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Criar ou modificar regiões de rede, sites de rede e sub-redes

Os tópicos a seguir fornecem etapas para criar ou modificar regiões de rede e sites de rede e para associar sub-redes a sites de rede. Esses tópicos não são específicos de qualquer recurso avançado do Enterprise Voice específico.

  - [Criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Criar ou modificar um site de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

