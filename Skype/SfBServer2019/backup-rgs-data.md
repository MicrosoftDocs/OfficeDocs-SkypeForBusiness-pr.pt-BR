---
title: Backup de dados do serviço de grupo de resposta (RGS) no Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Saiba como fazer backup de dados do serviço de grupo de resposta (RGS) no Skype for Business Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824065"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="e377d-103">Fazer backup de dados do serviço de grupo de resposta (RGS)</span><span class="sxs-lookup"><span data-stu-id="e377d-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="e377d-104">Com o Skype for Business Server 2019 atualização cumulativa de julho, incluímos a capacidade de incluir RGS dados como parte do backup padrão.</span><span class="sxs-lookup"><span data-stu-id="e377d-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="e377d-105">A replicação de dados do RGS</span><span class="sxs-lookup"><span data-stu-id="e377d-105">RGS data replication</span></span>

<span data-ttu-id="e377d-106">Para experimentar a funcionalidade de replicação de dados do RGS, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="e377d-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="e377d-107">Instale a atualização cumulativa de julho em todas as front-ends (FEs) do seu pool emparelhado.</span><span class="sxs-lookup"><span data-stu-id="e377d-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="e377d-108">Instale o banco de dados do RGS em ambos os membros do pool emparelhado:</span><span class="sxs-lookup"><span data-stu-id="e377d-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="e377d-109">Execute o cmdlet a seguir nos dois pools para replicar os dados existentes do RGS para as tabelas de backup, de modo que os dados possam ser retirados por RGSBackupService:</span><span class="sxs-lookup"><span data-stu-id="e377d-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="e377d-110">Habilite o RGSBackupService (isso permitirá que o RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="e377d-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="e377d-111">Se esse parâmetro for definido como true, o RGSBackupService começará a sincronizar os dados do RGS em pools emparelhados (os dois pools precisam ser CU1).</span><span class="sxs-lookup"><span data-stu-id="e377d-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="e377d-112">Aguarde alguns minutos para começar.</span><span class="sxs-lookup"><span data-stu-id="e377d-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="e377d-113">Inicialmente, RGS BackupService status será não inicializado.):</span><span class="sxs-lookup"><span data-stu-id="e377d-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="e377d-114">Para verificar o BackupServiceStatus:</span><span class="sxs-lookup"><span data-stu-id="e377d-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="e377d-115">Para verificar a replicação de dados entre pools, use esses cmdlets (estes cmdlets mostram somente dados do pool proprietário):</span><span class="sxs-lookup"><span data-stu-id="e377d-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="e377d-116">Para verificar os dados do pool de proprietários RGS e seus dados de backup:</span><span class="sxs-lookup"><span data-stu-id="e377d-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="e377d-117">Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e377d-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="e377d-118">Failover do pool de proprietários do RGS.</span><span class="sxs-lookup"><span data-stu-id="e377d-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="e377d-119">Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e377d-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="e377d-120">Failback do pool.</span><span class="sxs-lookup"><span data-stu-id="e377d-120">Failback the pool.</span></span>
1. <span data-ttu-id="e377d-121">Atualize RGS dados no pool de origem e execute outro failover para verificar se as alterações se refletem no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="e377d-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="e377d-122">RGS deve se comportar da mesma forma que era feita antes do failover.</span><span class="sxs-lookup"><span data-stu-id="e377d-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="e377d-123">É recomendável executar essas etapas em uma grande quantidade de dados e fazer failover e failbacks frequentes.</span><span class="sxs-lookup"><span data-stu-id="e377d-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="e377d-124">Qualquer novo RGS criado após essa atualização de RECOR também deve ser replicado.</span><span class="sxs-lookup"><span data-stu-id="e377d-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="e377d-125">Cmdlets RGS</span><span class="sxs-lookup"><span data-stu-id="e377d-125">RGS cmdlets</span></span>

- <span data-ttu-id="e377d-126">Para verificar BackupServiceStatus (o status de exportação deve estar no estado final ou Steady.</span><span class="sxs-lookup"><span data-stu-id="e377d-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="e377d-127">O status da importação deve estar no estado normal.</span><span class="sxs-lookup"><span data-stu-id="e377d-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="e377d-128">RGSBackupservice deve ser habilitado.):</span><span class="sxs-lookup"><span data-stu-id="e377d-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="e377d-129">Para sincronizar completamente os dados do pool de backup (isso sincronizará os dados completos do RGS no pool de backup.):</span><span class="sxs-lookup"><span data-stu-id="e377d-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="e377d-130">Para sincronizar completamente o repositório do RGS no pool de backup (isso irá sincronizar os dados completos dos RGS no pool de backup.):</span><span class="sxs-lookup"><span data-stu-id="e377d-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="e377d-131">Para sincronizar os dados Delta do RGS no pool de backup (isso sincronizará os dados Delta no pool de backup somente para RGS.):</span><span class="sxs-lookup"><span data-stu-id="e377d-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="e377d-132">Para sincronizar todos os dados do módulo, incluindo RGS:</span><span class="sxs-lookup"><span data-stu-id="e377d-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="e377d-133">Para desabilitar o RGSBackupService (isso irá desabilitar o RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="e377d-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="e377d-134">Se esse parâmetro for definido como true, o RGSBackupService será desabilitado em todos os pools emparelhados.):</span><span class="sxs-lookup"><span data-stu-id="e377d-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
