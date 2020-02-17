---
title: Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d0572ad17d5359cf082c6bd06ab722d8322180e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="7c460-102">Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c460-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c460-103">_**Última modificação do tópico:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="7c460-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="7c460-104">Um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) é um aplicativo somente de script que usa uma linguagem de script em vez da API do Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="7c460-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="7c460-105">O MSPL fornece controle mais granular sobre os comportamentos de filtragem e proxy, além de um recurso para despachar mensagens específicas para aplicativos SIP baseados em transações.</span><span class="sxs-lookup"><span data-stu-id="7c460-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="7c460-106">O MSPL é usado especificamente para filtrar e rotear mensagens SIP.</span><span class="sxs-lookup"><span data-stu-id="7c460-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="7c460-107">Os aplicativos do MSPL são executados no mesmo processo que o módulo userservices, enquanto um programa baseado na API do Lync 2010 é executado em um processo separado.</span><span class="sxs-lookup"><span data-stu-id="7c460-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="7c460-108">Você pode usar a página **aplicativo de servidor** no grupo **topologia** do painel de controle do Lync Server para ver uma lista de aplicativos de servidor do MSPL que são executados em servidores front-end no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c460-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="7c460-109">A lista mostra os scripts disponíveis para cada pool, bem como se eles estão habilitados ou críticos.</span><span class="sxs-lookup"><span data-stu-id="7c460-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="7c460-110">Os scripts são executados na ordem em que são listados.</span><span class="sxs-lookup"><span data-stu-id="7c460-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="7c460-111">Eles incluem:</span><span class="sxs-lookup"><span data-stu-id="7c460-111">These scripts include the following:</span></span>

  - <span data-ttu-id="7c460-112">O ClientVersionFilter fornece ao administrador uma maneira de especificar a versão de clientes com suporte em um pool.</span><span class="sxs-lookup"><span data-stu-id="7c460-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="7c460-113">O filtro de versão do cliente verifica a versão do cliente e pode impedir que o cliente faça logon ou apresente o usuário com uma mensagem que indica que ele está usando um cliente que não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="7c460-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="7c460-114">O filtro de versão do cliente também pode ser configurado para exibir uma mensagem para o usuário que contém a URL da versão mais recente para download do cliente.</span><span class="sxs-lookup"><span data-stu-id="7c460-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="7c460-115">TranslationService converte um número que um usuário disca para um número E. 164 de acordo com as regras de normalização definidas pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="7c460-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="7c460-116">Para obter detalhes, consulte [regras de conversão no Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="7c460-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="7c460-117">O IncomingFederation impõe a validação de Federação no nível do locatário para mensagens de entrada e de inter-locatário de implantações externas.</span><span class="sxs-lookup"><span data-stu-id="7c460-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="7c460-118">Userservices é o componente de registrador SIP, presença e conferência de um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7c460-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="7c460-119">Ele oferece recursos de IM, presença e conferência intimamente integrados, criados na parte superior do proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="7c460-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="7c460-120">InterClusterRouting é responsável por rotear chamadas para o pool de registradores primários do chamador.</span><span class="sxs-lookup"><span data-stu-id="7c460-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="7c460-121">Para obter detalhes, consulte [componentes de VoIP do servidor front-end para Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="7c460-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="7c460-122">IIMFilter (filtro de IM inteligente) bloqueia mensagens que contêm URLs que podem ser clicadas ou que tentam iniciar transferências de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7c460-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="7c460-123">O IIMFilter também verifica a versão do cliente em nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="7c460-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="7c460-124">IIMFilter afeta transferências de arquivos que são iniciadas usando o Lync Server ou o Communicator.</span><span class="sxs-lookup"><span data-stu-id="7c460-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="7c460-125">Por padrão, os links que podem ser clicados são desabilitados adicionando um caractere de sublinhado antes do primeiro caractere do link.</span><span class="sxs-lookup"><span data-stu-id="7c460-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="7c460-126">Um administrador pode alterar esse comportamento para que o link seja bloqueado, caso em que as mensagens que contenham URLs de clique ou que tentam iniciar uma transferência de arquivo sejam bloqueadas pelo servidor para atingir seus destinos pretendidos.</span><span class="sxs-lookup"><span data-stu-id="7c460-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="7c460-127">O IIMFilter está instalado em todos os servidores que executam o Lync Server, exceto servidores proxy e servidores de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7c460-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="7c460-128">UserPinService é usado para verificar números de identificação pessoal do usuário (PINs) para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="7c460-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="7c460-129">Defaultrouting é o aplicativo de roteamento padrão para servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c460-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="7c460-130">Ele é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="7c460-130">It is enabled by default.</span></span> <span data-ttu-id="7c460-131">O aplicativo de roteamento é instalado em todos os servidores Standard Edition e Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7c460-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="7c460-132">ExumRouting roteia chamadas para a UM (Unificação de mensagens) do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7c460-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="7c460-133">ExumRouting determina o servidor de UM do Exchange apropriado para direcionar a chamada quando houver uma nova mensagem de caixa postal para o depósito.</span><span class="sxs-lookup"><span data-stu-id="7c460-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="7c460-134">O ExumRouting também lida com outros aspectos de integração do UM do Exchange, incluindo o roteamento para o atendedor automático e o acesso ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="7c460-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="7c460-135">OutboundRouting determina o gateway que roteia uma chamada para um número de telefone de acordo com o número discado e a autorização de discagem do usuário.</span><span class="sxs-lookup"><span data-stu-id="7c460-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="7c460-136">OutboundRouting também gerencia o redirecionamento de chamadas se um gateway não puder processar uma chamada.</span><span class="sxs-lookup"><span data-stu-id="7c460-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="7c460-137">O QoEAgent recebe relatórios de dados de QoE (qualidade da experiência) de pontos de extremidade por meio de solicitações de serviço SIP e envia os dados para a fila de destino no servidor de monitoramento ou para consumidores de terceiros usando HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="7c460-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="7c460-138">Para obter detalhes, consulte [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="7c460-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="7c460-139">O OutgoingFederation impõe a validação de Federação em nível de locatário para mensagens indo para uma implantação externa de destino.</span><span class="sxs-lookup"><span data-stu-id="7c460-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="7c460-140">Os proxies do AcpRouting CONVIDEm solicitações destinadas ao provedor de audioconferência para o gateway de provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7c460-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="7c460-141">Os scripts executados em servidores de borda incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7c460-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="7c460-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="7c460-142">IIMFilter</span></span>

  - <span data-ttu-id="7c460-143">OptionsHandler responderá às solicitações de opções de entrada com **200 OK** se a solicitação for destinada ao servidor atual.</span><span class="sxs-lookup"><span data-stu-id="7c460-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="7c460-144">Isso é usado para validação de topologia.</span><span class="sxs-lookup"><span data-stu-id="7c460-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7c460-145">Confira Também</span><span class="sxs-lookup"><span data-stu-id="7c460-145">See Also</span></span>


[<span data-ttu-id="7c460-146">Habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c460-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="7c460-147">Marcar um aplicativo de idioma de processamento SIP da Microsoft (MSPL) como crítico ou não crítico no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c460-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

