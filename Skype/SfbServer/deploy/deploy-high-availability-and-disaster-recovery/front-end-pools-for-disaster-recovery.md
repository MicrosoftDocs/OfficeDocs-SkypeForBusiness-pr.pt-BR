---
title: Implantar pools de front-end emparelhados para recuperação de desastres no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Você pode usar pools de front-ends para fornecer proteção à recuperação de desastre, mas isso não é obrigatório.
ms.openlocfilehash: 4aa24c3a5150efbea87cd3837aca9216f047b11e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240031"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="50960-103">Implantar pools de front-end emparelhados para recuperação de desastres no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="50960-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="50960-104">Você pode usar pools de front-ends para fornecer proteção à recuperação de desastre, mas isso não é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="50960-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="50960-105">Você pode implantar facilmente a topologia de recuperação de desastres de pools front-end em par usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="50960-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="50960-106">Para implantar um par de pools de front-ends</span><span class="sxs-lookup"><span data-stu-id="50960-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="50960-107">Se os pools forem novos e ainda não estiverem definidos, use o construtor de topologias para criar os grupos.</span><span class="sxs-lookup"><span data-stu-id="50960-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="50960-108">No construtor de topologias, clique com o botão direito do mouse em um dos dois grupos e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="50960-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="50960-109">Clique em **Resiliência** no painel esquerdo e selecione **Pool de Backup Associado** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="50960-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="50960-p101">Na caixa abaixo de **Pool de Backup Associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estejam emparelhados com outro pool estarão disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="50960-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="50960-112">Selecione **Failback e failover automático para Voz** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="50960-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="50960-113">Quando você exibir os detalhes sobre este pool, o pool associado agora aparecerá no painel direito em **Resiliência**. </span><span class="sxs-lookup"><span data-stu-id="50960-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="50960-114">Use o construtor de topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="50960-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="50960-p102">Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída. Você pode ignorar as duas etapas finais deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="50960-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="50960-117">No entanto, se os pools já foram implantados antes de você definir a relação emparelhada, você deverá concluir as duas etapas finais a seguir.</span><span class="sxs-lookup"><span data-stu-id="50960-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="50960-118">Em cada Servidor Front-End nos pools, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50960-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="50960-119">Isso configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="50960-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="50960-120">Em um prompt de comando do Shell de gerenciamento do Skype for Business Server, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50960-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="50960-121">Force a sincronização dos dados do usuário e de conferência de ambos os pools com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="50960-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="50960-p103">A sincronização dos dados pode levar algum tempo. É possível usar os cmdlets a seguir para verificar o status. O status em ambas as direções deve estar em um estado estável.</span><span class="sxs-lookup"><span data-stu-id="50960-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="50960-125">A opção **failover automático e failback para voz** e os intervalos de tempo associados no construtor de topologia só se aplicam aos recursos de resiliência de voz que foram introduzidos no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50960-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="50960-126">Selecionar essa opção não implica que o failover de pool discutido neste documento seja automático.</span><span class="sxs-lookup"><span data-stu-id="50960-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="50960-127">O failback e o failover de pool sempre exigem que um administrador invoque manualmente os cmdlets de failback e failover, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="50960-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50960-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="50960-128">See also</span></span>

[<span data-ttu-id="50960-129">Recuperação de desastre do pool de front-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="50960-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
