---
title: 'Lync Server 2013: Requisitos do serviço de descoberta automática'
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
ms.openlocfilehash: 777d70b20a51e5408fe9d9248028c3dbcaebeba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="23948-102">Requisitos do serviço de descoberta automática para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23948-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23948-103">_**Tópico da última modificação:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="23948-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="23948-104">O serviço descoberta automática do Microsoft Lync Server 2013 é executado nos servidores do diretor e do pool de front-end e, quando publicados no DNS, pode ser usado por dispositivos móveis que executam o Lync Mobile para localizar serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="23948-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="23948-105">Antes que os dispositivos móveis que executam o Lync Mobile possam tirar proveito da descoberta automática, você precisará modificar listas de nomes alternativos de entidades de certificado em qualquer director e servidor front-end executando o serviço descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="23948-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="23948-106">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidades nos certificados usados para regras de publicação de serviço Web externo em proxies reverso.</span><span class="sxs-lookup"><span data-stu-id="23948-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="23948-107">Para obter detalhes sobre as entradas de nome alternativo do assunto que são necessárias para os directors, servidores front-end e proxies reverso, consulte [requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) no planejamento para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="23948-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="23948-108">A decisão sobre o uso de listas de nomes alternativos de entidades em proxies invertidos baseia-se na publicação do serviço de descoberta automática na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="23948-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="23948-109">**Publicado na porta 80**   nenhuma alteração de certificado será necessária se a consulta inicial para o serviço descoberta automática ocorrer na porta 80.</span><span class="sxs-lookup"><span data-stu-id="23948-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="23948-110">Isso ocorre porque os dispositivos móveis que executam o Lync acessam o proxy reverso na porta 80 externamente e, em seguida, redirecionados para um diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="23948-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="23948-111">Para obter detalhes, consulte a seção "processo de descoberta automática inicial usando a porta 80" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="23948-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="23948-112">**Publicado na porta 443**   a lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos deve conter um *lyncdiscover.\< entrada\> sipdomain* para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="23948-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="23948-113">A emissão de certificados usando uma autoridade de certificação interna geralmente é um processo simples, mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nome alternativo à entidade pode ficar caro.</span><span class="sxs-lookup"><span data-stu-id="23948-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="23948-114">Para contornar esse problema, oferecemos suporte para a conexão de descoberta automática inicial na porta 80, que é redirecionada para a porta 8080 do diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="23948-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="23948-115">Por exemplo, suponha que um cliente móvel que executa o Lync Mobile esteja configurado para entrar no Lync Server 2013 usando o recurso de descoberta automática usando HTTP para a solicitação inicial.</span><span class="sxs-lookup"><span data-stu-id="23948-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="23948-116">Processo de descoberta automática inicial para dispositivos móveis usando a porta 80</span><span class="sxs-lookup"><span data-stu-id="23948-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="23948-117">O dispositivo móvel que executa o Lync Mobile pesquisa lyncdiscover.contoso.com usando DNS, onde existe um registro A.</span><span class="sxs-lookup"><span data-stu-id="23948-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="23948-118">DNS externo retorna o endereço IP dos serviços Web externos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="23948-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="23948-119">O dispositivo móvel que executa o Lync http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com Mobile envia uma solicitação ao proxy reverso</span><span class="sxs-lookup"><span data-stu-id="23948-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="23948-120">A regra de publicação na Web fará a ponte da porta 80 externamente para a porta 8080 internamente, o que a encaminhará para um diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="23948-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="23948-121">Como a solicitação é HTTP e não HTTPS, nenhuma modificação é necessária para o certificado na regra de publicação de serviço Web externo para dar suporte ao serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="23948-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="23948-122">O serviço descoberta automática retorna as URLs do serviço Web externo (em formato HTTPS).</span><span class="sxs-lookup"><span data-stu-id="23948-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="23948-123">O dispositivo móvel que executa o Lync Mobile poderá reconectar-se ao proxy reverso na porta 443 e será redirecionado sobre o 4443 para o serviço de mobilidade em execução no pool primário do usuário.</span><span class="sxs-lookup"><span data-stu-id="23948-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="23948-124">Como a consulta HTTPS é para a URL de serviços Web externos versus a URL do serviço de descoberta automática, ela terá êxito porque o certificado já contém entradas de nome alternativo para os serviços Web externos (FQDNs) dos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="23948-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="23948-125">Nesse cenário, não há nenhuma alteração de certificado necessária para dar suporte à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="23948-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23948-126">Se o servidor Web de destino tiver um certificado que não tenha um valor correspondente para lyncdiscover.contoso.com como um valor de lista de nomes alternativos do assunto:</span><span class="sxs-lookup"><span data-stu-id="23948-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="23948-127">&nbsp;&nbsp;um servidor Web responde com um "servidor Olá"&nbsp;e sem certificado.</span><span class="sxs-lookup"><span data-stu-id="23948-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="23948-128">b.&nbsp;&nbsp;&nbsp;o dispositivo móvel que executa o Lync Mobile imediatamente finaliza a sessão.</span><span class="sxs-lookup"><span data-stu-id="23948-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="23948-129">Se o servidor Web de destino tiver um certificado que inclua lyncdiscover.contoso.com como um valor de lista de nomes alternativos do assunto:</span><span class="sxs-lookup"><span data-stu-id="23948-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="23948-130">&nbsp;&nbsp;um servidor Web responde com uma "saudação de servidor"&nbsp;e um certificado.</span><span class="sxs-lookup"><span data-stu-id="23948-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="23948-131">b.&nbsp;&nbsp;&nbsp;o dispositivo móvel que executa o Lync Mobile valida o certificado e conclui o handshake.</span><span class="sxs-lookup"><span data-stu-id="23948-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="23948-132">Para dar suporte a uma conexão inicial com o serviço de descoberta automática usando a porta 80 em seu servidor proxy reverso, você pode criar uma regra de publicação http semelhante a este exemplo para uma regra de publicação de proxy da Web do Forefront Threat Management Gateway 2010:</span><span class="sxs-lookup"><span data-stu-id="23948-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="23948-133">Criar uma nova regra de publicação na Web (por exemplo, **descoberta automática do Lync Server (http)**).</span><span class="sxs-lookup"><span data-stu-id="23948-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="23948-134">Em **nome público**, digite lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="23948-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="23948-135">Na guia **ponte** , selecione somente a opção para fazer a ponte de solicitações da porta 80 para a porta 8080.</span><span class="sxs-lookup"><span data-stu-id="23948-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="23948-136">Na guia **autenticação** , selecione **sem autenticação**, e o **cliente não pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="23948-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="23948-137">Confirme as alterações e mova a regra para a parte superior da lista de regras do Lync (primeiro em ordem de processamento).</span><span class="sxs-lookup"><span data-stu-id="23948-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="23948-138">Mobilidade para a implantação de domínio dividido</span><span class="sxs-lookup"><span data-stu-id="23948-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="23948-139">Um espaço de endereço SIP compartilhado, também conhecido como um *domínio dividido*, ou uma *implantação híbrida* , é uma configuração na qual os usuários são implantados em uma implantação local e em um ambiente online.</span><span class="sxs-lookup"><span data-stu-id="23948-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="23948-140">O resultado desejado é ter um usuário, independentemente de onde o servidor local está localizado (local ou online), fazer logon na implantação e ser redirecionado para o local do servidor de casa.</span><span class="sxs-lookup"><span data-stu-id="23948-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="23948-141">Para fazer isso, o recurso descoberta automática do Microsoft Lync Server 2013 é usado para redirecionar o usuário online para a topologia online.</span><span class="sxs-lookup"><span data-stu-id="23948-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="23948-142">Isso é feito configurando o localizador de recursos uniforme (URL) da descoberta automática usando o Shell de gerenciamento do Lync Server e os cmdlets **Get-CsHostingProvider** e **set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="23948-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="23948-143">Será preciso coletar e gravar os seguintes atributos implantados:</span><span class="sxs-lookup"><span data-stu-id="23948-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="23948-144">No Shell de gerenciamento do Lync Server, digite</span><span class="sxs-lookup"><span data-stu-id="23948-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="23948-145">Nos resultados, localize o provedor online com o atributo **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="23948-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="23948-146">Por exemplo, sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="23948-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="23948-147">Gravar o valor do ProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="23948-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="23948-148">Habilite a Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online</span><span class="sxs-lookup"><span data-stu-id="23948-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="23948-149">Habilite a Federação para o provedor online.</span><span class="sxs-lookup"><span data-stu-id="23948-149">Enable federation for the online provider.</span></span> <span data-ttu-id="23948-150">Por padrão, todos os usuários online estão habilitados para Federação de domínio e podem se comunicar com todos os domínios</span><span class="sxs-lookup"><span data-stu-id="23948-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="23948-151">Se você definirá domínios bloqueados e permitidos, determine os domínios que você permitirá explicitamente ou bloqueará explicitamente</span><span class="sxs-lookup"><span data-stu-id="23948-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="23948-152">Para a Federação online, você deve planejar exceções de firewall, certificados e host DNS (A ou AAAA, se estiver usando IPv6) registros.</span><span class="sxs-lookup"><span data-stu-id="23948-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="23948-153">Além disso, você deve configurar políticas de Federação.</span><span class="sxs-lookup"><span data-stu-id="23948-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="23948-154">Para obter detalhes, consulte [planejando a Federação para o Lync server 2013 e o Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="23948-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

