---
title: 'Lync Server 2013: associar sub-redes a sites de rede para bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74f007accc53158a1f541dbe4ac6aa821cd8be4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Associar sub-redes a sites de rede para bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-12_

<div>


> [!NOTE]  
> Este tópico assume que você tenha definido as configurações globais de desvio de mídia, a região da rede e os locais de rede para desvio de mídia.



</div>

Cada sub-rede em sua rede deve ser associada a um site de rede específico. Isso ocorre porque as informações da sub-rede são usadas para determinar o site de rede no qual um ponto de extremidade está localizado. Quando os locais de ambas as partes em uma sessão são conhecidos, os desvio de mídia pode determinar para onde a mídia é enviada para processamento.

O desvio de mídia não tem requisitos especiais para associar sub-redes a sites de rede. Para criar uma associação entre as sub-redes e os sites de rede em sua topologia, siga os procedimentos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Próximas etapas: criar perfis de políticas de largura de banda

Depois de associar sub-redes a sites da rede para o desvio de mídia, você deverá criar um ou mais perfis de política de largura de banda que dividirão as sub-redes entre aquelas com boa conectividade e aquelas sem, para fins de desvio de mídia. Todas as sub-redes em uma região com sites de rede que não têm restrições de largura de banda possuem boa conectividade e, portanto, essas sub-redes podem usar o desvio de mídia.

Para obter os procedimentos para configurar perfis de política de largura de banda, consulte [Create Bandwidth Policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

