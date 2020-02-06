---
title: Configurando e monitorando o Serviço de Backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode usar os comandos do Shell de gerenciamento do Skype for Business Server para configurar e monitorar o serviço de backup.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818212"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="3781d-103">Configurando e monitorando o serviço de backup no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3781d-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="3781d-104">Você pode usar os seguintes comandos do Shell de gerenciamento do Skype for Business Server para configurar e monitorar o serviço de backup.</span><span class="sxs-lookup"><span data-stu-id="3781d-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="3781d-105">Para restaurar as informações de conferência armazenadas no repositório de arquivos de um pool de front-end, consulte [restaurar conteúdo da conferência usando o serviço de backup](#restore-conference-contents-using-the-backup-service)abaixo.</span><span class="sxs-lookup"><span data-stu-id="3781d-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="3781d-106">O grupo RTCUniversalServerAdmins é o único grupo que tem permissões para executar **Get-CsBackupServiceStatus** por padrão.</span><span class="sxs-lookup"><span data-stu-id="3781d-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="3781d-107">Para usar esse cmdlet, faça logon como membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="3781d-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="3781d-108">Ou você pode conceder acesso a esse comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet **set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3781d-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="3781d-109">Para ver a configuração do serviço de backup</span><span class="sxs-lookup"><span data-stu-id="3781d-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="3781d-110">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3781d-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="3781d-111">O padrão para SyncInterval é de dois minutos.</span><span class="sxs-lookup"><span data-stu-id="3781d-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="3781d-112">Para definir o intervalo de sincronização do serviço de backup</span><span class="sxs-lookup"><span data-stu-id="3781d-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="3781d-113">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3781d-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="3781d-114">Por exemplo, o seguinte define o intervalo como três minutos.</span><span class="sxs-lookup"><span data-stu-id="3781d-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="3781d-115">Embora você possa usar esse cmdlet para alterar o intervalo de sincronização padrão do serviço de backup, não deve fazê-lo, a menos que seja absolutamente necessário, pois o intervalo de sincronização tem um grande impacto sobre o desempenho do serviço de backup e o RPO (objetivo do ponto de recuperação).</span><span class="sxs-lookup"><span data-stu-id="3781d-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="3781d-116">Para obter o status do serviço de backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="3781d-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="3781d-117">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3781d-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="3781d-118">O status de sincronização do serviço de backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2).</span><span class="sxs-lookup"><span data-stu-id="3781d-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="3781d-119">O status de sincronização de P1 a P2 pode ser diferente do do P2 para P1.</span><span class="sxs-lookup"><span data-stu-id="3781d-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="3781d-120">Para P1 a P2, o serviço de backup está em um estado "estacionário" se todas as alterações feitas em P1 são completamente duplicadas para P2 dentro do intervalo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="3781d-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="3781d-121">Ele está no estado "final" se não houver mais alterações a serem sincronizadas do P1 ao P2.</span><span class="sxs-lookup"><span data-stu-id="3781d-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="3781d-122">Os dois Estados indicam um instantâneo do serviço de backup no momento em que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="3781d-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="3781d-123">Isso não significa que o estado retornado permanecerá como mais tarde.</span><span class="sxs-lookup"><span data-stu-id="3781d-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="3781d-124">Em particular, o estado "final" continuará a ser suspenso apenas se P1 não gerar nenhuma alteração após a execução do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3781d-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="3781d-125">Isso é verdade no caso de falha P1 para P2 após o P1 ser colocado no modo somente leitura como parte da lógica de execução **Invoke-CsPoolfailover** .</span><span class="sxs-lookup"><span data-stu-id="3781d-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="3781d-126">Para obter informações sobre a relação de backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="3781d-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="3781d-127">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3781d-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="3781d-128">Para forçar uma sincronização do serviço de backup</span><span class="sxs-lookup"><span data-stu-id="3781d-128">To force a Backup Service sync</span></span>

<span data-ttu-id="3781d-129">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3781d-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="3781d-130">Restaurar o conteúdo da conferência usando o serviço de backup</span><span class="sxs-lookup"><span data-stu-id="3781d-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="3781d-131">Se as informações de conferência armazenadas no repositório de arquivos de um pool de front-ends ficar indisponíveis, você deverá restaurar essas informações para que os usuários hospedados no pool mantenham seus dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="3781d-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="3781d-132">Se o pool de front-ends que perdeu dados de conferências estiver emparelhado com outro pool de front-end, você pode usar o serviço de backup para restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="3781d-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="3781d-133">Você também deve realizar essa tarefa se um pool inteiro tiver falhado e tiver que fazer failover de seus usuários para um pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3781d-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="3781d-134">Quando esses usuários falham novamente em seu pool original, você deve usar esse procedimento para copiar o conteúdo de conferência de volta para o pool original também.</span><span class="sxs-lookup"><span data-stu-id="3781d-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="3781d-135">Suponha que o Pool1 está emparelhado com Pool2, e os dados de conferência no Pool1 são perdidos.</span><span class="sxs-lookup"><span data-stu-id="3781d-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="3781d-136">Você pode usar o cmdlet a seguir para invocar o serviço de backup para restaurar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="3781d-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="3781d-137">A restauração do conteúdo da conferência pode levar algum tempo, dependendo do tamanho.</span><span class="sxs-lookup"><span data-stu-id="3781d-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="3781d-138">Você pode usar o cmdlet a seguir para verificar o status do processo:</span><span class="sxs-lookup"><span data-stu-id="3781d-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="3781d-139">O processo é feito quando esse cmdlet retorna um valor de estado Steady para o módulo de conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="3781d-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
