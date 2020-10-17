---
title: 'Lync Server 2013: atualizar ou atualizar servidores front-end'
description: 'Lync Server 2013: atualizar ou atualizar servidores front-end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569917"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="3455d-103">Atualizar ou atualizar servidores front-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3455d-103">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3455d-104">_**Última modificação do tópico:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="3455d-104">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="3455d-105">Os Servidores de Front-End em um pool do Enterprise Edition são organizados nos *domínios de atualização*.</span><span class="sxs-lookup"><span data-stu-id="3455d-105">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="3455d-106">Estes são subconjuntos de Servidores de Front-End no pool.</span><span class="sxs-lookup"><span data-stu-id="3455d-106">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="3455d-107">Os domínios de atualização são criados automaticamente pelo construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="3455d-107">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="3455d-108">Ao atualizar servidores, você deve fazer isso um domínio de atualização por vez.</span><span class="sxs-lookup"><span data-stu-id="3455d-108">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="3455d-109">Coloque cada servidor em um domínio de atualização para baixo, atualize-o e reinicie-o antes de passar para outro domínio de atualização.</span><span class="sxs-lookup"><span data-stu-id="3455d-109">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="3455d-110">Certifique-se de acompanhar quais domínios e servidores de atualização foram atualizados até o momento.</span><span class="sxs-lookup"><span data-stu-id="3455d-110">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="3455d-111">Use o diagrama de fluxograma a seguir ao atualizar cada servidor.</span><span class="sxs-lookup"><span data-stu-id="3455d-111">Use the following flowchart diagram when upgrading each server.</span></span>

![Atualizar servidores Front End](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="3455d-113">Para aplicar uma atualização aos servidores front-end em um pool</span><span class="sxs-lookup"><span data-stu-id="3455d-113">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="3455d-114">Em um Servidor de Front-End no pool, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3455d-114">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="3455d-115">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="3455d-115">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="3455d-116">Se o valor de *PoolUpgradeState* estiver **ocupado**, aguarde 10 minutos e tente **Get-CsPoolUpgradeReadinessState** novamente.</span><span class="sxs-lookup"><span data-stu-id="3455d-116">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="3455d-117">Se você vir **ocupado** por pelo menos três vezes consecutivas, após aguardar 10 minutos entre cada tentativa ou se vir qualquer resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** haverá um problema com o pool.</span><span class="sxs-lookup"><span data-stu-id="3455d-117">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="3455d-118">Se este pool está emparelhado com outro pool de Front-End em uma topologia de recuperação de desastres, deve falhar o pool sobre o pool de backup e atualizar os servidores neste pool.</span><span class="sxs-lookup"><span data-stu-id="3455d-118">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="3455d-119">Para obter detalhes, consulte [failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="3455d-119">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="3455d-120">Se o valor de *PoolUpgradeState* é **Pronto**, vá para a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3455d-120">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="3455d-121">O cmdlet **Get-CsPoolUpgradeReadinessState** também retorna informações sobre cada domínio de atualização no pool e sobre quais servidores front-end estão em cada domínio de atualização.</span><span class="sxs-lookup"><span data-stu-id="3455d-121">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="3455d-122">Se o valor **ReadyforUpgrade** for **true** para o domínio de atualização que contém o servidor ou os servidores que você deseja atualizar, você pode atualizar esses servidores com segurança agora.</span><span class="sxs-lookup"><span data-stu-id="3455d-122">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="3455d-123">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="3455d-123">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="3455d-124">Interrompa novas conexões com os servidores front-end que você vai atualizar usando o `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3455d-124">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3455d-125">Se estiver executando essas atualizações de servidor durante um tempo de inatividade do servidor agendado, você pode executar esse cmdlet sem o parâmetro '-<STRONG>normal</STRONG>', da seguinte maneira: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3455d-125">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="3455d-126">Isso fechará imediatamente os serviços, sem esperar que todas as solicitações de serviço existentes sejam preenchidas.</span><span class="sxs-lookup"><span data-stu-id="3455d-126">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="3455d-127">Atualize os servidores associados a este domínio de atualização.</span><span class="sxs-lookup"><span data-stu-id="3455d-127">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="3455d-128">Reinicie os servidores e verifique se eles estão aceitando novas conexões.</span><span class="sxs-lookup"><span data-stu-id="3455d-128">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="3455d-129">Repita as etapas 1 e 2 para cada outro domínio de atualização no pool, até que todos os servidores front-end tenham sido atualizados.</span><span class="sxs-lookup"><span data-stu-id="3455d-129">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

