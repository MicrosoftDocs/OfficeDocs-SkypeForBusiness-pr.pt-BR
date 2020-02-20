---
title: 'Lync Server 2013: requisitos técnicos para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f12b84149c713ed4684cad7cf9fd3bc33bad8ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="ae78a-102">Requisitos técnicos para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae78a-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae78a-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ae78a-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ae78a-104">Os requisitos técnicos do Lync Server 2013 incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae78a-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="ae78a-105">Requisitos de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="ae78a-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="ae78a-106">Software que é pré-requisito e que deve estar instalado para o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="ae78a-107">Requisitos de armazenamento de dados para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="ae78a-108">Requisitos de dimensionamento e considerações para a implantação de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="ae78a-109">Requisitos de desempenho e considerações para os bancos de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae78a-110">As informações de escala e desempenho não estão disponíveis nesta versão do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae78a-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="ae78a-111">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="ae78a-111">Infrastructure Requirements</span></span>

<span data-ttu-id="ae78a-112">Os requisitos de infraestrutura de arquivamento do Lync Server 2013 são os mesmos para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae78a-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="ae78a-113">Para obter detalhes, consulte [determinando seus requisitos de infraestrutura para o Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="ae78a-114">Pré-requisitos de arquivamento</span><span class="sxs-lookup"><span data-stu-id="ae78a-114">Archiving Prerequisites</span></span>

<span data-ttu-id="ae78a-115">O Lync Server 2013 simplifica os pré-requisitos para arquivamento por causa do seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae78a-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="ae78a-p102">O servidor de arquivamento não é mais uma função do servidor. Em vez disso, o agente de coleta de dados unificada é executado em um pool e em servidores Standard Edition para registrar dados para arquivamento, de forma que não é preciso configurar plataformas de sistemas separados para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-p102">Archiving Server is no longer a server role. Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="ae78a-118">O arquivamento usa o armazenamento de arquivos do Lync Server 2013 para armazenamento temporário de arquivos de conteúdo de reunião, portanto, você não configura um repositório de arquivos separado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="ae78a-119">No Lync Server 2013, o enfileiramento de mensagens não é necessário.</span><span class="sxs-lookup"><span data-stu-id="ae78a-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="ae78a-120">Requisitos de armazenamento de dados para arquivamento</span><span class="sxs-lookup"><span data-stu-id="ae78a-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="ae78a-p103">Além disso, você deve configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui uma ou ambas as opções abaixo:</span><span class="sxs-lookup"><span data-stu-id="ae78a-p103">Additionally, you need to set up the infrastructure for Archiving storage. This includes one or both of the following:</span></span>

  - <span data-ttu-id="ae78a-123">**Armazenamento do Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ae78a-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="ae78a-124">Conteúdo de reuniões, como apresentações em PowerPoint, são arquivados como anexos.</span><span class="sxs-lookup"><span data-stu-id="ae78a-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="ae78a-125">Se você quiser usar a integração do Microsoft Exchange para que os dados de arquivo morto do Lync sejam armazenados com dados de conformidade do Exchange, você deve usar o Exchange 2013 para sua implantação do Exchange e garantir que o tamanho máximo de armazenamento seja compatível com o armazenamento dos arquivos de conteúdo da reunião.</span><span class="sxs-lookup"><span data-stu-id="ae78a-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="ae78a-126">Se você implantar o arquivamento usando a opção de integração do Microsoft Exchange, os dados de arquivo morto do Lync serão armazenados com dados de conformidade do Exchange 2013 somente para os usuários hospedados em seus servidores do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ae78a-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="ae78a-127">Você deve implantar o Exchange 2013 antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="ae78a-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="ae78a-128">Se você optar por usar o armazenamento do Exchange 2013, não será necessário implantar bancos de dados separados do SQL Server para arquivamento, a menos que você tenha usuários do Lync que não estejam hospedados em seus servidores do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ae78a-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="ae78a-129">**Armazenamento de banco de dados do SQL Server para arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="ae78a-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="ae78a-130">Para dar suporte a usuários que não estão hospedados em servidores Exchange 2013, ou se você não deseja usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae78a-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="ae78a-131">O Lync Server 2013 oferece suporte às seguintes versões de 64 bits do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ae78a-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="ae78a-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae78a-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="ae78a-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="ae78a-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="ae78a-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae78a-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="ae78a-135">Microsoft SQL Server 2012 padrão</span><span class="sxs-lookup"><span data-stu-id="ae78a-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae78a-136">O Microsoft SQL Server 2008 R2 Express e o Microsoft SQL Server 2012 Express não têm suporte para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="ae78a-137">Não há suporte para as versões de 32 bits do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae78a-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="ae78a-138">Para obter requisitos e restrições adicionais do SQL Server, confira <A href="lync-server-2013-database-software-support.md">suporte a software de banco de dados no Lync Server 2013</A> na documentação de planejamento ou na documentação de capacidade de suporte.</span><span class="sxs-lookup"><span data-stu-id="ae78a-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="ae78a-139">Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="ae78a-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="ae78a-140">Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="ae78a-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="ae78a-141">Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="ae78a-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="ae78a-142">Para obter detalhes sobre o SQL Server, consulte o TechCenter do [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.</span><span class="sxs-lookup"><span data-stu-id="ae78a-142">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

