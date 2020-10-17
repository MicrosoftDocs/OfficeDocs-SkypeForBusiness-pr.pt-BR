---
title: Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware
description: Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware.
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
ms.openlocfilehash: b30dfcc3515420ffb34343e4653e9518b1b9c3ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563457"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Um pool de diretores em escala, onde há mais de um diretor implantado para lidar com capacidade adicional e para fornecer alta disponibilidade, requer o balanceamento de carga para distribuir a comunicação de cliente e servidor para todos os membros do pool. Um diretor hospeda serviços Web da mesma forma que um pool de front-ends. Para fornecer o balanceamento de carga, você pode usar o balanceamento de carga de hardware, ou balanceamento de carga do DNS (sistema de nomes de domínio) e balanceamento de carga de hardware. O balanceamento de carga de hardware é obrigatório para serviços web e o balanceamento de carga do DNS sozinho não fornece os recursos exigidos pelos serviços web.

Os tópicos a seguir descrevem as considerações de planejamento para a implantação de um pool de diretores usando o balanceamento de carga DNS em conjunto com o balanceamento de carga de hardware. Se você pretende usar o balanceamento de carga de hardware, mas não o balanceamento de carga DNS para o pool diretor, consulte o tópico [pool de diretores em escala-hardware Load Balancer no Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que descreve os requisitos de planejamento para essa topologia.

![Novo Pool de Diretor em Escala](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Novo Pool de Diretor em Escala")

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado-carga de DNS e HLB balanceada no Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumo de porta-carga de DNS e HLB balanceada no Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Resumo de DNS-cargas de DNS e de HLB balanceadas no Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

