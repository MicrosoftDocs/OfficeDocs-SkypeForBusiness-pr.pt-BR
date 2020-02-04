---
title: Pré-requisitos e permissões de configuração de conferência discada
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
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="143fb-102">Pré-requisitos e permissões de configuração de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143fb-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="143fb-103">_**Tópico da última modificação:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="143fb-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="143fb-104">A conferência discada é um componente opcional da carga de trabalho de conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="143fb-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="143fb-105">Os componentes que você precisa instalar antes de configurar a conferência discada são implantados quando você usa o construtor de topologias para criar sua topologia e, em seguida, configurar seu pool de front-end ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="143fb-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="143fb-106">Este tópico descreve o que você precisa ter feito antes de poder configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="143fb-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="143fb-107">Esta seção pressupõe que você tenha lido as seções de planejamento relacionadas à carga de trabalho de conferência e conferência discada em particular.</span><span class="sxs-lookup"><span data-stu-id="143fb-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="143fb-108">Pré-requisitos de configuração da conferência discada</span><span class="sxs-lookup"><span data-stu-id="143fb-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="143fb-109">A conferência discada requer os seguintes componentes do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="143fb-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="143fb-110">UCAS (Unified Communications Application Service) (chamado de *Serviço de aplicativos*)</span><span class="sxs-lookup"><span data-stu-id="143fb-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="143fb-111">Aplicativo Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="143fb-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="143fb-112">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="143fb-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="143fb-113">Página da Web Configurações de Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="143fb-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="143fb-114">Pelo menos um servidor de mediação do Lync Server 2013 e pelo menos um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="143fb-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="143fb-115">Você implanta esses componentes quando usa o construtor de topologias para definir e publicar sua topologia e, em seguida, implantar um pool de front-ends ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="143fb-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="143fb-116">Se você estiver implantando o Enterprise Voice, deve implantá-lo antes de configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="143fb-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="143fb-117">Se você não estiver implantando o Enterprise Voice, poderá implantar um servidor de mediação e um gateway PSTN (rede telefônica pública comutada) ao implantar seu pool de front-end ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="143fb-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="143fb-118">Se você estiver atualizando do Office Communications Server 2007 R2 para o Lync Server 2013, implante a conferência discada em todos os pools que planeja usar para hospedar conferências do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="143fb-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="143fb-119">Para obter detalhes sobre a migração de conferência discada, consulte <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migração do Office Communications Server 2007 R2 para o Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="143fb-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="143fb-120">Esta seção pressupõe que você tenha feito o seguinte:</span><span class="sxs-lookup"><span data-stu-id="143fb-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="143fb-121">Aplicadas as atualizações mais recentes para o seu ambiente do Office Communications Server 2007 R2, se você estiver migrando para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="143fb-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="143fb-122">Usou o construtor de topologias para projetar e configurar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="143fb-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="143fb-123">Ao especificar a carga de trabalho de conferência, você selecionou a opção de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="143fb-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="143fb-124">Para obter detalhes sobre como definir sua topologia, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="143fb-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="143fb-125">Publicou sua topologia e configurar o pool de front-end ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="143fb-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="143fb-126">Para obter detalhes sobre como publicar a topologia e instalar o Lync Server 2013, consulte [implantação do Lync server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="143fb-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="143fb-127">Quando você instala sua topologia publicada, a página da Web configurações de conferência discada é instalada no servidor front-end ou no servidor Standard Edition como parte dos serviços Web.</span><span class="sxs-lookup"><span data-stu-id="143fb-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="143fb-128">Se você alterar o caminho para o repositório de arquivos no construtor de topologias depois de implantar o Lync Server 2013, será necessário reiniciar o atendedor de conferências e os aplicativos de anúncio de conferência para usar o novo caminho.</span><span class="sxs-lookup"><span data-stu-id="143fb-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="143fb-129">Enterprise Voice implantado.</span><span class="sxs-lookup"><span data-stu-id="143fb-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="143fb-130">Se não estiver implantando o Enterprise Voice, você colocaria um servidor de mediação no servidor front-end do Enterprise Edition ou do servidor Standard Edition ou implantou um servidor de mediação autônomo e implantou um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="143fb-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="143fb-131">Para obter detalhes sobre a implantação do Enterprise Voice, consulte [implantação do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="143fb-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="143fb-132">Para obter detalhes sobre como instalar um servidor autônomo de mediação e um gateway PSTN, consulte [implantação de servidores de mediação e definição de pares no Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="143fb-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="143fb-133">O fluxograma a seguir mostra as etapas que você deve executar antes de poder configurar a conferência discada e as etapas que você executa para configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="143fb-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="143fb-134">**Implantando conferência discada**</span><span class="sxs-lookup"><span data-stu-id="143fb-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="143fb-135">![Fluxograma de implantação de conferência discada](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Fluxograma de implantação de conferência discada")</span><span class="sxs-lookup"><span data-stu-id="143fb-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="143fb-136">Permissões de conferência discada</span><span class="sxs-lookup"><span data-stu-id="143fb-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="143fb-137">Para configurar a conferência discada, você precisará usar as seguintes ferramentas administrativas:</span><span class="sxs-lookup"><span data-stu-id="143fb-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="143fb-138">Painel de Controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143fb-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="143fb-139">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="143fb-139">Lync Server Management Shell</span></span>

<span data-ttu-id="143fb-140">Use essas ferramentas administrativas para configurar as configurações de conferência discada e os planos de discagem, as políticas e outras configurações necessárias para a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="143fb-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="143fb-141">A configuração da conferência discada requer qualquer uma das seguintes funções administrativas, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="143fb-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="143fb-142">**CsVoiceAdministrator**   essa função de administrador pode criar, configurar e gerenciar configurações e políticas relacionadas à voz.</span><span class="sxs-lookup"><span data-stu-id="143fb-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="143fb-143">**CsUserAdministrator**   essa função de administrador pode habilitar e desabilitar usuários do Lync Server e atribuir políticas existentes, como políticas de conferência e políticas de PIN, a usuários.</span><span class="sxs-lookup"><span data-stu-id="143fb-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="143fb-144">**CsAdministrator**   essa função de administrador pode executar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="143fb-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="143fb-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="143fb-145">See Also</span></span>


[<span data-ttu-id="143fb-146">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143fb-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

