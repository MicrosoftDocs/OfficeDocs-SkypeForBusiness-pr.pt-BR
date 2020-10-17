---
title: 'Lync Server 2013: novos recursos de recuperação de desastre e alta disponibilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33a9039c65d059042d9eb93c9d5437a00ebff266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512558"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Novos recursos de recuperação de desastre e alta disponibilidade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-20_

Como no Lync Server 2010, o principal esquema de alta disponibilidade (HA) do Lync Server 2013 é baseado em redundância de servidor por meio de Pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor. Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.

O Lync Server 2013 adiciona novas medidas de recuperação de desastres, permitindo que você emparelhe pools de front-ends localizados em dois data centers. Se um dos pools emparelhados parar de funcionar, um administrador pode transferir os usuários do pool para outro pool no emparelhamento, para fornecer a continuação do serviço. Essa função não requer soluções de rede ou de hardware dispendiosas, como redes de armazenamentos ou discos compartilhados.

O Lync Server 2013 também adiciona alta disponibilidade do servidor back-end. Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-ends e configura o espelhamento do SQL síncrono para todos os bancos de dados do Lync executados nos servidores back-end. Você também pode escolher implantar uma testemunha para o espelhamento.

<div>

## <a name="see-also"></a>Confira também


[Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

