---
title: Localização do servidor do Lync Server 2013 em uma implantação do servidor Standard Edition
description: Lync Server 2013 colocação de servidor em uma implantação de servidor Standard Edition.
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
ms.openlocfilehash: af44761d36c472de1a3da5cd3b3938dc1a130836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555107"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="c0778-103">Colocação de servidor em uma implantação de servidor Standard Edition para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0778-103">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0778-104">_**Última modificação do tópico:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="c0778-104">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="c0778-105">Esta seção descreve as funções de servidor, os bancos de dados e os compartilhamentos de arquivos que podem ser colocados em uma implantação do servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0778-105">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="c0778-106">Funções do Servidor</span><span class="sxs-lookup"><span data-stu-id="c0778-106">Server Roles</span></span>

<span data-ttu-id="c0778-107">No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são colocados no servidor Standard Edition, mas é necessária configuração adicional para habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="c0778-107">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="c0778-108">Você pode optar por implantar o serviço de Mediação em servidores separados.</span><span class="sxs-lookup"><span data-stu-id="c0778-108">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="c0778-109">É possível colocar um servidor de aplicativo confiável com o Servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0778-109">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="c0778-110">As funções do servidor mostradas a seguir devem ser implantadas cada uma em um computador separado:</span><span class="sxs-lookup"><span data-stu-id="c0778-110">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="c0778-111">Diretor</span><span class="sxs-lookup"><span data-stu-id="c0778-111">Director</span></span>

  - <span data-ttu-id="c0778-112">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="c0778-112">Edge Server</span></span>

  - <span data-ttu-id="c0778-113">Servidor de mediação (se não colocado com o servidor Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="c0778-113">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="c0778-114">Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c0778-114">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="c0778-115">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="c0778-115">Databases</span></span>

<span data-ttu-id="c0778-116">Por padrão, o banco de dados back-end do SQL Server Express está posicionado no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0778-116">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="c0778-117">Você não pode movê-la para um computador separado.</span><span class="sxs-lookup"><span data-stu-id="c0778-117">You cannot move it to a separate computer.</span></span> <span data-ttu-id="c0778-118">Com uma exceção, não é possível colocar outros bancos de dados no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0778-118">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="c0778-119">Se você optar por implantar o servidor de chat persistente em um servidor Standard Edition, poderá colocar o banco de dados de chat persistente e o banco de dados de conformidade de chat persistente no mesmo servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0778-119">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="c0778-120">Você pode colocar cada um dos seguintes bancos de dados em um único servidor de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="c0778-120">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="c0778-121">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="c0778-121">Monitoring database</span></span>

  - <span data-ttu-id="c0778-122">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="c0778-122">Archiving database</span></span>

  - <span data-ttu-id="c0778-123">Um banco de dados back-end para um pool de front-ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c0778-123">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="c0778-124">Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância SQL ou usar instâncias SQL separadas para cada um, com as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="c0778-124">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="c0778-125">Cada instância SQL pode conter apenas um único banco de dados back-end (para um pool de front-ends Enterprise Edition), um banco de dados de monitoramento único, um banco de dados de arquivamento único, um banco de dados de chat persistente único e um banco de dados de conformidade de chat</span><span class="sxs-lookup"><span data-stu-id="c0778-125">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="c0778-126">O servidor de banco de dados não pode suportar mais de um pool de front-ends Enterprise Edition, um servidor executando o arquivamento, um servidor executando monitoramento, um banco de dados de chat persistente único e um banco de dados de conformidade de chat persistente único, mas pode suportar um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c0778-126">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="c0778-127">É possível colocar um compartilhamento de arquivo com um banco de dados, conforme será descrito ainda nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c0778-127">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0778-128">No Lync Server 2013, você tem a opção de integrar o monitoramento e o armazenamento de arquivamento com o armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c0778-128">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="c0778-129">Você não pode implantar servidores que executam o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c0778-129">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c0778-130">Embora a colocação de bancos de dados seja suportada, o tamanho dos bancos de dados pode aumentar muito rápido.</span><span class="sxs-lookup"><span data-stu-id="c0778-130">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="c0778-131">Por exemplo, quando você considera colocar o banco de dados de Arquivamento com outros bancos de dados, se estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco exigido pelo banco de dados de Arquivamento poderá aumentar bastante.</span><span class="sxs-lookup"><span data-stu-id="c0778-131">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="c0778-132">Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, banco de dados de chat persistente e banco de dados de conformidade de chat persistente com o banco de dados back-end de um pool corporativo.</span><span class="sxs-lookup"><span data-stu-id="c0778-132">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="c0778-133">Compartilhamentos de arquivos</span><span class="sxs-lookup"><span data-stu-id="c0778-133">File Shares</span></span>

<span data-ttu-id="c0778-134">O compartilhamento de arquivo pode ser um servidor separado ou pode ser colocado no mesmo servidor como qualquer um ou todos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0778-134">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="c0778-135">Servidor de banco de dados, incluindo o Servidor Back-End de um pool de Front-Ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c0778-135">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="c0778-136">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="c0778-136">Archiving database</span></span>

  - <span data-ttu-id="c0778-137">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="c0778-137">Monitoring database</span></span>

  - <span data-ttu-id="c0778-138">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="c0778-138">Persistent Chat database</span></span>

  - <span data-ttu-id="c0778-139">Banco de dados de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="c0778-139">Persistent Chat compliance database</span></span>

<span data-ttu-id="c0778-140">Um compartilhamento de arquivo único pode ser usado para múltiplos pools de Front-Ends, servidores Standard Edition (todos no mesmo site).</span><span class="sxs-lookup"><span data-stu-id="c0778-140">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0778-141">No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivos do Lync Server como o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0778-141">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="c0778-142">Outros componentes</span><span class="sxs-lookup"><span data-stu-id="c0778-142">Other Components</span></span>

<span data-ttu-id="c0778-143">Não é possível colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0778-143">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="c0778-144">No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c0778-144">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="c0778-145">Não é possível colocar nenhum componente do Exchange ou UM componente do SharePoint com nenhuma função do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0778-145">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

