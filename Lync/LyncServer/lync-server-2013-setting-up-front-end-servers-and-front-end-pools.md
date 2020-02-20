---
title: 'Lync Server 2013: configurar servidores front-end e pools de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9af600e6c95a33aa743d518c654f3abfe4275d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="62dd0-102">Configurando servidores front-end e pools de front-ends para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62dd0-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="62dd0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="62dd0-104">Esta seção orienta você durante a instalação do Lync Server 2013 e a configuração das funções de servidor para o servidor Standard Edition e o pool de front-ends, incluindo os servidores front-end e qualquer função de servidor posicionada com os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="62dd0-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="62dd0-105">Para instalar e configurar funções de servidor, execute o assistente de implantação do Lync Server em cada computador em que você está instalando uma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="62dd0-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="62dd0-106">Você usa o assistente de implantação para concluir todas as quatro etapas de implantação, incluindo a instalação do repositório de configuração local, instalação dos servidores front-end, configuração de certificados e início de serviços.</span><span class="sxs-lookup"><span data-stu-id="62dd0-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62dd0-107">Antes de poder configurar as funções de servidor, é necessário ter publicado com êxito uma topologia.</span><span class="sxs-lookup"><span data-stu-id="62dd0-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="62dd0-108">Para obter detalhes sobre como publicar uma topologia, consulte <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">finalizando e implementando o design de topologia no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="62dd0-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62dd0-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="62dd0-109">In This Section</span></span>

  - [<span data-ttu-id="62dd0-110">Instalar o repositório de configuração local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="62dd0-111">Instalar componentes de servidor do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="62dd0-112">Configurar certificados para servidores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="62dd0-113">Iniciar serviços em servidores para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="62dd0-114">Testar a implantação do pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="62dd0-115">Testar o servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dd0-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

