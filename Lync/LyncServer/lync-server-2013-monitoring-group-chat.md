---
title: 'Lync Server 2013: Monitoring Group Chat'
description: 'Lync Server 2013: Monitoring Group Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562027"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="bc5bd-103">Monitorando o chat do grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5bd-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc5bd-104">_**Última modificação do tópico:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="bc5bd-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="bc5bd-105">É altamente recomendável executar o [instalador de atualização cumulativa](https://support.microsoft.com/kb/968802) mais recente do servidor disponível no centro de download da Microsoft para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="bc5bd-106">Supondo que você esteja executando a atualização cumulativa mais recente, use a seguinte tabela de teste de estresse para métricas para entender se seus servidores de chat de grupo estão sendo executados na integridade ideal.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="bc5bd-107">Ambiente de teste e modelo de usuário</span><span class="sxs-lookup"><span data-stu-id="bc5bd-107">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-108">Três servidores de chat de grupo em um pool de chat de grupo, cada um com 8 GB de memória e 8 processadores.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5bd-109">Dois front-ends do Lync Server 2013 na Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-110">60.000 usuários simultâneos em três servidores de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5bd-111">25.000 canais hospedados pelo pool de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-112">Tamanho do canal:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-113">Tamanho do canal pequeno: 30</span><span class="sxs-lookup"><span data-stu-id="bc5bd-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-114">Tamanho médio do canal: 150</span><span class="sxs-lookup"><span data-stu-id="bc5bd-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-115">Tamanho de canal grande: 2500</span><span class="sxs-lookup"><span data-stu-id="bc5bd-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5bd-116">Contagem de canal:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-117">Números pequenos de canais: 24.000</span><span class="sxs-lookup"><span data-stu-id="bc5bd-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-118">Número de canais médios de 800</span><span class="sxs-lookup"><span data-stu-id="bc5bd-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-119">Número grande de canais 24</span><span class="sxs-lookup"><span data-stu-id="bc5bd-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-120">Total de canais 24.824</span><span class="sxs-lookup"><span data-stu-id="bc5bd-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-121">Canais de convite:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-122">Metade dos canais eram convidados canais</span><span class="sxs-lookup"><span data-stu-id="bc5bd-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5bd-123">Número de canais que um usuário ingressa:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-124">Pequeno: 12</span><span class="sxs-lookup"><span data-stu-id="bc5bd-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-125">Médio: 2</span><span class="sxs-lookup"><span data-stu-id="bc5bd-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="bc5bd-126">Grande: 1</span><span class="sxs-lookup"><span data-stu-id="bc5bd-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-127">Taxa de junção:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-128">10 no total/segundo, 3,33/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="bc5bd-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5bd-129">Taxa de logout:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-130">10 no total/segundo, 3,33/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="bc5bd-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-131">Taxa de chat:</span><span class="sxs-lookup"><span data-stu-id="bc5bd-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc5bd-132">20 no total/segundo, 6.66/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="bc5bd-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc5bd-133">Os seguintes números de contadores de desempenho provavelmente variam quando especificações de hardware ou perfis de usuário diferentes são usados.</span><span class="sxs-lookup"><span data-stu-id="bc5bd-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="bc5bd-134">Contador de desempenho a ser monitorado</span><span class="sxs-lookup"><span data-stu-id="bc5bd-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc5bd-135">Contador de Desempenho</span><span class="sxs-lookup"><span data-stu-id="bc5bd-135">Performance Counter</span></span></th>
<th><span data-ttu-id="bc5bd-136">Limites</span><span class="sxs-lookup"><span data-stu-id="bc5bd-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc5bd-137">Processo (ChannelService)- &gt; % tempo do processador</span><span class="sxs-lookup"><span data-stu-id="bc5bd-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="bc5bd-138">Mín: 0</span><span class="sxs-lookup"><span data-stu-id="bc5bd-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

