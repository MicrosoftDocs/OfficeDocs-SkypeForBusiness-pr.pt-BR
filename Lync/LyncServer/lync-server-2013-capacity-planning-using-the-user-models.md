---
title: Lync Server 2013 planejamento de capacidade usando os modelos de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664091baee67d0ddf953d8a114370fdb875eef29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="6bde8-102">Planejamento de capacidade para Lync Server 2013 usando modelos de usuário</span><span class="sxs-lookup"><span data-stu-id="6bde8-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bde8-103">_**Última modificação do tópico:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="6bde8-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="6bde8-104">Esta seção oferece orientação sobre quantos servidores são necessários em um site para o número de usuários desse site, de acordo com o uso descrito em [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="6bde8-105">Plataforma de hardware testada</span><span class="sxs-lookup"><span data-stu-id="6bde8-105">Tested Hardware Platform</span></span>

<span data-ttu-id="6bde8-106">Todos os resultados de desempenho e recomendações de implantação nesta seção são baseados nos testes de desempenho em servidores que executam o hardware descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6bde8-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="6bde8-107">Recomendamos que você use hardware semelhante.</span><span class="sxs-lookup"><span data-stu-id="6bde8-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="6bde8-108">Se você usar hardware menos poderoso, você pode enfrentar problemas de funcionalidade ou mau desempenho.</span><span class="sxs-lookup"><span data-stu-id="6bde8-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="6bde8-109">Observe que essas recomendações de hardware são superiores às das versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bde8-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="6bde8-110">Hardware usado em testes de desempenho</span><span class="sxs-lookup"><span data-stu-id="6bde8-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bde8-111">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="6bde8-111">Hardware component</span></span></th>
<th><span data-ttu-id="6bde8-112">Recomendado</span><span class="sxs-lookup"><span data-stu-id="6bde8-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-113">CPU</span><span class="sxs-lookup"><span data-stu-id="6bde8-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="6bde8-114">Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior</span><span class="sxs-lookup"><span data-stu-id="6bde8-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="6bde8-115">Processadores Intel Itanium não são suportados para funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bde8-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-116">Memória</span><span class="sxs-lookup"><span data-stu-id="6bde8-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="6bde8-117">32 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="6bde8-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-118">Disco</span><span class="sxs-lookup"><span data-stu-id="6bde8-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6bde8-119">8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="6bde8-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="6bde8-120">Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="6bde8-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="6bde8-121">-Ou</span><span class="sxs-lookup"><span data-stu-id="6bde8-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="6bde8-122">Drivers de estado sólido (SSDs) que oferecem desempenho semelhante à 8 drivers de disco mecânico de 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="6bde8-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-123">Rede</span><span class="sxs-lookup"><span data-stu-id="6bde8-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6bde8-124">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que exige agrupamento com um único endereço MAC e um único endereço IP)</span><span class="sxs-lookup"><span data-stu-id="6bde8-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="6bde8-125">Resumo dos resultados</span><span class="sxs-lookup"><span data-stu-id="6bde8-125">Summary of Results</span></span>

