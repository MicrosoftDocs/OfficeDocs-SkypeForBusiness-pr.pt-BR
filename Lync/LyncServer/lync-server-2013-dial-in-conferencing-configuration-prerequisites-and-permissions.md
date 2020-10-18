---
title: Pré-requisitos e permissões de configuração de conferência discada
description: Pré-requisitos e permissões de configuração de conferência discada.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eced67f33e35c711c4fcd31120480b6d5c2e41ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576167"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="a5024-103">Pré-requisitos e permissões de configuração de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5024-103">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5024-104">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a5024-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a5024-105">A conferência discada é um componente opcional da carga de trabalho de conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5024-105">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="a5024-106">Os componentes que precisam ser instalados para que você possa configurar a conferência discada são implantados quando você usa o construtor de topologias para criar sua topologia e, em seguida, configurar seu pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a5024-106">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="a5024-107">Este tópico descreve o que você precisa fazer para poder configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="a5024-107">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="a5024-108">Esta seção supõe que você leu as seções de planejamento relacionadas à carga de trabalho Conferência e conferência discada em particular.</span><span class="sxs-lookup"><span data-stu-id="a5024-108">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="a5024-109">Pré-requisitos de configuração de conferência discada</span><span class="sxs-lookup"><span data-stu-id="a5024-109">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="a5024-110">A conferência discada requer os seguintes componentes do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a5024-110">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="a5024-111">UCAS (Unified Communications Application Service) (chamado de *Serviço de Aplicativo*)</span><span class="sxs-lookup"><span data-stu-id="a5024-111">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="a5024-112">Aplicativo Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="a5024-112">Conferencing Attendant application</span></span>

  - <span data-ttu-id="a5024-113">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="a5024-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="a5024-114">Página da Web Configurações de Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="a5024-114">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="a5024-115">Pelo menos um servidor de mediação do Lync Server 2013 e pelo menos um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="a5024-115">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="a5024-116">Você implanta esses componentes quando usa o construtor de topologias para definir e publicar sua topologia e, em seguida, implantar um pool de front-ends ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a5024-116">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="a5024-117">Se você estiver implantando o Enterprise Voice, deverá implantá-lo antes de configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="a5024-117">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="a5024-118">Se você não estiver implantando o Enterprise Voice, poderá implantar um servidor de mediação e um gateway PSTN (rede telefônica pública comutada) ao implantar seu pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a5024-118">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a5024-119">Se você estiver atualizando do Office Communications Server 2007 R2 para o Lync Server 2013, implante a conferência discada em todos os pools que pretende usar para hospedar as conferências do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5024-119">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="a5024-120">Para obter detalhes sobre a migração de conferência discada, consulte <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migração do Office Communications Server 2007 R2 para o Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a5024-120">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a5024-121">Esta seção supõe que você fez o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5024-121">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="a5024-122">Aplicadas as atualizações mais recentes para o seu ambiente do Office Communications Server 2007 R2, se você estiver migrando para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5024-122">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="a5024-123">Usou o construtor de topologias para projetar e configurar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="a5024-123">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="a5024-124">Durante a especificação da carga de trabalho Conferência, você selecionou a opção de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="a5024-124">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="a5024-125">Para obter detalhes sobre como definir sua topologia, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a5024-125">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a5024-126">Publicou sua topologia e configurou o pool Front-End ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a5024-126">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="a5024-127">Para obter detalhes sobre como publicar a topologia e instalar o Lync Server 2013, consulte [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a5024-127">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a5024-128">Ao instalar sua topologia publicada, a página da Web Configurações de Conferência Discada é instalada no servidor Front-End ou servidor Standard Edition como parte dos Serviços da Web.</span><span class="sxs-lookup"><span data-stu-id="a5024-128">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="a5024-129">Se você alterar o caminho para o repositório de arquivos no construtor de topologias depois de implantar o Lync Server 2013, será necessário reiniciar o atendedor de conferência e os aplicativos de anúncio de conferência para usar o novo caminho.</span><span class="sxs-lookup"><span data-stu-id="a5024-129">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="a5024-130">Enterprise Voice implantado.</span><span class="sxs-lookup"><span data-stu-id="a5024-130">Deployed Enterprise Voice.</span></span> <span data-ttu-id="a5024-131">Se você não estiver implantando o Enterprise Voice, colocará um servidor de mediação no servidor de front-ends Enterprise Edition ou o servidor Standard Edition, ou implantou um servidor de mediação autônomo e implantou um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="a5024-131">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="a5024-132">Para obter detalhes sobre a implantação do Enterprise Voice, consulte [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a5024-132">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="a5024-133">Para obter detalhes sobre como instalar um servidor de mediação autônomo e gateway PSTN, consulte [implantando servidores de mediação e definindo pares no Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a5024-133">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="a5024-134">O fluxograma a seguir mostra as etapas que devem ser executadas antes de você poder configurar a conferência discada e as etapas executadas para configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="a5024-134">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="a5024-135">**Implantando a conferência discada**</span><span class="sxs-lookup"><span data-stu-id="a5024-135">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="a5024-136">![Fluxograma de implantação de conferência discada](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Fluxograma de implantação de conferência discada")</span><span class="sxs-lookup"><span data-stu-id="a5024-136">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="a5024-137">Permissões de conferência discada</span><span class="sxs-lookup"><span data-stu-id="a5024-137">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="a5024-138">Para configurar a conferência discada, é necessário usar as seguintes ferramentas administrativas:</span><span class="sxs-lookup"><span data-stu-id="a5024-138">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="a5024-139">Painel de Controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5024-139">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="a5024-140">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a5024-140">Lync Server Management Shell</span></span>

<span data-ttu-id="a5024-141">Use essas ferramentas administrativas para definir as configurações de conferência discada e os planos, políticas e outras configurações de discagem exigidas pela conferência discada.</span><span class="sxs-lookup"><span data-stu-id="a5024-141">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="a5024-142">A configuração de uma conferência discada exige qualquer uma das funções administrativas a seguir, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="a5024-142">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="a5024-143">**CsVoiceAdministrator**     Essa função de administrador pode criar, configurar e gerenciar configurações e políticas relacionadas à voz.</span><span class="sxs-lookup"><span data-stu-id="a5024-143">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="a5024-144">**CsUserAdministrator**     Essa função de administrador pode habilitar e desabilitar usuários para o Lync Server e atribuir políticas existentes, como políticas de conferência e políticas de PIN, aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a5024-144">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="a5024-145">**CsAdministrator**     Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5024-145">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5024-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5024-146">See Also</span></span>


[<span data-ttu-id="a5024-147">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5024-147">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

