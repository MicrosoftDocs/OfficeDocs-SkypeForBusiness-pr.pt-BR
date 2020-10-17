---
title: 'Lync Server 2013: verificar regras de normalização para estacionamento de chamada'
description: 'Lync Server 2013: Verifique as regras de normalização para estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ac4c15091141e3069e7b77533d0e4148459f570
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547057"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Verificar regras de normalização para estacionamento de chamada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-11_

As órbitas do estacionamento de chamadas não devem ser normalizadas. Verifique seus planos de discagem para ter certeza de que seus números de órbita não estão normalizados. Se você precisar criar uma regra de normalização adicional para impedir que as órbitas sejam normalizadas, siga o procedimento em [Create a dial Plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir uma nova regra de normalização, para que o **padrão correspondente** identifique o intervalo de órbitas e o **padrão de conversão** seja **$1**. Por exemplo, se o intervalo de órbita de estacionamento de chamadas for 7000 – 7999, o **padrão a ser correspondido** será **^ (7 \\ d {3} ) $** e o **padrão de conversão** será **$1**.

<div>


> [!IMPORTANT]  
> Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha <STRONG>^ (\d *)</STRONG>. Caso contrário, sua regra de normalização de estacionamento de chamada nunca será executada.



</div>

<div>

## <a name="see-also"></a>Confira também


[Criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

