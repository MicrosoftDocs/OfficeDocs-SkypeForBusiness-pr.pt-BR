---
title: 'Lync Server 2013: Planejamento para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a0eeb-102">Planejamento para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0eeb-103">_**Tópico da última modificação:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="a0eeb-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="a0eeb-104">As comunicações na maioria das organizações envolvem serviços e usuários que não estão dentro da sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="a0eeb-105">Esses serviços e usuários incluem funcionários que são temporários ou permanentemente externos, funcionários de organizações de clientes ou parceiros, pessoas que usam serviços de mensagens instantâneas (IM) públicas e clientes potenciais, parceiros e usuários anônimos convidados para reuniões e apresentações.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="a0eeb-106">Nesta documentação, essas pessoas são chamadas coletivamente como *usuários externos*.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="a0eeb-107">Com o Microsoft Lync Server 2013, os usuários em sua organização podem usar mensagens instantâneas e presença para se comunicar com usuários externos, e podem participar de conferências de áudio/vídeo (A/V) e conferência via Web com seus funcionários externos e outros tipos de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="a0eeb-108">Você também pode dar suporte ao acesso externo de dispositivos móveis e do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="a0eeb-109">Os usuários externos que não são membros da sua organização podem participar de reuniões do Lync Server 2013, permitindo participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="a0eeb-110">Para dar suporte à comunicação no firewall da sua organização, implante o servidor de borda do Lync Server 2013 na sua rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada).</span><span class="sxs-lookup"><span data-stu-id="a0eeb-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="a0eeb-111">O servidor de borda controla como os usuários de fora do firewall podem se conectar à sua implantação interna do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="a0eeb-112">Ele também controla comunicações com usuários externos que se originam dentro do firewall.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="a0eeb-113">Dependendo dos seus requisitos, você pode implantar um ou mais servidores de borda em um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="a0eeb-114">Esta seção descreve os cenários de acesso de usuários externos no Lync Server 2013, e explica como planejar a topologia de borda e de proxy inversa.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0eeb-115">Embora você precise de um servidor de borda para dar suporte a acesso de usuário externo e de voz, esta seção enfoca o suporte para mensagens instantâneas, presença, conferência A/V, Federação, conferência via Web e Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="a0eeb-116">Para obter detalhes sobre o suporte para Enterprise Voice, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">planejamento para Enterprise Voice no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a0eeb-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0eeb-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a0eeb-117">In This Section</span></span>

  - [<span data-ttu-id="a0eeb-118">Alterações no Lync Server 2013 que afetam o planejamento do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a0eeb-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="a0eeb-119">Requisitos do sistema para componentes de acesso de usuário externo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="a0eeb-120">Visão geral de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="a0eeb-121">Compreendendo a descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="a0eeb-122">Escolhendo uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="a0eeb-123">Coleta de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="a0eeb-124">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="a0eeb-125">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="a0eeb-126">Planejar certificados do Servidor de Borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="a0eeb-127">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0eeb-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

