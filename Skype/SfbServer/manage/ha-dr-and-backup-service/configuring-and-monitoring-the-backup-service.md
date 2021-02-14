---
title: Configurando e monitorando o Serviço de Backup
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode usar os comandos do Shell de Gerenciamento do Skype for Business Server para configurar e monitorar o Serviço de Backup.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817191"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="bfcfb-103">Configurando e monitorando o Serviço de Backup no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bfcfb-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="bfcfb-104">Você pode usar os seguintes comandos do Shell de Gerenciamento do Skype for Business Server para configurar e monitorar o Serviço de Backup.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="bfcfb-105">Para restaurar informações de conferência armazenadas no armazenamento de arquivos de um pool de Front-End, consulte Restaurar conteúdo de conferência [usando o Serviço de Backup](#restore-conference-contents-using-the-backup-service), abaixo.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="bfcfb-106">O grupo RTCUniversalServerAdmins é o único grupo que possui permissões para executar o **Get-CsBackupServiceStatus** por padrão.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="bfcfb-107">Para usar este cmdlet, faça o login como membro deste grupo.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="bfcfb-108">Em alternativa, é possível conceder acesso a este comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet **Set-CsBackupServiceConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="bfcfb-109">Para ver a configuração do Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="bfcfb-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="bfcfb-110">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="bfcfb-111">O padrão para SyncInterval é dois minutos.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="bfcfb-112">Para definir o intervalo de sincronização do Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="bfcfb-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="bfcfb-113">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="bfcfb-114">Por exemplo, o seguinte define o intervalo para três minutos.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="bfcfb-115">Embora seja possível usar este cmdlet para alterar o intervalo de sincronização padrão para o Serviço de Backup, você não deve fazer menos do que o absolutamente necessário, pois o intervalo de sincronização possui um grande impacto no desempenho do Serviço de Backup e o objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="bfcfb-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="bfcfb-116">Para obter o status do Serviço de Backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="bfcfb-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="bfcfb-117">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="bfcfb-118">O status de sincronização do Serviço de Backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2).</span><span class="sxs-lookup"><span data-stu-id="bfcfb-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="bfcfb-119">O status de sincronização de P1 para P2 pode ser diferente do que de P2 para P1.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="bfcfb-120">Para P1 para P2, o Serviço de Backup está em estado "pronto" se todas as alterações realizadas em P1 são completamente replicadas para P2 dentro do intervalo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="bfcfb-121">Está no estado “final” se não há mais mudanças a serem sincronizadas de P1 para P2.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="bfcfb-122">Ambos os estados indicam um instantâneo do Serviço de Backup no momento que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="bfcfb-123">Não implica que o estado retornado permanecerá como é posteriormente.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="bfcfb-124">Em particular, o estado “final” continuará a manter apenas se P1 não gerar qualquer mudança após o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="bfcfb-125">Isto é verdadeiro em caso de falha de P1 por P2 após P1 ser inserido no modo somente leitura como parte da lógica de execução do **Invoke-CsPoolfailover**.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="bfcfb-126">Para obter informações sobre a relação de backup de um determinado pool</span><span class="sxs-lookup"><span data-stu-id="bfcfb-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="bfcfb-127">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="bfcfb-128">Para forçar uma sincronização do Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="bfcfb-128">To force a Backup Service sync</span></span>

<span data-ttu-id="bfcfb-129">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="bfcfb-130">Restaurar o conteúdo da conferência usando o Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="bfcfb-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="bfcfb-131">Se as informações de conferência armazenadas no armazenamento de arquivos de um pool de Front-End se tornam indisponíveis, você deve restaurar essas informações para que os usuários que estão no pool mantenham seus dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="bfcfb-132">Se o pool de Front-End que perdeu dados de conferência estiver emparelhado com outro pool de Front-End, você poderá usar o Serviço de Backup para restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="bfcfb-p105">Você também deve efetuar tal tarefa caso todo um pool falhe e você tenha que executar failover nos usuários para um pool de backup. Quando esses usuários retornarem para o pool original, você deve utilizar este procedimento para copiar o conteúdo de conferência de volta para o pool original.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="bfcfb-135">Presuma que o Pool1 está pareado com Pool2, e os dados de conferência de Pool1 foram perdidos.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="bfcfb-136">Você pode usar o seguinte cmdlet para invocar o Serviço de Backup para restaurar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bfcfb-p107">Restaurar o conteúdo pode levar algum tempo, dependendo do tamanho. Você pode utilizar o seguinte cmdlet para verificar o status do processo:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bfcfb-139">O processo é concluído quando este cmdlet retorna um valor de Estado Estável para o módulo de conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
