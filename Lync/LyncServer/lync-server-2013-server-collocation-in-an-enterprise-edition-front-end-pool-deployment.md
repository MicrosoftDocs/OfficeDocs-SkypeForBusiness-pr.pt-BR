---
title: 'Lync Server 2013: Posicionamento do servidor em uma implantação do pool de front-ends do Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="b2537-102">Posicionamento do servidor em uma implantação do pool de front-ends do Enterprise Edition para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2537-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2537-103">_**Tópico da última modificação:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="b2537-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="b2537-104">Esta seção descreve as funções de servidor, bancos de dados e compartilhamentos de arquivos que você pode colocar em uma implantação de pool de front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2537-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="b2537-105">Funções de servidor</span><span class="sxs-lookup"><span data-stu-id="b2537-105">Server Roles</span></span>

<span data-ttu-id="b2537-106">No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são posicionados no servidor front-end, mas é necessária configuração adicional para habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="b2537-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="b2537-107">Se você não quiser posicionar o servidor de mediação com o servidor front-end, poderá implantá-lo como um servidor de mediação autônomo em um computador separado.</span><span class="sxs-lookup"><span data-stu-id="b2537-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="b2537-108">Você pode posicionar um servidor de aplicativos confiável com o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b2537-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="b2537-109">As seguintes funções de servidor devem ser implantadas em um computador separado:</span><span class="sxs-lookup"><span data-stu-id="b2537-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="b2537-110">Diretor</span><span class="sxs-lookup"><span data-stu-id="b2537-110">Director</span></span>

  - <span data-ttu-id="b2537-111">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b2537-111">Edge Server</span></span>

  - <span data-ttu-id="b2537-112">Servidor de mediação (se não estiver posicionado com o servidor front-end)</span><span class="sxs-lookup"><span data-stu-id="b2537-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="b2537-113">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="b2537-113">Office Web Apps Server</span></span>

<span data-ttu-id="b2537-114">Não é possível colocar a função de servidor de chat persistente com o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b2537-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="b2537-115">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="b2537-115">Databases</span></span>

<span data-ttu-id="b2537-116">Você pode posicionar cada um dos seguintes bancos de dados no mesmo servidor de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="b2537-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="b2537-117">Banco de dados back-end</span><span class="sxs-lookup"><span data-stu-id="b2537-117">Back-end database</span></span>

  - <span data-ttu-id="b2537-118">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="b2537-118">Monitoring database</span></span>

  - <span data-ttu-id="b2537-119">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="b2537-119">Archiving database</span></span>

  - <span data-ttu-id="b2537-120">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b2537-120">Persistent Chat database</span></span>

  - <span data-ttu-id="b2537-121">Banco de dados de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b2537-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="b2537-122">Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância do SQL Server ou usar uma instância separada do SQL Server para cada um deles, com as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="b2537-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="b2537-123">Cada instância do SQL Server pode conter apenas um único banco de dados back-end, um único banco de dados de monitoramento, um único banco de dados de arquivamento, um único banco de dados persistente de chat e um único banco de dados de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b2537-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="b2537-124">O servidor de banco de dados não pode dar suporte a mais de um pool de front-end, uma implantação de arquivamento e uma implantação de monitoramento, mas ele pode dar suporte a um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2537-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="b2537-125">Você pode posicionar um compartilhamento de arquivos com os bancos de dados, conforme descrito mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="b2537-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2537-126">No Lync Server 2013, você tem a opção de integrar o armazenamento de arquivamento com o armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b2537-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="b2537-127">Você não pode implantar servidores que estejam executando o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b2537-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b2537-128">Embora a colocação de bancos de dados seja compatível, o tamanho dos bancos de dados pode crescer rapidamente.</span><span class="sxs-lookup"><span data-stu-id="b2537-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="b2537-129">Por exemplo, quando você considera posicionar o banco de dados de arquivamento com outros bancos de dados, lembre-se de que, se você estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados do arquivamento pode crescer muito grande.</span><span class="sxs-lookup"><span data-stu-id="b2537-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="b2537-130">Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, o banco de dados de chat persistente ou o banco de dados de conformidade de chat persistente com o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="b2537-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="b2537-131">Compartilhamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="b2537-131">File Share</span></span>

<span data-ttu-id="b2537-132">O compartilhamento de arquivos pode ser um servidor separado ou pode ser posicionado no mesmo servidor que qualquer um ou todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="b2537-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="b2537-133">Servidor de banco de dados, incluindo o servidor back-end de um pool Front-end da Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b2537-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="b2537-134">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="b2537-134">Archiving database</span></span>

  - <span data-ttu-id="b2537-135">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="b2537-135">Monitoring database</span></span>

  - <span data-ttu-id="b2537-136">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b2537-136">Persistent Chat database</span></span>

  - <span data-ttu-id="b2537-137">Banco de dados de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b2537-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="b2537-138">Um único compartilhamento de arquivo pode ser usado para vários pools de front-end, servidores Standard Edition (todos no mesmo site).</span><span class="sxs-lookup"><span data-stu-id="b2537-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2537-139">No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivos do Lync Server como o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b2537-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="b2537-140">Outros componentes</span><span class="sxs-lookup"><span data-stu-id="b2537-140">Other Components</span></span>

<span data-ttu-id="b2537-141">Você não pode colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2537-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="b2537-142">No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b2537-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="b2537-143">Você não pode colocar nenhum componente de Unificação de mensagens (UM) do Exchange ou componente do SharePoint com qualquer função do SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="b2537-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

