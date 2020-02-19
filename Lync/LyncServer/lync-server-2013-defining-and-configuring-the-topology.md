---
title: 'Lync Server 2013: definindo e configurando a topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a443aaa7cf523e1cb02beb3d944ec53632732291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="e2664-102">Definindo e configurando a topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2664-103">_**Última modificação do tópico:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="e2664-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="e2664-104">Você define e configura sua topologia usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="e2664-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="e2664-105">O construtor de topologias não exige que você seja membro do grupo Administradores local ou de um grupo de domínio privilegiado (como administradores de domínio).</span><span class="sxs-lookup"><span data-stu-id="e2664-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="e2664-106">Você pode definir sua topologia como um usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="e2664-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="e2664-107">Quando você iniciar o construtor de topologia no primeiro uso e nas sessões de edição subsequentes, será solicitado o local em que deseja que o construtor de topologia carregue o documento de configuração atual.</span><span class="sxs-lookup"><span data-stu-id="e2664-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="e2664-108">As opções são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e2664-108">The choices are the following:</span></span>

  - <span data-ttu-id="e2664-109">Baixar a topologia da implantação existente</span><span class="sxs-lookup"><span data-stu-id="e2664-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="e2664-110">Abrir a topologia de um arquivo local</span><span class="sxs-lookup"><span data-stu-id="e2664-110">Open topology from a local file</span></span>

  - <span data-ttu-id="e2664-111">Nova topologia</span><span class="sxs-lookup"><span data-stu-id="e2664-111">New topology</span></span>

<span data-ttu-id="e2664-112">Se já tiver definido uma topologia e tiver estabelecido o repositório de gerenciamento central, você deverá optar por baixar uma topologia de uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="e2664-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="e2664-113">O construtor de topologias lerá o banco de dados e recuperará a definição atual.</span><span class="sxs-lookup"><span data-stu-id="e2664-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="e2664-114">Se você tiver um repositório de gerenciamento central existente, você deve sempre escolher esta opção.</span><span class="sxs-lookup"><span data-stu-id="e2664-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="e2664-115">Se você não tiver estabelecido um repositório de gerenciamento central e quiser editar uma configuração salva anteriormente, deverá optar por abrir a topologia de um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="e2664-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="e2664-116">O arquivo que será aberto seria o arquivo de configuração salvo em uma sessão anterior.</span><span class="sxs-lookup"><span data-stu-id="e2664-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="e2664-117">Você pode usar esta opção para editar a topologia salva anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e2664-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e2664-p104">Se você já tem uma topologia publicada, não deve carregar um arquivo de configuração local. Você deve baixar topologia de uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="e2664-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="e2664-120">Escolha criar uma nova topologia, se você quiser criar uma nova configuração do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="e2664-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="e2664-121">Um projeto salvo anteriormente não é substituído, a menos que você escolha salvá-lo como o mesmo arquivo criado em uma sessão anterior do design.</span><span class="sxs-lookup"><span data-stu-id="e2664-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="e2664-122">Em cada uma dessas opções, você será solicitado a fornecer um local para armazenar o arquivo de configuração do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="e2664-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="e2664-123">O local do arquivo poderia ser local, um local compartilhado em um compartilhamento de arquivos estabelecido ou uma mídia removível.</span><span class="sxs-lookup"><span data-stu-id="e2664-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2664-124">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e2664-124">In This Section</span></span>

  - [<span data-ttu-id="e2664-125">Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="e2664-126">Definir e configurar um pool Front-end ou um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="e2664-127">Implantando pools front-end emparelhados para recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="e2664-128">Implantando o espelhamento SQL para alta disponibilidade do servidor back-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="e2664-129">Editar ou configurar URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="e2664-130">Selecionar o servidor de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2664-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

