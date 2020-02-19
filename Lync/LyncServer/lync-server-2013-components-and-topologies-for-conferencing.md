---
title: Componentes e topologias do Lync Server 2013 para conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa3cf9b5a9e588b837648d7d801c3f7c355165bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="de147-102">Componentes e topologias para conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de147-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de147-103">_**Última modificação do tópico:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="de147-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="de147-104">Quando você seleciona conferências no construtor de topologias, a conferência é implantada como parte do servidor front-end ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="de147-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="de147-105">A conferência discada e o compartilhamento de PowerPoint requer componentes e configurações adicionais.</span><span class="sxs-lookup"><span data-stu-id="de147-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="de147-106">As seções a seguir descrevem os componentes e topologias suportados para webconferência, conferência A/V e conferência discada.</span><span class="sxs-lookup"><span data-stu-id="de147-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="de147-107">Componentes suportados</span><span class="sxs-lookup"><span data-stu-id="de147-107">Supported Components</span></span>

<span data-ttu-id="de147-108">Os únicos componentes de conferência da Web e conferência A/V exigem os servidores front-end da sua organização ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="de147-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="de147-109">Para obter uma lista de requisitos de hardware e software para servidores front-end e servidores Standard Edition, consulte [hardware suportado para o Lync server 2013](lync-server-2013-supported-hardware.md) e [suporte a infraestrutura e software de servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="de147-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="de147-110">O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="de147-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="de147-111">Para obter detalhes sobre como instalar e configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="de147-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="de147-112">Além dos requisitos de conferência da Web e conferência A/V, a conferência discada usa os seguintes componentes do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="de147-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="de147-113">\*\*\*\*   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada (UC).</span><span class="sxs-lookup"><span data-stu-id="de147-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="de147-114">A conferência discada usa dois aplicativos de comunicação unificada que exigem o serviço de aplicativo: o atendedor de conferência e o comunicado de conferência.</span><span class="sxs-lookup"><span data-stu-id="de147-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="de147-115">O Serviço de aplicativo é instalado e ativado por padrão em cada Servidor Front-End em um pool de Front-Ends e em cada Servidor Standard Edition ao implantar uma carga de trabalho de Conferência e selecionar a opção de conferência de discagem.</span><span class="sxs-lookup"><span data-stu-id="de147-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="de147-116">**Assistente de conferência**   o aplicativo atendedor de conferência do aplicativo é um aplicativo de comunicações unificado que aceita chamadas PSTN (rede telefônica pública comutada), reproduz prompts e une as chamadas a uma conferência a/V.</span><span class="sxs-lookup"><span data-stu-id="de147-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="de147-117">O aplicativo atendedor de conferência é instalado e ativado por padrão ao implantar uma carga de trabalho de conferência e selecionar a opção de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="de147-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="de147-118">**Comunicado de conferência**   o aplicativo comunicado de conferência de aplicativo é um aplicativo de comunicações unificado que reproduz tons e avisa para os participantes de PSTN em determinadas ações, como quando os participantes ingressam ou saem de uma conferência, os participantes são desativados ou desativados, alguém entra no lobby de conferência ou está bloqueado ou desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="de147-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="de147-119">O aplicativo de anúncio de conferência também suporta comandos DTMF (multifrequência de tom dual) do teclado numérico do telefone.</span><span class="sxs-lookup"><span data-stu-id="de147-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="de147-120">O aplicativo de anúncio de conferência é automaticamente instalado e ativado por padrão ao implantar uma carga de trabalho de conferência e selecionar a opção de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="de147-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="de147-121">**Página de configurações de conferência discada**   a página de configurações de conferência discada exibe números de discagem de conferência com seus idiomas disponíveis, informações de conferência atribuídas (ou seja, para reuniões que não precisam ser agendadas) e controles de DTMF em conferência, e suporta o gerenciamento de PIN (número de identificação pessoal) e informações de conferência atribuídas.</span><span class="sxs-lookup"><span data-stu-id="de147-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="de147-122">A página de configurações de conferência discada é instalada automaticamente como parte dos serviços Web.</span><span class="sxs-lookup"><span data-stu-id="de147-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="de147-123">**Lync Server 2013, servidor de mediação e**   conferência de discagem de gateway PSTN requer um servidor de mediação para converter sinalização (e mídia, em algumas configurações) entre o Lync Server 2013 e o gateway PSTN e um gateway PSTN para converter sinalização e mídia entre o servidor de mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="de147-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="de147-124">Para a Conferência de Discagem, você deve implantar pelo menos um Servidor de Mediação e pelo menos um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="de147-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="de147-125">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="de147-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="de147-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="de147-126">IP-PBX</span></span>
    
      - <span data-ttu-id="de147-127">Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)</span><span class="sxs-lookup"><span data-stu-id="de147-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de147-128">Se você também estiver implantando o Enterprise Voice, o servidor de mediação e os gateways PSTN serão parte da implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="de147-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="de147-129">Se você não estiver implantando o Enterprise Voice, será necessário implantar pelo menos um Servidor de Mediação e um gateway PSTN, IP-PBX ou SBC para a conferência de discagem.</span><span class="sxs-lookup"><span data-stu-id="de147-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="de147-130">\*\*\*\*   O repositório de arquivos do repositório de arquivos é usado para arquivos de áudio de nome gravados.</span><span class="sxs-lookup"><span data-stu-id="de147-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="de147-131">O repositório de arquivos é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="de147-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="de147-132">**Repositório do usuário o**   armazenamento do usuário é usado para armazenar Pins do usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de147-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="de147-133">Os PINs estão em hash.</span><span class="sxs-lookup"><span data-stu-id="de147-133">PINs are hashed.</span></span> <span data-ttu-id="de147-134">O repositório de usuário é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="de147-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="de147-135">**Painel de controle do Lync Server**   algumas configurações de discagem podem ser configuradas usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de147-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="de147-136">**Shell de gerenciamento do Lync Server**   todas as configurações de discagem podem ser configuradas usando os cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de147-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="de147-137">Os cmdlets do Shell de gerenciamento do Lync Server estão disponíveis para implantação, configuração, execução, monitoramento e solução de problemas de aplicativo e anúncio de conferência do atendedor de conferência.</span><span class="sxs-lookup"><span data-stu-id="de147-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="de147-138">Para obter detalhes sobre cmdlets específicos, consulte Lync Server Management Shell Documentation.</span><span class="sxs-lookup"><span data-stu-id="de147-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="de147-139">Topologias suportadas</span><span class="sxs-lookup"><span data-stu-id="de147-139">Supported Topologies</span></span>

