---
title: Implantar pools de front-end emparelhados para recuperação de desastre no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Você pode optar por usar pools de Front End emparelhados para fornecer proteção de recuperação de desastres, mas fazer isso não é um requisito.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830601"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="50728-103">Implantar pools de front-end emparelhados para recuperação de desastre no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="50728-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="50728-104">Você pode optar por usar pools de Front End emparelhados para fornecer proteção de recuperação de desastres, mas fazer isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="50728-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="50728-105">Você pode implantar facilmente a topologia de recuperação de desastres de pools de front-end emparelhados usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="50728-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="50728-106">Para implantar um par de pools do Front-End</span><span class="sxs-lookup"><span data-stu-id="50728-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="50728-107">Se os pools são novos e ainda não foram definidos, use o Construtor de Topologias para criar os pools.</span><span class="sxs-lookup"><span data-stu-id="50728-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="50728-108">No Construtor de Topologias, clique com o botão direito do mouse em um dos dois pools e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="50728-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="50728-109">Clique em **Resiliência** no painel esquerdo e selecione **Pool de backup associado** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="50728-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="50728-p101">Na caixa abaixo **Pool de backup associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estão emparelhados com outro pool estarão disponíveis para selecionar.</span><span class="sxs-lookup"><span data-stu-id="50728-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="50728-112">Selecione **Failover automático e failback para voz** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="50728-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="50728-113">Ao exibir os detalhes sobre este pool, o pool associado agora aparece no painel direito em **Resiliência**.</span><span class="sxs-lookup"><span data-stu-id="50728-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="50728-114">Use o Construtor de Topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="50728-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="50728-115">Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída.</span><span class="sxs-lookup"><span data-stu-id="50728-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="50728-116">Você pode ignorar as etapas finais deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="50728-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="50728-117">No entanto, se os pools já foram implantados antes de você definir o relacionamento emparelhado, você deve concluir as etapas finais a seguir.</span><span class="sxs-lookup"><span data-stu-id="50728-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="50728-118">Em cada Servidor de Front-End Server nos pools, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50728-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="50728-119">Isto configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="50728-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="50728-120">Depois que o Bootstrapper terminar de instalar os componentes necessários para o emparelhamento de backup em cada Servidor Front-end em ambos os pools, certifique-se de aplicar novamente qualquer Atualização Cumulativa existente que tenha sido aplicada anteriormente nesses Servidores Front End em ambos os pools e continue com a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="50728-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="50728-121">Em um prompt de comando do Shell de Gerenciamento do Skype for Business Server, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50728-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="50728-122">Force o usuário e os dados de conferência de ambos os pools a serem sincronizados uns com os outros com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="50728-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="50728-123">Sincronizar os dados pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="50728-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="50728-124">É possível usar os seguintes cmdlets para verificar os tatus.</span><span class="sxs-lookup"><span data-stu-id="50728-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="50728-125">Certifique-se de que o status em ambas as direções está em estado estável.</span><span class="sxs-lookup"><span data-stu-id="50728-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="50728-126">O **failover automático** e failback para a opção Voz e os intervalos de tempo associados no Construtor de Topologias se aplicam somente aos recursos de resiliência de voz que foram introduzidos no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50728-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="50728-127">Selecionar esta opção não implica que o failover de pool discutido neste documento seja automático.</span><span class="sxs-lookup"><span data-stu-id="50728-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="50728-128">O failover de pool e failback sempre exige que um administrador invoque manualmente os cmdlets de failover e failback, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="50728-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50728-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="50728-129">See also</span></span>

[<span data-ttu-id="50728-130">Recuperação de desastre do pool de front-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="50728-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
