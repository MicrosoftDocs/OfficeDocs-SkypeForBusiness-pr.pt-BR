---
title: 'Lync Server 2013: Alterações no Lync Server que afetam o planejamento do Servidor de Borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="93d00-102">Alterações no Lync Server 2013 que afetam o planejamento do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="93d00-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93d00-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="93d00-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="93d00-104">O Lync Server 2013 introduz novos recursos que ampliam os recursos e métodos de comunicação para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="93d00-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="93d00-105">Além disso, o Lync Server 2013 introduz alterações em serviços existentes para integrar melhor e estender os serviços que estão disponíveis para sua organização.</span><span class="sxs-lookup"><span data-stu-id="93d00-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="93d00-106">Veja a seguir um resumo das alterações que podem afetar o planejamento e a implantação de serviços do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93d00-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="93d00-107">Suporte para endereçamento IPv6</span><span class="sxs-lookup"><span data-stu-id="93d00-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="93d00-108">O Lync Server 2013 dá suporte ao endereçamento IPv6 para todos os serviços de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="93d00-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="93d00-109">Se você tiver fornecido endereços IPv6 para as interfaces por meio da configuração no Windows Server, poderá usar endereços IPv6 na configuração do servidor de borda por meio da configuração do endereço IP no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="93d00-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="93d00-110">Além disso, o protocolo de presença e mensagens extensível (XMPP) é compatível com IPv6.</span><span class="sxs-lookup"><span data-stu-id="93d00-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="93d00-111">Nenhuma configuração adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="93d00-111">No additional configuration is required.</span></span> <span data-ttu-id="93d00-112">Se o IPv6 estiver configurado na topologia, o XMPP usará IPv6 (quando necessário).</span><span class="sxs-lookup"><span data-stu-id="93d00-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="93d00-113">Um requisito adicional para dar suporte ao IPv6 no Lync Server 2013 é criar registros de sistema de nome de domínio para registros que devem ser descobertos e resolvidos para um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="93d00-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="93d00-114">O DNS IPv6 usa registros de host que são definidos como **aaaa** e chamados "quad-a".</span><span class="sxs-lookup"><span data-stu-id="93d00-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="93d00-115">Outros tipos de registro são consistentes com seus correspondentes IPv4.</span><span class="sxs-lookup"><span data-stu-id="93d00-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="93d00-116">Suporte para implantação de protocolo de presença e mensagens extensíveis (XMPP)</span><span class="sxs-lookup"><span data-stu-id="93d00-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="93d00-117">O servidor de borda introduz um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP (implantado em seus servidores front-end).</span><span class="sxs-lookup"><span data-stu-id="93d00-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="93d00-118">Você pode implantar a Federação do XMPP como um componente opcional.</span><span class="sxs-lookup"><span data-stu-id="93d00-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="93d00-119">Ao adicionar e configurar o XMPP proxy e o gateway do XMPP, você pode habilitar seus usuários do Microsoft Lync 2013 para adicionar contatos de parceiros baseados no XMPP para mensagens instantâneas (IM) e presença.</span><span class="sxs-lookup"><span data-stu-id="93d00-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93d00-120">Atualmente, os serviços do XMPP no servidor de borda só fornecem mensagens instantâneas e presença entre os clientes do Lync Server e os contatos baseados no XMPP.</span><span class="sxs-lookup"><span data-stu-id="93d00-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="93d00-121">Além disso, o XMPP é hospedado em apenas um site.</span><span class="sxs-lookup"><span data-stu-id="93d00-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="93d00-p106">O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="93d00-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="93d00-124">Suporte para a interrupção da autenticação de áudio/vídeo e do servidor para certificados de autenticação do servidor</span><span class="sxs-lookup"><span data-stu-id="93d00-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="93d00-125">Um certificado é usado para gerar tokens que são emitidos para clientes e outros consumidores do serviço de autenticação A/V e para autenticação do servidor para o servidor.</span><span class="sxs-lookup"><span data-stu-id="93d00-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="93d00-126">O certificado de autenticação de áudio/vídeo é do tipo *AudioVideoAuthentication* e o certificado de autenticação do servidor para o servidor é do tipo *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="93d00-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="93d00-127">Para autenticação de áudio/vídeo, os tokens são usados para autenticar solicitações de alocação de porta e os tokens são armazenados em cache por até 8 horas – o tempo de vida padrão do token.</span><span class="sxs-lookup"><span data-stu-id="93d00-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="93d00-128">Em operação normal, esse é um método muito confiável para criar e distribuir material de autenticação para os consumidores a/V.</span><span class="sxs-lookup"><span data-stu-id="93d00-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="93d00-129">No entanto, os certificados têm uma vida útil finita e expiram em uma data e hora predefinidas (com base na data de criação e nas políticas impostas na autoridade de certificação que criou o certificado, geralmente há 2 anos para esse tipo de certificado).</span><span class="sxs-lookup"><span data-stu-id="93d00-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="93d00-130">Quando o certificado expira, todos os tokens criados pelo certificado expirado e armazenados em cache por consumidores se tornam inválidos.</span><span class="sxs-lookup"><span data-stu-id="93d00-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="93d00-131">Qualquer tentativa de usar um token criado com um certificado expirado resultará em falha nas atribuições de retransmissão de mídia e nas sessões de áudio/vídeo atuais.</span><span class="sxs-lookup"><span data-stu-id="93d00-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="93d00-132">O cliente precisaria adquirir um novo token criado por um certificado válido para retomar a funcionalidade normal de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="93d00-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="93d00-133">A autenticação do servidor para o servidor é gerenciada por um certificado global que é solicitado e aplicado a todos os servidores na implantação.</span><span class="sxs-lookup"><span data-stu-id="93d00-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="93d00-134">O certificado é responsável pela autenticação de servidores no Lync Server 2013, bem como pela autenticação do Exchange 2013 e do Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93d00-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="93d00-135">Para obter mais informações sobre como funciona a autenticação do servidor com o servidor, consulte Gerenciando a autenticação de servidor [para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="93d00-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="93d00-136">Uma diferença muito importante entre o processo de autenticação de áudio/vídeo e o processo de autenticação do servidor no servidor é o tempo de vida da autenticação ou dos tokens.</span><span class="sxs-lookup"><span data-stu-id="93d00-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="93d00-137">Para a autenticação de áudio/vídeo, a autenticação expira após oito horas.</span><span class="sxs-lookup"><span data-stu-id="93d00-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="93d00-138">A autenticação de servidor para servidor tem uma vida útil de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="93d00-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="93d00-139">Você deve planejar adequadamente para cada um dos tipos de certificado.</span><span class="sxs-lookup"><span data-stu-id="93d00-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="93d00-140">Novo para o Lync Server 2013 é a capacidade de transferir um certificado de autenticação de áudio/vídeo e um certificado de autenticação de servidor para servidor com antecedência da expiração do certificado atual.</span><span class="sxs-lookup"><span data-stu-id="93d00-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="93d00-141">O novo certificado é usado para gerar novos tokens ou novas solicitações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="93d00-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="93d00-142">mas retém o certificado antigo para verificar as sessões e autenticações atuais..</span><span class="sxs-lookup"><span data-stu-id="93d00-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="93d00-143">O que isso faz é evitar efetivamente praticamente todas as falhas devido a expirações de token e certificado.</span><span class="sxs-lookup"><span data-stu-id="93d00-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="93d00-144">Para obter detalhes sobre esse recurso e como configurá-lo, consulte [preparando certificados do AV e do OAuth no Lync Server 2013 using-roll Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="93d00-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="93d00-145">Dependência reduzida na afinidade baseada em cookies</span><span class="sxs-lookup"><span data-stu-id="93d00-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="93d00-146">Em versões anteriores do Lync Server e do Office Communications Server, a afinidade baseada em cookies era usada pelos serviços Web para garantir que o estado da sessão do cliente e dos serviços Web tenha sido mantido.</span><span class="sxs-lookup"><span data-stu-id="93d00-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="93d00-147">Os serviços Web do Lync Server 2013 usam um mecanismo de afinidade interno que elimina a maioria dos requisitos para afinidade baseada em cookies.</span><span class="sxs-lookup"><span data-stu-id="93d00-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="93d00-148">O cliente móvel do Microsoft Lync 2010 ainda deve usar afinidade baseada em cookies e exigirá a configuração da afinidade baseada em cookies até que você migre todos os clientes para o próximo cliente móvel do Microsoft Lync (data do lançamento ainda não determinado).</span><span class="sxs-lookup"><span data-stu-id="93d00-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="93d00-149">Para obter detalhes sobre a afinidade baseada em cookies no Lync Server 2013, consulte [componentes necessários para o acesso de usuários externos no Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="93d00-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="93d00-150">Aprimoramentos de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="93d00-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="93d00-151">O recurso descoberta automática no Lync Server 2013 permite que os clientes localizem recursos adicionais que são disponibilizados para comunicação.</span><span class="sxs-lookup"><span data-stu-id="93d00-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="93d00-152">A descoberta automática foi introduzida pela primeira vez na atualização cumulativa do Lync Server 2010: novembro de 2011 para Mobility e Microsoft Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="93d00-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="93d00-153">O recurso de descoberta automática (também conhecido pelos nomes de registros de DNS LyncDiscover e LyncDiscoverInternal) permite que os clientes localizem e usem serviços de mobilidade (para clientes móveis do Microsoft Lync 2010), o Microsoft Lync Web App e o Lync Web Scheduler, bem como comunicações com o Microsoft Exchange Server e o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="93d00-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="93d00-154">A descoberta automática é instalada como parte normal da configuração e implantação de sua infraestrutura e dos servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93d00-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="93d00-155">O construtor de topologias e o assistente de implantação do Lync Server eliminam a maioria das tarefas de configuração necessárias na atualização cumulativa do Lync Server 2010:2011 de novembro.</span><span class="sxs-lookup"><span data-stu-id="93d00-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="93d00-156">Serviços para clientes móveis</span><span class="sxs-lookup"><span data-stu-id="93d00-156">Services for Mobile Clients</span></span>