<span data-ttu-id="de147-140">No Lync Server 2013, o servidor que executa o serviços de conferência é sempre colocado com os servidores front-end ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="de147-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="de147-141">Durante a implantação inicial, o construtor de topologias oferece a opção de incluir a conferência em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="de147-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="de147-142">Você também pode usar o construtor de topologias para adicionar conferências a uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="de147-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="de147-143">Para obter detalhes, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="de147-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="de147-144">Topologias de conferência discada</span><span class="sxs-lookup"><span data-stu-id="de147-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="de147-145">É possível implantar a conferência discada nas seguintes topologias e configurações:</span><span class="sxs-lookup"><span data-stu-id="de147-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="de147-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="de147-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="de147-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="de147-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="de147-148">Com ou sem Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="de147-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="de147-149">Você pode implantar o serviço de aplicativo, o aplicativo de atendedor de conferência e o aplicativo de anúncio de conferência em um site central, mas não em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="de147-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de147-150">Se você implantar a conferência discada, deverá implantá-la em todos os pools onde você implantar a conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de147-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="de147-151">Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool.</span><span class="sxs-lookup"><span data-stu-id="de147-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="de147-152">Esse requisito suporta o recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Lync Server 2013 em um pool diferente.</span><span class="sxs-lookup"><span data-stu-id="de147-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="de147-153">Topologias suportadas para Lync Server 2013 e Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="de147-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="de147-154">O Lync Server 2013 oferece as seguintes maneiras de configurar o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="de147-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="de147-155">Dependendo das suas necessidades, você pode:</span><span class="sxs-lookup"><span data-stu-id="de147-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="de147-156">**Instale o Lync Server 2013 e o servidor do Office Web Apps no local por meio do firewall da sua organização e na mesma zona de rede.**</span><span class="sxs-lookup"><span data-stu-id="de147-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="de147-157">Com essa topologia, o acesso externo ao servidor do Office Web Apps será fornecido pelo servidor de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="de147-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="de147-158">O Lync Server 2013 e o servidor do Office Web Apps (ou um farm do servidor do Office Web Apps) estão instalados no local e por trás do firewall da sua organização.</span><span class="sxs-lookup"><span data-stu-id="de147-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="de147-159">O ideal é que você instale o servidor do Office Web Apps na mesma zona de rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de147-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="de147-160">Os clientes externos do Lync podem se conectar ao Lync Server 2013 e ao servidor do Office Web Apps usando um servidor proxy reverso, que é um servidor que toma solicitações da Internet e as encaminha para a rede interna.</span><span class="sxs-lookup"><span data-stu-id="de147-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="de147-161">(Os clientes internos não precisam usar o servidor proxy reverso, pois podem se conectar diretamente ao servidor do Office Web Apps.) Essa topologia funciona melhor se você quiser usar um farm dedicado do servidor do Office Web Apps que é usado apenas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de147-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="de147-162">**Usando um servidor do Office Web Apps implantado externamente**</span><span class="sxs-lookup"><span data-stu-id="de147-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="de147-163">Nesta topologia, o Lync Server 2013 é implantado localmente e usa um servidor do Office Web Apps implantado fora da zona de rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de147-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="de147-164">Isso pode acontecer quando o servidor do Office Web Apps é compartilhado entre vários aplicativos na empresa e é implantado em uma rede que requer o Lync Server para usar a interface externa do servidor do Office Web Apps e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="de147-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="de147-165">Não é necessário instalar um servidor de proxy reverso; em vez disso, todas as solicitações do servidor do Office Web Apps para o Lync Server 2013 são roteadas através do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="de147-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="de147-166">Os seus clientes internos e externos do Lync se conectam ao servidor do Office Web Apps usando a URL externa.</span><span class="sxs-lookup"><span data-stu-id="de147-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="de147-167">Se o servidor do Office Web Apps for implantado fora do seu firewall interno, selecione a opção o **servidor do Office Web Apps é implantado em uma rede externa (ou seja, perímetro/Internet)** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="de147-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="de147-168">Para obter mais detalhes, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="de147-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="de147-169">Independente da topologia selecionada, é fundamental que as portas de firewall certas estejam abertas.</span><span class="sxs-lookup"><span data-stu-id="de147-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="de147-170">Você deve verificar se os nomes DNS, endereços IP e portas não são bloqueados por firewalls no servidor do Office Web Apps, no balanceador de carga ou no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de147-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de147-171">Outra opção para fornecer acesso externo ao servidor do Office Web Apps é implantar o servidor na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="de147-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="de147-172">Se você optar por fazer isso, tenha em mente que a instalação do servidor do Office Web Apps exige que o computador servidor seja membro do seu domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="de147-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="de147-173">A menos que a política de rede permita que os computadores na rede de perímetro sejam membros do domínio do Active Directory, é recomendável que você não instale o servidor do Office Web Apps na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="de147-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="de147-174">Em vez disso, você deve instalar o servidor do Office Web Apps na rede interna e fornecer acesso de usuário externo através do servidor de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="de147-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