<span data-ttu-id="6bde8-126">A tabela a seguir resume essas recomendações.</span><span class="sxs-lookup"><span data-stu-id="6bde8-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bde8-127">Função de servidor</span><span class="sxs-lookup"><span data-stu-id="6bde8-127">Server role</span></span></th>
<th><span data-ttu-id="6bde8-128">Número máximo de usuários suportados</span><span class="sxs-lookup"><span data-stu-id="6bde8-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-129">Pool de front-ends com doze servidores front-end e um servidor back-end ou um par espelhado de servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="6bde8-130">80.000 usuários exclusivos fizeram logon simultaneamente, mais 50% de pontos múltiplos de presença (MPOP) representando instâncias não móveis, mais 40% dos usuários habilitados para mobilidade para um total de 152.000 pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="6bde8-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-131">Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="6bde8-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="6bde8-132">O serviço de conferência A/V fornecido por um pool de front-ends oferece suporte às conferências do pool, supondo um tamanho máximo de conferência de 250 usuários e apenas uma conferência grande sendo executada de cada vez.</span><span class="sxs-lookup"><span data-stu-id="6bde8-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6bde8-133">Além disso, você pode dar suporte a conferências grandes de usuários de 250 e 1000 implantando um pool de front-ends separado com dois servidores front-end para hospedar as grandes conferências.</span><span class="sxs-lookup"><span data-stu-id="6bde8-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="6bde8-134">Para obter detalhes, consulte <A href="lync-server-2013-supporting-large-meetings.md">Supporting Large encontros using Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6bde8-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-135">Um Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="6bde8-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="6bde8-136">12.000 usuários remotos simultâneos</span><span class="sxs-lookup"><span data-stu-id="6bde8-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-137">Um Diretor</span><span class="sxs-lookup"><span data-stu-id="6bde8-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="6bde8-138">12.000 usuários remotos simultâneos</span><span class="sxs-lookup"><span data-stu-id="6bde8-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-139">Monitoramento e arquivamento</span><span class="sxs-lookup"><span data-stu-id="6bde8-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="6bde8-140">No Lync Server 2013, os serviços de front-end de monitoramento e arquivamento agora são executados em cada servidor de front-end, em vez de em funções de servidor separadas.</span><span class="sxs-lookup"><span data-stu-id="6bde8-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="6bde8-141">O monitoramento e o arquivamento cada ainda exigem seus próprios repositórios de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="6bde8-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="6bde8-142">Se você também executar o Exchange 2013, poderá manter seus dados de arquivamento no Exchange, em vez de em um banco de dados SQL dedicado.</span><span class="sxs-lookup"><span data-stu-id="6bde8-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-143">Um Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6bde8-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="6bde8-144">O servidor de mediação colocado com o servidor front-end é executado em todos os servidores front-end em um pool e deve fornecer capacidade suficiente para os usuários no pool.</span><span class="sxs-lookup"><span data-stu-id="6bde8-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="6bde8-145">Para o servidor de mediação autônomo, consulte a seção "servidor de mediação" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6bde8-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-146">Um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6bde8-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="6bde8-147">É altamente recomendável que, se você usar servidores Standard Edition para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6bde8-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="6bde8-148">Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá suportar 5.000 usuários em um cenário de failover.</span><span class="sxs-lookup"><span data-stu-id="6bde8-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="6bde8-149">Se sua implantação inclui uma quantidade significativa de tráfego de áudio ou vídeo, o desempenho do servidor pode ser prejudicado com mais de 2.500 usuários por servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="6bde8-150">Nesse caso, você deve considerar a adição de servidores Standard Edition ou a migração para o Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6bde8-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="6bde8-151">Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="6bde8-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-152">Não há suporte para pools estendidos para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="6bde8-153">Em um pool de front-ends, você deve ter um servidor front-end para cada 6.660 usuários hospedados no pool, supondo que o Hyper-Threading esteja habilitado em todos os servidores do pool e que o hardware do servidor atenda às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="6bde8-154">O número máximo de usuários em um pool de front-ends é 80.000, supondo que o Hyper-Threading esteja habilitado em todos os servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="6bde8-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="6bde8-155">Se houver mais de 80.000 usuários em um site, é possível implantar mais de um pool de Front End.</span><span class="sxs-lookup"><span data-stu-id="6bde8-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="6bde8-156">Ao contar o número de usuários em um pool de Front End, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a este pool de Front End.</span><span class="sxs-lookup"><span data-stu-id="6bde8-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="6bde8-157">Quando um servidor ativo fica indisponível, suas conexões são transferidas automaticamente para os outros servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="6bde8-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="6bde8-158">Por exemplo, se você tiver 30.000 usuários e cinco servidores front-end, se um servidor não estiver disponível, as conexões de 6000 usuários precisam ser transferidas para os outros quatro servidores.</span><span class="sxs-lookup"><span data-stu-id="6bde8-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="6bde8-159">Os quatro servidores restantes terão 7500 usuários, o que é um número maior do que o recomendado.</span><span class="sxs-lookup"><span data-stu-id="6bde8-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="6bde8-160">Se, em vez disso, você começou com seis servidores front-end para os seus usuários 30.000 e, posteriormente, um se tornou indisponível, um total de 5000 usuários será movido para os cinco servidores restantes.</span><span class="sxs-lookup"><span data-stu-id="6bde8-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="6bde8-161">Esses cinco servidores serão cada host 6000 usuários, que está no intervalo recomendado.</span><span class="sxs-lookup"><span data-stu-id="6bde8-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="6bde8-162">O número máximo de usuários em um pool de Front End é 80.000.</span><span class="sxs-lookup"><span data-stu-id="6bde8-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="6bde8-163">O número máximo de servidores front-end em um pool é 12.</span><span class="sxs-lookup"><span data-stu-id="6bde8-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="6bde8-164">Para um pool de front-ends com 80.000 usuários, doze servidores front-end são suficientes para o desempenho, em implantações comuns que seguem os [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="6bde8-165">As implantações projetadas para dar suporte ao failover de recuperação de desastres presumem que um máximo de 40.000 usuários possam ser hospedados em cada um dos dois pools de front-ends emparelhados, em que cada pool tenha servidores de front end suficientes para acomodar os usuários em ambos os pools deve haver falha em um pool para o outro.</span><span class="sxs-lookup"><span data-stu-id="6bde8-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="6bde8-166">O número de usuários com suporte com bom desempenho por um pool de front-ends específico pode diferir desses números pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="6bde8-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="6bde8-167">O hardware para seus servidores front-end não atende às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="6bde8-168">A utilização da sua organização difere de forma significativa dos modelos de usuário, bem como possui um volume consideravelmente maior de tráfego de conferências.</span><span class="sxs-lookup"><span data-stu-id="6bde8-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6bde8-169">No Lync Server 2013, os bancos de dados de presença agora estão hospedados em servidores front-end, ao contrário do Lync Server 2010 onde estavam hospedados no servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="6bde8-170">Isso significa que o desempenho do disco e a capacidade de seus servidores front-end não devem ser comprometidos das recomendações listadas anteriormente nesta seção e nas <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor do Lync Server 2013</A>, independentemente do número de usuários hospedados por seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="6bde8-171">A tabela a seguir mostra a largura de banda média para IM e presença, dado o modelo de usuário, conforme definido nos [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bde8-172">Largura de banda média por usuário</span><span class="sxs-lookup"><span data-stu-id="6bde8-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="6bde8-173">Requisitos de largura de banda por servidor front-end com 6.660 usuários</span><span class="sxs-lookup"><span data-stu-id="6bde8-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="6bde8-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="6bde8-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="6bde8-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-176">Para melhorar o desempenho de mídia da funcionalidade do servidor de mediação e de conferência a/V alocada em seus servidores front-end, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="6bde8-177">O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="6bde8-178">Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>Windows Server 2008" em.</span><span class="sxs-lookup"><span data-stu-id="6bde8-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="6bde8-179">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="6bde8-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="6bde8-180">Máximos de Conferência</span><span class="sxs-lookup"><span data-stu-id="6bde8-180">Conferencing Maximums</span></span>

