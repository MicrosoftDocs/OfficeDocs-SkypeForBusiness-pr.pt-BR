---
title: 'Lync Server 2013: planejamento para acesso de usuário externo'
description: 'Lync Server 2013: planejamento para acesso de usuário externo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562777"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="591f8-103">Planejamento para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-103">Planning for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="591f8-104">_**Última modificação do tópico:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="591f8-104">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="591f8-p101">Muitas das comunicações na sua organização provavelmente envolvem pessoas fora do firewall: funcionários que estão temporariamente ou permanentemente fora do escritório, funcionários de clientes ou de organizações parceiras, pessoas que usam IMs (serviços de mensagens instantâneas) e clientes em potencial que você convida para reuniões e apresentações. Nesta documentação, essas pessoas são coletivamente chamadas de *usuários externos*.</span><span class="sxs-lookup"><span data-stu-id="591f8-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="591f8-108">Com o Microsoft Lync Server 2013, os usuários da sua organização podem usar IM e presença para se comunicar com usuários externos e podem participar de conferência de áudio/vídeo (A/V) e conferência via Web com seus funcionários externos e outros tipos de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="591f8-108">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="591f8-109">Também é possível suportar acesso externo de dispositivos móveis e sobre o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="591f8-109">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="591f8-110">Usuários externos que não são membros de sua organização podem participar de reuniões do Lync Server 2013, permitindo participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="591f8-110">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="591f8-111">Para dar suporte à comunicação no firewall da sua organização, implante o servidor de borda do Lync Server 2013 em sua rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada).</span><span class="sxs-lookup"><span data-stu-id="591f8-111">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="591f8-112">O servidor de borda controla como os usuários fora do firewall podem se conectar à sua implantação interna do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="591f8-112">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="591f8-113">Também controla as comunicações com os usuários externos originários dentro do firewall.</span><span class="sxs-lookup"><span data-stu-id="591f8-113">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="591f8-114">Dependendo de seus requisitos, é possível implantar um ou mais Servidores de Borda em um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="591f8-114">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="591f8-115">Esta seção descreve cenários para acesso de usuário externo no Lync Server 2013 e explica como planejar a topologia de borda e de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="591f8-115">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="591f8-116">Embora você precise de um servidor de borda para dar suporte ao acesso de usuário externo e do Enterprise Voice, esta seção se concentra em suporte para IM, presença, conferência A/V, Federação, Webconferência e Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="591f8-116">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="591f8-117">Para obter detalhes sobre o suporte para o Enterprise Voice, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="591f8-117">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="591f8-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="591f8-118">In This Section</span></span>

  - [<span data-ttu-id="591f8-119">Alterações no Lync Server 2013 que afetam o planejamento do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="591f8-119">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="591f8-120">Requisitos do sistema para componentes de acesso de usuário externo para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-120">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="591f8-121">Visão geral do acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-121">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="591f8-122">Compreendendo a descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-122">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="591f8-123">Escolhendo uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-123">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="591f8-124">Coleta de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-124">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="591f8-125">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="591f8-126">Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-126">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="591f8-127">Planejar certificados de servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-127">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="591f8-128">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="591f8-128">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

