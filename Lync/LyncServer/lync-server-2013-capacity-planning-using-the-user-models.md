---
title: Planejamento da capacidade do Lync Server 2013 usando os modelos de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="f897f-102">Planejamento de capacidade do Lync Server 2013 usando modelos de usuário</span><span class="sxs-lookup"><span data-stu-id="f897f-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f897f-103">_**Tópico da última modificação:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="f897f-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="f897f-104">Esta seção fornece orientação sobre quantos servidores você precisa em um site para o número de usuários nesse site, de acordo com o uso descrito em [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="f897f-105">Plataforma de hardware testada</span><span class="sxs-lookup"><span data-stu-id="f897f-105">Tested Hardware Platform</span></span>

<span data-ttu-id="f897f-106">Todos os resultados de desempenho e recomendações de implantação nesta seção são baseados em teste de desempenho em servidores que executam o hardware descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f897f-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="f897f-107">Recomendamos que você use hardware semelhante.</span><span class="sxs-lookup"><span data-stu-id="f897f-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="f897f-108">Se usar um hardware menos poderoso, você poderá enfrentar problemas de funcionalidade ou mau desempenho.</span><span class="sxs-lookup"><span data-stu-id="f897f-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="f897f-109">Observe que essas recomendações de hardware são superiores às versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f897f-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="f897f-110">Hardware usado em testes de desempenho</span><span class="sxs-lookup"><span data-stu-id="f897f-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f897f-111">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="f897f-111">Hardware component</span></span></th>
<th><span data-ttu-id="f897f-112">Recomendado</span><span class="sxs-lookup"><span data-stu-id="f897f-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f897f-113">CPU</span><span class="sxs-lookup"><span data-stu-id="f897f-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="f897f-114">Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior</span><span class="sxs-lookup"><span data-stu-id="f897f-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="f897f-115">Não há suporte para processadores Intel Itanium para funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f897f-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-116">Memória</span><span class="sxs-lookup"><span data-stu-id="f897f-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="f897f-117">32 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="f897f-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-118">Disco</span><span class="sxs-lookup"><span data-stu-id="f897f-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f897f-119">8 ou mais discos rígidos de 10.000-RPM com pelo menos 72 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="f897f-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="f897f-120">Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="f897f-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="f897f-121">-OR</span><span class="sxs-lookup"><span data-stu-id="f897f-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="f897f-122">Drivers de estado sólido (SSDs) que oferecem desempenho semelhante a 8 drivers de disco mecânico de 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="f897f-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-123">Rede</span><span class="sxs-lookup"><span data-stu-id="f897f-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f897f-124">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP)</span><span class="sxs-lookup"><span data-stu-id="f897f-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="f897f-125">Resumo de Resultados</span><span class="sxs-lookup"><span data-stu-id="f897f-125">Summary of Results</span></span>

