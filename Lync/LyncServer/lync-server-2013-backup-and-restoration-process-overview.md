---
title: 'Lync Server 2013: visão geral do processo de backup e restauração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd6efce509283d59c5cecc7325c35c9cf1ab371e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="424d9-102">Visão geral do processo de backup e restauração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="424d9-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="424d9-103">_**Última modificação do tópico:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="424d9-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="424d9-104">Esta seção fornece uma visão geral de como o processo de backup e restauração funciona para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="424d9-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="424d9-105">Você usa o mesmo processo para todos os servidores Standard Edition e servidores Enterprise Edition, independentemente do local.</span><span class="sxs-lookup"><span data-stu-id="424d9-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="424d9-106">Em geral, o processo de backup funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="424d9-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="424d9-107">Você cria um local de backup como uma pasta compartilhada em um computador autônomo que não faz parte de nenhum pool.</span><span class="sxs-lookup"><span data-stu-id="424d9-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="424d9-108">O local do backup é referenciado no **$backup**.</span><span class="sxs-lookup"><span data-stu-id="424d9-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="424d9-109">Em uma base normal e agendada, você faz o backup de todos os bancos de dados do Lync Server e de todos os repositórios de arquivos descritos nos [requisitos de backup e restauração no Lync server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) , seguindo os procedimentos descritos em [backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) o repositório de gerenciamento central inclui todas as configurações e configurações do servidor.</span><span class="sxs-lookup"><span data-stu-id="424d9-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="424d9-110">Cada vez que você executar um backup subsequente, crie uma nova pasta compartilhada e altere o caminho que **$backup** referências.</span><span class="sxs-lookup"><span data-stu-id="424d9-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="424d9-111">Em geral, o processo de restauração funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="424d9-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="424d9-112">Quando ocorre uma falha ou uma interrupção, você restaura os dados no local referenciado por **$backup** para computadores novos ou limpos.</span><span class="sxs-lookup"><span data-stu-id="424d9-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="424d9-113">Esse processo de restauração não restaura dados em um estado de servidor existente.</span><span class="sxs-lookup"><span data-stu-id="424d9-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="424d9-114">Ou seja, esse processo requer que o servidor seja limpo ou novo.</span><span class="sxs-lookup"><span data-stu-id="424d9-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="424d9-115">Para permitir que suas informações de usuário e conferência sejam recuperáveis para o ponto de falha, você pode implementar uma topologia de recuperação de desastre com pools de front-ends emparelhados, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="424d9-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="424d9-116">Toda configuração de sistema de nomes de domínio (DNS), configuração de protocolo de configuração dinâmica de host (DHCP), nomes de domínio, nomes de domínio totalmente qualificados (FQDNs) do computador, caminhos de repositório de arquivos e assim por diante deve ser o mesmo no momento da restauração que estavam no momento da backup.</span><span class="sxs-lookup"><span data-stu-id="424d9-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="424d9-117">Se um servidor que executa o Lync Server falhar, a recuperação inclui as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="424d9-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="424d9-118">Instale o sistema operacional em um computador novo ou limpo com o mesmo FQDN que o computador com falha.</span><span class="sxs-lookup"><span data-stu-id="424d9-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="424d9-119">Reinstale os certificados.</span><span class="sxs-lookup"><span data-stu-id="424d9-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="424d9-120">Se o servidor hospedar um banco de dados, instale o Microsoft SQL Server 2012 ou o Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="424d9-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="424d9-121">Em geral, se o servidor hospedar um banco de dados, execute o construtor de topologias para criar e instalar o banco de dados e configurar as listas de controle de acesso (ACLs).</span><span class="sxs-lookup"><span data-stu-id="424d9-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="424d9-122">Em geral, se o servidor hospedar uma função de servidor, execute a etapa 1 até a etapa 4 do assistente de implantação do Lync Server para instalar os arquivos de configuração local, instalar os componentes da função de servidor, atribuir certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="424d9-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="424d9-123">Se o servidor hospedado por um banco de dados colocado com a função de servidor, a execução da etapa 2 do assistente de implantação do Lync Server recriará o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="424d9-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="424d9-124">Se o servidor hospedar um banco de dados, restaure os dados de backup.</span><span class="sxs-lookup"><span data-stu-id="424d9-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

