---
title: 'Lync Server 2013: componentes e topologias para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec153b237df086f3622acc70c104bddc64fef28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502608"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="09f21-102">Componentes e topologias para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09f21-102">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09f21-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="09f21-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="09f21-104">Se você deseja arquivar o conteúdo de IM e conferência do Lync Server 2013, é possível implementar o arquivamento no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09f21-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="09f21-105">Componentes de arquivamento</span><span class="sxs-lookup"><span data-stu-id="09f21-105">Archiving Components</span></span>

<span data-ttu-id="09f21-106">O recurso de arquivamento inclui os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="09f21-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="09f21-p101">**Operadores de arquivamento**. Os operadores de arquivamento (também conhecido como operadores de coleta de dados unificados) são instalados e ativados automaticamente em cada pool de Front-Ends e servidor Standard Edition. Embora os operadores de arquivamento sejam ativados automaticamente, nenhuma mensagem será realmente capturada até o arquivamento ser habilitado e configurado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="09f21-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="09f21-110">**Armazenamento de dados de arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="09f21-110">**Archiving data storage**.</span></span> <span data-ttu-id="09f21-111">O armazenamento de dados do Lync Server 2013 pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="09f21-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="09f21-112">Armazenamento 2013 do Exchange.</span><span class="sxs-lookup"><span data-stu-id="09f21-112">Exchange 2013 storage.</span></span> <span data-ttu-id="09f21-113">Se você habilitar a opção de integração do Microsoft Exchange, as caixas de correio do usuário hospedadas no servidor Exchange 2013 usam o armazenamento do Exchange 2013 para dados arquivados, mas somente se as caixas de correio foram colocadas em In-Place.</span><span class="sxs-lookup"><span data-stu-id="09f21-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="09f21-114">Armazenamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09f21-114">SQL Server storage.</span></span> <span data-ttu-id="09f21-115">Se você tiver usuários na sua implantação hospedados no Lync Server 2013, poderá configurar bancos de dados de arquivamento que executam uma versão com suporte do SQL Server para habilitar o arquivamento para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="09f21-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="09f21-116">O arquivamento também requer armazenamento de arquivos, mas o arquivamento utiliza o mesmo armazenamento de arquivos como servidores Front-End ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="09f21-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="09f21-117">Para obter uma lista de requisitos de hardware e software para arquivamento, consulte [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md) e [suporte a infraestrutura e software do servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="09f21-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="09f21-118">Topologias suportadas</span><span class="sxs-lookup"><span data-stu-id="09f21-118">Supported Topologies</span></span>

<span data-ttu-id="09f21-119">Você implanta o arquivamento em cada pool que possui usuários que requerem suporte ao arquivamento.</span><span class="sxs-lookup"><span data-stu-id="09f21-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="09f21-120">O arquivamento é executado em servidores front-end em pools do Enterprise Edition e em servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="09f21-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="09f21-121">O armazenamento de dados de arquivamento pode ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09f21-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="09f21-122">Integrado ao armazenamento do Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="09f21-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="09f21-123">Implantado usando bancos de dados do SQL Server separados</span><span class="sxs-lookup"><span data-stu-id="09f21-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="09f21-124">Se sua implantação do Exchange 2013 não inclui todos os usuários em sua implantação do Lync Server, você deve usar a integração do Microsoft Exchange para os usuários cujas caixas de correio estão em casa nos servidores do Exchange 2013 e você deve implantar bancos de dados do SQL Server separados para todos os outros usuários do Lync usarem para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="09f21-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="09f21-125">Colocação suportada</span><span class="sxs-lookup"><span data-stu-id="09f21-125">Supported Collocation</span></span>

<span data-ttu-id="09f21-126">O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, permitindo que você tenha flexibilidade para salvar os custos de hardware executando vários componentes em um servidor (se você tiver uma organização pequena) ou para executar componentes individuais em servidores diferentes (se você tiver uma organização maior que precise de escalabilidade e desempenho).</span><span class="sxs-lookup"><span data-stu-id="09f21-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="09f21-127">Os fatores de escalabilidade certamente devem ser considerados antes de você decidir se quer colocar componentes.</span><span class="sxs-lookup"><span data-stu-id="09f21-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="09f21-128">O arquivamento é implantado nos servidores front-end de um pool ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="09f21-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="09f21-129">Para obter detalhes sobre os componentes que podem ser colocados no local, consulte [suporte à colocação de servidor no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="09f21-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="09f21-130">Se você usar bancos de dados separados do SQL Server para arquivamento, em vez de ou além de integrar o armazenamento com o armazenamento do Exchange 2013, poderá colocar o banco de dados de arquivamento com qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="09f21-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="09f21-131">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="09f21-131">Monitoring database</span></span>

  - <span data-ttu-id="09f21-132">Banco de dados back-end de um pool de Front-Ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="09f21-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09f21-p108">O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="09f21-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="09f21-136">Se você colocar o banco de dados de arquivamento com o banco de dados de monitoramento, banco de dados back-end ou ambos, é possível utilizar uma instância SQL exclusiva para qualquer ou todos os bancos de dados ou uma instância SQL separada para cada banco de dados, com a seguinte limitação:</span><span class="sxs-lookup"><span data-stu-id="09f21-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="09f21-137">Cada instância SQL pode conter somente um banco de dados back-end exclusivo, um banco de dados de monitoramento exclusivo e um banco de dados de arquivamento exclusivo.</span><span class="sxs-lookup"><span data-stu-id="09f21-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="09f21-138">Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [supported Server Coexistence no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="09f21-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

