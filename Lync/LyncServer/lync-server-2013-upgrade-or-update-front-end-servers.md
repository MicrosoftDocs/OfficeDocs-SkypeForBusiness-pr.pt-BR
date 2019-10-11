---
title: 'Lync Server 2013: atualizar ou atualizar servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4edb5ea009960fe0456f266a428431049f542b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="84446-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84446-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84446-103">_**Tópico da última modificação:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="84446-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="84446-104">Os servidores de front-end em um pool da edição Enterprise são organizados em *domínios de atualização*.</span><span class="sxs-lookup"><span data-stu-id="84446-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="84446-105">Esses são subconjuntos de servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="84446-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="84446-106">Os domínios de atualização são criados automaticamente pelo construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="84446-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="84446-107">Ao atualizar os servidores, você deve fazer um domínio de atualização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="84446-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="84446-108">Coloque cada servidor em um domínio de atualização abaixo, atualize-o e reinicie-o antes de passar para outro domínio de atualização.</span><span class="sxs-lookup"><span data-stu-id="84446-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="84446-109">Certifique-se de acompanhar quais domínios e servidores de atualização você atualizou até agora.</span><span class="sxs-lookup"><span data-stu-id="84446-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="84446-110">Use o diagrama de fluxograma a seguir ao atualizar cada servidor.</span><span class="sxs-lookup"><span data-stu-id="84446-110">Use the following flowchart diagram when upgrading each server.</span></span>

<span data-ttu-id="84446-111">:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Atualizar ou atualizar servidores front-end":::</span><span class="sxs-lookup"><span data-stu-id="84446-111">:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Upgrade or Update Front End Servers":::</span></span>

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="84446-112">Para aplicar uma atualização aos servidores Front-End em um pool</span><span class="sxs-lookup"><span data-stu-id="84446-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="84446-113">Em um servidor front-end do pool, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="84446-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="84446-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="84446-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="84446-115">Se o valor de *PoolUpgradeState* estiver **ocupado**, aguarde 10 minutos e tente **Get-CsPoolUpgradeReadinessState** novamente.</span><span class="sxs-lookup"><span data-stu-id="84446-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="84446-116">Se você vir **ocupado** pelo menos três vezes consecutivos, após esperar 10 minutos entre cada tentativa, ou se vir qualquer resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** há um problema com o pool.</span><span class="sxs-lookup"><span data-stu-id="84446-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="84446-117">Se esse pool estiver emparelhado com outro pool de front-ends em uma topologia de recuperação de desastre, você deverá fazer failover do pool para o pool de backup e, em seguida, atualizar os servidores nesse pool.</span><span class="sxs-lookup"><span data-stu-id="84446-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="84446-118">Para obter detalhes, consulte [falha em um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="84446-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="84446-119">Se o valor de *PoolUpgradeState* estiver **pronto**, vá para a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="84446-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="84446-120">O cmdlet **Get-CsPoolUpgradeReadinessState** também retorna informações sobre cada domínio de atualização do pool e sobre quais servidores de front-end estão em cada domínio de atualização.</span><span class="sxs-lookup"><span data-stu-id="84446-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="84446-121">Se o valor de **ReadyforUpgrade** for **verdadeiro** para o domínio de atualização que contém o servidor ou servidores que você deseja atualizar, você pode atualizar os servidores com segurança agora.</span><span class="sxs-lookup"><span data-stu-id="84446-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="84446-122">Para fazer isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="84446-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="84446-123">Pare as novas conexões com os servidores front end que você vai atualizar usando o `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="84446-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="84446-124">Se você estiver executando essas atualizações do servidor durante um tempo de inatividade do servidor programado, poderá executar esse cmdlet sem o parâmetro '-<STRONG>normal</STRONG>', da seguinte maneira: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="84446-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="84446-125">Isso encerrará imediatamente os serviços, sem esperar que todas as solicitações de serviço existentes sejam preenchidas.</span><span class="sxs-lookup"><span data-stu-id="84446-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="84446-126">Atualize os servidores associados a este domínio de atualização.</span><span class="sxs-lookup"><span data-stu-id="84446-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="84446-127">Reinicie os servidores e certifique-se de que eles estejam aceitando novas conexões.</span><span class="sxs-lookup"><span data-stu-id="84446-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="84446-128">Repita as etapas 1 e 2 para cada outro domínio de atualização do pool, até que todos os servidores front end tenham sido atualizados.</span><span class="sxs-lookup"><span data-stu-id="84446-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

