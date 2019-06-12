---
title: 'Lync Server 2013: Configurand Servidores e pools Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab21e5933623af58834d3b9effa5ba1e2beecc43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="2fcb6-102">Configurand Servidores e pools Front-End para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fcb6-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2fcb6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2fcb6-104">Esta seção orienta você na instalação do Lync Server 2013 e na configuração das funções de servidor para o servidor Standard Edition e o pool de front-ends, incluindo os servidores de front-end e todas as funções de servidor posicionadas com os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="2fcb6-105">Para instalar e configurar funções de servidor, execute o assistente de implantação do Lync Server em cada computador em que você está instalando uma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="2fcb6-106">Você usará o Assistente de Implantação para completar as quatro etapas de implantação (instalação do repositório de configuração local, instalação dos servidores front-end, configuração dos certificados e inicialização dos serviços).</span><span class="sxs-lookup"><span data-stu-id="2fcb6-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fcb6-107">Antes de poder configurar funções de servidor, você deve ter publicado uma topologia com êxito.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="2fcb6-108">Para obter detalhes sobre como publicar uma topologia, consulte <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">finalizar e implementar o design de topologia no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2fcb6-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2fcb6-109">In This Section</span></span>

  - [<span data-ttu-id="2fcb6-110">Instalar o repositório de Configuração Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="2fcb6-111">Instalar componentes de servidor para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="2fcb6-112">Configurar certificados para servidores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="2fcb6-113">Iniciar serviços nos servidores para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="2fcb6-114">Testar a implantação de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="2fcb6-115">Testar o servidor de Edição Padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcb6-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

