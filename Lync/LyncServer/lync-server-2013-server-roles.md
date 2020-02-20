---
title: Funções de servidor do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2166d6fb3f7f5c8c159c150cd9a0eff07e8fe0de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="a247b-102">Funções de servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a247b-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a247b-103">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="a247b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="a247b-104">Cada servidor que executa o Lync Server executa uma ou mais *funções de servidor*.</span><span class="sxs-lookup"><span data-stu-id="a247b-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="a247b-105">Uma função de servidor é um conjunto definido de funcionalidades do Lync Server fornecidas por esse servidor.</span><span class="sxs-lookup"><span data-stu-id="a247b-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="a247b-106">Você não precisa implantar todas as funções de servidor disponíveis na sua rede.</span><span class="sxs-lookup"><span data-stu-id="a247b-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="a247b-107">Instale somente as funções com a funcionalidade desejada.</span><span class="sxs-lookup"><span data-stu-id="a247b-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="a247b-108">Mesmo que você não esteja familiarizado com as funções de servidor no Lync Server, a ferramenta de planejamento poderá orientá-lo na melhor solução para os servidores que você precisa implantar, com base nos recursos desejados.</span><span class="sxs-lookup"><span data-stu-id="a247b-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="a247b-109">Esta seção fornece uma visão geral sobre as funções de servidor e os recursos gerais que eles fornecem:</span><span class="sxs-lookup"><span data-stu-id="a247b-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="a247b-110">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="a247b-110">Standard Edition Server</span></span>

  - <span data-ttu-id="a247b-111">Servidor Front-End e Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="a247b-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="a247b-112">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a247b-112">Edge Server</span></span>

  - <span data-ttu-id="a247b-113">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="a247b-113">Mediation Server</span></span>

  - <span data-ttu-id="a247b-114">Be</span><span class="sxs-lookup"><span data-stu-id="a247b-114">Director</span></span>

  - <span data-ttu-id="a247b-115">Servidor front-end de chats persistentes</span><span class="sxs-lookup"><span data-stu-id="a247b-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="a247b-116">Repositório de chats persistentes (servidor back-end de chats persistentes)</span><span class="sxs-lookup"><span data-stu-id="a247b-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="a247b-117">Repositório de conformidade de chats persistentes (servidor back-end de conformidade de chats persistentes)</span><span class="sxs-lookup"><span data-stu-id="a247b-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="a247b-118">Na maioria das funções de servidor, para escalabilidade e alta disponibilidade você pode implantar *pools* de vários servidores, todos executando a mesma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="a247b-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="a247b-119">Cada servidor em um pool deve executar uma função ou funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="a247b-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="a247b-120">Para a maioria dos tipos de pools no Lync Server, você deve implantar um balanceador de carga para espalhar o tráfego entre os vários servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="a247b-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="a247b-121">O Lync Server suporta o balanceamento de carga do DNS (sistema de nomes de domínio) e balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="a247b-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="a247b-122">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a247b-122">Standard Edition Server</span></span>

