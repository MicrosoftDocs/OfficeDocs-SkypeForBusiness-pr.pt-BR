---
title: 'Lync Server 2013: planejamento para alta disponibilidade e recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ba7e58f29bb4e54972804fbe338c2e1345e91e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="6ad89-102">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ad89-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ad89-103">_**Última modificação do tópico:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="6ad89-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="6ad89-104">Como no Lync Server 2010, o principal esquema de alta disponibilidade para a maioria das funções de servidor no Lync Server 2013 é baseado em redundância de servidor por meio de Pooling.</span><span class="sxs-lookup"><span data-stu-id="6ad89-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="6ad89-105">Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.</span><span class="sxs-lookup"><span data-stu-id="6ad89-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="6ad89-106">Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="6ad89-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="6ad89-107">O Lync Server 2013 adiciona novas medidas de recuperação de desastres para pools de front-ends, introduzindo dispersão geográficos de seus servidores em dois data centers para fornecer a continuação do serviço, caso um pool ou site inteiro fique inativo.</span><span class="sxs-lookup"><span data-stu-id="6ad89-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="6ad89-108">O Lync Server 2013 também aprimora a alta disponibilidade do servidor back-end, oferecendo suporte ao espelhamento síncrono do SQL para seus bancos de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="6ad89-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="6ad89-109">Essa seção explica como estes principais recursos de alta disponibilidade e de recuperação de disastres, e também cobre quais passos você pode tomar para ter alta disponibilidade e recuperação de disastres também para suas outras funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="6ad89-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6ad89-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6ad89-110">In This Section</span></span>

  - [<span data-ttu-id="6ad89-111">Recuperação de desastre do pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ad89-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="6ad89-112">Recuperação de desastre do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ad89-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="6ad89-113">Planejamento para resiliência do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ad89-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="6ad89-114">Recursos de gerenciamento de chamada para recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ad89-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="6ad89-115">Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ad89-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="6ad89-116">Lync Server 2010 Metropolitan de resiliência de site</span><span class="sxs-lookup"><span data-stu-id="6ad89-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

