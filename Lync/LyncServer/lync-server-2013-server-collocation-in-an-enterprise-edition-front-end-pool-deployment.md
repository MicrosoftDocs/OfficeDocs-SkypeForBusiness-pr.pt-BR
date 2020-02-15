---
title: Lync Server 2013 colocação de servidor em uma implantação de pool de front-ends Enterprise Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74afcdd9212ebced9d93f0f699b90dd7a89edefd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="f9898-102">Colocação de servidor em uma implantação de pool de front-ends Enterprise Edition para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9898-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9898-103">_**Última modificação do tópico:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="f9898-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="f9898-104">Esta seção descreve as funções de servidor, os bancos de dados e os compartilhamentos de arquivos que podem ser colocados em uma implantação de pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9898-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="f9898-105">Funções do Servidor</span><span class="sxs-lookup"><span data-stu-id="f9898-105">Server Roles</span></span>

<span data-ttu-id="f9898-106">No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são colocados no servidor front-end, mas é necessária configuração adicional para habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="f9898-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="f9898-107">Se você não os posicionar no Servidor de Mediação com o Servidor Front-End, poderá implantá-lo como um Servidor de Mediação autônomo em um computador separado.</span><span class="sxs-lookup"><span data-stu-id="f9898-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="f9898-108">É possível colocar um servidor de aplicativo confiável com o Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="f9898-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="f9898-109">As funções do servidor mostradas a seguir devem ser implantadas cada uma em um computador separado:</span><span class="sxs-lookup"><span data-stu-id="f9898-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="f9898-110">Be</span><span class="sxs-lookup"><span data-stu-id="f9898-110">Director</span></span>

  - <span data-ttu-id="f9898-111">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="f9898-111">Edge Server</span></span>

  - <span data-ttu-id="f9898-112">Servidor de Mediação (se não colocado junto ao Servidor Front-End)</span><span class="sxs-lookup"><span data-stu-id="f9898-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="f9898-113">Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f9898-113">Office Web Apps Server</span></span>

<span data-ttu-id="f9898-114">Não é possível colocar a função de servidor de chat persistente com o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f9898-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="f9898-115">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="f9898-115">Databases</span></span>

<span data-ttu-id="f9898-116">Você pode colocar cada um dos bancos de dados a seguir no mesmo servidor de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="f9898-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="f9898-117">Banco de dados de back-end</span><span class="sxs-lookup"><span data-stu-id="f9898-117">Back-end database</span></span>

  - <span data-ttu-id="f9898-118">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="f9898-118">Monitoring database</span></span>

  - <span data-ttu-id="f9898-119">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="f9898-119">Archiving database</span></span>

  - <span data-ttu-id="f9898-120">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f9898-120">Persistent Chat database</span></span>

  - <span data-ttu-id="f9898-121">Banco de dados de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f9898-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="f9898-122">Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância do SQL Server ou usar uma instância separada do SQL Server para cada, com as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="f9898-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="f9898-123">Cada instância do SQL Server pode conter apenas um único banco de dados de back-end, um único banco de dados de monitoramento, um único banco de dados de arquivamento, um único banco de dados de chat persistente e um único banco de dados de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f9898-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="f9898-124">O servidor de banco de dados não pode dar suporte a mais de um pool de front-ends, uma implantação de arquivamento e uma implantação de monitoramento, mas pode dar suporte a um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9898-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="f9898-125">É possível colocar um compartilhamento de arquivo com um banco de dados, conforme será descrito ainda nesta seção.</span><span class="sxs-lookup"><span data-stu-id="f9898-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9898-126">No Lync Server 2013, você tem a opção de integrar o armazenamento de arquivamento ao armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f9898-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="f9898-127">Você não pode implantar servidores que executam o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f9898-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9898-128">Embora a colocação de bancos de dados seja suportada, o tamanho dos bancos de dados pode aumentar muito rápido.</span><span class="sxs-lookup"><span data-stu-id="f9898-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="f9898-129">Por exemplo, quando você considera colocar o banco de dados de Arquivamento com outros bancos de dados, se estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco exigido pelo banco de dados de Arquivamento poderá aumentar bastante.</span><span class="sxs-lookup"><span data-stu-id="f9898-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="f9898-130">Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, o banco de dados de chat persistente ou o banco de dados de conformidade de chat persistente com o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="f9898-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="f9898-131">Compartilhamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="f9898-131">File Share</span></span>

<span data-ttu-id="f9898-132">O compartilhamento de arquivo pode ser um servidor separado ou pode ser colocado no mesmo servidor como qualquer um ou todos a seguir:</span><span class="sxs-lookup"><span data-stu-id="f9898-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="f9898-133">Servidor de banco de dados, incluindo o Servidor Back-End de um pool de Front-Ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f9898-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="f9898-134">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="f9898-134">Archiving database</span></span>

  - <span data-ttu-id="f9898-135">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="f9898-135">Monitoring database</span></span>

  - <span data-ttu-id="f9898-136">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f9898-136">Persistent Chat database</span></span>

  - <span data-ttu-id="f9898-137">Banco de dados de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f9898-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="f9898-138">Um compartilhamento de arquivo único pode ser usado para múltiplos pools de Front-Ends, servidores Standard Edition (todos no mesmo site).</span><span class="sxs-lookup"><span data-stu-id="f9898-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9898-139">No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivo do Lync Server como servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="f9898-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="f9898-140">Outros componentes</span><span class="sxs-lookup"><span data-stu-id="f9898-140">Other Components</span></span>

<span data-ttu-id="f9898-141">Não é possível colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9898-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="f9898-142">No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f9898-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="f9898-143">Não é possível colocar nenhum componente da Unificação de mensagens (UM) do Exchange ou componente do SharePoint com nenhuma função de servidor do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9898-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

