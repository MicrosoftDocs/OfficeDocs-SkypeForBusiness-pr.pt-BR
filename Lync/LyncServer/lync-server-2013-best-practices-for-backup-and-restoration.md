---
title: 'Lync Server 2013: práticas recomendadas para backup e restauração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="47388-102">Práticas recomendadas para backup e restauração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47388-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47388-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="47388-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="47388-104">Esta seção inclui dois tipos de práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="47388-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="47388-105">Práticas recomendadas para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="47388-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="47388-106">Práticas recomendadas para minimizar o impacto de um desastre.</span><span class="sxs-lookup"><span data-stu-id="47388-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="47388-107">Práticas recomendadas para backup e restauração</span><span class="sxs-lookup"><span data-stu-id="47388-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="47388-108">Para facilitar o processo de backup e restauração, aplique as seguintes práticas recomendadas ao fazer backup ou restaurar seus dados:</span><span class="sxs-lookup"><span data-stu-id="47388-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="47388-109">Faça backups regulares em intervalos apropriados.</span><span class="sxs-lookup"><span data-stu-id="47388-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="47388-110">O tipo de backup mais simples e mais comumente usado e o cronograma de rotação é um backup noturno completo de todo o banco de dados SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47388-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="47388-111">Em seguida, se a restauração for necessária, o processo de restauração exigirá apenas um backup, e não mais do que os dados do dia deverão ser perdidos.</span><span class="sxs-lookup"><span data-stu-id="47388-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="47388-112">Se você usar cmdlets ou o painel de controle do Lync Server para fazer alterações de configuração, use o cmdlet **Export-CsConfiguration** para fazer um backup de instantâneo do arquivo de configuração de topologia (XDS. MDF) depois de fazer as alterações, para que você não perca as alterações se precisar restaurar seus bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="47388-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="47388-113">Observe que a configuração é feita com o backup em formato XML e compactada como um arquivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="47388-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="47388-114">Verifique se a pasta compartilhada que você planeja usar para fazer backup do Lync Server tem espaço em disco suficiente para armazenar todos os dados de backup.</span><span class="sxs-lookup"><span data-stu-id="47388-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="47388-115">Agende backups quando o uso do Lync Server geralmente está baixo, para melhorar o desempenho do servidor e a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="47388-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="47388-116">Verifique se o local onde você fez backup dos dados é seguro (recomendamos um local remoto).</span><span class="sxs-lookup"><span data-stu-id="47388-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="47388-117">Mantenha os arquivos de backup onde estarão disponíveis, caso você precise restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="47388-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="47388-118">Planeje e agende testes periódicos dos processos de restauração que têm suporte na sua organização.</span><span class="sxs-lookup"><span data-stu-id="47388-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="47388-119">Valide seus processos de backup e restauração com antecedência para garantir que eles funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="47388-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="47388-120">Práticas recomendadas para minimizar o impacto de um desastre</span><span class="sxs-lookup"><span data-stu-id="47388-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="47388-121">A melhor estratégia para lidar com interrupções de serviço desastrosas (causados por eventos não gerenciáveis, como quedas de energia ou falhas súbitas de hardware) é pressupor que elas ocorram e planejar de acordo com isso.</span><span class="sxs-lookup"><span data-stu-id="47388-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="47388-122">Se os serviços do Lync, com um mínimo de interrupções e paralisações, forem críticos para a sua organização, você deve considerar a implementação de pools de front-ends em pares, conforme descrito em [planejamento para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="47388-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="47388-123">Em seguida, se um desses pools tiver um desastre, um administrador poderá trocar os usuários desse pool a serem servidos pelo outro pool, com um mínimo de tempo de inatividade.</span><span class="sxs-lookup"><span data-stu-id="47388-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="47388-124">Os planos de gerenciamento de desastres desenvolvidos como parte da estratégia de backup e restauração devem incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47388-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="47388-125">Manter a mídia do software e as atualizações de software e firmware prontamente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="47388-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="47388-126">Manutenção de registros de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="47388-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="47388-127">Fazer backup de seus dados regularmente e monitorar a integridade dos backups.</span><span class="sxs-lookup"><span data-stu-id="47388-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="47388-128">Treinar seus funcionários em recuperação de desastres, documentar procedimentos e fazer a implementação de buscas de simulação de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="47388-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="47388-129">Manter o hardware de reserva disponível ou, se você tiver um contrato de nível de serviço (SLA), contratar fornecedores e fornecedores de hardware para fazer substituições de solicitações.</span><span class="sxs-lookup"><span data-stu-id="47388-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="47388-130">Separar o local dos arquivos de log de transação (arquivos. ldf) e arquivos de banco de dados (arquivos. MDF).</span><span class="sxs-lookup"><span data-stu-id="47388-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

