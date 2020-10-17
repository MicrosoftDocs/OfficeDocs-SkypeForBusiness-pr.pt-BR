---
title: 'Lync Server 2013: requisitos do serviço de descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515768"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="2d53d-102">Requisitos do serviço de descoberta automática para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d53d-102">Autodiscover service requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d53d-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="2d53d-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="2d53d-104">O serviço de descoberta automática do Microsoft Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends e, quando publicado no DNS, pode ser usado por dispositivos móveis que executam o Lync Mobile para localizar serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="2d53d-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="2d53d-105">Antes que os dispositivos móveis que executam o Lync Mobile possam aproveitar a descoberta automática, você precisa modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="2d53d-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="2d53d-106">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.</span><span class="sxs-lookup"><span data-stu-id="2d53d-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="2d53d-107">Para obter detalhes sobre as entradas de nome alternativo de entidade que são necessárias para diretores, servidores front-end e proxies reversos, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span><span class="sxs-lookup"><span data-stu-id="2d53d-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="2d53d-108">A decisão sobre usar listas de nomes alternativos de entidade em proxies reversos é fundamentada na porta em que o serviço de Descoberta Automática foi publicado, a saber, na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="2d53d-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="2d53d-109">**Publicado na porta 80**     Nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer na porta 80.</span><span class="sxs-lookup"><span data-stu-id="2d53d-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="2d53d-110">Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão redirecionados para um diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="2d53d-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="2d53d-111">Para obter detalhes, consulte a seção “Processo inicial de descoberta automática usando a porta 80” mais adiante, neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2d53d-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="2d53d-112">**Publicado na porta 443**     A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um \*lyncdiscover. \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="2d53d-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="2d53d-113">entrada para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2d53d-113">entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="2d53d-114">A reemissão de certificados usando uma autoridade de certificado interna geralmente é um processo simples, mas para os certificados públicos usados na regra de publicação do serviço da Web, adicionar várias entradas de nomes alternativos de entidade pode se tornar caro.</span><span class="sxs-lookup"><span data-stu-id="2d53d-114">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="2d53d-115">Para contornar esse problema, oferecemos suporte à conexão de descoberta automática inicial na porta 80, que é então redirecionada para a porta 8080 no diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="2d53d-115">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="2d53d-116">Por exemplo, suponha que um cliente móvel executando o Lync Mobile esteja configurado para entrar no Lync Server 2013 usando o recurso de descoberta automática usando HTTP para a solicitação inicial.</span><span class="sxs-lookup"><span data-stu-id="2d53d-116">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="2d53d-117">Processo de descoberta automática inicial para dispositivos móveis usando a porta 80</span><span class="sxs-lookup"><span data-stu-id="2d53d-117">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="2d53d-118">O dispositivo móvel que executa o Lync Mobile procura lyncdiscover.contoso.com usando o DNS, onde existe um registro A.</span><span class="sxs-lookup"><span data-stu-id="2d53d-118">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="2d53d-119">DNS externo retorna o endereço IP dos serviços Web externos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="2d53d-119">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="2d53d-120">O dispositivo móvel que executa o Lync Mobile envia http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com uma solicitação para o proxy reverso</span><span class="sxs-lookup"><span data-stu-id="2d53d-120">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="2d53d-121">A regra de publicação na Web preencherá a solicitação da porta 80 externamente para a porta 8080 internamente, que a encaminhará para um diretor ou servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="2d53d-121">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="2d53d-122">Uma vez que a solicitação é em HTTP e não HTTPS, não são necessárias modificações para o certificado na regra de publicação de serviço da Web externa para suportar o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="2d53d-122">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="2d53d-123">O serviço de Descoberta Automática retorna os URLs do serviço de Web externa (em formato HTTPS).</span><span class="sxs-lookup"><span data-stu-id="2d53d-123">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="2d53d-124">O dispositivo móvel que executa o Lync Mobile pode se reconectar ao proxy reverso na porta 443 e é redirecionado sobre 4443 para o serviço de mobilidade em execução no pool local do usuário.</span><span class="sxs-lookup"><span data-stu-id="2d53d-124">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="2d53d-125">Uma vez que a consulta do HTTPS é sobre o URL dos serviços de Web externa versus o URL do serviço de descoberta automática, ela é bem-sucedida, pois o certificado já deve conter entradas de nomes alternativos de entidade para os FQDNs (nomes de domínio totalmente qualificados) de serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="2d53d-125">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="2d53d-126">Neste cenário, não há alterações necessárias para dar suporte à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="2d53d-126">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d53d-127">Se o servidor Web de destino possuir um certificado que não tenha um valor de correspondência para lyncdiscover.contoso.com como um valor de lista de nome alternativo de entidade:</span><span class="sxs-lookup"><span data-stu-id="2d53d-127">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="2d53d-128">um. &nbsp; &nbsp; &nbsp; O servidor Web responde com uma "saudação de servidor" e nenhum certificado.</span><span class="sxs-lookup"><span data-stu-id="2d53d-128">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="2d53d-129">b. &nbsp; &nbsp; &nbsp; O dispositivo móvel que executa o Lync Mobile interrompe imediatamente a sessão.</span><span class="sxs-lookup"><span data-stu-id="2d53d-129">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="2d53d-130">Se o servidor da Web de destino tiver um certificado que inclui lyncdiscover.contoso.com como valor de lista de nome alternativo de entidade:</span><span class="sxs-lookup"><span data-stu-id="2d53d-130">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="2d53d-131">um. &nbsp; &nbsp; &nbsp; O servidor Web responde com uma "saudação de servidor" e um certificado.</span><span class="sxs-lookup"><span data-stu-id="2d53d-131">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="2d53d-132">b. &nbsp; &nbsp; &nbsp; O dispositivo móvel que executa o Lync Mobile valida o certificado e conclui o handshake.</span><span class="sxs-lookup"><span data-stu-id="2d53d-132">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="2d53d-133">Para dar suporte a uma conexão inicial ao serviço de descoberta automática usando a porta 80 no seu servidor de proxy reverso, você pode criar uma regra de publicação de http semelhante a este exemplo para uma regra de publicação de proxy reverso do Forefront Threat Management Gateway 2010:</span><span class="sxs-lookup"><span data-stu-id="2d53d-133">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="2d53d-134">Crie uma nova regra de publicação da Web (por exemplo, **Descoberta Automática do Lync Server (HTTP)**).</span><span class="sxs-lookup"><span data-stu-id="2d53d-134">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="2d53d-135">Em **Nome Público**, insira lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d53d-135">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="2d53d-136">Na guia **Ponte**, selecione apenas a opção das solicitações de ponte da Porta 80 à Porta 8080.</span><span class="sxs-lookup"><span data-stu-id="2d53d-136">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="2d53d-137">Na guia **Autenticação**, selecione **Sem autenticação** e **Cliente não pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="2d53d-137">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="2d53d-138">Confirme as alterações e mova a regra para a parte superior da lista de regras do Lync (primeiro na ordem de processamento).</span><span class="sxs-lookup"><span data-stu-id="2d53d-138">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="2d53d-139">Mobilidade para a Implantação de domínio dividido</span><span class="sxs-lookup"><span data-stu-id="2d53d-139">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="2d53d-140">Um espaço de endereço SIP compartilhado, também conhecido como *domínio dividido* ou *implantação híbrida* é uma configuração na qual os usuários são implantados em uma implantação local e um ambiente online.</span><span class="sxs-lookup"><span data-stu-id="2d53d-140">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="2d53d-141">O resultado desejado é ter um usuário, independentemente de onde seu servidor doméstico esteja localizado (local ou online), para fazer logon na implantação e ser redirecionado ao local de seu servidor doméstico.</span><span class="sxs-lookup"><span data-stu-id="2d53d-141">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="2d53d-142">Para fazer isso, o recurso de descoberta automática do Microsoft Lync Server 2013 é usado para redirecionar o usuário online para a topologia online.</span><span class="sxs-lookup"><span data-stu-id="2d53d-142">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="2d53d-143">Isso é feito configurando o localizador de recursos uniforme (URL) de descoberta automática usando o Shell de gerenciamento do Lync Server e os cmdlets **Get-CsHostingProvider** e **set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="2d53d-143">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="2d53d-144">Será necessário coletar e registrar os seguintes atributos implantados:</span><span class="sxs-lookup"><span data-stu-id="2d53d-144">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="2d53d-145">No Shell de gerenciamento do Lync Server, digite</span><span class="sxs-lookup"><span data-stu-id="2d53d-145">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="2d53d-p106">Nos resultados, encontre o provedor online com o atributo **ProxyFQDN**. Por exemplo, sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2d53d-p106">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="2d53d-148">Registre o valor do ProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="2d53d-148">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="2d53d-149">Habilitar Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online</span><span class="sxs-lookup"><span data-stu-id="2d53d-149">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="2d53d-p107">Habilite a federação para o provedor online. Por padrão, todos os usuários online são habilitados para federação de domínio e podem se comunicar com todos os domínios</span><span class="sxs-lookup"><span data-stu-id="2d53d-p107">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="2d53d-152">Se você for definir domínios bloqueados e permitidos, determine os domínios que permitirá ou bloqueará explicitamente</span><span class="sxs-lookup"><span data-stu-id="2d53d-152">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="2d53d-153">Para federação online, é necessário planejar exceções de firewall, certificados e registros de host DNS (A ou AAAA, se estiver usando IPv6).</span><span class="sxs-lookup"><span data-stu-id="2d53d-153">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="2d53d-154">Além disso, é necessário configurar as políticas de federação.</span><span class="sxs-lookup"><span data-stu-id="2d53d-154">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="2d53d-155">Para obter detalhes, consulte [Planning for Lync server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="2d53d-155">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

