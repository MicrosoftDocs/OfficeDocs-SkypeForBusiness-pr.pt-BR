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
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Associar sub-redes a sites de rede para ignorar mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

<div>


> [!NOTE]  
> Este tópico pressupõe que você configurou as configurações globais de bypass de mídia e que configurou a região de rede e os sites de rede para bypass de mídia.



</div>

Todas as sub-redes na rede devem estar associadas a um site de rede específico. Isso ocorre porque as informações de sub-rede são usadas para determinar o site de rede no qual se encontra um ponto de extremidade. Quando os locais de ambas as partes de uma sessão são conhecidos, o bypass de mídia pode determinar para onde enviar mídia para processamento.

O bypass de mídia não tem nenhum requisito especial para associar sub-redes a sites de rede. Para criar uma associação entre as sub-redes e os sites de rede em sua topologia, siga os procedimentos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Próximas etapas: criar perfis de política de largura de banda

Depois de associar sub-redes a sites de rede para bypass de mídia, você deve criar um ou mais perfis de política de largura de banda que particionem sub-redes em uma boa conectividade e aquelas sem, para fins de bypass de mídia. Todas as sub-redes dentro de uma região de rede com sites de rede que não têm restrições de largura de banda têm boa conectividade e, portanto, essas sub-redes podem usar o bypass de mídia.

Para obter os procedimentos para configurar perfis de política de largura de banda, consulte [criar perfis de política de largura de banda no Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

