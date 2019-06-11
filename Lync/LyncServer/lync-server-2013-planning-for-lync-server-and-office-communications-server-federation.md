---
title: Planejando a Federação do Lync Server e do Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="b7ebf-102">Planejando a Federação do Lync Server 2013 e do Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="b7ebf-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7ebf-103">_**Tópico da última modificação:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="b7ebf-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="b7ebf-104">Federação entre o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server oferece suporte a comunicações ponto a ponto e de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="b7ebf-105">As conversas ponto a ponto podem ser escalonadas para conversas com vários participantes, permitindo reuniões ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="b7ebf-106">Reuniões: Webconferência ou conferências de áudio/visuais – podem ser programadas para incluir contatos dentro da sua organização e contatos em parceiros com os quais você se federa.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="b7ebf-107">A Federação apareceu primeiro no Microsoft Office Live Communications Server 2005 e com suporte um tipo de Federação, Federação direta.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="b7ebf-108">A Federação direta exigia que você saiba o domínio SIP (Session Initiation Protocol) do parceiro de Federação e o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="b7ebf-109">O Live Communications Server 2005 com SP1 introduziu tipos de Federação adicionais, todos os registros SRV do sistema de nome de domínio (DNS) necessários a serem publicados pelo parceiro federado para localizar o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="b7ebf-110">A terminologia do lançamento era:</span><span class="sxs-lookup"><span data-stu-id="b7ebf-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="b7ebf-111">*Abrir a Federação aprimorada*: aceitar qualquer nome de domínio SIP e usar o SRV DNS para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="b7ebf-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="b7ebf-112">*Federação aprimorada*: configurar o nome de domínio SIP do parceiro como um parceiro de Federação para a sua organização e usar o SRV DNS para localizar o servidor de borda de parceiro</span><span class="sxs-lookup"><span data-stu-id="b7ebf-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="b7ebf-113">*Federação direta*: configurar o nome de domínio SIP do parceiro e o FQDN para o servidor de borda do parceiro</span><span class="sxs-lookup"><span data-stu-id="b7ebf-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="b7ebf-114">*Lista de permissões do servidor*: aceitar qualquer domínio, usar o SRV DNS para localizar o servidor de borda de um provedor de hospedagem ou um provedor de conectividade de mensagens instantâneas (IM) público</span><span class="sxs-lookup"><span data-stu-id="b7ebf-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="b7ebf-115">O Microsoft Office Communications Server 2007 introduziu o nome atualizado dos tipos de Federação para definir melhor o que cada tipo de Federação realmente realizou:</span><span class="sxs-lookup"><span data-stu-id="b7ebf-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="b7ebf-116">A Federação aprimorada aberta se tornou conhecida como *domínio de parceiro descoberto*</span><span class="sxs-lookup"><span data-stu-id="b7ebf-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="b7ebf-117">A Federação aprimorada se tornou conhecida como *domínio de parceiro permitido*</span><span class="sxs-lookup"><span data-stu-id="b7ebf-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="b7ebf-118">A Federação direta se tornou conhecida como *servidor parceiro permitido*</span><span class="sxs-lookup"><span data-stu-id="b7ebf-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="b7ebf-119">A lista de permissões do servidor se tornou conhecida como *provedor de hospedagem* e provedor de mensagens de chat *públicas*</span><span class="sxs-lookup"><span data-stu-id="b7ebf-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="b7ebf-120">O Microsoft Lync Server 2010 introduziu uma definição mais estreita do provedor de Hospedagem de acordo com o Microsoft Lync Online 2010 e o Microsoft Office 365 e também o fez sujeito à mesma lista permitida definida pelo tipo de Federação do domínio parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="b7ebf-121">Habilitar a Federação entre o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server usa os servidores de borda e proxies reverso para impor as regras e os domínios de parceiros permitidos que você definir.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="b7ebf-122">De uma perspectiva de planejamento, a Federação com outro Lync Server, o Office Communications Server exige o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b7ebf-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="b7ebf-123">Habilite a Federação no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="b7ebf-124">Para obter detalhes, consulte o tópico de implantação Configurando a [Federação do SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="b7ebf-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="b7ebf-125">Determine suas necessidades para descoberta de domínio federado:</span><span class="sxs-lookup"><span data-stu-id="b7ebf-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="b7ebf-126">Para a configuração manual da Federação, você deve ter o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro e do nome do domínio, ou nome do domínio online, que é inserido no painel de controle do Lync Server, **agrupamento e acesso externo**, **SIP Domínios federados**.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="b7ebf-127">Crie uma **nova** política ou **edite** uma política existente para permitir ou bloquear domínios por FQDN.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="b7ebf-128">A configuração manual do servidor de borda do parceiro de Federação está sujeita a falhas caso o parceiro altere o endereço IP do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="b7ebf-129">Para <STRONG>novos domínios federados SIP</STRONG>, você deve fornecer o <STRONG>nome de domínio (ou FQDN)</STRONG> para o Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="b7ebf-130">Para o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server, você também deve fornecer um <STRONG>serviço de borda de acesso (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="b7ebf-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="b7ebf-131">Para a Federação de parceiro descoberto, em que os parceiros podem descobrir seu servidor de borda, você cria um registro SRV \_em seu DNS-sipfederationtls externo. \_TCP.contoso.com – que aponta para a porta 5061 e para o registro do host (A) de seu servidor de borda</span><span class="sxs-lookup"><span data-stu-id="b7ebf-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="b7ebf-132">Se você estiver oferecendo suporte para clientes móveis do Microsoft Lync no Windows Phone ou no iPhone do Apple, no iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar o sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="b7ebf-133">&lt;Registros SRV&gt; do domínio SIP para cada domínio SIP para os quais você tem clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="b7ebf-134">Android e Nokia Symbian Lync Mobile não use a notificação por push e não está sujeito a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="b7ebf-135">Configurar políticas de acesso de usuários externos para dar suporte a domínios federados</span><span class="sxs-lookup"><span data-stu-id="b7ebf-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="b7ebf-136">Abra portas de firewall para o protocolo SIP, conferência da Web e áudio/visual para acomodar a Federação ou os contatos que você está habilitando.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="b7ebf-137">Para obter detalhes, consulte: [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="b7ebf-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="b7ebf-138">As informações a seguir ajudarão você a definir os requisitos de certificado, de porta/protocolo e DNS para federação com o Microsoft Lync Server 2013 e o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="b7ebf-139">O planejamento de certificados, firewall e requisitos de porta/protocolo e requisitos de DNS geralmente é um processo direto se você planejou ou implantou seus servidores de borda do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="b7ebf-140">Como a Federação é um recurso adicional que usa o servidor de borda existente, os requisitos de planejamento geralmente são atendidos pelo planejamento e implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="b7ebf-141">Você deve usar as tabelas a seguir para determinar se os seus requisitos são atendidos e fazer alterações de acordo com a porta/protocolo e DNS.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b7ebf-142">Se você tiver um pool de servidores de borda e estiver conferindo-se com os parceiros do Lync Server 2013 ou Lync Server 2010, poderá usar o balanceamento de carga DNS ou os balanceadores de carga de hardware nos lados internos e externos dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="b7ebf-143">Se você estiver fazendo a Federação com o Office Communications Server 2007 ou o Office Communications Server 2007 R2, o balanceamento de carga de hardware fornecerá suporte de failover em caso de um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="b7ebf-144">O Office Communications Server 2007 e o Office Communications Server 2007 R2 não têm reconhecimento de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="b7ebf-145">Os servidores de borda de parceiro estabelecerão comunicação com o primeiro servidor de borda no pool que responde.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="b7ebf-146">Se esse servidor de borda falhar, a comunicação não executará automaticamente o failover.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="b7ebf-147">Os requisitos do certificado geralmente são atendidos pelo planejamento de certificados para o servidor de borda escolhido ou plano do servidor de borda em pool.</span><span class="sxs-lookup"><span data-stu-id="b7ebf-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7ebf-148">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b7ebf-148">In This Section</span></span>

  - [<span data-ttu-id="b7ebf-149">Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="b7ebf-150">Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="b7ebf-151">Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7ebf-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="b7ebf-152">See Also</span></span>


[<span data-ttu-id="b7ebf-153">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="b7ebf-154">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="b7ebf-155">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="b7ebf-156">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="b7ebf-157">Gerenciar configuração da borda de acesso para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="b7ebf-158">Gerenciar domínios SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="b7ebf-159">Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ebf-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