<span data-ttu-id="6bde8-181">Dado o modelo de usuário em que 5% dos usuários em um pool podem estar em uma conferência em qualquer momento, um pool de 80.000 usuários poderia ter cerca de 4.000 usuários em conferências de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="6bde8-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="6bde8-182">Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes.</span><span class="sxs-lookup"><span data-stu-id="6bde8-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="6bde8-183">Não existe um limite rígido para o número real de conferências permitidas e o uso real determina o desempenho real.</span><span class="sxs-lookup"><span data-stu-id="6bde8-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="6bde8-184">Por exemplo, se sua organização tem muito mais conferências de modo misto do que as supostas no modelo de usuário, pode ser necessário implantar mais Servidores Front End ou Servidores de Conferência A/V do que as recomendações neste documento.</span><span class="sxs-lookup"><span data-stu-id="6bde8-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="6bde8-185">Para obter detalhes sobre as suposições no modelo de usuário, consulte [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="6bde8-186">O tamanho máximo de conferência compatível hospedado por um pool de front-ends normal do Lync Server 2013 que também hospeda os usuários é de 250 participantes.</span><span class="sxs-lookup"><span data-stu-id="6bde8-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="6bde8-187">Enquanto uma conferência de um usuário 250 está acontecendo, o pool ainda oferece suporte a outras conferências, de forma que um total de 5% dos usuários do pool estejam em conferências simultâneas.</span><span class="sxs-lookup"><span data-stu-id="6bde8-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="6bde8-188">Por exemplo, em um pool de doze servidores front-end e 80.000 usuários, enquanto a conferência 250-User está acontecendo, o Lync Server oferece suporte a 3.750 outros usuários que participam de conferências menores.</span><span class="sxs-lookup"><span data-stu-id="6bde8-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="6bde8-189">Independentemente do número de usuários hospedados no pool de front-ends ou no servidor Standard Edition, o Lync Server oferece suporte a um mínimo de 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que está hospedando uma conferência de 250 usuários.</span><span class="sxs-lookup"><span data-stu-id="6bde8-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="6bde8-190">Para habilitar conferências entre 250 e 1000 usuários, você pode configurar um pool de front-ends separado apenas para hospedar essas conferências.</span><span class="sxs-lookup"><span data-stu-id="6bde8-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="6bde8-191">Este pool de front-ends não hospedará nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="6bde8-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="6bde8-192">Para obter detalhes, consulte [Supporting Large encontros using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="6bde8-193">Se sua organização tiver muito mais conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end do que as recomendações neste documento (até um limite de 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="6bde8-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="6bde8-194">Para obter detalhes sobre as suposições no modelo de usuário, consulte [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="6bde8-195">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="6bde8-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-196">Não há suporte para pools estendidos para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="6bde8-197">Você deve implantar um servidor de borda para cada 12.000 usuários remotos que acessarão um site simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="6bde8-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="6bde8-198">São recomendados no mínimo dois Servidores de Borda para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6bde8-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="6bde8-199">Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="6bde8-200">Ao contar o número de usuários para os Servidores de Borda, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.</span><span class="sxs-lookup"><span data-stu-id="6bde8-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-201">Para aprimorar o desempenho do serviço de Borda de Conferência A/V em seus Servidores de Borda, você deve habilitar o receive-side scaling (RSS) nos adaptadores de rede em seus Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="6bde8-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="6bde8-202">O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="6bde8-203">Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>Windows Server 2008" em.</span><span class="sxs-lookup"><span data-stu-id="6bde8-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="6bde8-204">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="6bde8-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="6bde8-205">Be</span><span class="sxs-lookup"><span data-stu-id="6bde8-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-206">Não há suporte para pools estendidos para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="6bde8-207">Se você implantar a função de servidor diretor, recomendamos implantar um diretor para cada 12.000 usuários remotos que acessarão um site simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="6bde8-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="6bde8-208">São recomendados no mínimo dois Diretores para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6bde8-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="6bde8-209">Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="6bde8-210">Ao contar o número de usuários para os Diretores, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.</span><span class="sxs-lookup"><span data-stu-id="6bde8-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="6bde8-211">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6bde8-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-212">Não há suporte para pools estendidos para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="6bde8-213">Se você colocar o servidor de mediação com o servidor front-end, o servidor de mediação será executado em todos os servidores front-end no pool e deve fornecer capacidade suficiente para os usuários no pool.</span><span class="sxs-lookup"><span data-stu-id="6bde8-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="6bde8-214">Se você implantar um pool de servidor de mediação autônomo, o número de servidores de mediação a serem implantados depende de vários fatores, incluindo o hardware usado para o servidor de mediação, o número de usuários de VoIP, o número de pares de gateway que cada pool de servidor de mediação controles, o tráfego de horas de ocupado por esses gateways e a porcentagem de chamadas com mídia que ignora o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="6bde8-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="6bde8-215">As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um servidor de mediação pode lidar, supondo que o hardware para os servidores de mediação atenda aos requisitos em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) e que o Hyper-Threading esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="6bde8-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="6bde8-216">Para obter detalhes sobre a escalabilidade do servidor de mediação, consulte [estimativa de uso de voz e tráfego para o Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="6bde8-217">Todas as tabelas a seguir consideram o uso resumido em [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="6bde8-218">Capacidade de servidor de mediação autônomo: 70% de usuários internos, 30% de usuários externos com capacidade de chamada não-bypass (transcodificação de mídia executada pelo servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="6bde8-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bde8-219">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="6bde8-219">Server hardware</span></span></th>
<th><span data-ttu-id="6bde8-220">Número máximo de chamadas</span><span class="sxs-lookup"><span data-stu-id="6bde8-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="6bde8-221">Número máximo de linhas T1</span><span class="sxs-lookup"><span data-stu-id="6bde8-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="6bde8-222">Número máximo de linhas E1</span><span class="sxs-lookup"><span data-stu-id="6bde8-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-223">Processador duplo, Hex Core, CPU de 2,26 GHz <strong>com Hyper-Threading desabilitado</strong>, com memória de 32 GB e uma placa de adaptador de rede de duas portas.</span><span class="sxs-lookup"><span data-stu-id="6bde8-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="6bde8-224">1100</span><span class="sxs-lookup"><span data-stu-id="6bde8-224">1100</span></span></p></td>
<td><p><span data-ttu-id="6bde8-225">46</span><span class="sxs-lookup"><span data-stu-id="6bde8-225">46</span></span></p></td>
<td><p><span data-ttu-id="6bde8-226">35</span><span class="sxs-lookup"><span data-stu-id="6bde8-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-227">Processador dual, Hex Core, 2,26 GHz com hyper-threaded CPU, com memória de 32 GB e uma placa de adaptador de rede de duas portas.</span><span class="sxs-lookup"><span data-stu-id="6bde8-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="6bde8-228">1500</span><span class="sxs-lookup"><span data-stu-id="6bde8-228">1500</span></span></p></td>
<td><p><span data-ttu-id="6bde8-229">63</span><span class="sxs-lookup"><span data-stu-id="6bde8-229">63</span></span></p></td>
<td><p><span data-ttu-id="6bde8-230">47</span><span class="sxs-lookup"><span data-stu-id="6bde8-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-231">Embora servidores com 32 GB de memória tenham sido usados para testes de desempenho, servidores com 16 GB de memória são suportados para um Servidor de Mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="6bde8-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="6bde8-232">Capacidade do servidor de mediação (servidor de mediação colocado com o servidor front-end) 70% de usuários internos, 30% de usuários externos, capacidade de chamadas sem desvio (processamento de mídia executado pelo servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="6bde8-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bde8-233">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="6bde8-233">Server hardware</span></span></th>
<th><span data-ttu-id="6bde8-234">Número máximo de chamadas</span><span class="sxs-lookup"><span data-stu-id="6bde8-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-235">Processador dual, Hex Core, 2,26 GHz com hyper-threaded CPU, com memória de 32 GB e 2 placas de adaptador de rede de 1 GB.</span><span class="sxs-lookup"><span data-stu-id="6bde8-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="6bde8-236">150</span><span class="sxs-lookup"><span data-stu-id="6bde8-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-237">Esse número é muito menor do que os números para o servidor de mediação autônomo porque o servidor front-end tem que lidar com outros recursos e funções para os usuários do 6600 hospedados nele, além da transcodificação necessária para chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="6bde8-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6bde8-238">Para melhorar o desempenho do servidor de mediação, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="6bde8-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="6bde8-239">O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="6bde8-240">Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>Windows Server 2008" em.</span><span class="sxs-lookup"><span data-stu-id="6bde8-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="6bde8-241">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="6bde8-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="6bde8-242">Servidor de Back-End</span><span class="sxs-lookup"><span data-stu-id="6bde8-242">Back End Server</span></span>

<span data-ttu-id="6bde8-243">No Lync Server 2013, os bancos de dados de presença estão localizados nos servidores front-end, e não no servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="6bde8-244">Isso resultou em um requisito muito mais simples para cada servidor back-end no Lync Server 2013, equivalente ao requisito de hardware para o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="6bde8-245">Compare com isso com o Lync Server 2010, onde o servidor back-end era necessário para ser um servidor muito mais elevado com 25 discos.</span><span class="sxs-lookup"><span data-stu-id="6bde8-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="6bde8-246">No entanto, a carga de trabalho dos servidores de back-end ainda não deve atender às recomendações de hardware listadas anteriormente nesta seção e em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="6bde8-247">Para fornecer alta disponibilidade do servidor back-end, recomendamos implantar o espelhamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="6bde8-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="6bde8-248">Para obter mais informações, consulte [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="6bde8-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="6bde8-249">Monitoramento e arquivamento</span><span class="sxs-lookup"><span data-stu-id="6bde8-249">Monitoring and Archiving</span></span>

<span data-ttu-id="6bde8-250">No Lync Server 2013, se você implantar o monitoramento ou arquivamento, a funcionalidade de front end desses serviços é executada nos servidores front-end, em vez de em funções de servidor separadas.</span><span class="sxs-lookup"><span data-stu-id="6bde8-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="6bde8-251">O monitoramento e o arquivamento cada ainda usam seu próprio repositório de banco de dados, separado do repositório de back-end.</span><span class="sxs-lookup"><span data-stu-id="6bde8-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="6bde8-252">Como alternativa, se você tiver o Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange, em vez de em um repositório SQL dedicado.</span><span class="sxs-lookup"><span data-stu-id="6bde8-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="6bde8-253">A tabela a seguir indica a quantidade de armazenamento de banco de dados necessária por usuário por dia para monitoramento e arquivamento de dados.</span><span class="sxs-lookup"><span data-stu-id="6bde8-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="6bde8-254"><strong>CDR (monitoramento)</strong></span><span class="sxs-lookup"><span data-stu-id="6bde8-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="6bde8-255"><strong>QoE (monitoramento)</strong></span><span class="sxs-lookup"><span data-stu-id="6bde8-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="6bde8-256"><strong>Arquivamento</strong></span><span class="sxs-lookup"><span data-stu-id="6bde8-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-257">Espaço em disco exigido por usuário por dia</span><span class="sxs-lookup"><span data-stu-id="6bde8-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="6bde8-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="6bde8-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="6bde8-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="6bde8-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="6bde8-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="6bde8-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6bde8-261">A Microsoft utilizou o hardware na tabela a seguir para o servidor de banco de dados para monitoramento e arquivamento durante o teste de desempenho.</span><span class="sxs-lookup"><span data-stu-id="6bde8-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="6bde8-262">O teste coletou os dados de dois pools de front-ends, cada um contendo 80.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="6bde8-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="6bde8-263">Hardware usado em testes de desempenho de monitoramento e arquivamento</span><span class="sxs-lookup"><span data-stu-id="6bde8-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bde8-264">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="6bde8-264">Hardware component</span></span></th>
<th><span data-ttu-id="6bde8-265">Recomendado</span><span class="sxs-lookup"><span data-stu-id="6bde8-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-266">CPU</span><span class="sxs-lookup"><span data-stu-id="6bde8-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="6bde8-267">Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior</span><span class="sxs-lookup"><span data-stu-id="6bde8-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-268">Memória</span><span class="sxs-lookup"><span data-stu-id="6bde8-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="6bde8-269">48 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="6bde8-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-270">Disco</span><span class="sxs-lookup"><span data-stu-id="6bde8-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="6bde8-271">unidades de disco rígido de 25 10.000 RPM com 300 GB em cada disco, com a seguinte configuração</span><span class="sxs-lookup"><span data-stu-id="6bde8-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="6bde8-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="6bde8-273"><strong>Configuração de RAID</strong></span><span class="sxs-lookup"><span data-stu-id="6bde8-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bde8-274"><strong>Número de discos</strong></span><span class="sxs-lookup"><span data-stu-id="6bde8-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-275">Arquivos de dados de banco de dados de CDR, QoE e arquivamento, em uma única unidade</span><span class="sxs-lookup"><span data-stu-id="6bde8-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="6bde8-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="6bde8-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="6bde8-277">16 </span><span class="sxs-lookup"><span data-stu-id="6bde8-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-278">Arquivo de log do banco de dados CDR</span><span class="sxs-lookup"><span data-stu-id="6bde8-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="6bde8-279">1</span><span class="sxs-lookup"><span data-stu-id="6bde8-279">1</span></span></p></td>
<td><p><span data-ttu-id="6bde8-280">duas</span><span class="sxs-lookup"><span data-stu-id="6bde8-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-281">Arquivo de log do banco de dados QoE</span><span class="sxs-lookup"><span data-stu-id="6bde8-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="6bde8-282">1</span><span class="sxs-lookup"><span data-stu-id="6bde8-282">1</span></span></p></td>
<td><p><span data-ttu-id="6bde8-283">duas</span><span class="sxs-lookup"><span data-stu-id="6bde8-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bde8-284">Arquivo de log do banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="6bde8-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="6bde8-285">1</span><span class="sxs-lookup"><span data-stu-id="6bde8-285">1</span></span></p></td>
<td><p><span data-ttu-id="6bde8-286">duas</span><span class="sxs-lookup"><span data-stu-id="6bde8-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bde8-287">Rede</span><span class="sxs-lookup"><span data-stu-id="6bde8-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6bde8-288">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que exige agrupamento com um único endereço MAC e um único endereço IP)</span><span class="sxs-lookup"><span data-stu-id="6bde8-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6bde8-289">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6bde8-289">In This Section</span></span>

  - [<span data-ttu-id="6bde8-290">Estimando o uso de voz e o tráfego do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bde8-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="6bde8-291">Diretrizes de implantação para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bde8-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

