---
title: Localização do servidor do Lync Server 2013 em uma implantação do servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7390c3cee8be94f6bead96ff990e380b06011eb7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="e9d62-102">Colocação de servidor em uma implantação de servidor Standard Edition para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9d62-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d62-103">_**Última modificação do tópico:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="e9d62-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="e9d62-104">Esta seção descreve as funções de servidor, os bancos de dados e os compartilhamentos de arquivos que podem ser colocados em uma implantação do servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9d62-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="e9d62-105">Funções do Servidor</span><span class="sxs-lookup"><span data-stu-id="e9d62-105">Server Roles</span></span>

<span data-ttu-id="e9d62-106">No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são colocados no servidor Standard Edition, mas é necessária configuração adicional para habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="e9d62-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="e9d62-107">Você pode optar por implantar o serviço de Mediação em servidores separados.</span><span class="sxs-lookup"><span data-stu-id="e9d62-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="e9d62-108">É possível colocar um servidor de aplicativo confiável com o Servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9d62-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="e9d62-109">As funções do servidor mostradas a seguir devem ser implantadas cada uma em um computador separado:</span><span class="sxs-lookup"><span data-stu-id="e9d62-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="e9d62-110">Be</span><span class="sxs-lookup"><span data-stu-id="e9d62-110">Director</span></span>

  - <span data-ttu-id="e9d62-111">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="e9d62-111">Edge Server</span></span>

  - <span data-ttu-id="e9d62-112">Servidor de mediação (se não colocado com o servidor Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="e9d62-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="e9d62-113">Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e9d62-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="e9d62-114">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="e9d62-114">Databases</span></span>

<span data-ttu-id="e9d62-115">Por padrão, o banco de dados back-end do SQL Server Express está posicionado no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9d62-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="e9d62-116">Você não pode movê-la para um computador separado.</span><span class="sxs-lookup"><span data-stu-id="e9d62-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="e9d62-117">Com uma exceção, não é possível colocar outros bancos de dados no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9d62-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="e9d62-118">Se você optar por implantar o servidor de chat persistente em um servidor Standard Edition, poderá colocar o banco de dados de chat persistente e o banco de dados de conformidade de chat persistente no mesmo servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9d62-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="e9d62-119">Você pode colocar cada um dos seguintes bancos de dados em um único servidor de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="e9d62-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="e9d62-120">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="e9d62-120">Monitoring database</span></span>

  - <span data-ttu-id="e9d62-121">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="e9d62-121">Archiving database</span></span>

  - <span data-ttu-id="e9d62-122">Um banco de dados back-end para um pool de front-ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e9d62-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="e9d62-123">Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância SQL ou usar instâncias SQL separadas para cada um, com as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="e9d62-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="e9d62-124">Cada instância SQL pode conter apenas um único banco de dados back-end (para um pool de front-ends Enterprise Edition), um banco de dados de monitoramento único, um banco de dados de arquivamento único, um banco de dados de chat persistente único e um banco de dados de conformidade de chat</span><span class="sxs-lookup"><span data-stu-id="e9d62-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="e9d62-125">O servidor de banco de dados não pode dar suporte a mais de um pool de front-ends Enterprise Edition, um servidor executando o arquivamento, um servidor executando monitoramento, um banco de dados de chat persistente único e um banco de dados de conformidade de chat persistente único, mas pode suportar um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9d62-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="e9d62-126">É possível colocar um compartilhamento de arquivo com um banco de dados, conforme será descrito ainda nesta seção.</span><span class="sxs-lookup"><span data-stu-id="e9d62-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9d62-127">No Lync Server 2013, você tem a opção de integrar o monitoramento e o armazenamento de arquivamento com o armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e9d62-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="e9d62-128">Você não pode implantar servidores que executam o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9d62-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9d62-129">Embora a colocação de bancos de dados seja suportada, o tamanho dos bancos de dados pode aumentar muito rápido.</span><span class="sxs-lookup"><span data-stu-id="e9d62-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="e9d62-130">Por exemplo, quando você considera colocar o banco de dados de Arquivamento com outros bancos de dados, se estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco exigido pelo banco de dados de Arquivamento poderá aumentar bastante.</span><span class="sxs-lookup"><span data-stu-id="e9d62-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="e9d62-131">Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, banco de dados de chat persistente e banco de dados de conformidade de chat persistente com o banco de dados back-end de um pool corporativo.</span><span class="sxs-lookup"><span data-stu-id="e9d62-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="e9d62-132">Compartilhamentos de arquivos</span><span class="sxs-lookup"><span data-stu-id="e9d62-132">File Shares</span></span>

<span data-ttu-id="e9d62-133">O compartilhamento de arquivo pode ser um servidor separado ou pode ser colocado no mesmo servidor como qualquer um ou todos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9d62-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="e9d62-134">Servidor de banco de dados, incluindo o Servidor Back-End de um pool de Front-Ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e9d62-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="e9d62-135">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="e9d62-135">Archiving database</span></span>

  - <span data-ttu-id="e9d62-136">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="e9d62-136">Monitoring database</span></span>

  - <span data-ttu-id="e9d62-137">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e9d62-137">Persistent Chat database</span></span>

  - <span data-ttu-id="e9d62-138">Banco de dados de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e9d62-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="e9d62-139">Um compartilhamento de arquivo único pode ser usado para múltiplos pools de Front-Ends, servidores Standard Edition (todos no mesmo site).</span><span class="sxs-lookup"><span data-stu-id="e9d62-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9d62-140">No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivos do Lync Server como o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9d62-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="e9d62-141">Outros componentes</span><span class="sxs-lookup"><span data-stu-id="e9d62-141">Other Components</span></span>

<span data-ttu-id="e9d62-142">Não é possível colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9d62-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="e9d62-143">No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9d62-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="e9d62-144">Não é possível colocar nenhum componente do Exchange ou UM componente do SharePoint com nenhuma função do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9d62-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

