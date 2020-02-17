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
ms.openlocfilehash: 6d69a77e1277b843ed1df13a130e67a9ee081d98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="2ba82-102">Novos recursos de recuperação de desastre e alta disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ba82-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba82-103">_**Última modificação do tópico:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="2ba82-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="2ba82-104">Como no Lync Server 2010, o principal esquema de alta disponibilidade (HA) do Lync Server 2013 é baseado em redundância de servidor por meio de Pooling.</span><span class="sxs-lookup"><span data-stu-id="2ba82-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="2ba82-105">Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.</span><span class="sxs-lookup"><span data-stu-id="2ba82-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="2ba82-106">Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="2ba82-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="2ba82-107">O Lync Server 2013 adiciona novas medidas de recuperação de desastres, permitindo que você emparelhe pools de front-ends localizados em dois data centers.</span><span class="sxs-lookup"><span data-stu-id="2ba82-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="2ba82-108">Se um dos pools emparelhados parar de funcionar, um administrador pode transferir os usuários do pool para outro pool no emparelhamento, para fornecer a continuação do serviço.</span><span class="sxs-lookup"><span data-stu-id="2ba82-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="2ba82-109">Essa função não requer soluções de rede ou de hardware dispendiosas, como redes de armazenamentos ou discos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="2ba82-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="2ba82-110">O Lync Server 2013 também adiciona alta disponibilidade do servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="2ba82-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="2ba82-111">Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-ends e configura o espelhamento do SQL síncrono para todos os bancos de dados do Lync executados nos servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="2ba82-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="2ba82-112">Você também pode escolher implantar uma testemunha para o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="2ba82-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2ba82-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ba82-113">See Also</span></span>


[<span data-ttu-id="2ba82-114">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ba82-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