<span data-ttu-id="a247b-123">O servidor Standard Edition foi projetado para pequenas empresas e para projetos piloto de grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="a247b-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="a247b-124">Ele permite que muitos dos recursos do Lync Server, incluindo os bancos de dados necessários, sejam executados em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="a247b-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="a247b-125">Isso permite que você tenha a funcionalidade do Lync Server para um custo menor, mas não fornece uma solução real de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a247b-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="a247b-126">Servidor Standard Edition permite que você use mensagens instantâneas (IM), presença, conferência e Enterprise Voice, tudo em execução em um servidor.</span><span class="sxs-lookup"><span data-stu-id="a247b-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="a247b-127">Para uma solução de alta disponibilidade, use o Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a247b-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="a247b-128">Servidor de front-end e Servidor de back-end</span><span class="sxs-lookup"><span data-stu-id="a247b-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="a247b-129">No Lync Server Enterprise Edition, o servidor front-end é a função de servidor principal e executa muitas funções básicas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a247b-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="a247b-130">O servidor front-end, junto com os servidores back-end, são as únicas funções de servidor necessárias para estar em qualquer implantação do Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a247b-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="a247b-p106">Um *pool de Front-Ends* é um conjunto de servidores Front-End, configurados de forma idêntica, que trabalham juntos para fornecer serviços a um grupo de usuários comuns. Um pool de vários servidores executando a mesma função fornece a capacidade de escalabilidade e failover.</span><span class="sxs-lookup"><span data-stu-id="a247b-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="a247b-133">O servidor Front-End inclui:</span><span class="sxs-lookup"><span data-stu-id="a247b-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="a247b-134">Registro e autenticação de usuário</span><span class="sxs-lookup"><span data-stu-id="a247b-134">User authentication and registration</span></span>

  - <span data-ttu-id="a247b-135">Informações de presença e troca do cartão contato</span><span class="sxs-lookup"><span data-stu-id="a247b-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="a247b-136">Serviços de catálogo de endereço e expansão de lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="a247b-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="a247b-137">Funcionalidade de mensagens instantâneas, incluindo conferências de mensagens instantâneas com vários participantes</span><span class="sxs-lookup"><span data-stu-id="a247b-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="a247b-138">Webconferências, conferências de discagem PSTN e conferências A/V (se implantadas)</span><span class="sxs-lookup"><span data-stu-id="a247b-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="a247b-139">Hospedagem de aplicativos, para os dois aplicativos incluídos no Lync Server (por exemplo, o atendedor de conferência e o aplicativo de grupo de resposta) e aplicativos de terceiros</span><span class="sxs-lookup"><span data-stu-id="a247b-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="a247b-140">Opcionalmente, Monitoramento para coletar informações de uso na forma de CDRs (registros de detalhes de chamada) e CERs (registros de erros de chamada).</span><span class="sxs-lookup"><span data-stu-id="a247b-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="a247b-141">Essas informações fornecem métricas sobre a qualidade da mídia (áudio e vídeo) que atravessam sua rede para chamadas do Enterprise Voice e conferências A/V.</span><span class="sxs-lookup"><span data-stu-id="a247b-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="a247b-142">Componentes da Web para tarefas compatíveis com base na Web, como agendador da Web e iniciador de ingresso.</span><span class="sxs-lookup"><span data-stu-id="a247b-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="a247b-143">Opcionalmente, Arquivamento para arquivar comunicações de mensagens instantâneas e conteúdo de reunião por motivos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a247b-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="a247b-144">Para obter detalhes, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a247b-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="a247b-145">No Lync Server 2010 e versões anteriores, o monitoramento e o arquivamento eram funções de servidor separadas, não posicionadas no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a247b-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="a247b-146">Opcionalmente, e o chat persistente estiver habilitado, serviços Web de chat persistente para gerenciamento de salas de chat e serviços Web de chat persistente para upload/download de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a247b-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="a247b-p109">Os pools front-end também são o repositórios principal de dados de usuários e conferências. As informações sobre cada usuário são replicadas em três servidores front-end no pool, e o backup delas é realizado nos servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="a247b-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="a247b-149">Além disso, um pool de front-ends na implantação também executa o *servidor de gerenciamento central*, que gerencia e implanta dados básicos de configuração para todos os servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a247b-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="a247b-150">O servidor de gerenciamento central também fornece o Shell de gerenciamento do Lync Server e os recursos de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a247b-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="a247b-151">Os servidores de back-end são servidores de banco de dados executando o Microsoft SQL Server que fornecem os serviços de banco de dados para o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="a247b-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="a247b-152">Os servidores de back-end servem como repositórios de backup para os dados de usuário e conferência do pool e são os principais repositórios de outros bancos de dados, como o banco de dados do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="a247b-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="a247b-153">Você pode ter um único servidor back-end, mas uma solução que usa o espelhamento do SQL Server é recomendada para failover.</span><span class="sxs-lookup"><span data-stu-id="a247b-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="a247b-154">Os servidores de back-end não executam qualquer software do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a247b-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a247b-155">Não recomendamos colocar os bancos de dados do Lync Server com outros bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="a247b-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="a247b-156">Caso contrário, a disponibilidade e o desempenho poderão ser afetados.</span><span class="sxs-lookup"><span data-stu-id="a247b-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="a247b-157">As informações armazenadas nos bancos de dados do servidor Back-End incluem informações de presença, listas de contatos dos usuários, dados de conferência, incluindo os dados persistentes sobre o estado de todas as conferências atuais e dados de agendamento de conferência.</span><span class="sxs-lookup"><span data-stu-id="a247b-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="a247b-158">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a247b-158">Edge Server</span></span>

