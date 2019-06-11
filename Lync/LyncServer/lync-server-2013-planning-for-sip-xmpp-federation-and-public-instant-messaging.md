---
title: Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="51f82-102">Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51f82-103">_**Tópico da última modificação:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="51f82-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="51f82-104">Os servidores de borda podem ser configurados para permitir que seus usuários internos e externos tenham acesso a contatos em organizações ou serviços de parceiros.</span><span class="sxs-lookup"><span data-stu-id="51f82-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="51f82-105">As federações, pois esses contratos de parceiros são conhecidos, podem fornecer qualquer um dos itens a seguir ou todos eles para os contatos da sua organização na Federação de parceiros ou contatos na Federação de parceiros para o seu:</span><span class="sxs-lookup"><span data-stu-id="51f82-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="51f82-106">Mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="51f82-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="51f82-107">Colaboração e conferência, por exemplo: conferência via Web</span><span class="sxs-lookup"><span data-stu-id="51f82-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="51f82-108">Conferência de áudio, videoconferência ou ambos</span><span class="sxs-lookup"><span data-stu-id="51f82-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="51f82-109">Em alguns casos, a comunicação, por exemplo, mensagens instantâneas (IM) e presença entre um Microsoft Lync Server 2013 e um contato XMPP (Extensible Messaging and Presence Protocol), é somente ponto-a-ponto-dando suporte somente você e o contato no federado sócio.</span><span class="sxs-lookup"><span data-stu-id="51f82-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="51f82-110">Em outros casos, como um Lync Server, Lync Server 2010 para Lync Server 2013 Federation, vários participantes podem ser convidados para ingressar na conversa.</span><span class="sxs-lookup"><span data-stu-id="51f82-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="51f82-111">Federação do Lync Server e do Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="51f82-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="51f82-112">Federação entre o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server oferece suporte a comunicações ponto a ponto e de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="51f82-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="51f82-113">As conversas ponto a ponto podem ser escalonadas para conversas com vários participantes, permitindo reuniões ad hoc.</span><span class="sxs-lookup"><span data-stu-id="51f82-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="51f82-114">Reuniões: Webconferência ou conferências de áudio/visuais – podem ser programadas para incluir contatos dentro da sua organização e contatos em parceiros com os quais você se federa.</span><span class="sxs-lookup"><span data-stu-id="51f82-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="51f82-115">A Federação apareceu primeiro no Microsoft Office Live Communications Server 2005 e com suporte um tipo de Federação, Federação direta.</span><span class="sxs-lookup"><span data-stu-id="51f82-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="51f82-116">A Federação direta exigia que você saiba o domínio SIP (Session Initiation Protocol) do parceiro de Federação e o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro.</span><span class="sxs-lookup"><span data-stu-id="51f82-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="51f82-117">O Live Communications Server 2005 com SP1 introduziu tipos de Federação adicionais, todos os registros SRV do sistema de nome de domínio (DNS) necessários a serem publicados pelo parceiro federado para localizar o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="51f82-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="51f82-118">A terminologia do lançamento era:</span><span class="sxs-lookup"><span data-stu-id="51f82-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="51f82-119">*Abrir a Federação aprimorada*: aceitar qualquer nome de domínio SIP e usar o SRV DNS para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="51f82-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="51f82-120">*Federação aprimorada*: configurar o nome de domínio SIP do parceiro como um parceiro de Federação para a sua organização e usar o SRV DNS para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="51f82-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="51f82-121">*Federação direta*: configurar o nome de domínio SIP do parceiro e o FQDN para o servidor de borda do parceiro</span><span class="sxs-lookup"><span data-stu-id="51f82-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="51f82-122">*Lista de permissões do servidor*: aceitar qualquer domínio, usar o SRV DNS para localizar o servidor de borda de um provedor de hospedagem ou um provedor de conectividade de mensagens instantâneas (IM) público</span><span class="sxs-lookup"><span data-stu-id="51f82-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="51f82-123">O Microsoft Office Communications Server 2007 introduziu o nome atualizado dos tipos de Federação para definir melhor o que cada tipo de Federação realmente realizou:</span><span class="sxs-lookup"><span data-stu-id="51f82-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="51f82-124">A Federação aprimorada aberta se tornou conhecida como *domínio de parceiro descoberto*</span><span class="sxs-lookup"><span data-stu-id="51f82-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="51f82-125">A Federação aprimorada se tornou conhecida como *domínio de parceiro permitido*</span><span class="sxs-lookup"><span data-stu-id="51f82-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="51f82-126">A Federação direta se tornou conhecida como *servidor parceiro permitido*</span><span class="sxs-lookup"><span data-stu-id="51f82-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="51f82-127">A lista de permissões do servidor se tornou conhecida como *provedor de hospedagem* e provedor de mensagens de chat *públicas*</span><span class="sxs-lookup"><span data-stu-id="51f82-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="51f82-128">O Microsoft Lync Server 2010 introduziu uma definição mais estreita do provedor de Hospedagem de acordo com o Microsoft Lync Online 2010 e o Microsoft Office 365 e também o fez sujeito à mesma lista permitida definida pelo tipo de Federação do domínio parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="51f82-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="51f82-129">Habilitar a Federação entre o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server usa os servidores de borda e proxies reverso para impor as regras e os domínios de parceiros permitidos que você definir.</span><span class="sxs-lookup"><span data-stu-id="51f82-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="51f82-130">De uma perspectiva de planejamento, a Federação com outro Lync Server, o Office Communications Server exige o seguinte:</span><span class="sxs-lookup"><span data-stu-id="51f82-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="51f82-131">Habilite a Federação no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="51f82-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="51f82-132">Para obter detalhes, consulte o tópico de implantação Configurando a [Federação do SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="51f82-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="51f82-133">Determine suas necessidades para descoberta de domínio federado:</span><span class="sxs-lookup"><span data-stu-id="51f82-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="51f82-134">Para a configuração manual da Federação, você deve ter o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro e do nome do domínio, ou nome do domínio online, que é inserido no painel de controle do Lync Server, **agrupamento e acesso externo**, **SIP Domínios federados**.</span><span class="sxs-lookup"><span data-stu-id="51f82-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="51f82-135">Crie uma **nova** política ou **edite** uma política existente para permitir ou bloquear domínios por FQDN.</span><span class="sxs-lookup"><span data-stu-id="51f82-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="51f82-136">A configuração manual do servidor de borda do parceiro de Federação está sujeita a falhas caso o parceiro altere o endereço IP do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="51f82-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="51f82-137">Para <STRONG>novos domínios federados SIP</STRONG>, você deve fornecer o <STRONG>nome de domínio (ou FQDN)</STRONG> para o Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="51f82-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="51f82-138">Para o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server, você também deve fornecer um <STRONG>serviço de borda de acesso (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="51f82-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="51f82-139">Para a Federação de parceiro descoberto, em que os parceiros podem descobrir seu servidor de borda, você cria um registro SRV \_em seu DNS-sipfederationtls externo. \_TCP.contoso.com – que aponta para a porta 5061 e para o registro do host (A) de seu servidor de borda</span><span class="sxs-lookup"><span data-stu-id="51f82-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="51f82-140">Se você estiver oferecendo suporte para clientes móveis do Microsoft Lync no Windows Phone ou no iPhone do Apple, no iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar o sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="51f82-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="51f82-141">&lt;Registros SRV&gt; do domínio SIP para cada domínio SIP para os quais você tem clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="51f82-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="51f82-142">Android e Nokia Symbian Lync Mobile não use a notificação por push e não está sujeito a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="51f82-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="51f82-143">Configurar políticas de acesso de usuários externos para dar suporte a domínios federados</span><span class="sxs-lookup"><span data-stu-id="51f82-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="51f82-144">Abra portas de firewall para o protocolo SIP, conferência da Web e áudio/visual para acomodar a Federação ou os contatos que você está habilitando.</span><span class="sxs-lookup"><span data-stu-id="51f82-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="51f82-145">Para obter detalhes, consulte: [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="51f82-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="51f82-146">As informações a seguir ajudarão você a definir os requisitos de certificado, de porta/protocolo e DNS para federação com o Microsoft Lync Server 2013 e o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="51f82-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="51f82-147">O planejamento de certificados, firewall e requisitos de porta/protocolo e requisitos de DNS geralmente é um processo direto se você planejou ou implantou seus servidores de borda do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51f82-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="51f82-148">Como a Federação é um recurso adicional que usa o servidor de borda existente, os requisitos de planejamento geralmente são atendidos pelo planejamento e implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="51f82-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="51f82-149">Você deve usar as tabelas a seguir para determinar se os seus requisitos são atendidos e fazer alterações de acordo com a porta/protocolo e DNS.</span><span class="sxs-lookup"><span data-stu-id="51f82-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="51f82-150">Se você tiver um pool de servidores de borda e estiver conferindo-se com os parceiros do Lync Server 2013 ou Lync Server 2010, poderá usar o balanceamento de carga DNS ou os balanceadores de carga de hardware nos lados internos e externos dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="51f82-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="51f82-151">Se você estiver fazendo a Federação com o Office Communications Server 2007 ou o Office Communications Server 2007 R2, o balanceamento de carga de hardware fornecerá suporte de failover em caso de um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="51f82-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="51f82-152">O Office Communications Server 2007 e o Office Communications Server 2007 R2 não têm reconhecimento de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="51f82-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="51f82-153">Os servidores de borda de parceiro estabelecerão comunicação com o primeiro servidor de borda no pool que responde.</span><span class="sxs-lookup"><span data-stu-id="51f82-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="51f82-154">Se esse servidor de borda falhar, a comunicação não executará automaticamente o failover.</span><span class="sxs-lookup"><span data-stu-id="51f82-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="51f82-155">Os requisitos do certificado geralmente são atendidos pelo planejamento de certificados para o servidor de borda escolhido ou plano do servidor de borda em pool.</span><span class="sxs-lookup"><span data-stu-id="51f82-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="51f82-156">Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="51f82-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="51f82-157">A conectividade de mensagens instantâneas públicas é uma classe de Federação e está configurada para permitir que os usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="51f82-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="51f82-158">Contatos do Messenger</span><span class="sxs-lookup"><span data-stu-id="51f82-158">Messenger contacts</span></span>

  - <span data-ttu-id="51f82-159">Instant\!</span><span class="sxs-lookup"><span data-stu-id="51f82-159">Yahoo\!</span></span> <span data-ttu-id="51f82-160">contatos</span><span class="sxs-lookup"><span data-stu-id="51f82-160">contacts</span></span>

  - <span data-ttu-id="51f82-161">Contatos do America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="51f82-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="51f82-162">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="51f82-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="51f82-163">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="51f82-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="51f82-164">Messenger até a data de desligamento do serviço (a data exata ainda precisa ser decidida, mas não mais cedo que 2013).</span><span class="sxs-lookup"><span data-stu-id="51f82-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="51f82-165">O PIC USL é uma licença de assinatura por usuário e por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="51f82-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="51f82-166">Spam.</span><span class="sxs-lookup"><span data-stu-id="51f82-166">Messenger.</span></span> <span data-ttu-id="51f82-167">O recurso da Microsoft para fornecer esse serviço tem o apoio acordado do Yahoo!, o contrato subjacente para o qual não será renovado.</span><span class="sxs-lookup"><span data-stu-id="51f82-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="51f82-168">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="51f82-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="51f82-169">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="51f82-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="51f82-170">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de mensagens instantâneas e de voz.</span><span class="sxs-lookup"><span data-stu-id="51f82-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="51f82-171">Essa classe de Federação requer as seguintes considerações de planejamento:</span><span class="sxs-lookup"><span data-stu-id="51f82-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="51f82-172">Os usuários do Windows Live Messenger podem ter áudio/comunicação visual ponto a ponto com usuários do Lync Server 2013, além de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="51f82-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="51f82-173">Seus servidores de borda devem atender a requisitos específicos de portabilidade e protocolo.</span><span class="sxs-lookup"><span data-stu-id="51f82-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="51f82-174">Para obter detalhes, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f82-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="51f82-175">O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles geralmente usados no planejamento e na implantação do servidor de borda típico que está fornecendo a Federação.</span><span class="sxs-lookup"><span data-stu-id="51f82-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="51f82-176">O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um uso avançado de chave (EKU) do cliente.</span><span class="sxs-lookup"><span data-stu-id="51f82-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="51f82-177">Federação de protocolo de presença e mensagens extensíveis (XMPP)</span><span class="sxs-lookup"><span data-stu-id="51f82-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="51f82-178">As versões anteriores do Lync Server e do Office Communications Server forneciam um gateway de protocolo de presença e mensagens (XMPP) extensível que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="51f82-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="51f82-179">No Microsoft Lync Server 2013, a funcionalidade XMPP pode ser implantada como um recurso.</span><span class="sxs-lookup"><span data-stu-id="51f82-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="51f82-180">A funcionalidade XMPP é instalada em duas partes: um proxy do XMPP que é executado no servidor de borda e o gateway de XMPP que é executado nos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="51f82-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="51f82-181">A implantação e a configuração do XMPP são abordadas na [implantação de acesso ao usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) você planeja oferecer suporte a XMPP em sua organização definindo regras de porta e protocolo em seu firewall, configuração de certificados e adicionar DNS registos.</span><span class="sxs-lookup"><span data-stu-id="51f82-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="51f82-182">Os tópicos a seguir nesta seção resumem as informações que você precisará para planejar com êxito a Federação do XMPP para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="51f82-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="51f82-p120">O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="51f82-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="51f82-185">Não há suporte para a Federação do XMPP para usuários que são hospedados em aparelhos de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="51f82-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="51f82-186">Isso se aplica a ambos ver informações de presença e troca de mensagens INSTANTÂNEAs.</span><span class="sxs-lookup"><span data-stu-id="51f82-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="51f82-187">Nos tópicos a seguir, contenham orientação para definir certificados, portas de firewall e entradas de DNS para os tipos de cenários de Federação com suporte.</span><span class="sxs-lookup"><span data-stu-id="51f82-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="51f82-188">Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="51f82-189">Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="51f82-190">Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51f82-191">Confira também</span><span class="sxs-lookup"><span data-stu-id="51f82-191">See Also</span></span>


[<span data-ttu-id="51f82-192">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="51f82-193">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="51f82-194">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="51f82-195">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="51f82-196">Gerenciar configuração da borda de acesso para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="51f82-197">Gerenciar domínios SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="51f82-198">Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51f82-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

