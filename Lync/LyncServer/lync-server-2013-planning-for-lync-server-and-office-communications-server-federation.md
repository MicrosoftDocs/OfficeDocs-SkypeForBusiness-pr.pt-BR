---
title: Planejamento para Federação do Lync Server e Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c94254921e3aa1cde8d93998f8fe5bf122ac92
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="3e20e-102">Planejamento para Federação do Lync Server 2013 e Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="3e20e-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e20e-103">_**Última modificação do tópico:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="3e20e-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="3e20e-104">Federação entre o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server suporta comunicação ponto a ponto e vários participantes.</span><span class="sxs-lookup"><span data-stu-id="3e20e-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="3e20e-105">As conversas ponto a ponto podem ser posicionadas para conversas de várias partes, permitindo reuniões locais.</span><span class="sxs-lookup"><span data-stu-id="3e20e-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="3e20e-106">Reuniões - Conferência da Web ou conferências áudio/visual - podem ser programadas para incluir contatos dentro da sua organização, assim como contatos em parceiros que você federar.</span><span class="sxs-lookup"><span data-stu-id="3e20e-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="3e20e-107">A Federação apareceu primeiro no Microsoft Office Live Communications Server 2005 e suportava um tipo de Federação, Federação direta.</span><span class="sxs-lookup"><span data-stu-id="3e20e-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="3e20e-108">A Federação direta exigia que você saiba o domínio SIP (Session Initiation Protocol) do parceiro de Federação e o FQDN (nome de domínio totalmente qualificado) do servidor de borda do parceiro.</span><span class="sxs-lookup"><span data-stu-id="3e20e-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="3e20e-109">O Live Communications Server 2005 com SP1 apresentou tipos de Federação adicionais, todos os quais os registros SRV do sistema de nomes de domínio (DNS) necessários serão publicados pelo parceiro federado para localizar seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3e20e-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="3e20e-110">A terminologia para esta versão foi:</span><span class="sxs-lookup"><span data-stu-id="3e20e-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="3e20e-111">*Abrir Federação aprimorada*: aceitar qualquer nome de domínio SIP e usar SRV DNS para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="3e20e-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="3e20e-112">*Federação avançada*: Configure o nome de domínio SIP do parceiro como um parceiro de Federação para sua organização e use DNS SRV para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="3e20e-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="3e20e-113">*Federação direta*: Configure o nome de domínio SIP do parceiro e o FQDN para o servidor de borda do parceiro</span><span class="sxs-lookup"><span data-stu-id="3e20e-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="3e20e-114">*Lista de permissões de servidor*: aceitar qualquer domínio, usar SRV DNS para localizar o servidor de borda de um provedor de hospedagem ou um provedor de conectividade de mensagens instantâneas (IM) público</span><span class="sxs-lookup"><span data-stu-id="3e20e-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="3e20e-115">O Microsoft Office Communications Server 2007 introduziu a nomenclatura atualizada para tipos de Federação para definir melhor o que cada tipo de Federação realmente realizou:</span><span class="sxs-lookup"><span data-stu-id="3e20e-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="3e20e-116">A Federação Avançada Aberta se tornou *Domínio de Parceiro Descoberto*</span><span class="sxs-lookup"><span data-stu-id="3e20e-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="3e20e-117">A Federação Avançada se tornou *Domínio de Parceiro Permitido*</span><span class="sxs-lookup"><span data-stu-id="3e20e-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="3e20e-118">A Federação Direta se tornou *Servidor de Parceiro Permitido*</span><span class="sxs-lookup"><span data-stu-id="3e20e-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="3e20e-119">A Lista de Permissão do Servidor se tornou *Provedor de Hospedagem* e *Provedor IM Público*</span><span class="sxs-lookup"><span data-stu-id="3e20e-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="3e20e-120">O Microsoft Lync Server 2010 introduziu uma definição mais estreita de provedor de Hospedagem de acordo com o Microsoft Lync Online 2010 e com o Microsoft Office 365 e também o fez sujeito à mesma lista permitida definida pelo tipo de Federação de domínio de parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="3e20e-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="3e20e-121">Habilitar a Federação entre o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server usa os servidores de borda e os proxies reverso para impor as regras e domínios de parceiros permitidos que você definir.</span><span class="sxs-lookup"><span data-stu-id="3e20e-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="3e20e-122">De uma perspectiva de planejamento, a Federação com outro Lync Server, o Office Communications Server requer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e20e-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="3e20e-123">Habilitar federação no Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="3e20e-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="3e20e-124">Para obter detalhes, consulte o tópico de implantação [Configurando a Federação SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="3e20e-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="3e20e-125">Determine seus requisitos para descoberta do domínio federado:</span><span class="sxs-lookup"><span data-stu-id="3e20e-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="3e20e-126">Para a configuração manual da Federação, você deve ter o FQDN (nome de domínio totalmente qualificado) do servidor de borda e do nome de domínio do parceiro, ou nome de domínio online, que é inserido no painel de controle do Lync Server, **Federação e acesso externo**, **domínios federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="3e20e-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="3e20e-127">Crie uma política **Novo** ou **Edite** uma política existente para permitir ou bloquear domínios pelo FQDN.</span><span class="sxs-lookup"><span data-stu-id="3e20e-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="3e20e-128">A configuração manual do servidor de borda de um parceiro de Federação está sujeita a falhas caso o parceiro altere o endereço IP de seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3e20e-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3e20e-129">Para <STRONG>novos domínios federados SIP</STRONG>, você deve fornecer o <STRONG>nome de domínio (ou FQDN)</STRONG> para o Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="3e20e-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="3e20e-130">Para o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server, você também deve fornecer um <STRONG>serviço de borda de acesso (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="3e20e-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="3e20e-131">Para Federação de parceiro descoberta, onde os parceiros podem descobrir seu servidor de borda, você cria um registro SRV em seu \_DNS-sipfederationtls externo. \_TCP.contoso.com – que aponta para a porta 5061 e o registro de host (A) do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3e20e-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="3e20e-132">Se você estiver oferecendo suporte aos clientes do Microsoft Lync Mobile no Windows Phone ou no iPhone, iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="3e20e-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="3e20e-133">&lt;Registros SRV&gt; de domínio SIP para cada domínio SIP que você tenha clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="3e20e-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="3e20e-134">Android e Nokia Symbian Lync Mobile não usam a notificação por push e não estão sujeitos a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="3e20e-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="3e20e-135">Configure políticas de acesso do usuário externo para suportar domínios federados</span><span class="sxs-lookup"><span data-stu-id="3e20e-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="3e20e-136">Abra portas de firewall para SIP, conferência da Web e áudio/visual para acomodar a federação ou contatos que estiver habilitando.</span><span class="sxs-lookup"><span data-stu-id="3e20e-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="3e20e-137">Para obter detalhes, consulte: [determinar firewall A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3e20e-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="3e20e-138">As informações a seguir ajudarão você a definir os requisitos de certificado, de porta/protocolo e DNS para federação com o Microsoft Lync Server 2013 e o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e20e-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="3e20e-139">O planejamento de certificados, firewall e requisitos de porta/protocolo e DNS é geralmente um processo de avanço direto se você tiver planejado ou implantado seus servidores de borda do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e20e-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="3e20e-140">Como a Federação é um recurso adicional que usa o servidor de borda existente, os requisitos de planejamento geralmente são atendidos pelo planejamento e implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3e20e-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="3e20e-141">Você deve usar as seguintes tabelas para determinar quais de seus requisitos são atendidos e faz mudanças na porta/protocolo e DNS da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="3e20e-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3e20e-142">Se você tiver um pool de servidores de borda e estiver se Federando com parceiros do Lync Server 2013 ou do Lync Server 2010, poderá usar balanceamento de carga DNS ou balanceadores de carga de hardware nos lados internos e externos voltados para os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="3e20e-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="3e20e-143">Se você estiver se Federando com o Office Communications Server 2007 ou o Office Communications Server 2007 R2, o balanceamento de carga de hardware fornecerá suporte de failover no caso de um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3e20e-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="3e20e-144">O Office Communications Server 2007 e o Office Communications Server 2007 R2 não têm reconhecimento de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="3e20e-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="3e20e-145">Os servidores de borda de parceiro estabelecerão a comunicação com o primeiro servidor de borda no pool que responder.</span><span class="sxs-lookup"><span data-stu-id="3e20e-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="3e20e-146">Se esse servidor de borda falhar, a comunicação não executará automaticamente o failover.</span><span class="sxs-lookup"><span data-stu-id="3e20e-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="3e20e-147">Os requisitos de certificado normalmente são atendidos pelo planejamento de certificados para o servidor de borda escolhido ou para o plano do servidor de borda em pool.</span><span class="sxs-lookup"><span data-stu-id="3e20e-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e20e-148">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3e20e-148">In This Section</span></span>

  - [<span data-ttu-id="3e20e-149">Resumo de certificado-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="3e20e-150">Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="3e20e-151">Resumo de DNS-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e20e-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="3e20e-152">See Also</span></span>


[<span data-ttu-id="3e20e-153">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="3e20e-154">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="3e20e-155">Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="3e20e-156">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="3e20e-157">Gerenciar a configuração de borda de acesso para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="3e20e-158">Gerenciar domínios federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="3e20e-159">Gerenciar provedores federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e20e-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

