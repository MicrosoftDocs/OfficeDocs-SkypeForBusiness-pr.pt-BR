---
title: 'Lync Server 2013: visão geral do processo de backup e restauração'
description: 'Lync Server 2013: visão geral do processo de backup e restauração.'
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
ms.openlocfilehash: 77b833a05021d3a848e9de1ee8768f7daa194c6a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563167"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="51181-103">Visão geral do processo de backup e restauração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51181-103">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51181-104">_**Última modificação do tópico:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="51181-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="51181-105">Esta seção fornece uma visão geral de como o processo de backup e restauração funciona para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51181-105">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="51181-106">Você usa o mesmo processo para todos os servidores Standard Edition e servidores Enterprise Edition, independentemente do local.</span><span class="sxs-lookup"><span data-stu-id="51181-106">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="51181-107">Em geral, o processo de backup funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="51181-107">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="51181-108">Você cria um local de backup como uma pasta compartilhada em um computador autônomo que não faz parte de nenhum pool.</span><span class="sxs-lookup"><span data-stu-id="51181-108">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="51181-109">O local do backup é referenciado no **$backup**.</span><span class="sxs-lookup"><span data-stu-id="51181-109">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="51181-110">Em uma base normal e agendada, você faz o backup de todos os bancos de dados do Lync Server e de todos os repositórios de arquivos descritos nos [requisitos de backup e restauração no Lync server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) , seguindo os procedimentos descritos em [backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) o repositório de gerenciamento central inclui todas as configurações e configurações do servidor.</span><span class="sxs-lookup"><span data-stu-id="51181-110">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="51181-111">Cada vez que você executar um backup subsequente, crie uma nova pasta compartilhada e altere o caminho que **$backup** referências.</span><span class="sxs-lookup"><span data-stu-id="51181-111">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="51181-112">Em geral, o processo de restauração funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="51181-112">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="51181-113">Quando ocorre uma falha ou uma interrupção, você restaura os dados no local referenciado por **$backup** para computadores novos ou limpos.</span><span class="sxs-lookup"><span data-stu-id="51181-113">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="51181-114">Esse processo de restauração não restaura dados em um estado de servidor existente.</span><span class="sxs-lookup"><span data-stu-id="51181-114">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="51181-115">Ou seja, esse processo requer que o servidor seja limpo ou novo.</span><span class="sxs-lookup"><span data-stu-id="51181-115">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="51181-116">Para permitir que suas informações de usuário e conferência sejam recuperáveis para o ponto de falha, você pode implementar uma topologia de recuperação de desastre com pools de front-ends emparelhados, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="51181-116">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="51181-117">Toda configuração de sistema de nomes de domínio (DNS), configuração de protocolo de configuração dinâmica de host (DHCP), nomes de domínio, nomes de domínio totalmente qualificados (FQDNs) do computador, caminhos de repositório de arquivos e assim por diante deve ser o mesmo no momento da restauração que estavam no momento do backup.</span><span class="sxs-lookup"><span data-stu-id="51181-117">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="51181-118">Se um servidor que executa o Lync Server falhar, a recuperação inclui as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="51181-118">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="51181-119">Instale o sistema operacional em um computador novo ou limpo com o mesmo FQDN que o computador com falha.</span><span class="sxs-lookup"><span data-stu-id="51181-119">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="51181-120">Reinstale os certificados.</span><span class="sxs-lookup"><span data-stu-id="51181-120">Reinstall certificates.</span></span>

  - <span data-ttu-id="51181-121">Se o servidor hospedar um banco de dados, instale o Microsoft SQL Server 2012 ou o Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="51181-121">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="51181-122">Em geral, se o servidor hospedar um banco de dados, execute o construtor de topologias para criar e instalar o banco de dados e configurar as listas de controle de acesso (ACLs).</span><span class="sxs-lookup"><span data-stu-id="51181-122">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="51181-123">Em geral, se o servidor hospedar uma função de servidor, execute a etapa 1 até a etapa 4 do assistente de implantação do Lync Server para instalar os arquivos de configuração local, instalar os componentes da função de servidor, atribuir certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="51181-123">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="51181-124">Se o servidor hospedado por um banco de dados colocado com a função de servidor, a execução da etapa 2 do assistente de implantação do Lync Server recriará o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="51181-124">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="51181-125">Se o servidor hospedar um banco de dados, restaure os dados de backup.</span><span class="sxs-lookup"><span data-stu-id="51181-125">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

