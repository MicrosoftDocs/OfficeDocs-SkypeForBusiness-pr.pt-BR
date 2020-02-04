---
title: 'Lync Server 2013: Considerações de migração e de coexistência para IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Considerações de migração e de coexistência para IPv6 no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-14_

Não há suporte para IP versão 6 (IPv6) no Lync Server 2010 ou no Office Communications Server. Para fins de piloto, você pode testar o Lync Server 2010 e o Lync Server 2013 dual-stack de coexistência. Recomendamos que todos os pools de um determinado site central sejam atualizados para o Lync Server 2013 antes de habilitar o IPv6 (rede de pilha dupla) para qualquer um dos pools. Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.

Os cenários a seguir são suportados durante a migração e coexistência:

  - Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 pools R2 no modo IPv4, coexistente com o Lync Server 2013 em modo de pilha dupla.

  - Pool do Lync Server 2013 no modo somente IPv6, se o pool somente IPv6 estiver em silo.

</div>

<span> </span>

</div>

</div>

</div>

