---
title: 'Lync Server 2013: Configurando troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c2fd4a79937477edbe01f5550a81e92a663d3d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517338"
---
# <a name="configuring-trunks-in-lync-server-2013"></a>Configurando troncos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes pontos para fornecer conectividade de rede telefônica pública comutada (PSTN) para clientes e dispositivos Enterprise Voice em sua organização:

  - Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)

  - Gateway PSTN

  - Central privada de comutação telefônica (PBX)

Para obter detalhes, consulte [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) na documentação de planejamento.

<div>


> [!IMPORTANT]  
> Antes de começar a configuração de tronco, verifique se a topologia foi criada e se o servidor de mediação e seu par foram configurados e associados uns aos outros. Para obter detalhes, consulte <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir um gateway no construtor de topologias no Lync Server 2013</A> na documentação de implantação.



</div>

<div>


> [!NOTE]  
> Como parte da configuração de tronco, você pode habilitar o recurso de bypass de mídia do Lync Server 2013, que permite que a mídia ignore o servidor de mediação. Os troncos podem ser configurados com ou sem o desvio de mídia habilitado, mas recomendamos fortemente que você o habilite. Para obter detalhes, consulte <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media bypass in Lync Server 2013</A> na documentação de planejamento.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Suporte a vários troncos no Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Roteamento entre troncos no Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Exibir informações de configuração de tronco no Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Criar um novo conjunto de definições de configuração de tronco no Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Excluir um conjunto existente de definições de configuração do tronco SIP no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modificar as definições de configuração do tronco SIP no Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Testar as definições de configuração do tronco SIP no Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Exibir informações sobre troncos SIP individuais no Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Definir um gateway no construtor de topologia no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Planejamento da conectividade PSTN no Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

