---
title: 'Lync Server 2013: criando uma topologia de borda e de diretor'
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
ms.openlocfilehash: be41eb547589c74b070a55325efcfd05e33f4588
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="05e37-102">Criando uma topologia de borda e de diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05e37-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05e37-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="05e37-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="05e37-104">A criação da topologia envolve as seguintes tarefas de planejamento e implantação:</span><span class="sxs-lookup"><span data-stu-id="05e37-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="05e37-105">**Planejamento**   você precisa definir uma topologia apropriada para sua organização e identificar os componentes necessários para implantá-lo.</span><span class="sxs-lookup"><span data-stu-id="05e37-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="05e37-106">Estas são as etapas padrão no processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="05e37-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="05e37-107">A ferramenta de planejamento do Microsoft Lync Server 2013, fornecida com o Lync Server 2013, facilita o início do processo de planejamento, além de incluir a capacidade de fazer alterações facilmente à medida que seus requisitos e planos são finalizados.</span><span class="sxs-lookup"><span data-stu-id="05e37-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="05e37-108">**Implantação**   a topologia que você define usando o construtor de topologias é essencial para a implantação de qualquer servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05e37-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="05e37-109">Se você não terminar de definir e publicar sua topologia usando o construtor de topologias como parte de seus esforços de planejamento, deverá concluí-la e publicar a topologia antes de implantar seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="05e37-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="05e37-110">Você não pode implantar componentes do servidor de borda até ter implantado pelo menos um pool interno e deve instalar o construtor de topologias para implantar um pool interno.</span><span class="sxs-lookup"><span data-stu-id="05e37-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="05e37-111">Esta seção não aborda a instalação do construtor de topologias porque faz parte do processo de instalação do pool interno.</span><span class="sxs-lookup"><span data-stu-id="05e37-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="05e37-112">Para obter detalhes sobre essas ferramentas, consulte [Deployment Checklist for External User Access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="05e37-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05e37-113">Se você usou anteriormente o construtor de topologias para definir uma topologia completa, incluindo a topologia de borda, é possível ignorar a <A href="lync-server-2013-define-your-edge-topology.md">sua topologia de definição de borda no Lync server 2013</A> e <A href="lync-server-2013-publish-your-topology.md">publicar sua topologia no Lync Server 2013</A> tarefas nesta seção, mas é necessário concluir a tarefa <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação de borda</A> .</span><span class="sxs-lookup"><span data-stu-id="05e37-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05e37-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="05e37-114">In This Section</span></span>

  - [<span data-ttu-id="05e37-115">Definir sua topologia de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05e37-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="05e37-116">Definir topologias opcionais de diretor em sua topologia para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05e37-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="05e37-117">Publicar sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05e37-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="05e37-118">Exporte sua topologia do Lync Server 2013 e copie-a para a mídia externa para instalação de borda</span><span class="sxs-lookup"><span data-stu-id="05e37-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

