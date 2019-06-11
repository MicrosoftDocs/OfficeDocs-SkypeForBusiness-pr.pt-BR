---
title: 'Lync Server 2013: requisitos técnicos para o servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="abf80-102">Requisitos técnicos para servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abf80-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abf80-103">_**Tópico da última modificação:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="abf80-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="abf80-104">Cada computador que hospeda um servidor de chat persistente deve ter acesso a uma topologia existente do Lync Server 2013 com os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="abf80-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="abf80-105">**Lync Server 2013, servidor front-end.**  O servidor front-end é a base para o roteamento SIP (Session Initiation Protocol), que faz a comunicação entre computadores que executam o servidor de chat persistente e a funcionalidade de chat persistente possível.</span><span class="sxs-lookup"><span data-stu-id="abf80-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="abf80-106">Antes de começar a implantar o servidor de chat persistente, verifique a implantação do Lync Server 2013, Standard Edition ou um pool de front-end do Lync Server e qualquer outro computador interno que esteja executando o Lync Server, conforme apropriado para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="abf80-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="abf80-107">As seções a seguir descrevem os requisitos específicos do servidor de chat persistente e do banco de dados que armazena os dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="abf80-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="abf80-108">Requisitos de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="abf80-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="abf80-109">Para obter detalhes sobre o hardware recomendado para a implantação do Lync Server e a versão mais recente do servidor de chat persistente, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="abf80-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="abf80-110">Para obter detalhes sobre o servidor e ferramentas de suporte do sistema operacional do Lync Server e do servidor de chat persistente, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="abf80-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="abf80-111">Para obter detalhes sobre o software adicional necessário para a implantação do servidor de chat persistente, consulte a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="abf80-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="abf80-112">Pré-requisitos de software do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="abf80-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abf80-113">Software</span><span class="sxs-lookup"><span data-stu-id="abf80-113">Software</span></span></th>
<th><span data-ttu-id="abf80-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="abf80-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abf80-115">Enfileiramento de mensagens</span><span class="sxs-lookup"><span data-stu-id="abf80-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="abf80-116">Usado pelo servidor de chat persistente e pelo serviço de conformidade de chat persistente, se implantado.</span><span class="sxs-lookup"><span data-stu-id="abf80-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="abf80-117">Requisitos de banco de dados persistente do servidor de chat</span><span class="sxs-lookup"><span data-stu-id="abf80-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="abf80-118">O servidor de chat persistente usa o banco de dados de chat persistente para armazenar os dados de histórico de chat, configuração e provisionamento de usuário.</span><span class="sxs-lookup"><span data-stu-id="abf80-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="abf80-119">Opcionalmente, ele usa o banco de dados de conformidade de chat persistente para armazenar dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="abf80-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abf80-120">O banco de dados de chat persistente (MGC) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em servidores SQL diferentes.</span><span class="sxs-lookup"><span data-stu-id="abf80-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="abf80-121">Para preparar uma plataforma de servidor de banco de dados, verifique se todos os computadores atendem aos requisitos de hardware, depois instale o software de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="abf80-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="abf80-122">A plataforma do servidor para os servidores de banco de dados de chat persistente requer o mesmo hardware que o servidor de banco de dados back-end do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="abf80-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="abf80-123">Para obter detalhes, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="abf80-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="abf80-124">No servidor de banco de dados. verifique se um dos seguintes aplicativos de software está instalado:</span><span class="sxs-lookup"><span data-stu-id="abf80-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="abf80-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="abf80-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="abf80-126">Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte "instalar o SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)" em.</span><span class="sxs-lookup"><span data-stu-id="abf80-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="abf80-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="abf80-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="abf80-128">Para obter detalhes sobre como instalar o Microsoft SQL Server 2008 R2, consulte "instalação do SQL Server (SQL Server 2008 R2) [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)" em.</span><span class="sxs-lookup"><span data-stu-id="abf80-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="abf80-129">Requisitos de certificado do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="abf80-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="abf80-130">Para obter detalhes sobre como adquirir certificados, criar o banco de dados do SQL Server e criar armazenamentos de arquivos, consulte Implantando o [Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="abf80-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