<span data-ttu-id="a247b-159">O Servidor de Borda permite que os usuários se comuniquem e colaborem com usuários fora dos firewalls da organização.</span><span class="sxs-lookup"><span data-stu-id="a247b-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="a247b-160">Esses usuários externos podem incluir os próprios usuários da organização que estão trabalhando fora do local, usuários de organizações de parceiros federados e usuários externos que tenham sido convidados a participar de conferências hospedadas na sua implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a247b-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="a247b-161">O servidor de borda também permite a conectividade para serviços públicos de conectividade de IM, incluindo Windows\!Live, AOL, Yahoo e Google Talk.</span><span class="sxs-lookup"><span data-stu-id="a247b-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="a247b-162">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="a247b-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="a247b-163">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="a247b-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="a247b-164">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="a247b-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="a247b-165">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="a247b-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="a247b-166">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="a247b-166">has been announced.</span></span> <span data-ttu-id="a247b-167">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a247b-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="a247b-168">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="a247b-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="a247b-169">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="a247b-169">Messenger.</span></span> <span data-ttu-id="a247b-170">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="a247b-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="a247b-171">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="a247b-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="a247b-172">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="a247b-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="a247b-173">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="a247b-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="a247b-174">A implantação do servidor de borda também habilita serviços de mobilidade, com suporte à funcionalidade do Lync em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="a247b-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="a247b-175">Os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades como enviar e receber mensagens instantâneas, exibir contatos e exibir presença.</span><span class="sxs-lookup"><span data-stu-id="a247b-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="a247b-176">Além disso, os dispositivos móveis suportam alguns recursos do Enterprise Voice, como clicar para participar de uma conferência, Chamada via Trabalho, acesso a único número, caixa postal e chamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="a247b-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="a247b-177">O recurso de mobilidade também oferece suporte a *notificações por push* para dispositivos móveis que não oferecem suporte a aplicativos em execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a247b-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="a247b-178">Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="a247b-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="a247b-179">Os servidores de borda também incluem um proxy XMPP completamente integrado, com um gateway XMPP incluído nos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a247b-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="a247b-180">Você pode configurar esses componentes do XMPP para permitir que seus usuários do Lync Server 2013 adicionem contatos de parceiros baseados no XMPP (como Google Talk) para mensagens instantâneas e presença.</span><span class="sxs-lookup"><span data-stu-id="a247b-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="a247b-181">Para obter detalhes, consulte [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a247b-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="a247b-182">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="a247b-182">Mediation Server</span></span>

<span data-ttu-id="a247b-183">O servidor de mediação é um componente necessário para a implementação da conferência de discagem e voz da empresa.</span><span class="sxs-lookup"><span data-stu-id="a247b-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="a247b-184">O servidor de mediação converte a sinalização e, em algumas configurações, mídia entre sua infraestrutura interna do Lync Server e um gateway PSTN (rede telefônica pública comutada), IP-PBX ou um tronco SIP (protocolo de iniciação de sessão).</span><span class="sxs-lookup"><span data-stu-id="a247b-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="a247b-185">Você pode executar o Servidor de Mediação colocado no mesmo servidor do servidor front-end ou separado em um pool de Servidor de Mediação independente.</span><span class="sxs-lookup"><span data-stu-id="a247b-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a247b-186">Para obter detalhes, consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a247b-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="a247b-187">Be</span><span class="sxs-lookup"><span data-stu-id="a247b-187">Director</span></span>

<span data-ttu-id="a247b-188">Os diretores podem autenticar solicitações de usuário do Lync Server, mas não hospedam contas de usuário nem fornecem serviços de presença ou conferência.</span><span class="sxs-lookup"><span data-stu-id="a247b-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="a247b-189">Os diretores são mais úteis para aprimorar a segurança em implantações que permitam o acesso de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="a247b-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="a247b-190">O diretor pode autenticar solicitações antes de enviá-las a servidores internos.</span><span class="sxs-lookup"><span data-stu-id="a247b-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="a247b-191">No caso de ataque de negação de serviço, o ataque termina no diretor e não atinge os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a247b-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="a247b-192">Para obter detalhes, consulte [cenários para o diretor no Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a247b-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="a247b-193">Funções de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a247b-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="a247b-p121">O chat persistente permite que os usuários participem de conversações baseadas em tópicos com várias pessoas. Essas conversas persistem ao longo do tempo. O servidor front-end de chat persistente executa o serviço de chat persistente. O servidor back-end de chat persistente armazena os dados de histórico e as informações sobre categorias e salas de chat. O servidor back-end de conformidade de chat persistente (opcional) pode armazenar o conteúdo de chats e eventos de conformidade para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a247b-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="a247b-198">Os servidores que executam o Lync Server Standard Edition também podem executar o chat persistente colocado no mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="a247b-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="a247b-199">Não é possível colocar o servidor front-end de chat persistente com o servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a247b-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="a247b-200">Para obter detalhes, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="a247b-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a247b-201">Confira também</span><span class="sxs-lookup"><span data-stu-id="a247b-201">See Also</span></span>


[<span data-ttu-id="a247b-202">Componente do servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a247b-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="a247b-203">Planejamento para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a247b-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="a247b-204">Planejamento para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a247b-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="a247b-205">Cenários para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a247b-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="a247b-206">Planejando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a247b-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

