---
title: 'Lync Server 2013: Configurando e monitorando o Serviço de Backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="34949-102">Configurando e monitorando o Serviço de Backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34949-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34949-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="34949-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="34949-104">Você pode usar os seguintes comandos do Shell de gerenciamento do Lync Server para configurar e monitorar o serviço de backup.</span><span class="sxs-lookup"><span data-stu-id="34949-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34949-105">O grupo RTCUniversalServerAdmins é o único grupo que tem permissões para executar <STRONG>Get-CsBackupServiceStatus</STRONG> por padrão.</span><span class="sxs-lookup"><span data-stu-id="34949-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="34949-106">Para usar esse cmdlet, faça logon como membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="34949-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="34949-107">Ou você pode conceder acesso a esse comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet <STRONG>set-CsBackupServiceConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="34949-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="34949-108">Para ver a configuração do serviço de backup</span><span class="sxs-lookup"><span data-stu-id="34949-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="34949-109">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="34949-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="34949-110">O padrão para SyncInterval é de dois minutos.</span><span class="sxs-lookup"><span data-stu-id="34949-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="34949-111">Para definir o intervalo de sincronização do serviço de backup</span><span class="sxs-lookup"><span data-stu-id="34949-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="34949-112">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="34949-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="34949-113">Por exemplo, o seguinte define o intervalo como três minutos.</span><span class="sxs-lookup"><span data-stu-id="34949-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="34949-114">Embora você possa usar esse cmdlet para alterar o intervalo de sincronização padrão do serviço de backup, não deve fazê-lo, a menos que seja absolutamente necessário, pois o intervalo de sincronização tem um grande impacto sobre o desempenho do serviço de backup e o RPO (objetivo do ponto de recuperação).</span><span class="sxs-lookup"><span data-stu-id="34949-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="34949-115">Para obter o status do serviço de backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="34949-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="34949-116">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="34949-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="34949-117">O status de sincronização do serviço de backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2).</span><span class="sxs-lookup"><span data-stu-id="34949-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="34949-118">O status de sincronização de P1 a P2 pode ser diferente do do P2 para P1.</span><span class="sxs-lookup"><span data-stu-id="34949-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="34949-119">Para P1 a P2, o serviço de backup está em um estado "estacionário" se todas as alterações feitas em P1 são completamente duplicadas para P2 dentro do intervalo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="34949-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="34949-120">Ele está no estado "final" se não houver mais alterações a serem sincronizadas do P1 ao P2.</span><span class="sxs-lookup"><span data-stu-id="34949-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="34949-121">Os dois Estados indicam um instantâneo do serviço de backup no momento em que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="34949-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="34949-122">Isso não significa que o estado retornado permanecerá como mais tarde.</span><span class="sxs-lookup"><span data-stu-id="34949-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="34949-123">Em particular, o estado "final" continuará a ser suspenso apenas se P1 não gerar nenhuma alteração após a execução do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="34949-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="34949-124">Isso é verdade no caso de falha P1 para P2 após o P1 ser colocado no modo somente leitura como parte da lógica de execução <STRONG>Invoke-CsPoolfailover</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="34949-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="34949-125">Para obter informações sobre a relação de backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="34949-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="34949-126">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="34949-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="34949-127">Para forçar uma sincronização do serviço de backup</span><span class="sxs-lookup"><span data-stu-id="34949-127">To force a Backup Service sync</span></span>

<span data-ttu-id="34949-128">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="34949-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

