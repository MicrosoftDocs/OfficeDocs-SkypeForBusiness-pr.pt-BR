---
title: 'Lync Server 2013: executando um failover de pool de front-ends ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddda9d00ce7b6f22c6428dce7ef395b26ef8bfd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="842e7-102">Executando um failover de pool de front-ends ABC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="842e7-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="842e7-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="842e7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="842e7-104">Os dois tópicos desta seção descrevem o procedimento para executar um failover de pool ABC no Lync Server 2013, onde há pools de front-ends do Lync Server A e B e o pool A se torna irrecuperável.</span><span class="sxs-lookup"><span data-stu-id="842e7-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="842e7-105">Usando esse procedimento, você cria um novo pool de front-ends C com um novo FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="842e7-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="842e7-106">O pool C é construído a partir das informações do pool A que falhou. O procedimento também inclui emparelhamento de pools B e C.</span><span class="sxs-lookup"><span data-stu-id="842e7-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="842e7-107">Pré-requisitos de backup para failover de pool ABC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="842e7-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="842e7-108">Procedimento de failover ABC do pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="842e7-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