<span data-ttu-id="f897f-126">A tabela a seguir resume essas recomendações.</span><span class="sxs-lookup"><span data-stu-id="f897f-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f897f-127">Função de servidor</span><span class="sxs-lookup"><span data-stu-id="f897f-127">Server role</span></span></th>
<th><span data-ttu-id="f897f-128">Número máximo de usuários suportados</span><span class="sxs-lookup"><span data-stu-id="f897f-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f897f-129">Pool de front-ends com doze servidores front-end e um servidor back-end ou um par espelhado de servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="f897f-130">80.000 usuários únicos, mais 50% de pontos múltiplos de presença (MPOP) representando instâncias não móveis, mais 40% de usuários ativados para mobilidade de um total de 152.000 pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f897f-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-131">Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="f897f-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="f897f-132">O serviço de conferência A/V fornecido por um pool de front-end oferece suporte a conferências do pool presumindo um tamanho máximo de conferência de usuários do 250, e apenas uma dessas grandes conferências sendo executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f897f-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f897f-133">Além disso, você pode dar suporte a conferências grandes de usuários do 250 e do 1000 implantando um pool de front-end separado com dois servidores front-end para hospedar as conferências grandes.</span><span class="sxs-lookup"><span data-stu-id="f897f-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="f897f-134">Para obter detalhes, consulte <A href="lync-server-2013-supporting-large-meetings.md">oferecendo suporte a reuniões grandes usando o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f897f-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-135">Um servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f897f-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="f897f-136">12.000 usuários remotos simultâneos</span><span class="sxs-lookup"><span data-stu-id="f897f-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-137">Um diretor</span><span class="sxs-lookup"><span data-stu-id="f897f-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="f897f-138">12.000 usuários remotos simultâneos</span><span class="sxs-lookup"><span data-stu-id="f897f-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-139">Monitoramento e Arquivamento</span><span class="sxs-lookup"><span data-stu-id="f897f-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="f897f-140">No Lync Server 2013, os serviços de front-end de monitoramento e arquivamento agora são executados em cada servidor front-end, em vez de funções de servidor separadas.</span><span class="sxs-lookup"><span data-stu-id="f897f-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="f897f-141">O monitoramento e arquivamento ainda exigem seus próprios armazenamentos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f897f-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="f897f-142">Se você também tiver o Exchange 2013, poderá manter seus dados de arquivamento no Exchange, em vez de em um banco de dados SQL dedicado.</span><span class="sxs-lookup"><span data-stu-id="f897f-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-143">Um servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="f897f-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f897f-144">O servidor de mediação colocado no front-end Server é executado em cada servidor front-end em um pool e deve fornecer capacidade suficiente para os usuários do pool.</span><span class="sxs-lookup"><span data-stu-id="f897f-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="f897f-145">Para o servidor de mediação autônomo, consulte a seção "servidor de mediação" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f897f-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-146">Um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f897f-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="f897f-147">É altamente recomendável que, se você usar os servidores de edição padrão para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planejamento para alta disponibilidade e recuperação de desastres no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f897f-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="f897f-148">Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá dar suporte a 5.000 usuários em um cenário de falha.</span><span class="sxs-lookup"><span data-stu-id="f897f-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="f897f-149">Se sua implantação inclui um quantidade de tráfego significativa de áudio ou vídeo, o desempenho do servidor pode ser prejudicado com mais de 2.500 usuários por servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="f897f-150">Nesse caso, você deve considerar adicionar mais servidores de edição padrão ou mover para o Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f897f-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="f897f-151">Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="f897f-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f897f-152">Pools ampliados não têm suporte para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="f897f-153">Em um pool de front-ends, você deve ter um servidor front-end para cada usuário do 6.660 hospedado no pool, pressupondo que o hyperthreading esteja habilitado em todos os servidores do pool e que o hardware do servidor atenda às recomendações nas [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="f897f-154">O número máximo de usuários em um pool de front-ends é 80.000, pressupondo que o hyperthreading esteja habilitado em todos os servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="f897f-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="f897f-155">Se você tiver mais de 80.000 usuários em um site, poderá implantar mais de um pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="f897f-156">Quando você conta com o número de usuários em um pool Front-end, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a este pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="f897f-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="f897f-157">Quando um servidor ativo está indisponível, suas conexões são transferidas automaticamente para outros serviços no pool.</span><span class="sxs-lookup"><span data-stu-id="f897f-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="f897f-158">Por exemplo, se você tiver usuários do 30.000 e cinco servidores front-end, então, se um servidor estiver indisponível, as conexões de 6000 usuários precisam ser transferidas para os outros quatro servidores.</span><span class="sxs-lookup"><span data-stu-id="f897f-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="f897f-159">Os quatro servidores restantes terão todos os usuários do 7500, que é um número maior do que o recomendado.</span><span class="sxs-lookup"><span data-stu-id="f897f-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="f897f-160">Se, em vez disso, você começou com seis servidores front end para seus usuários do 30.000 e, subsequentemente, ele se tornou indisponível, um total de 5000 usuários será movido para os cinco servidores restantes.</span><span class="sxs-lookup"><span data-stu-id="f897f-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="f897f-161">Esses cinco servidores serão todos os usuários do 6000 host, que estão no intervalo recomendado.</span><span class="sxs-lookup"><span data-stu-id="f897f-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="f897f-162">O número máximo de usuários em um pool de front-ends é 80.000.</span><span class="sxs-lookup"><span data-stu-id="f897f-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="f897f-163">O número máximo de servidores front-end em um pool é 12.</span><span class="sxs-lookup"><span data-stu-id="f897f-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="f897f-164">Para um pool de front-ends com usuários do 80.000, doze servidores front-end são suficientes para o desempenho, em implantações típicas que seguem os [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="f897f-165">Implantações projetadas para dar suporte a failover de recuperação de desastres presumindo que um máximo de 40.000 usuários podem ser hospedados em cada um dos dois pools front-ends emparelhados, em que cada pool tenha servidores de front-end suficientes para acomodar os usuários nos dois pools devem ser que um pool precise ser reprovado para o outro.</span><span class="sxs-lookup"><span data-stu-id="f897f-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="f897f-166">O número de usuários com suporte com bom desempenho por parte de um pool de front-end específico pode ser diferente dos seguintes números pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="f897f-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="f897f-167">O hardware para seus servidores front-ends não atende às recomendações nas [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="f897f-168">O uso da sua organização difere significativamente dos modelos de usuário, como tráfego de conferência significativamente maior.</span><span class="sxs-lookup"><span data-stu-id="f897f-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f897f-169">No Lync Server 2013, os bancos de dados de presença agora são hospedados em servidores front-end, ao contrário do Lync Server 2010 onde eles estavam hospedados no servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="f897f-170">Isso significa que o desempenho do disco e a capacidade dos seus servidores front-end não devem ser comprometidos das recomendações listadas anteriormente nesta seção e nas <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor do Lync server 2013</A>, independentemente do número de usuários hospedados por seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="f897f-171">A tabela a seguir mostra a média de largura de banda para mensagem instantânea e presença, considerando o modelo de usuário, conforme definido nos [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f897f-172">Largura de banda média por usuário</span><span class="sxs-lookup"><span data-stu-id="f897f-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="f897f-173">Requisitos de largura de banda por servidor front-end com usuários do 6.660</span><span class="sxs-lookup"><span data-stu-id="f897f-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f897f-174">1,3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="f897f-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="f897f-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="f897f-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f897f-176">Para melhorar o desempenho de mídia da funcionalidade co-localizado de conferência e servidor de mediação em seus servidores front-end, você deve habilitar o RSS (dimensionamento de recebimento) nos adaptadores de rede em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="f897f-177">O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="f897f-178">Para obter detalhes, consulte "aprimoramentos no redimensionamento do Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>em.</span><span class="sxs-lookup"><span data-stu-id="f897f-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="f897f-179">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="f897f-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="f897f-180">Máximos de Conferência</span><span class="sxs-lookup"><span data-stu-id="f897f-180">Conferencing Maximums</span></span>

<span data-ttu-id="f897f-181">Devido ao modelo de usuário de que 5% dos usuários em um pool pode estar em uma conferência a qualquer momento, um pool de usuários do 80.000 pode ter cerca de 4.000 usuários em conferências ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f897f-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="f897f-182">Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes.</span><span class="sxs-lookup"><span data-stu-id="f897f-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="f897f-183">Não há um limite rígido para o número real de conferências permitidas, e o uso real determina o desempenho real.</span><span class="sxs-lookup"><span data-stu-id="f897f-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="f897f-184">Por exemplo, se a sua organização tiver muitas outras conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end ou servidores de conferência A/V do que as recomendações contidas neste documento.</span><span class="sxs-lookup"><span data-stu-id="f897f-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="f897f-185">Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="f897f-186">O tamanho máximo de conferência compatível hospedado por um pool de front-end do Lync Server 2013 que também hospeda usuários é de 250 participantes.</span><span class="sxs-lookup"><span data-stu-id="f897f-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="f897f-187">Enquanto esta conferência de 250 usuários está acontecendo, o pool ainda suporta outras conferências, de forma que 5% dos usuários do pool estão em conferências simultâneas.</span><span class="sxs-lookup"><span data-stu-id="f897f-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="f897f-188">Por exemplo, em um pool de doze servidores de front-end e 80.000 usuários, enquanto a conferência de usuário do 250 está acontecendo, o Lync Server oferece suporte a 3.750 outros usuários que participam de conferências menores.</span><span class="sxs-lookup"><span data-stu-id="f897f-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="f897f-189">Independentemente do número de usuários hospedados no pool de front-ends ou no servidor Standard Edition, o Lync Server oferece suporte a um mínimo de 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que hospeda uma conferência de usuário do 250.</span><span class="sxs-lookup"><span data-stu-id="f897f-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="f897f-190">Para habilitar conferências com os usuários do 250 e do 1000, você pode configurar um pool de front-end separado apenas para hospedar essas conferências.</span><span class="sxs-lookup"><span data-stu-id="f897f-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="f897f-191">Este pool de front-ends não hospedará nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="f897f-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="f897f-192">Para obter detalhes, consulte [oferecendo suporte a reuniões grandes usando o Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="f897f-193">Se a sua organização tiver muitas outras conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end do que as recomendações contidas neste documento (até um limite de 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="f897f-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="f897f-194">Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="f897f-195">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="f897f-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f897f-196">Pools ampliados não têm suporte para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="f897f-197">Você deve implantar um servidor de borda para cada um dos usuários remotos do 12.000, que acessarão um site simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f897f-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="f897f-198">Recomendamos, no mínimo, dois servidores de borda para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f897f-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="f897f-199">Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações nas [plataformas de hardware do servidor do Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="f897f-200">Quando você conta com o número de usuários para os servidores de borda, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a um pool de front-ends neste site.</span><span class="sxs-lookup"><span data-stu-id="f897f-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f897f-201">Para melhorar o desempenho do serviço de borda de conferência A/V em seus servidores de borda, você deve habilitar o recurso de dimensionamento de recebimento (RSS) nos adaptadores de rede dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="f897f-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="f897f-202">O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="f897f-203">Para obter detalhes, consulte "aprimoramentos no redimensionamento do Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>em.</span><span class="sxs-lookup"><span data-stu-id="f897f-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="f897f-204">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="f897f-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="f897f-205">Diretor</span><span class="sxs-lookup"><span data-stu-id="f897f-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f897f-206">Pools ampliados não têm suporte para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="f897f-207">Se você implantar a função de servidor diretor, recomendamos implantar um director para cada um dos usuários remotos do 12.000 que acessarão um site simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f897f-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="f897f-208">Recomendamos, no mínimo, dois diretores para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f897f-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="f897f-209">Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações nas [plataformas de hardware do servidor do Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="f897f-210">Quando você conta com o número de usuários para os directors, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a um pool de front-end neste site.</span><span class="sxs-lookup"><span data-stu-id="f897f-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="f897f-211">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="f897f-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f897f-212">Pools ampliados não têm suporte para esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="f897f-213">Se você colocar o servidor de mediação com servidor front-end, o servidor de mediação será executado em todos os servidores front-end do pool e deve fornecer capacidade suficiente para os usuários do pool.</span><span class="sxs-lookup"><span data-stu-id="f897f-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="f897f-214">Se você implantar um pool autônomo do servidor de mediação, o número de servidores de mediação a serem implantados depende de muitos fatores, incluindo o hardware usado para o servidor de mediação, o número de usuários de VoIP que você tem, o número de pares de gateways que cada pool de servidores de mediação controles, o tráfego de horas ocupados por meio desses gateways e a porcentagem de chamadas com mídia que ignora o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f897f-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="f897f-215">As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um servidor de mediação pode manipular, pressupondo que o hardware dos servidores de mediação atenda aos requisitos nas [plataformas de hardware do servidor para o Lync Server 2013 e para](lync-server-2013-server-hardware-platforms.md) o Hyper-Threading está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f897f-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="f897f-216">Para obter detalhes sobre a escalabilidade do servidor de mediação, consulte Estimando o [uso de voz e o tráfego do Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [diretrizes de implantação do servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="f897f-217">Todas as tabelas a seguir consideram o uso resumido nos [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="f897f-218">Capacidade autônoma do servidor de mediação: 70% usuários internos, 30% usuários externos com capacidade de chamada não ignorada (transcodificação de mídia realizada pelo servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="f897f-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f897f-219">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="f897f-219">Server hardware</span></span></th>
<th><span data-ttu-id="f897f-220">Número máximo de chamadas</span><span class="sxs-lookup"><span data-stu-id="f897f-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="f897f-221">Número máximo de linhas T1</span><span class="sxs-lookup"><span data-stu-id="f897f-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="f897f-222">Número máximo de linhas E1</span><span class="sxs-lookup"><span data-stu-id="f897f-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f897f-223">Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded, <strong>com hyper-threading desabilitado</strong>, com 32 GB de memória e uma placa de adaptador de rede dual-port.</span><span class="sxs-lookup"><span data-stu-id="f897f-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="f897f-224">1100</span><span class="sxs-lookup"><span data-stu-id="f897f-224">1100</span></span></p></td>
<td><p><span data-ttu-id="f897f-225">46</span><span class="sxs-lookup"><span data-stu-id="f897f-225">46</span></span></p></td>
<td><p><span data-ttu-id="f897f-226">35</span><span class="sxs-lookup"><span data-stu-id="f897f-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-227">Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded, com 32 GB de memória e uma placa de adaptador de rede dual-port.</span><span class="sxs-lookup"><span data-stu-id="f897f-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="f897f-228">1500</span><span class="sxs-lookup"><span data-stu-id="f897f-228">1500</span></span></p></td>
<td><p><span data-ttu-id="f897f-229">63</span><span class="sxs-lookup"><span data-stu-id="f897f-229">63</span></span></p></td>
<td><p><span data-ttu-id="f897f-230">47</span><span class="sxs-lookup"><span data-stu-id="f897f-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f897f-231">Embora os servidores com 32 GB de memória sejam usados para teste de desempenho, os servidores com 16 GB de memória são compatíveis com o servidor de mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="f897f-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="f897f-232">Capacidade do servidor de mediação (servidor de mediação posicionado com servidor front-end) 70% usuários internos, 30% usuários externos, capacidade de chamada sem bypass (processamento de mídia executado pelo servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="f897f-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f897f-233">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="f897f-233">Server hardware</span></span></th>
<th><span data-ttu-id="f897f-234">Número máximo de chamadas</span><span class="sxs-lookup"><span data-stu-id="f897f-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f897f-235">Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded com hyper-threading e 2 placas de adaptador de rede de 1GB.</span><span class="sxs-lookup"><span data-stu-id="f897f-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="f897f-236">150</span><span class="sxs-lookup"><span data-stu-id="f897f-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f897f-237">Esse número é muito menor do que os números do servidor de mediação autônomo porque o servidor front-end tem de manipular outros recursos e funções para os usuários do 6600 hospedados nele, além da transcodificação necessária para chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="f897f-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f897f-238">Para melhorar o desempenho do servidor de mediação, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="f897f-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="f897f-239">O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="f897f-240">Para obter detalhes, consulte "aprimoramentos no redimensionamento do Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>em.</span><span class="sxs-lookup"><span data-stu-id="f897f-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="f897f-241">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="f897f-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="f897f-242">Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="f897f-242">Back End Server</span></span>

<span data-ttu-id="f897f-243">No Lync Server 2013, os bancos de dados de presença estão localizados nos servidores front-end, em vez do servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="f897f-244">Isso resultava em um requisito muito mais simples para cada servidor back-end no Lync Server 2013, equivalente ao requisito de hardware para o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="f897f-245">Compare isso com o Lync Server 2010, em que o servidor back-end era necessário para ser um servidor de nível muito mais alto com 25 discos.</span><span class="sxs-lookup"><span data-stu-id="f897f-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="f897f-246">No entanto, a carga de trabalho dos servidores back-end ainda não deve atender às recomendações de hardware listadas anteriormente nesta seção e nas [plataformas de hardware do servidor do Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="f897f-247">Para fornecer alta disponibilidade de seu servidor back-end, recomendamos implantar o espelhamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="f897f-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="f897f-248">Para obter mais informações, consulte [back-end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="f897f-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="f897f-249">Monitoramento e Arquivamento</span><span class="sxs-lookup"><span data-stu-id="f897f-249">Monitoring and Archiving</span></span>

<span data-ttu-id="f897f-250">No Lync Server 2013, se você implantar o monitoramento ou o arquivamento, a funcionalidade de front-end desses serviços é executada nos servidores front-end, em vez de nas funções de servidor separadas.</span><span class="sxs-lookup"><span data-stu-id="f897f-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="f897f-251">Monitorar e arquivar cada um ainda usa seu próprio repositório de banco de dados, separado da loja back-end.</span><span class="sxs-lookup"><span data-stu-id="f897f-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="f897f-252">Como alternativa, se você tiver o Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange em vez de em um repositório SQL dedicado.</span><span class="sxs-lookup"><span data-stu-id="f897f-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="f897f-253">A tabela a seguir indica aproximadamente quanto armazenamento de banco de dados é exigido por usuário, por dia, para os dados de monitoramento e arquivamento.</span><span class="sxs-lookup"><span data-stu-id="f897f-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="f897f-254"><strong>CDR (Monitoramento)</strong></span><span class="sxs-lookup"><span data-stu-id="f897f-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="f897f-255"><strong>QoE (Monitoramento)</strong></span><span class="sxs-lookup"><span data-stu-id="f897f-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="f897f-256"><strong>Archiving</strong></span><span class="sxs-lookup"><span data-stu-id="f897f-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-257">Espaço em disco exigido por usuário, por dia</span><span class="sxs-lookup"><span data-stu-id="f897f-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="f897f-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="f897f-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="f897f-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="f897f-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="f897f-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="f897f-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f897f-261">A Microsoft usou o hardware na tabela a seguir para p servidor de banco de dados para monitoramento e arquivamento durante seus testes de desempenho.</span><span class="sxs-lookup"><span data-stu-id="f897f-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="f897f-262">O teste coletou os dados de dois pools de front-end, cada um contendo 80.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="f897f-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="f897f-263">Hardware usado nos testes de desempenho de monitoramento e arquivamento</span><span class="sxs-lookup"><span data-stu-id="f897f-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f897f-264">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="f897f-264">Hardware component</span></span></th>
<th><span data-ttu-id="f897f-265">Recomendado</span><span class="sxs-lookup"><span data-stu-id="f897f-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f897f-266">CPU</span><span class="sxs-lookup"><span data-stu-id="f897f-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="f897f-267">Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior</span><span class="sxs-lookup"><span data-stu-id="f897f-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-268">Memória</span><span class="sxs-lookup"><span data-stu-id="f897f-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="f897f-269">48 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="f897f-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-270">Disco</span><span class="sxs-lookup"><span data-stu-id="f897f-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="f897f-271">25 unidades de disco rígido de 10.000-RPM com 300 GB em cada unidade, com a seguinte configuração</span><span class="sxs-lookup"><span data-stu-id="f897f-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="f897f-272"><strong>Unidade</strong></span><span class="sxs-lookup"><span data-stu-id="f897f-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="f897f-273"><strong>Configuração RAID</strong></span><span class="sxs-lookup"><span data-stu-id="f897f-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f897f-274"><strong>Número de discos</strong></span><span class="sxs-lookup"><span data-stu-id="f897f-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-275">CDR, QoE e arquivos de banco de dados de arquivamento, em uma única unidade</span><span class="sxs-lookup"><span data-stu-id="f897f-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="f897f-276">1+0</span><span class="sxs-lookup"><span data-stu-id="f897f-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="f897f-277">16</span><span class="sxs-lookup"><span data-stu-id="f897f-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-278">Arquivo de log do banco de dados de CDR</span><span class="sxs-lookup"><span data-stu-id="f897f-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="f897f-279">1</span><span class="sxs-lookup"><span data-stu-id="f897f-279">1</span></span></p></td>
<td><p><span data-ttu-id="f897f-280">2</span><span class="sxs-lookup"><span data-stu-id="f897f-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-281">Arquivo de log do banco de dados de QoE</span><span class="sxs-lookup"><span data-stu-id="f897f-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="f897f-282">1</span><span class="sxs-lookup"><span data-stu-id="f897f-282">1</span></span></p></td>
<td><p><span data-ttu-id="f897f-283">2</span><span class="sxs-lookup"><span data-stu-id="f897f-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f897f-284">Arquivo de log do banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="f897f-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="f897f-285">1</span><span class="sxs-lookup"><span data-stu-id="f897f-285">1</span></span></p></td>
<td><p><span data-ttu-id="f897f-286">2</span><span class="sxs-lookup"><span data-stu-id="f897f-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f897f-287">Rede</span><span class="sxs-lookup"><span data-stu-id="f897f-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f897f-288">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP)</span><span class="sxs-lookup"><span data-stu-id="f897f-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f897f-289">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f897f-289">In This Section</span></span>

  - [<span data-ttu-id="f897f-290">Estimando uso e tráfego de voz para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f897f-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="f897f-291">Diretrizes de implantação para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f897f-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