<span data-ttu-id="93d00-157">Apresentado na atualização cumulativa do Lync Server 2010: serviços de mobilidade de novembro de 2011 no Lync Server 2013 habilitar telefones celulares que executam dispositivos móveis do Lync e tablets com dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia para executar atividades como enviar e receber mensagens instantâneas, ver contatos e ver a presença.</span><span class="sxs-lookup"><span data-stu-id="93d00-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="93d00-158">Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas por meio de trabalho, de alcance de número único, caixa postal e notificação de chamada perdida.</span><span class="sxs-lookup"><span data-stu-id="93d00-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93d00-159">Os serviços de mobilidade usam o proxy reverso e os serviços publicados que são implantados em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="93d00-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="93d00-160">Nenhuma alteração é necessária para servidores Edge.</span><span class="sxs-lookup"><span data-stu-id="93d00-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="93d00-161">Minimamente, você precisa do SIP/TCP/5061from o servidor que executa o serviço de borda de acesso ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93d00-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="93d00-162">A função diretor é opcional</span><span class="sxs-lookup"><span data-stu-id="93d00-162">Director Role is Optional</span></span>

<span data-ttu-id="93d00-163">A função do servidor Diretor na topologia do Lync Server 2013 não mudou.</span><span class="sxs-lookup"><span data-stu-id="93d00-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="93d00-164">Ele ainda hospeda serviços Web, autentica solicitações do usuário recebidas e direciona os usuários externos para o pool inicial.</span><span class="sxs-lookup"><span data-stu-id="93d00-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="93d00-165">Ao alterar o diretor de uma função recomendada para uma função opcional, a Microsoft não pretende diminuir o valor do diretor.</span><span class="sxs-lookup"><span data-stu-id="93d00-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="93d00-166">A intenção é reduzir a contagem do servidor e outros requisitos de hardware (por exemplo, balanceadores de carga de hardware para o diretor) sem comprometer recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="93d00-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="93d00-167">Como os servidores de front-end podem fazer o mesmo trabalho que o diretor sem impacto nos serviços fornecidos, você pode implantar diretores se optar por fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="93d00-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="93d00-168">Você pode excluir com segurança o diretor com certeza de que os servidores de front-end fornecerão os mesmos serviços no lugar de um diretor.</span><span class="sxs-lookup"><span data-stu-id="93d00-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

