---
title: Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2070d9e977a730b7c667a2c49a7e896d1309eef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="330d2-102">Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="330d2-103">_**Última modificação do tópico:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="330d2-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="330d2-104">Os servidores de borda podem ser configurados para permitir que os usuários internos e externos acessem contatos em organizações ou serviços de parceiros.</span><span class="sxs-lookup"><span data-stu-id="330d2-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="330d2-105">As federações, pois esses contratos de parceiros são conhecidos, podem fornecer qualquer um ou todos os seguintes itens para os contatos em sua organização na Federação de parceiros ou contatos na Federação de parceiro para o seu:</span><span class="sxs-lookup"><span data-stu-id="330d2-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="330d2-106">Sistema de mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="330d2-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="330d2-107">Colaboração e conferência, por exemplo – Webconferência</span><span class="sxs-lookup"><span data-stu-id="330d2-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="330d2-108">Audioconferência, conferência de vídeo ou ambos</span><span class="sxs-lookup"><span data-stu-id="330d2-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="330d2-109">Em alguns casos, a comunicação, por exemplo, mensagens instantâneas (IM) e presença entre o Microsoft Lync Server 2013 e um contato XMPP (Extensible Messaging and Presence Protocol), é ponto-a-ponto apenas que suporta apenas você e o contato no federado parceira.</span><span class="sxs-lookup"><span data-stu-id="330d2-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="330d2-110">Em outros casos, como um Lync Server, Lync Server 2010 para a Federação do Lync Server 2013, vários participantes podem ser convidados para entrar na conversa.</span><span class="sxs-lookup"><span data-stu-id="330d2-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="330d2-111">Federação do Lync Server e Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="330d2-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="330d2-112">Federação entre o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server suporta comunicação ponto a ponto e vários participantes.</span><span class="sxs-lookup"><span data-stu-id="330d2-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="330d2-113">As conversas ponto a ponto podem ser posicionadas para conversas de várias partes, permitindo reuniões locais.</span><span class="sxs-lookup"><span data-stu-id="330d2-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="330d2-114">Reuniões - Conferência da Web ou conferências áudio/visual - podem ser programadas para incluir contatos dentro da sua organização, assim como contatos em parceiros que você federar.</span><span class="sxs-lookup"><span data-stu-id="330d2-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="330d2-115">A Federação apareceu primeiro no Microsoft Office Live Communications Server 2005 e suportava um tipo de Federação, Federação direta.</span><span class="sxs-lookup"><span data-stu-id="330d2-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="330d2-116">A Federação direta exigia que você saiba o domínio SIP (Session Initiation Protocol) do parceiro de Federação e o FQDN (nome de domínio totalmente qualificado) do servidor de borda do parceiro.</span><span class="sxs-lookup"><span data-stu-id="330d2-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="330d2-117">O Live Communications Server 2005 com SP1 apresentou tipos de Federação adicionais, todos os quais os registros SRV do sistema de nomes de domínio (DNS) necessários serão publicados pelo parceiro federado para localizar seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="330d2-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="330d2-118">A terminologia para esta versão foi:</span><span class="sxs-lookup"><span data-stu-id="330d2-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="330d2-119">*Abrir Federação aprimorada*: aceitar qualquer nome de domínio SIP e usar SRV DNS para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="330d2-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="330d2-120">*Federação avançada*: Configure o nome de domínio SIP do parceiro como um parceiro de Federação para sua organização e use DNS SRV para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="330d2-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="330d2-121">*Federação direta*: Configure o nome de domínio SIP do parceiro e o FQDN para o servidor de borda do parceiro</span><span class="sxs-lookup"><span data-stu-id="330d2-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="330d2-122">*Lista de permissões de servidor*: aceitar qualquer domínio, usar SRV DNS para localizar o servidor de borda de um provedor de hospedagem ou um provedor de conectividade de mensagens instantâneas (IM) público</span><span class="sxs-lookup"><span data-stu-id="330d2-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="330d2-123">O Microsoft Office Communications Server 2007 introduziu a nomenclatura atualizada para tipos de Federação para definir melhor o que cada tipo de Federação realmente realizou:</span><span class="sxs-lookup"><span data-stu-id="330d2-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="330d2-124">A Federação Avançada Aberta se tornou *Domínio de Parceiro Descoberto*</span><span class="sxs-lookup"><span data-stu-id="330d2-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="330d2-125">A Federação Avançada se tornou *Domínio de Parceiro Permitido*</span><span class="sxs-lookup"><span data-stu-id="330d2-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="330d2-126">A Federação Direta se tornou *Servidor de Parceiro Permitido*</span><span class="sxs-lookup"><span data-stu-id="330d2-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="330d2-127">A Lista de Permissão do Servidor se tornou *Provedor de Hospedagem* e *Provedor IM Público*</span><span class="sxs-lookup"><span data-stu-id="330d2-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="330d2-128">O Microsoft Lync Server 2010 introduziu uma definição mais estreita de provedor de Hospedagem de acordo com o Microsoft Lync Online 2010 e com o Microsoft Office 365 e também o fez sujeito à mesma lista permitida definida pelo tipo de Federação de domínio de parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="330d2-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="330d2-129">Habilitar a Federação entre o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server usa os servidores de borda e os proxies reverso para impor as regras e domínios de parceiros permitidos que você definir.</span><span class="sxs-lookup"><span data-stu-id="330d2-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="330d2-130">De uma perspectiva de planejamento, a Federação com outro Lync Server, o Office Communications Server requer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="330d2-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="330d2-131">Habilitar federação no Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="330d2-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="330d2-132">Para obter detalhes, consulte o tópico de implantação [Configurando a Federação SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="330d2-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="330d2-133">Determine seus requisitos para descoberta do domínio federado:</span><span class="sxs-lookup"><span data-stu-id="330d2-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="330d2-134">Para a configuração manual da Federação, você deve ter o FQDN (nome de domínio totalmente qualificado) do servidor de borda e do nome de domínio do parceiro, ou nome de domínio online, que é inserido no painel de controle do Lync Server, **Federação e acesso externo**, **domínios federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="330d2-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="330d2-135">Crie uma política **Novo** ou **Edite** uma política existente para permitir ou bloquear domínios pelo FQDN.</span><span class="sxs-lookup"><span data-stu-id="330d2-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="330d2-136">A configuração manual do servidor de borda de um parceiro de Federação está sujeita a falhas caso o parceiro altere o endereço IP de seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="330d2-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="330d2-137">Para <STRONG>novos domínios federados SIP</STRONG>, você deve fornecer o <STRONG>nome de domínio (ou FQDN)</STRONG> para o Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="330d2-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="330d2-138">Para o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server, você também deve fornecer um <STRONG>serviço de borda de acesso (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="330d2-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="330d2-139">Para Federação de parceiro descoberta, onde os parceiros podem descobrir seu servidor de borda, você cria um registro SRV em seu \_DNS-sipfederationtls externo. \_TCP.contoso.com – que aponta para a porta 5061 e o registro de host (A) do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="330d2-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="330d2-140">Se você estiver oferecendo suporte aos clientes do Microsoft Lync Mobile no Windows Phone ou no iPhone, iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="330d2-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="330d2-141">&lt;Registros SRV&gt; de domínio SIP para cada domínio SIP que você tenha clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="330d2-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="330d2-142">Android e Nokia Symbian Lync Mobile não usam a notificação por push e não estão sujeitos a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="330d2-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="330d2-143">Configure políticas de acesso do usuário externo para suportar domínios federados</span><span class="sxs-lookup"><span data-stu-id="330d2-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="330d2-144">Abra portas de firewall para SIP, conferência da Web e áudio/visual para acomodar a federação ou contatos que estiver habilitando.</span><span class="sxs-lookup"><span data-stu-id="330d2-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="330d2-145">Para obter detalhes, consulte: [determinar firewall A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="330d2-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="330d2-146">As informações a seguir ajudarão você a definir os requisitos de certificado, de porta/protocolo e DNS para federação com o Microsoft Lync Server 2013 e o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="330d2-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="330d2-147">O planejamento de certificados, firewall e requisitos de porta/protocolo e DNS é geralmente um processo de avanço direto se você tiver planejado ou implantado seus servidores de borda do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="330d2-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="330d2-148">Como a Federação é um recurso adicional que usa o servidor de borda existente, os requisitos de planejamento geralmente são atendidos pelo planejamento e implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="330d2-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="330d2-149">Você deve usar as seguintes tabelas para determinar quais de seus requisitos são atendidos e faz mudanças na porta/protocolo e DNS da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="330d2-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="330d2-150">Se você tiver um pool de servidores de borda e estiver se Federando com parceiros do Lync Server 2013 ou do Lync Server 2010, poderá usar balanceamento de carga DNS ou balanceadores de carga de hardware nos lados internos e externos voltados para os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="330d2-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="330d2-151">Se você estiver se Federando com o Office Communications Server 2007 ou o Office Communications Server 2007 R2, o balanceamento de carga de hardware fornecerá suporte de failover no caso de um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="330d2-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="330d2-152">O Office Communications Server 2007 e o Office Communications Server 2007 R2 não têm reconhecimento de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="330d2-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="330d2-153">Os servidores de borda de parceiro estabelecerão a comunicação com o primeiro servidor de borda no pool que responder.</span><span class="sxs-lookup"><span data-stu-id="330d2-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="330d2-154">Se esse servidor de borda falhar, a comunicação não executará automaticamente o failover.</span><span class="sxs-lookup"><span data-stu-id="330d2-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="330d2-155">Os requisitos de certificado normalmente são atendidos pelo planejamento de certificados para o servidor de borda escolhido ou para o plano do servidor de borda em pool.</span><span class="sxs-lookup"><span data-stu-id="330d2-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="330d2-156">Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="330d2-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="330d2-157">A conectividade de mensagens instantâneas públicas é uma classe de Federação e é configurada para permitir que seus usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="330d2-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="330d2-158">Contatos do Messenger</span><span class="sxs-lookup"><span data-stu-id="330d2-158">Messenger contacts</span></span>

  - <span data-ttu-id="330d2-159">Instant\!</span><span class="sxs-lookup"><span data-stu-id="330d2-159">Yahoo\!</span></span> <span data-ttu-id="330d2-160">contacts</span><span class="sxs-lookup"><span data-stu-id="330d2-160">contacts</span></span>

  - <span data-ttu-id="330d2-161">Contatos do America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="330d2-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="330d2-162">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="330d2-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="330d2-163">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="330d2-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="330d2-164">Messenger até a data de desligamento do serviço (a data exata ainda deve ser decidida, mas não antes de junho de 2013).</span><span class="sxs-lookup"><span data-stu-id="330d2-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="330d2-165">O PIC USL é uma licença de assinatura por usuário, por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="330d2-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="330d2-166">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="330d2-166">Messenger.</span></span> <span data-ttu-id="330d2-167">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual não será renovado.</span><span class="sxs-lookup"><span data-stu-id="330d2-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="330d2-168">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="330d2-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="330d2-169">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="330d2-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="330d2-170">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de IM e voz.</span><span class="sxs-lookup"><span data-stu-id="330d2-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="330d2-171">Essa classe de Federação requer as seguintes considerações de planejamento:</span><span class="sxs-lookup"><span data-stu-id="330d2-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="330d2-172">Os usuários do Windows Live Messenger podem ter a comunicação de áudio/vídeo ponto a ponto com os usuários do Lync Server 2013, além de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="330d2-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="330d2-173">Os servidores de borda devem atender a requisitos específicos de porta e protocolo.</span><span class="sxs-lookup"><span data-stu-id="330d2-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="330d2-174">Para obter detalhes, consulte [determine external A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="330d2-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="330d2-175">O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles normalmente usados no planejamento e implantação do servidor de borda típico que está fornecendo Federação.</span><span class="sxs-lookup"><span data-stu-id="330d2-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="330d2-176">O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um cliente de uso avançado de chave (EKU).</span><span class="sxs-lookup"><span data-stu-id="330d2-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="330d2-177">Federação do protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="330d2-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="330d2-178">Versões anteriores do Lync Server e Office Communications Server forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que pode ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="330d2-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="330d2-179">No Microsoft Lync Server 2013, a funcionalidade do XMPP pode ser implantada como um recurso.</span><span class="sxs-lookup"><span data-stu-id="330d2-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="330d2-180">A funcionalidade do XMPP está instalada em duas partes: um proxy do XMPP que é executado no servidor de borda e o gateway do XMPP que é executado nos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="330d2-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="330d2-181">A implantação e a configuração do XMPP são abordadas na [implantação de acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) você planeja oferecer suporte a XMPP em sua organização definindo regras de porta e protocolo no firewall, configuração de certificados e adição de registros DNS.</span><span class="sxs-lookup"><span data-stu-id="330d2-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="330d2-182">Os seguintes tópicos nesta seção resumem as informações que você precisará para planejar com êxito a Federação do XMPP para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="330d2-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="330d2-183">O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="330d2-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="330d2-184">Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="330d2-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="330d2-185">A Federação XMPP não é suportada para usuários hospedados em aparelhos de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="330d2-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="330d2-186">Isso se aplica a informações de presença e troca de mensagens de IM.</span><span class="sxs-lookup"><span data-stu-id="330d2-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="330d2-187">Nos tópicos a seguir contêm orientações para definir certificados, portas de firewall e entradas de DNS para os tipos de cenários de Federação com suporte.</span><span class="sxs-lookup"><span data-stu-id="330d2-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="330d2-188">Resumo de certificado-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="330d2-189">Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="330d2-190">Resumo de DNS-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="330d2-191">Confira Também</span><span class="sxs-lookup"><span data-stu-id="330d2-191">See Also</span></span>


[<span data-ttu-id="330d2-192">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="330d2-193">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="330d2-194">Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="330d2-195">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="330d2-196">Gerenciar a configuração de borda de acesso para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="330d2-197">Gerenciar domínios federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="330d2-198">Gerenciar provedores federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330d2-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

