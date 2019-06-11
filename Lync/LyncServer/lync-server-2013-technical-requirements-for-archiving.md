---
title: 'Lync Server 2013: requisitos técnicos para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="12c86-102">Requisitos técnicos para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12c86-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12c86-103">_**Tópico da última modificação:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="12c86-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="12c86-104">Os requisitos técnicos do Lync Server 2013 incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12c86-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="12c86-105">Requisitos de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="12c86-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="12c86-106">Software obrigatório que deve ser instalado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="12c86-107">Requisitos de armazenamento de dados para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="12c86-108">Redimensionamento de requisitos e considerações para a implantação de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="12c86-109">Requisitos de desempenho e considerações para seus bancos de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12c86-110">As informações de dimensionamento e desempenho não estão disponíveis neste lançamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12c86-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="12c86-111">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="12c86-111">Infrastructure Requirements</span></span>

<span data-ttu-id="12c86-112">Os requisitos da infraestrutura de arquivamento do Lync Server 2013 são os mesmos para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12c86-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="12c86-113">Para obter detalhes, consulte determinando os [requisitos de infraestrutura do Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="12c86-114">Pré-requisitos de arquivamento</span><span class="sxs-lookup"><span data-stu-id="12c86-114">Archiving Prerequisites</span></span>

<span data-ttu-id="12c86-115">O Lync Server 2013 simplifica os pré-requisitos de arquivamento devido ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="12c86-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="12c86-116">O servidor de arquivamento não é mais uma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="12c86-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="12c86-117">Em vez disso, os agentes de coleta de dados unificados são executados nos servidores de front-end em um pool e servidores Standard Edition para capturar dados para arquivamento, para que você não configure plataformas de sistema separadas para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="12c86-118">O arquivamento usa o armazenamento de arquivos do Lync Server 2013 para armazenamento temporário de arquivos de conteúdo da reunião, para que você não configure um armazenamento de arquivos separado para o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="12c86-119">No Lync Server 2013, o enfileiramento de mensagens não é necessário.</span><span class="sxs-lookup"><span data-stu-id="12c86-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="12c86-120">Requisitos de armazenamento de dados para arquivamento</span><span class="sxs-lookup"><span data-stu-id="12c86-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="12c86-121">Além disso, você precisa configurar a infraestrutura para arquivar o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="12c86-122">Isso inclui um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="12c86-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="12c86-123">**Armazenamento do Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="12c86-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="12c86-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span><span class="sxs-lookup"><span data-stu-id="12c86-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="12c86-125">Se você quiser usar a integração do Microsoft Exchange para que os dados do arquivo morto do Lync sejam armazenados com dados de conformidade do Exchange, você deve usar o Exchange 2013 para a implantação do Exchange e garantir que o tamanho de armazenamento máximo seja compatível com o armazenamento dos arquivos de conteúdo da reunião.</span><span class="sxs-lookup"><span data-stu-id="12c86-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="12c86-126">Se você implantar o arquivamento usando a opção de integração do Microsoft Exchange, os dados do arquivo morto do Lync serão armazenados com os dados de conformidade do Exchange 2013 somente para os usuários que estiverem hospedados em seus servidores Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12c86-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="12c86-127">Você deve implantar o Exchange 2013 antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c86-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="12c86-128">Se optar por usar o armazenamento do Exchange 2013, você não precisará implantar bancos de dados do SQL Server separados para arquivamento, a menos que você tenha usuários do Lync que não são hospedados em seus servidores Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12c86-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="12c86-129">**Armazenamento de banco de dados do SQL Server para arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="12c86-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="12c86-130">Para dar suporte a usuários que não são hospedados em servidores Exchange 2013 ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12c86-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="12c86-131">O Lync Server 2013 é compatível com as seguintes versões de 64 bits do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="12c86-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="12c86-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12c86-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="12c86-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="12c86-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="12c86-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12c86-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="12c86-135">Microsoft SQL Server 2012 padrão</span><span class="sxs-lookup"><span data-stu-id="12c86-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12c86-136">Microsoft SQL Server 2008 R2 Express e Microsoft SQL Server 2012 Express não são compatíveis com o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="12c86-137">Não há suporte para as versões de 32 bits do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12c86-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="12c86-138">Para obter mais requisitos e restrições do SQL Server, consulte <A href="lync-server-2013-database-software-support.md">suporte a software de banco de dados no Lync Server 2013</A> na documentação de planejamento ou na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="12c86-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="12c86-139">Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="12c86-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="12c86-140">Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="12c86-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="12c86-141">Você também pode criar o banco de dados posteriormente, incluindo como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="12c86-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="12c86-142">Para obter detalhes sobre o SQL Server, consulte o TechCenter do [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.</span><span class="sxs-lookup"><span data-stu-id="12c86-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

