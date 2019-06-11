---
title: 'Lync Server 2013: Sobre regiões de rede, sites e subredes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Sobre regiões de rede, sites e subredes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

Os recursos avançados de voz empresarial descritos nesta seção compartilham determinados requisitos de configuração para regiões de rede, sites de rede e sub-redes. Por exemplo, todos os três recursos avançados exigem que cada sub-rede na sua topologia seja associada a um *site de rede*específico, e cada site de rede deve estar associado a uma *região de rede*.

<div>


> [!IMPORTANT]  
> Antes de iniciar a configuração de rede para o controle de admissão de chamadas, E9-1-1 ou ignorar mídia, verifique se você analisou informações adicionais sobre as configurações de rede nas <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configurações de voz do Advanced Enterprise Voice no Lync Server 2013</A> tópico na documentação de planejamento. Para obter detalhes sobre a configuração de rede principalmente sobre o controle de admissão de chamadas, consulte <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definir seus requisitos de controle de admissão de chamadas no Lync Server 2013</A> na documentação de planejamento.



</div>

O controle de admissão de chamada e o E9-1-1 têm requisitos adicionais de configuração para os sites da rede:

  - O serviço de controle de admissão de chamadas requer que um *perfil de política de largura de banda* seja especificado para cada site restrito pelas limitações de largura de banda WAN. Se você planeja implantar o controle de admissão de chamadas, deverá [criar perfis de política de largura de banda no Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) antes de configurar seus sites de rede.

  - O E9-1-1 requer que uma *política local* seja especificada para cada site. Se você planeja implantar o E9-1-1, será necessário [criar políticas de localização no Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar seus sites de rede.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Criar ou modificar regiões de rede, sites de rede e sub-redes

Os tópicos a seguir fornecem etapas para criar ou modificar regiões de rede e sites de rede e para associar sub-redes a sites de rede. Esses tópicos não são específicos para qualquer recurso avançado de Enterprise Voice específico.

  - [Criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Criar ou modificar um site da rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Associar uma subrede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

