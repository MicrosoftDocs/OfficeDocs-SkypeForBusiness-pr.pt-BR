---
title: Pool de diretores em escala - balanceamento de carga de DNS e balanceador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16203f7e291b7957793e71872483c93f2d1d04d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Pool de diretores em escala - balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Um pool de directors em escala, onde há mais de um director implantado para lidar com capacidade adicional e para fornecer alta disponibilidade, requer balanceamento de carga para distribuir a comunicação do cliente e do servidor para todos os membros do pool. Um diretor hospeda serviços Web muito como um pool de front-end. Para fornecer o balanceamento de carga, você pode usar o balanceamento de carga de hardware ou o balanceamento de carga do sistema de nome de domínio (DNS) e o balanceamento de carga de hardware. O balanceamento de carga de hardware é necessário para os serviços Web, e o balanceamento de carga de DNS sozinha não fornece as funcionalidades necessárias para os serviços Web.

Os tópicos a seguir descrevem as considerações de planejamento para a implantação de um pool de directors usando o balanceamento de carga de DNS em conjunto com o balanceamento de carga de hardware. Se você pretende usar o balanceamento de carga de hardware, mas não o balanceamento de carga de DNS para o pool de diretor, consulte o tópico [pool de diretor de dimensionamento-balanceamento de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que descreve os requisitos de planejamento para essa topologia.

![Pool de directors dimensionados](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool de directors dimensionados")

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado - Cargas de DNS e de HLB balanceadas no Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumo de porta - cargas de DNS e de HLB balanceadas no Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Resumo de DNS - Cargas de DNS e de HLB balanceadas no Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

