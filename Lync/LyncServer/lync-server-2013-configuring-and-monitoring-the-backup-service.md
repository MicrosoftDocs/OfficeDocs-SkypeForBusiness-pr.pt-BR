---
title: 'Lync Server 2013: Configurando e monitorando o serviço de backup'
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
ms.openlocfilehash: b3df8f2208566ed89feda0a06c4cce8f699d130d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517558"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="c0683-102">Configurando e monitorando o serviço de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0683-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0683-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c0683-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c0683-104">Você pode usar os seguintes comandos do Shell de gerenciamento do Lync Server para configurar e monitorar o serviço de backup.</span><span class="sxs-lookup"><span data-stu-id="c0683-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0683-105">O grupo RTCUniversalServerAdmins é o único grupo que possui permissões para executar o <STRONG>Get-CsBackupServiceStatus</STRONG> por padrão.</span><span class="sxs-lookup"><span data-stu-id="c0683-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="c0683-106">Para usar este cmdlet, faça o login como membro deste grupo.</span><span class="sxs-lookup"><span data-stu-id="c0683-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="c0683-107">Em alternativa, é possível conceder acesso a este comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet <STRONG>Set-CsBackupServiceConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c0683-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="c0683-108">Para ver a configuração do Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="c0683-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="c0683-109">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c0683-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="c0683-110">O padrão para SyncInterval é dois minutos.</span><span class="sxs-lookup"><span data-stu-id="c0683-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="c0683-111">Para definir o intervalo de sincronização do Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="c0683-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="c0683-112">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c0683-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="c0683-113">Por exemplo, o seguinte define o intervalo para três minutos.</span><span class="sxs-lookup"><span data-stu-id="c0683-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c0683-114">Embora seja possível usar este cmdlet para alterar o intervalo de sincronização padrão para o Serviço de Backup, você não deve fazer menos do que o absolutamente necessário, pois o intervalo de sincronização possui um grande impacto no desempenho do Serviço de Backup e o objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="c0683-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="c0683-115">Para obter o status do Serviço de Backup para um determinado pool</span><span class="sxs-lookup"><span data-stu-id="c0683-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="c0683-116">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c0683-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="c0683-117">O status de sincronização do Serviço de Backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2).</span><span class="sxs-lookup"><span data-stu-id="c0683-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="c0683-118">O status de sincronização de P1 para P2 pode ser diferente do que de P2 para P1.</span><span class="sxs-lookup"><span data-stu-id="c0683-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="c0683-119">Para P1 para P2, o Serviço de Backup está em estado "pronto" se todas as alterações realizadas em P1 são completamente replicadas para P2 dentro do intervalo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="c0683-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="c0683-120">Está no estado “final” se não há mais mudanças a serem sincronizadas de P1 para P2.</span><span class="sxs-lookup"><span data-stu-id="c0683-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="c0683-121">Ambos os estados indicam um instantâneo do Serviço de Backup no momento que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="c0683-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="c0683-122">Não implica que o estado retornado permanecerá como é posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c0683-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="c0683-123">Em particular, o estado “final” continuará a manter apenas se P1 não gerar qualquer mudança após o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="c0683-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="c0683-124">Isto é verdadeiro em caso de falha de P1 por P2 após P1 ser inserido no modo somente leitura como parte da lógica de execução do <STRONG>Invoke-CsPoolfailover</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c0683-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="c0683-125">Para obter informações sobre a relação de backup de um determinado pool</span><span class="sxs-lookup"><span data-stu-id="c0683-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="c0683-126">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c0683-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="c0683-127">Para forçar uma sincronização do Serviço de Backup</span><span class="sxs-lookup"><span data-stu-id="c0683-127">To force a Backup Service sync</span></span>

<span data-ttu-id="c0683-128">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c0683-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

