---
title: 'Lync Server 2013: tarefas de implantação para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b81da85fb7aff98728d0a79478164436cce5194a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="55e5c-102">Tarefas de implantação para o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55e5c-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55e5c-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="55e5c-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="55e5c-104">Este tópico descreve as tarefas de implantação que devem ser realizadas para habilitar o controle de chamada remota para usuários no seu ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55e5c-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55e5c-105">Se você estiver migrando usuários previamente habilitados para controle de chamada remota no Microsoft Office Communicator 2007 R2, deverá executar uma tarefa de implantação adicional antes de começar a executar as tarefas de implantação de controle de chamada remota descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="55e5c-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="55e5c-106">Durante o processo de migração para o Lync Server, as entradas de aplicativos confiáveis (anteriormente conhecidas como <EM>entradas de host autorizadas</EM>) devem ser removidas usando as ferramentas administrativas do Office Communications Server 2007 R2, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="55e5c-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="55e5c-107">Para obter detalhes sobre como remover hosts autorizados, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">remover um host autorizado herdado no Lync Server 2013 (opcional)</A>.</span><span class="sxs-lookup"><span data-stu-id="55e5c-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="55e5c-108">Etapa 1: Instale e configure o Gateway SIP/CSTA para se comunicar com seu PBX</span><span class="sxs-lookup"><span data-stu-id="55e5c-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="55e5c-109">Você precisa instalar pelo menos um gateway SIP/CSTA que possa se conectar ao Lync Server e ao servidor de filial privada (PBX) existente no seu ambiente para fornecer recursos de controle de chamada remota aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="55e5c-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="55e5c-110">Um gateway SIP/CSTA é um gateway entre o SIP e um CSTA (aplicativo de telecomunicações com suporte por computador).</span><span class="sxs-lookup"><span data-stu-id="55e5c-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="55e5c-111">Independente de você instalar múltiplos gateways ou somente um, cada usuário pode ser configurado somente com um gateway ou PBX.</span><span class="sxs-lookup"><span data-stu-id="55e5c-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="55e5c-112">Se o PBX existente não tiver uma interface SIP/CSTA, implante um gateway SIP/CSTA que possa suportar o PBX, incluindo o suporte para protocolos de sinalização específicos do fornecedor do PBX proprietário.</span><span class="sxs-lookup"><span data-stu-id="55e5c-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="55e5c-113">Para obter os detalhes das capacidades, consulte cada fornecedor diretamente.</span><span class="sxs-lookup"><span data-stu-id="55e5c-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="55e5c-114">Quando estiver pronto para implantar um gateway SIP/CSTA que possa se integrar ao Lync Server para controle de chamada remota, consulte também o fornecedor do gateway ou a documentação do gateway do fornecedor sobre a sintaxe necessária para o gateway para as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="55e5c-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="55e5c-115">URI do Servidor de linha do gateway</span><span class="sxs-lookup"><span data-stu-id="55e5c-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="55e5c-116">URI da linha para usuários que serão atribuídos ao gateway</span><span class="sxs-lookup"><span data-stu-id="55e5c-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="55e5c-117">As configurações acima são exigidas durante a configuração do usuário e devem ser especificadas como esperado pelo gateway, para encaminhar e se conectar corretamente ao PBX.</span><span class="sxs-lookup"><span data-stu-id="55e5c-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="55e5c-118">Você pode consultar fornecedores no site do programa de interoperabilidade aberta do Microsoft Unified Communications em [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span><span class="sxs-lookup"><span data-stu-id="55e5c-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="55e5c-119">Etapa 2: configurar o Lync Server para rotear solicitações de CSTA para o gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="55e5c-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="55e5c-120">Você deve criar rotas estáticas em pools do Lync Server para o endereço de destino (URI de servidor) de todos os gateways SIP/CSTA em sua implantação para o qual você pretende rotear as solicitações de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="55e5c-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="55e5c-121">Crie também uma entrada de aplicativo confiável que corresponda a cada endereço de destino.</span><span class="sxs-lookup"><span data-stu-id="55e5c-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="55e5c-122">Quando você designar o gateway como um aplicativo confiável, ele receberá um status confiável para ser executado como parte do ambiente do Lync Server, embora seja desenvolvido por um terceiro (e execute o que é conhecido como um *serviço externo* , pois é um serviço que não é uma parte interna do produto).</span><span class="sxs-lookup"><span data-stu-id="55e5c-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="55e5c-123">Por fim, se o Lync Server se conectar ao gateway SIP/CSTA usando uma conexão TCP (Transmission Control Protocol) em vez de uma conexão TLS (Transport Layer Security), você também deve definir o endereço IP do gateway usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="55e5c-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="55e5c-124">Para obter detalhes sobre como configurar rotas estáticas, consulte [Configurar uma rota estática para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="55e5c-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="55e5c-125">Para obter detalhes sobre como configurar as entradas de aplicativos confiáveis, consulte [Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="55e5c-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="55e5c-126">Para obter detalhes sobre como definir um endereço IP de gateway SIP/CSTA no construtor de topologias, consulte [definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="55e5c-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="55e5c-127">Etapa 3: Configurar usuários do Lync para controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="55e5c-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="55e5c-128">Depois que os usuários tiverem sido habilitados para o Lync Server, você poderá usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para habilitá-los para controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="55e5c-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="55e5c-129">É durante esta etapa da implementação que você atribui a cada usuário um URI de servidor de linha e um URI de linha.</span><span class="sxs-lookup"><span data-stu-id="55e5c-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="55e5c-130">O URI do servidor de linha é o URI SIP do gateway SIP/CSTA que você planeja atribuir ao usuário.</span><span class="sxs-lookup"><span data-stu-id="55e5c-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="55e5c-131">O URI de linha é o número de telefone exclusivo atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="55e5c-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="55e5c-132">Para obter detalhes sobre como configurar usuários para controle de chamada remota, consulte [habilitar usuários do Lync para controle de chamada remota no Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="55e5c-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="55e5c-133">Etapa 4: Defina as regras de normalização do número de telefone do Lync Server</span><span class="sxs-lookup"><span data-stu-id="55e5c-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="55e5c-134">Em cenários de controle de chamada remota, o Lync Server usa regras de normalização de número de telefone para converter números de telefone que ele recebe do gateway SIP/CSTA para o formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="55e5c-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="55e5c-135">Os números de telefone devem estar neste formato padronizado para que certos recursos do controle de chamada remota funcionem corretamente.</span><span class="sxs-lookup"><span data-stu-id="55e5c-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="55e5c-136">O controle de chamada remota utiliza as mesmas regras de normalização do número de telefone que você configura para o Serviço de Agenda, que são diferentes das regras usadas para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55e5c-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="55e5c-137">Para obter detalhes sobre como o controle de chamada remota usa regras de normalização de número de telefone, consulte [controle de chamada remota e normalização de número de telefone no Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="55e5c-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="55e5c-138">Para obter detalhes sobre as regras de normalização de número de telefone do serviço de catálogo de endereços, consulte [Administração do serviço de catálogo de endereços no Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) , na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="55e5c-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

