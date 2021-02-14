---
title: Fazer o back up de dados de RGS (Serviço de Grupo de Resposta) no Skype for Business Server 2019
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
description: Saiba como fazer o back up de dados RGS (Serviço de Grupo de Resposta) no Skype for Business Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824065"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="eb841-103">Fazer o back up de dados do Serviço de Grupo de Resposta (RGS)</span><span class="sxs-lookup"><span data-stu-id="eb841-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="eb841-104">Com a atualização cumulativa de julho de 2019 do Skype for Business Server, incluímos a capacidade de incluir dados RGS como parte do backup padrão.</span><span class="sxs-lookup"><span data-stu-id="eb841-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="eb841-105">Replicação de dados RGS</span><span class="sxs-lookup"><span data-stu-id="eb841-105">RGS data replication</span></span>

<span data-ttu-id="eb841-106">Para experimentar a funcionalidade de replicação de dados RGS, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="eb841-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="eb841-107">Instale a atualização cumulativa de julho em todos os front-ends (FEs) do seu pool emparelhado.</span><span class="sxs-lookup"><span data-stu-id="eb841-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="eb841-108">Instale o banco de dados RGS em ambos os membros do pool emparelhado:</span><span class="sxs-lookup"><span data-stu-id="eb841-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="eb841-109">Execute o seguinte cmdlet em ambos os pools para replicar dados RGS existentes para as tabelas de backup para que os dados possam ser coletados pelo RGSBackupService:</span><span class="sxs-lookup"><span data-stu-id="eb841-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="eb841-110">Habilitar RGSBackupService (isso habilita o RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="eb841-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="eb841-111">Se esse parâmetro for definido como true, o RGSBackupService começará a sincronizar dados RGS em pools emparelhados (ambos os pools precisam ser CU1).</span><span class="sxs-lookup"><span data-stu-id="eb841-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="eb841-112">Aguarde alguns minutos para começar.</span><span class="sxs-lookup"><span data-stu-id="eb841-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="eb841-113">Inicialmente, o status do RGS BackupService será NotInitialized.):</span><span class="sxs-lookup"><span data-stu-id="eb841-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="eb841-114">Para verificar BackupServiceStatus:</span><span class="sxs-lookup"><span data-stu-id="eb841-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="eb841-115">Para verificar DataReplication entre pools, use esses cmdlets (esses cmdlets mostram apenas os dados do pool do proprietário):</span><span class="sxs-lookup"><span data-stu-id="eb841-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="eb841-116">Para verificar os dados RGS do pool do Proprietário e seus dados de backup:</span><span class="sxs-lookup"><span data-stu-id="eb841-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="eb841-117">Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o Fluxo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="eb841-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="eb841-118">Failover do seu pool de Proprietários RGS.</span><span class="sxs-lookup"><span data-stu-id="eb841-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="eb841-119">Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o Fluxo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="eb841-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="eb841-120">Failback do pool.</span><span class="sxs-lookup"><span data-stu-id="eb841-120">Failback the pool.</span></span>
1. <span data-ttu-id="eb841-121">Atualize os dados RGS no pool de origem e execute outro failover para verificar se as alterações são refletidas no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="eb841-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="eb841-122">O RGS deve se comportar da mesma forma que estava se comportando antes do failover.</span><span class="sxs-lookup"><span data-stu-id="eb841-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="eb841-123">É recomendável que você execute essas etapas em uma grande parte dos dados e faça failover e failbacks frequentes.</span><span class="sxs-lookup"><span data-stu-id="eb841-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="eb841-124">Qualquer novo RGS criado após essa atualização cu também deve ser replicado.</span><span class="sxs-lookup"><span data-stu-id="eb841-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="eb841-125">Cmdlets RGS</span><span class="sxs-lookup"><span data-stu-id="eb841-125">RGS cmdlets</span></span>

- <span data-ttu-id="eb841-126">Para verificar BackupServiceStatus (o status de exportação deve estar no estado Final ou Estável.</span><span class="sxs-lookup"><span data-stu-id="eb841-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="eb841-127">O status de importação deve estar no estado Normal.</span><span class="sxs-lookup"><span data-stu-id="eb841-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="eb841-128">RGSBackupservice deve estar habilitado.):</span><span class="sxs-lookup"><span data-stu-id="eb841-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="eb841-129">Para sincronizar totalmente os dados RGS no pool de backup (isso sincroniza os dados RGS completos no pool de backup).):</span><span class="sxs-lookup"><span data-stu-id="eb841-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="eb841-130">Para sincronizar totalmente o repositório de arquivos RGS no pool de backup (isso sincroniza os dados RGS completos no pool de backup).):</span><span class="sxs-lookup"><span data-stu-id="eb841-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="eb841-131">Para sincronizar dados delta RGS no pool de backup (isso sincroniza os dados delta no pool de backup somente para RGS).):</span><span class="sxs-lookup"><span data-stu-id="eb841-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="eb841-132">Para sincronizar todos os dados do módulo, incluindo RGS:</span><span class="sxs-lookup"><span data-stu-id="eb841-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="eb841-133">Para desabilitar o RGSBackupService (isso desabilitará globalmente o RGSBackupService.</span><span class="sxs-lookup"><span data-stu-id="eb841-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="eb841-134">Se esse parâmetro for definido como true , RGSBackupService será desabilitado em todos os pools emparelhados.):</span><span class="sxs-lookup"><span data-stu-id="eb841-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
