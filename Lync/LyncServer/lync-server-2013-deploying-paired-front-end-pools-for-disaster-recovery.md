---
title: 'Lync Server 2013: Implantando pools front-end emparelhados para recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a18b92dde9b6ca48ffe8912f216331c39ef9cc9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="a753e-102">Implantando pools front-end emparelhados para recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a753e-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a753e-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a753e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a753e-104">Você pode implantar facilmente a topologia de recuperação de desastres dos pools de front-ends emparelhados usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a753e-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="a753e-105">Para implantar um par de pools do Front-End</span><span class="sxs-lookup"><span data-stu-id="a753e-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="a753e-106">Se os pools são novos e ainda não foram definidos, use o construtor de topologias para criar os pools.</span><span class="sxs-lookup"><span data-stu-id="a753e-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="a753e-107">No construtor de topologias, clique com o botão direito do mouse em um dos dois pools e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a753e-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a753e-108">Clique em **Resiliência** no painel esquerdo e selecione **Pool de backup associado** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="a753e-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="a753e-p101">Na caixa abaixo **Pool de backup associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estão emparelhados com outro pool estarão disponíveis para selecionar.</span><span class="sxs-lookup"><span data-stu-id="a753e-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="a753e-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="a753e-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="a753e-112">Selecione **Failover automático e failback para voz** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a753e-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="a753e-113">Ao exibir os detalhes sobre este pool, o pool associado agora aparece no painel direito em **Resiliência**.</span><span class="sxs-lookup"><span data-stu-id="a753e-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="a753e-114">Use o construtor de topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="a753e-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="a753e-p102">Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída. É possível pular as duas etapas finais neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a753e-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="a753e-117">No entanto, se os pools já foram implantados antes de você definir a relação emparelhada, você deve concluir as seguintes duas etapas finais.</span><span class="sxs-lookup"><span data-stu-id="a753e-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="a753e-118">Em cada Servidor de Front-End Server nos pools, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a753e-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="a753e-119">Isto configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="a753e-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="a753e-120">Em um prompt de comando do Shell de gerenciamento do Lync Server, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a753e-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="a753e-121">Force o usuário e os dados de conferência de ambos os pools para sincronização um com o outro, com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a753e-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="a753e-122">Sincronizar os dados pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="a753e-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="a753e-123">É possível usar os seguintes cmdlets para verificar os tatus.</span><span class="sxs-lookup"><span data-stu-id="a753e-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="a753e-124">Certifique-se de que o status em ambas as direções está no estado Steady.</span><span class="sxs-lookup"><span data-stu-id="a753e-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="a753e-125">A opção <STRONG>failover automático e failback para voz</STRONG> e os intervalos de tempo associados no construtor de topologia só se aplicam aos recursos de resiliência de voz introduzidos no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a753e-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="a753e-126">Selecionar esta opção não implica que o failover de pool discutido neste documento seja automático.</span><span class="sxs-lookup"><span data-stu-id="a753e-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="a753e-127">O failover de pool e failback sempre exige que um administrador invoque manualmente os cmdlets de failover e failback, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a753e-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

