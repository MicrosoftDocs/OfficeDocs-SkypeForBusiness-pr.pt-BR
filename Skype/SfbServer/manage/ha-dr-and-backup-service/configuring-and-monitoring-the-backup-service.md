---
title: Configurando e monitorando o Serviço de Backup
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode usar o Skype para comandos do Shell de gerenciamento do servidor de negócios para configurar e monitorar o serviço de Backup.
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896830"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="db346-103">Configurando e monitorando o serviço de Backup no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="db346-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="db346-104">Você pode usar o seguinte Skype para comandos do Shell de gerenciamento do servidor de negócios para configurar e monitorar o serviço de Backup.</span><span class="sxs-lookup"><span data-stu-id="db346-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="db346-105">Para restaurar informações de conferência armazenadas no repositório de arquivo de um pool de Front-End, consulte [restaurar conteúdo de conferência usando o serviço de Backup](#restore-conference-contents-using-the-backup-service), abaixo.</span><span class="sxs-lookup"><span data-stu-id="db346-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="db346-106">Grupo RTCUniversalServerAdmins é o único grupo que tem permissões para executar **Get-CsBackupServiceStatus** por padrão.</span><span class="sxs-lookup"><span data-stu-id="db346-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="db346-107">Para usar esse cmdlet, faça logon como um membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="db346-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="db346-108">Ou então, você pode conceder acesso a esse comando a outros grupos (por exemplo, CSAdministrator) usando o cmdlet **Set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="db346-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="db346-109">Para ver a configuração do serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="db346-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="db346-110">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db346-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="db346-111">O padrão para SyncInterval é dois minutos.</span><span class="sxs-lookup"><span data-stu-id="db346-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="db346-112">Para definir o intervalo de sincronização do serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="db346-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="db346-113">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db346-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="db346-114">Por exemplo, o exemplo a seguir define o intervalo para três minutos.</span><span class="sxs-lookup"><span data-stu-id="db346-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="db346-115">Embora você possa usar esse cmdlet para alterar o intervalo de sincronização padrão para o serviço de Backup, você não deve fazer para que a menos que seja absolutamente necessário, como a sincronização intervalo tem um grande impacto sobre o desempenho do serviço de Backup e o objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="db346-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="db346-116">Para obter o status do serviço de Backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="db346-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="db346-117">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db346-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="db346-118">O status de sincronização do serviço de Backup é definido unidirectionally de um pool (P1) para seu pool de backup (P2).</span><span class="sxs-lookup"><span data-stu-id="db346-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="db346-119">O status de sincronização de P1 para P2 pode ser diferente de P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="db346-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="db346-120">Para P1 para o P2, o serviço de Backup está em um estado "estável" se todas as alterações feitas em P1 são replicadas completamente via para P2 dentro do intervalo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="db346-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="db346-121">Não é no estado "final" se não houver nenhuma alteração mais sejam sincronizadas de P1 P2.</span><span class="sxs-lookup"><span data-stu-id="db346-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="db346-122">Ambos os estados indicam um instantâneo do serviço de Backup no momento em que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="db346-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="db346-123">Ele não supõe que o estado retornado permanecerá como está posteriormente.</span><span class="sxs-lookup"><span data-stu-id="db346-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="db346-124">Em particular, o estado "final" continuará mantenha apenas se P1 não gera quaisquer alterações depois que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="db346-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="db346-125">Isso acontece no caso de failover dos P1 P2 depois P1 é colocado no modo de somente leitura como parte da lógica de execução do **Invoke-CsPoolfailover** .</span><span class="sxs-lookup"><span data-stu-id="db346-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="db346-126">Para obter informações sobre o relacionamento de backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="db346-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="db346-127">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db346-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="db346-128">Para forçar uma sincronização do serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="db346-128">To force a Backup Service sync</span></span>

<span data-ttu-id="db346-129">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db346-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="db346-130">Restaurar conteúdo de conferência usando o serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="db346-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="db346-131">Se as informações de conferência armazenadas no repositório de arquivo de um pool de Front-End ficam indisponíveis, você deve restaurar essas informações para que os usuários hospedados no pool mantêm seus dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="db346-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="db346-132">Se o pool de Front-End que tem perda de dados de conferência é emparelhado com outro pool de Front-End, você pode usar o serviço de Backup para restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="db346-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="db346-133">Você também deve executar essa tarefa, se um pool inteiro falhar e você precisar realizar failover seus usuários para um pool de backup.</span><span class="sxs-lookup"><span data-stu-id="db346-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="db346-134">Quando esses usuários são falhou volta para seu pool original, você deve usar este procedimento para copiar o conteúdo de sua conferências volta ao seu pool original também.</span><span class="sxs-lookup"><span data-stu-id="db346-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="db346-135">Suponha que Pool1 está emparelhado com o Pool2, e os dados de conferência no Pool1 são perdidos.</span><span class="sxs-lookup"><span data-stu-id="db346-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="db346-136">Você pode usar o seguinte cmdlet para chamar o serviço de Backup para restaurar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="db346-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="db346-137">Restaurar o conteúdo de conferência pode levar algum tempo, dependendo de seu tamanho.</span><span class="sxs-lookup"><span data-stu-id="db346-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="db346-138">Você pode usar o seguinte cmdlet para verificar o status do processo:</span><span class="sxs-lookup"><span data-stu-id="db346-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="db346-139">O processo é concluído quando este cmdlet retorna um valor de estado estável para o módulo de conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="db346-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
