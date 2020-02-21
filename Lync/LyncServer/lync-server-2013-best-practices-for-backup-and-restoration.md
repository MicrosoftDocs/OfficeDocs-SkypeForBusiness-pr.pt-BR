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
ms.openlocfilehash: 30dd3345545ae8c77c4ebfcece7154e91059f9aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="d9930-102">Práticas recomendadas para backup e restauração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9930-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9930-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d9930-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d9930-104">Esta seção inclui dois tipos de melhores práticas:</span><span class="sxs-lookup"><span data-stu-id="d9930-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="d9930-105">Práticas recomendadas para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="d9930-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="d9930-106">Práticas recomendadas para minimizar o impacto de um desastre.</span><span class="sxs-lookup"><span data-stu-id="d9930-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="d9930-107">Melhores práticas para backup e restauração</span><span class="sxs-lookup"><span data-stu-id="d9930-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="d9930-108">Para facilitar o processo de backup e restauração, aplique as seguintes práticas recomendadas ao fazer backup ou restaurar seus dados:</span><span class="sxs-lookup"><span data-stu-id="d9930-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="d9930-109">Execute backups regulares a intervalos adequados.</span><span class="sxs-lookup"><span data-stu-id="d9930-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="d9930-110">O tipo de backup e agendamento rotativo mais simples e mais comumente usado é o backup noturno completo de todo o banco de dados SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d9930-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="d9930-111">Em seguida, se a restauração for necessária, o processo de restauração exigirá apenas um backup, e não mais do que os dados de um dia devem ser perdidos.</span><span class="sxs-lookup"><span data-stu-id="d9930-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="d9930-112">Se você usar cmdlets ou o painel de controle do Lync Server para fazer alterações de configuração, use o cmdlet **Export-CsConfiguration** para fazer um backup de instantâneo do arquivo de configuração de topologia (XDS. MDF) após fazer as alterações, para que você não perca as alterações se precisar restaurar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d9930-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="d9930-113">Observe que essa configuração é submetida a backup no formato XML e compactada como um arquivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="d9930-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="d9930-114">Certifique-se de que a pasta compartilhada que você planeja usar para fazer backup do Lync Server tem espaço em disco suficiente para armazenar todos os dados de backup.</span><span class="sxs-lookup"><span data-stu-id="d9930-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="d9930-115">Agendar backups quando o uso do Lync Server costuma ser baixo, para melhorar o desempenho do servidor e a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="d9930-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="d9930-116">Certifique-se de que o local onde você faz backup dos dados é seguro (recomendamos um local remoto).</span><span class="sxs-lookup"><span data-stu-id="d9930-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="d9930-117">Mantenha os arquivos de backup onde eles estarão disponíveis, caso você precise restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="d9930-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="d9930-118">Planejar e agendar testes periódicos dos processos de restauração suportados pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9930-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="d9930-119">Valide seus processos de backup e restauração com antecedência para garantir que eles funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="d9930-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="d9930-120">Melhores práticas para minimizar o impacto de um desastre</span><span class="sxs-lookup"><span data-stu-id="d9930-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="d9930-121">A melhor estratégia para lidar com interrupções de serviço desastrosas (causadas por eventos não gerenciáveis, como quedas de energia ou falhas repentinas de hardware) é supor que eles ocorram e planejar de acordo.</span><span class="sxs-lookup"><span data-stu-id="d9930-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="d9930-122">Se os serviços do Lync, com um mínimo de interrupções e paralisações, forem críticos para os negócios de sua organização, você deverá considerar a implementação de pools de front-end em pares, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d9930-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="d9930-123">Em seguida, se um desses pools tiver um desastre, um administrador pode mudar os usuários desse pool para serem servidos pelo outro pool, com um mínimo de tempo de inatividade.</span><span class="sxs-lookup"><span data-stu-id="d9930-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="d9930-124">Os planos de gerenciamento de desastres desenvolvidas como parte da estratégia de backup e restauração devem incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9930-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="d9930-125">Manter a mídia de software e as atualizações de software e firmware prontamente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d9930-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="d9930-126">Manter registros de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="d9930-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="d9930-127">Fazer o backup de seus dados regularmente e monitorar a integridade dos backups.</span><span class="sxs-lookup"><span data-stu-id="d9930-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="d9930-128">Treinar sua equipe em recuperação de desastres, procedimentos de documentação e implementar exercícios de simulação de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="d9930-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="d9930-129">Manter o hardware de reserva disponível ou, se você tiver um contrato de nível de serviço (SLA), contratando com fornecedores de hardware e fornecedores para substituição de prompts.</span><span class="sxs-lookup"><span data-stu-id="d9930-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="d9930-130">Separar a localização dos seus arquivos de log de transações (arquivos .ldf) e arquivos de banco de dados (arquivos .mdf).</span><span class="sxs-lookup"><span data-stu-id="d9930-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

