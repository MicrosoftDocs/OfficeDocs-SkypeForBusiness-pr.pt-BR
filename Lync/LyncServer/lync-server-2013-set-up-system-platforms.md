---
title: 'Lync Server 2013: configurar plataformas do sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bd5bff0b215060b1d352d5cc5798b114140c15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509778"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="fb9f8-102">Configurar plataformas de sistema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb9f8-102">Set up system platforms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb9f8-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fb9f8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fb9f8-104">Antes de iniciar a implantação do servidor de chat persistente, você deve instalar o sistema operacional necessário no hardware que atenda aos requisitos do sistema nos servidores:</span><span class="sxs-lookup"><span data-stu-id="fb9f8-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="fb9f8-105">Para obter detalhes sobre o hardware suportado para servidores que executam o Lync Server 2013, servidores de banco de dados e servidores de arquivos, consulte [hardware suportado para o Lync server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="fb9f8-106">Para obter detalhes sobre sistemas operacionais e software de banco de dados suportados, consulte [Server Software and Infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="fb9f8-107">Para obter detalhes sobre os requisitos do Windows Update, consulte [Additional Server Support and Requirements in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="fb9f8-108">O servidor front-end do servidor de chat persistente, **PersistentChatService**, pode ser implantado em um ou mais computadores autônomos em um pool do Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="fb9f8-109">Eles não podem ser colocados nos servidores front-end do Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="fb9f8-110">O servidor de chat persistente pode ser implantado pelo bootstrapper, assim como outras funções do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="fb9f8-111">Os **Serviços Web de chat persistente para upload/download de arquivo**e **Serviços Web de chat persistente para gerenciamento de salas de chat** são componentes da Web implantados nos servidores Front-End do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="fb9f8-112">Um servidor front-end único de servidor de chat persistente pode oferecer suporte A 20.000 usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="fb9f8-113">Você pode ter um pool de servidores de chat persistente com até 4 front-ends ativos suportando um total de 80.000 usuários simultâneos.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="fb9f8-114">O servidor back-end de chat persistente, **PersistentChatStore**, armazena as salas de chat e as categorias.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="fb9f8-115">Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado em seu pool Enterprise Edition; Embora ofereçamos suporte à colocação do servidor back-end do Lync Server 2013 e ao **PersistentChatStore** na mesma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="fb9f8-116">Se sua organização exigir o suporte de conformidade, você poderá instalá-lo usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="fb9f8-117">O serviço de conformidade do servidor de chat persistente está instalado no mesmo computador que o servidor de front-end do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="fb9f8-118">Um banco de dados separado é exigido para conformidade.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-118">A separate database is required for compliance.</span></span> <span data-ttu-id="fb9f8-119">Para obter detalhes sobre os requisitos de conformidade para o servidor de chat persistente, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="fb9f8-120">No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com o software de banco de dados do SQL Server instalado.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="fb9f8-121">O construtor de topologias suporta vários pools de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="fb9f8-122">Siga as mesmas instruções de implantação para implantar vários pools de servidores de chat persistente, como faria para qualquer pool de [implantação do Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="fb9f8-123">Você também pode implantar o servidor de chat persistente com o Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="fb9f8-124">Nesse caso, o servidor front-end do **PersistentChatService** é colocado no servidor Standard Edition, e você pode implantar o servidor back-end do **PersistentChatStore** na instância local do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fb9f8-125">Não há suporte para o servidor de chat persistente &nbsp; Standard Edition para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="fb9f8-126">Desempenho e escala será limitado.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-126">Performance and scale will be limited.</span></span> <span data-ttu-id="fb9f8-127">Além disso, damos suporte somente a novas &nbsp; implantações do servidor do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="fb9f8-128">Não há suporte para uma atualização do Lync Server 2010, o servidor de chat de grupo para um servidor de chat persistente do Lync Server 2013 &nbsp; persistent &nbsp; Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fb9f8-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb9f8-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb9f8-129">See Also</span></span>


[<span data-ttu-id="fb9f8-130">Suporte e requisitos adicionais do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb9f8-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="fb9f8-131">Hardware suportado para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb9f8-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="fb9f8-132">Suporte a infraestrutura e software de servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb9f8-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="fb9f8-133">Planejando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb9f8-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="fb9f8-134">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb9f8-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

