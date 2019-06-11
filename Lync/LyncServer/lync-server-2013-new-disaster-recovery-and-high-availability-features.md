---
title: 'Lync Server 2013: Novos recursos de recuperação de desastre e alta disponibilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="a5b99-102">Novos recursos de recuperação de desastre e alta disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5b99-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b99-103">_**Tópico da última modificação:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="a5b99-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="a5b99-104">Como no Lync Server 2010, o principal esquema de alta disponibilidade (HA) do Lync Server 2013 é baseado na redundância do servidor via pool.</span><span class="sxs-lookup"><span data-stu-id="a5b99-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a5b99-105">Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor.</span><span class="sxs-lookup"><span data-stu-id="a5b99-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a5b99-106">Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="a5b99-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="a5b99-107">O Lync Server 2013 adiciona novas medidas de recuperação de desastres permitindo que você emparelhe pools de front-end localizados em dois datacenters.</span><span class="sxs-lookup"><span data-stu-id="a5b99-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="a5b99-108">Se um dos pools emparelhados ficar inativo, um administrador poderá fazer failover dos usuários desse pool para o outro pool do par, para dar continuidade ao serviço.</span><span class="sxs-lookup"><span data-stu-id="a5b99-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="a5b99-109">Essa funcionalidade não requer soluções caras de rede ou hardware, como redes de armazenamento ou discos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="a5b99-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="a5b99-110">O Lync Server 2013 também adiciona alta disponibilidade do servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="a5b99-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="a5b99-111">Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-end e configura o espelhamento do SQL síncrono para todos os bancos de dados do Lync em execução nos servidores de back-end.</span><span class="sxs-lookup"><span data-stu-id="a5b99-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="a5b99-112">Você pode escolher se deseja implantar uma testemunha para o espelho.</span><span class="sxs-lookup"><span data-stu-id="a5b99-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a5b99-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5b99-113">See Also</span></span>


[<span data-ttu-id="a5b99-114">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5b99-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

