---
title: 'Lync Server 2013: Criando uma topologia de borda e de diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f8a86d4f80b7fb4fc9990911908ef0c8a317c98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="8273c-102">Criando uma topologia de borda e de diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8273c-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8273c-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8273c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8273c-104">A criação da topologia envolve as seguintes tarefas de planejamento e implantação:</span><span class="sxs-lookup"><span data-stu-id="8273c-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="8273c-105">**Planejamento**   você precisa definir uma topologia apropriada para sua organização e identificar os componentes necessários para implantá-lo.</span><span class="sxs-lookup"><span data-stu-id="8273c-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="8273c-106">Estas são as etapas padrão do processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8273c-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="8273c-107">O Microsoft Lync Server 2013, a ferramenta de planejamento fornecida com o Lync Server 2013 torna mais fácil iniciar o processo de planejamento, além de incluir a capacidade de fazer alterações facilmente conforme suas necessidades e planos são finalizados.</span><span class="sxs-lookup"><span data-stu-id="8273c-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="8273c-108">**Implantação**   a topologia que você define usando o construtor de topologias é essencial para a implantação de qualquer servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8273c-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="8273c-109">Se você não terminar de definir e publicar sua topologia usando o construtor de topologias como parte de seus esforços de planejamento, você deve concluí-lo e publicar a topologia antes de implantar seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="8273c-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="8273c-110">Você não pode implantar componentes do servidor de borda até que tenha implantado pelo menos um pool interno e deve instalar o construtor de topologias para implantar um pool interno.</span><span class="sxs-lookup"><span data-stu-id="8273c-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="8273c-111">Esta seção não aborda a instalação do construtor de topologias porque faz parte do processo de instalação do pool interno.</span><span class="sxs-lookup"><span data-stu-id="8273c-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="8273c-112">Para obter detalhes sobre essas ferramentas, consulte [lista de verificação de implantação para acesso externo de usuários no Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8273c-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8273c-113">Se você usou anteriormente o construtor de topologias para definir uma topologia completa, incluindo a topologia de borda, poderá ignorar a <A href="lync-server-2013-define-your-edge-topology.md">topologia definir sua borda no Lync server 2013</A> e <A href="lync-server-2013-publish-your-topology.md">publicar sua topologia no Lync Server 2013</A> tarefas nesta seção, mas precisará concluir a tarefa <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para a instalação do Edge</A> .</span><span class="sxs-lookup"><span data-stu-id="8273c-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8273c-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8273c-114">In This Section</span></span>

  - [<span data-ttu-id="8273c-115">Definir sua topologia de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8273c-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="8273c-116">Definir topologias opcionais de Diretor em sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8273c-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="8273c-117">Publicar sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8273c-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="8273c-118">Exportar sua topologia do Lync Server 2013 e copiá-la na mídia externa para instalação de borda</span><span class="sxs-lookup"><span data-stu-id="8273c-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

