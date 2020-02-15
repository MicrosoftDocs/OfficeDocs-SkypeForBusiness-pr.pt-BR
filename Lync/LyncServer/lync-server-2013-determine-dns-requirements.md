---
title: 'Lync Server 2013: determinar requisitos de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79f1c27f48beddd0c1fd3260193a71bb79b034bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="0f51e-102">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f51e-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f51e-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0f51e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0f51e-104">Use o fluxograma a seguir para determinar os requisitos do Sistema de Nomes de Domínio (DNS).</span><span class="sxs-lookup"><span data-stu-id="0f51e-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="0f51e-105">Alterações nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro são observadas onde se aplicam.</span><span class="sxs-lookup"><span data-stu-id="0f51e-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f51e-106">O Microsoft Lync Server 2013 suporta o uso de endereçamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="0f51e-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="0f51e-107">Para usar endereços IPv6, você também deve fornecer suporte para IPv6 DNS e configurar o host DNS AAAA (conhecido como registros "quad-A").</span><span class="sxs-lookup"><span data-stu-id="0f51e-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="0f51e-108">Em implantações nas quais o IPv4 e o IPv6 estão sendo usados, é melhor configurar e manter os registros de host A para IPv4 e o host AAAA para IPv6.</span><span class="sxs-lookup"><span data-stu-id="0f51e-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="0f51e-109">Mesmo que sua implantação tenha sido totalmente transicionada para IPv6, os registros de host DNS IPv4 ainda podem ser necessários quando usuários externos ainda estiverem usando IPv4.</span><span class="sxs-lookup"><span data-stu-id="0f51e-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="0f51e-110">**Fluxograma - Como determinar os requisitos do DNS**</span><span class="sxs-lookup"><span data-stu-id="0f51e-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="0f51e-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="0f51e-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f51e-112">Por padrão, o nome do computador de um computador que não faz parte de um domínio é um nome de host, não um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="0f51e-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="0f51e-113">O construtor de topologias usa FQDNs, não nomes de host.</span><span class="sxs-lookup"><span data-stu-id="0f51e-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="0f51e-114">Portanto, configure um sufixo DNS no nome do computador a ser implantado como um servidor de borda e que não esteja em um domínio.</span><span class="sxs-lookup"><span data-stu-id="0f51e-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="0f51e-115"><STRONG>Use somente caracteres padrão</STRONG> (inclusive A–Z, a–z, 0–9 e hifens) quando atribuir FQDNs de seus Lync Servers, servidores de borda e pools.</span><span class="sxs-lookup"><span data-stu-id="0f51e-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="0f51e-116">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="0f51e-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="0f51e-117">Os caracteres incompatíveis em um FQDN frequentemente não são suportados no DNS externo e CAs públicos (isto é, quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="0f51e-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="0f51e-118">Para obter detalhes adicionais, consulte <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS host Records for Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="0f51e-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="0f51e-119">Como os clientes do Lync localizam serviços</span><span class="sxs-lookup"><span data-stu-id="0f51e-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="0f51e-120">O Microsoft Lync 2010, o Lync 2013 e o Lync Mobile são semelhantes em como o cliente encontra e acessa serviços no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f51e-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="0f51e-121">A exceção notável é o aplicativo Lync da Windows Store que usa um processo de local de serviço diferente.</span><span class="sxs-lookup"><span data-stu-id="0f51e-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="0f51e-122">Esta seção detalha dois cenários de como os clientes localizam serviços, primeiro o método tradicional usando uma série de registros SRV e de host, segundo usando apenas os registros do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="0f51e-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="0f51e-123">Atualizações cumulativas para os clientes da área de trabalho alterar o processo de localização de DNS do Lync Server 2010 para todos os clientes, o processo de consulta DNS continua até que uma consulta bem-sucedida seja retornada ou a lista de possíveis registros de DNS seja esgotada e o erro final é retornado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="0f51e-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="0f51e-124">Para todos os clientes **, exceto** para o aplicativo Lync da Windows Store durante a pesquisa de DNS, os registros SRV são consultados e retornados ao cliente na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="0f51e-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="0f51e-125">lyncdiscoverinternal. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web internos</span><span class="sxs-lookup"><span data-stu-id="0f51e-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="0f51e-126">lyncdiscover. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web externos</span><span class="sxs-lookup"><span data-stu-id="0f51e-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="0f51e-127">\_sipinternaltls. \_TCP. \<registro\> de domínio SRV (localizador de serviço) para conexões TLS internas</span><span class="sxs-lookup"><span data-stu-id="0f51e-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="0f51e-128">\_sipinternal. \_TCP. \<registro\> de domínio SRV (localizador de serviço) para conexões TCP internas (executado somente se o TCP for permitido)</span><span class="sxs-lookup"><span data-stu-id="0f51e-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="0f51e-129">\_SIP. \_TLS. \<registro\> de domínio SRV (localizador de serviço) para conexões TLS externas</span><span class="sxs-lookup"><span data-stu-id="0f51e-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="0f51e-130">sipinternal. \<registro\> de domínio a (host) para o pool de front-ends ou diretor, que pode ser resolvido apenas na rede interna</span><span class="sxs-lookup"><span data-stu-id="0f51e-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="0f51e-131">SIP. \<registro\> de domínio a (host) para o pool de front-ends ou diretor na rede interna ou o serviço de borda de acesso quando o cliente é externo</span><span class="sxs-lookup"><span data-stu-id="0f51e-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="0f51e-132">sipexternal. \<registro\> de domínio a (host) para o serviço de borda de acesso quando o cliente é externo</span><span class="sxs-lookup"><span data-stu-id="0f51e-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="0f51e-133">O aplicativo Lync da Windows Store altera o processo completamente porque usa dois registros:</span><span class="sxs-lookup"><span data-stu-id="0f51e-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="0f51e-134">lyncdiscoverinternal. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web internos</span><span class="sxs-lookup"><span data-stu-id="0f51e-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="0f51e-135">lyncdiscover. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web externos</span><span class="sxs-lookup"><span data-stu-id="0f51e-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="0f51e-136">Não há fallback para os outros tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="0f51e-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="0f51e-137">A diferença entre os métodos usados para clientes mais recentes em comparação com clientes mais antigos é que o serviço de descoberta automática está se tornando o método preferencial para localizar todos os serviços.</span><span class="sxs-lookup"><span data-stu-id="0f51e-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="0f51e-138">Quando uma conexão é bem-sucedida, o serviço de descoberta automática retorna todas as URLs de serviços Web para o pool inicial do usuário, incluindo o serviço de mobilidade (conhecido como MCX pelo diretório virtual criado para o serviço no IIS), URLs do Microsoft Lync Web App e do Agendador da Web.</span><span class="sxs-lookup"><span data-stu-id="0f51e-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="0f51e-139">No entanto, tanto a URL do Serviço de Mobilidade Interno como a URL do Serviço de Mobilidade Externo está associado com o FQDN dos Serviços da Web Externos.</span><span class="sxs-lookup"><span data-stu-id="0f51e-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="0f51e-140">Portanto, independente de o dispositivo móvel ser interno ou externo à rede, sempre se conectará ao Serviço de Mobilidade externamente através do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0f51e-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="0f51e-141">Se as atualizações cumulativas do Lync Server 2013:2013 de fevereiro foram instaladas, o serviço de descoberta automática também retorna referências para interno/UCWA, External/UCWA e UCWA.</span><span class="sxs-lookup"><span data-stu-id="0f51e-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="0f51e-142">Essas entradas se referem ao componente da web da Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="0f51e-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="0f51e-143">Atualmente, somente a entrada UCWA é usada e fornece uma referência a uma URL para o componente da Web.</span><span class="sxs-lookup"><span data-stu-id="0f51e-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="0f51e-144">UCWA é usado por clientes móveis do Lync 2013 em vez do serviço de mobilidade do MCX usado pelos clientes móveis do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0f51e-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f51e-145">Ao criar registros SRV, é importante lembrar que eles devem apontar para um registro de DNS A e AAAA (se você estiver usando endereçamento IPv6) no mesmo domínio em que o registro SRV DNS é criado.</span><span class="sxs-lookup"><span data-stu-id="0f51e-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="0f51e-146">Por exemplo, se o registro SRV estiver em contoso.com, o registro a e AAAA (se você estiver usando endereçamento IPv6) aponta para não pode estar no fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="0f51e-147">A configuração padrão é direcionar todo o tráfego do cliente móvel através do site externo.</span><span class="sxs-lookup"><span data-stu-id="0f51e-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="0f51e-148">Você pode modificar as configurações para retornar apenas a URL interna, se isso for mais preferível aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="0f51e-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="0f51e-149">Com esta configuração, os usuários podem usar aplicativos móveis do Lync em seus dispositivos móveis apenas quando estiverem dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="0f51e-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="0f51e-150">Para definir essa configuração, use o cmdlet <STRONG>set-CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0f51e-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0f51e-151">Embora os aplicativos móveis também possam se conectar a outros serviços do Lync Server 2013, como o serviço de catálogo de endereços, as solicitações da Web do aplicativo móvel interno acessam o FQDN da Web externa somente para o serviço de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="0f51e-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="0f51e-152">Outras solicitações de serviços, como solicitações do Catálogo de Endereços, não exigem esta configuração.</span><span class="sxs-lookup"><span data-stu-id="0f51e-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="0f51e-153">Os dispositivos móveis oferecem suporte à descoberta manual de serviços.</span><span class="sxs-lookup"><span data-stu-id="0f51e-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="0f51e-154">Neste caso, cada usuário deve configurar as definições do dispositivo móvel com as URIs do Serviço de Descoberta Automática interna e externa completas, incluindo o protocolo e o caminho, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0f51e-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="0f51e-155">https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root para acesso externo</span><span class="sxs-lookup"><span data-stu-id="0f51e-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="0f51e-156">https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root para acesso interno</span><span class="sxs-lookup"><span data-stu-id="0f51e-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="0f51e-157">Recomendamos que você use a descoberta automática, em vez da descoberta manual.</span><span class="sxs-lookup"><span data-stu-id="0f51e-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="0f51e-158">No entanto, as configurações manuais podem ser úteis para solucionar problemas de conectividade de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="0f51e-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="0f51e-159">Configurando o DNS de Split-Brain com o Lync Server</span><span class="sxs-lookup"><span data-stu-id="0f51e-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="0f51e-160">O DNS de Split-Brain é conhecido por vários nomes, por exemplo, dividir DNS ou DNS de omissão de divisão.</span><span class="sxs-lookup"><span data-stu-id="0f51e-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="0f51e-161">Simplesmente, ele descreve uma configuração de DNS onde há duas zonas DNS com o mesmo namespace – mas uma solicitação somente de serviços de zona DNS e os outros serviços de zona DNS são solicitações somente externas.</span><span class="sxs-lookup"><span data-stu-id="0f51e-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="0f51e-162">No entanto, muitos dos registros SRV do DNS e DNS A contidos no DNS interno não estarão no DNS externo e o contrário também é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="0f51e-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="0f51e-163">Nos casos em que o mesmo registro DNS existe no DNS interno e externo (por exemplo, www.contoso.com), o endereço IP retornado será diferente com base em onde (interno ou externo) a consulta foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="0f51e-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f51e-164">No momento, não há suporte para DNS Split-Brain para a mobilidade ou, mais especificamente, os registros DNS do LyncDiscover e do LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="0f51e-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="0f51e-165">LyncDiscover deve ser definido em um servidor DNS externo e LyncDiscoverInternal deve ser definido em um servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="0f51e-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="0f51e-166">Para os fins desses tópicos, o termo DNS Split-Brain será usado.</span><span class="sxs-lookup"><span data-stu-id="0f51e-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="0f51e-167">Se você estiver configurando um split-brain DNS, as zonas interna e externa contêm um resumo dos tipos de registros DNS necessários em cada zona.</span><span class="sxs-lookup"><span data-stu-id="0f51e-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="0f51e-168">Para obter detalhes, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0f51e-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="0f51e-169">**DNA Interno:**</span><span class="sxs-lookup"><span data-stu-id="0f51e-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="0f51e-170">Contém uma zona do DNS chamada contoso.com, para a qual é autoritativo</span><span class="sxs-lookup"><span data-stu-id="0f51e-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="0f51e-171">A zona contoso.com interna contém:</span><span class="sxs-lookup"><span data-stu-id="0f51e-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="0f51e-172">DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para configuração automática do cliente do Lync Server 2013 interna (opcional)</span><span class="sxs-lookup"><span data-stu-id="0f51e-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="0f51e-173">DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="0f51e-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="0f51e-174">Registros A e AAAA (se você estiver usando endereçamento IPv6) para o nome do pool de front-end, diretor ou nome do pool de diretores e todos os servidores internos que executam o Lync Server 2013 na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="0f51e-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="0f51e-175">Registros A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de borda de cada Lync Server 2013, servidor de borda na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="0f51e-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="0f51e-176">Registros A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de cada servidor de proxy reverso na rede de perímetro (opcional para o gerenciamento de proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="0f51e-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="0f51e-177">Todas as interfaces de borda interna do servidor de borda do Lync Server 2013 na rede de perímetro usam a zona DNS interna para resolver consultas para o contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="0f51e-178">Todos os servidores que executam o Lync Server 2013 e clientes que executam o Lync 2013 na rede corporativa apontam para os servidores DNS internos para resolver consultas para o contoso.com ou o uso do arquivo HOSTs em cada servidor de borda e listar A e AAAA (se você estiver usando o endereçamento IPv6) para servidor de próximo salto, especificamente o diretor ou VIP, o VIP do pool de front-ends ou o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0f51e-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="0f51e-179">**DNS Externo:**</span><span class="sxs-lookup"><span data-stu-id="0f51e-179">**External DNS:**</span></span>

  - <span data-ttu-id="0f51e-180">Contém uma zona de DNS chamada contoso.com, para a qual é autoritativo</span><span class="sxs-lookup"><span data-stu-id="0f51e-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="0f51e-181">A zona contoso.com externa contém:</span><span class="sxs-lookup"><span data-stu-id="0f51e-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="0f51e-182">DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a configuração automática do cliente do Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="0f51e-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="0f51e-183">DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Lync Server 2013 para uso com mobilidade</span><span class="sxs-lookup"><span data-stu-id="0f51e-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="0f51e-184">DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a interface externa de borda de cada Lync Server 2013, servidor de borda ou IP virtual (VIP) do balanceador de carga de hardware na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="0f51e-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="0f51e-185">Registros A e AAAA de DNS (se você estiver usando endereçamento IPv6) para a interface externa do servidor de proxy reverso ou VIP para um pool de servidores de proxy reverso na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="0f51e-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="0f51e-186">Configuração automática sem Split-Brain DNS</span><span class="sxs-lookup"><span data-stu-id="0f51e-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="0f51e-187">Usando o DNS Split-Brain, um usuário do Lync Server 2013 que entra internamente pode aproveitar a configuração automática se a zona DNS interna contiver \_um sipinternaltls. \_registro SRV TCP para cada domínio SIP em uso.</span><span class="sxs-lookup"><span data-stu-id="0f51e-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="0f51e-188">No entanto, se você não usar o DNS Split-Brain, a configuração automática interna de clientes que executam o Lync não funcionará, a menos que uma das soluções alternativas descritas posteriormente nesta seção seja implementada.</span><span class="sxs-lookup"><span data-stu-id="0f51e-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="0f51e-189">Isso ocorre porque o Lync Server 2013 requer que o URI do SIP do usuário corresponda ao domínio do pool de front-ends designado para configuração automática.</span><span class="sxs-lookup"><span data-stu-id="0f51e-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="0f51e-190">Isso também se trata de versões anteriores do Communicator.</span><span class="sxs-lookup"><span data-stu-id="0f51e-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="0f51e-191">Por exemplo, se você tem dois domínios SIP em uso, os registros de serviço (SRV) do DNS a seguir serão necessários:</span><span class="sxs-lookup"><span data-stu-id="0f51e-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="0f51e-192">Se um usuário entrar como bob@contoso.com, o seguinte registro SRV funcionará para a configuração automática, porque o domínio SIP do usuário (contoso.com) corresponde ao domínio do pool de front-ends de configuração automática):</span><span class="sxs-lookup"><span data-stu-id="0f51e-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="0f51e-193">\_sipinternaltls. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="0f51e-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="0f51e-195">Se um usuário entrar como alice@fabrikam.com, o seguinte registro SRV DNS funcionará para a configuração automática do segundo domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="0f51e-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="0f51e-196">\_sipinternaltls. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="0f51e-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="0f51e-198">Para comparação, se um usuário entrar como tim@litwareinc.com, o seguinte registro SRV DNS não funcionará para a configuração automática, porque o domínio SIP do cliente (litwareinc.com) não corresponde ao domínio no qual o pool está (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="0f51e-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="0f51e-199">\_sipinternaltls. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="0f51e-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="0f51e-201">Se a configuração automática for necessária para clientes que executam o Lync, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0f51e-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="0f51e-202">**Os objetos**   de política de grupo usam objetos de política de grupo (GPOs) para popular os valores de servidor corretos.</span><span class="sxs-lookup"><span data-stu-id="0f51e-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f51e-203">Esta opção não habilita a configuração automática, mas automatiza o processo de configuração manual; assim, se esta abordagem for utilizada, os registros SRV associados à configuração automática não são necessários.</span><span class="sxs-lookup"><span data-stu-id="0f51e-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="0f51e-204">**Zona interna correspondente**   crie uma zona no DNS interno que corresponda à zona DNS externa (por exemplo, contoso.com) e crie registros a e AAAA de DNS (se você estiver usando endereçamento IPv6) correspondentes ao pool do Lync Server 2013 usado para configuração automática.</span><span class="sxs-lookup"><span data-stu-id="0f51e-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="0f51e-205">Por exemplo, se um usuário for hospedado no pool01.contoso.net mas entrar no Lync como bob@contoso.com, crie uma zona DNS interna chamada contoso.com e dentro dela, crie um registro DNS A e AAAA (se o endereçamento IPv6 for usado) para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="0f51e-206">**Zona interna de ponto PIN**   se você estiver criando uma zona inteira no DNS interno não é uma opção, você pode criar zonas de ponto PIN (ou seja, dedicada) que correspondem aos Registros SRV necessários para a configuração automática e preencher essas zonas usando o DNSCmd. exe.</span><span class="sxs-lookup"><span data-stu-id="0f51e-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="0f51e-207">O dnscmd.exe é necessário porque a interface do usuário do DNS não é compatível com a criação de zonas exatas.</span><span class="sxs-lookup"><span data-stu-id="0f51e-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="0f51e-208">Por exemplo, se o domínio SIP for contoso.com e você tiver um pool de Front End chamado pool01 que contém dois Servidores Front End, serão necessárias as seguintes zonas exatas e registros A em seu DNS interno:</span><span class="sxs-lookup"><span data-stu-id="0f51e-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="0f51e-209">Se seu ambiente possui um segundo domínio SIP (por exemplo, fabrikam.com), as seguintes zonas exatas e registros A são necessários em seu DNS interno:</span><span class="sxs-lookup"><span data-stu-id="0f51e-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="0f51e-p121">O FQDN do pool de Front End aparece duas vezes, mas com dois endereços IP diferentes. Isso acontece porque o balanceamento de carga do DNS é usado, mas se o balanceamento de carga do hardware for utilizado, existirá apenas uma única entrada do pool de Front End. Além disso, os valores do FQDN do pool de Front End mudam entre os exemplos contoso.com e fabrikam.com, mas os endereços IP permanecem os mesmos. Isso acontece porque usuários entrando a partir do domínio SIP usam o mesmo pool de Front End para a configuração automática.</span><span class="sxs-lookup"><span data-stu-id="0f51e-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="0f51e-214">Para obter detalhes, consulte o artigo do blog DMTF, "configuração automática do Communicator e DNS de Split- [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)Brain" em.</span><span class="sxs-lookup"><span data-stu-id="0f51e-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f51e-215">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="0f51e-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="0f51e-216">Configurando o DNS (sistema de nomes de domínio) para recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="0f51e-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="0f51e-217">Para configurar o DNS para redirecionar o tráfego da Web do Lync Server 2013 para seus sites de recuperação de desastre e failover, você deve estar usando um provedor de DNS que ofereça suporte a GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="0f51e-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="0f51e-218">Você pode configurar seus registros DNS para Web para dar suporte à recuperação de desastres, para que os recursos que usam os serviços Web continuem mesmo se um pool de front-ends inteiro for desativado.</span><span class="sxs-lookup"><span data-stu-id="0f51e-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="0f51e-219">Esse recurso de recuperação de desastre oferece suporte a URLs simples de descoberta automática (URL de Lyncdiscover), de reunião e discagem.</span><span class="sxs-lookup"><span data-stu-id="0f51e-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="0f51e-220">Você define e configura os registros adicionais de host DNS (A e AAAA se estiver usando IPv6) para resolução interna e externa de serviços Web em seu provedor GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="0f51e-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="0f51e-221">Os detalhes a seguir pressupõem pools emparelhados, geograficamente dispersos e GeoDNS com suporte de seu provedor com o DNS de rodízio, ou configurados para usar o Pool1 como principal, e failover para o Pool2 no caso de perda de comunicação ou falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="0f51e-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f51e-222">Registro GeoDNS (exemplo)</span><span class="sxs-lookup"><span data-stu-id="0f51e-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="0f51e-223">Registros de pool (exemplo)</span><span class="sxs-lookup"><span data-stu-id="0f51e-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="0f51e-224">Registros CNAME (exemplo)</span><span class="sxs-lookup"><span data-stu-id="0f51e-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="0f51e-225">Configurações de DNS (selecione uma opção)</span><span class="sxs-lookup"><span data-stu-id="0f51e-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f51e-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-229">Alias Meet.contoso.com para Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-230">Alias Meet.contoso.com para Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-231">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-232">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f51e-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-236">Alias Meet.contoso.com para Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-237">Alias Meet.contoso.com para Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-238">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-239">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f51e-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-243">Alias Dialin.contoso.com para Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-244">Alias Dialin.contoso.com para Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-245">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-246">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f51e-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-250">Alias Dialin.contoso.com para Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-251">Alias Dialin.contoso.com para Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-252">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-253">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f51e-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-257">Alias Lyncdiscoverinternal.contoso.com para Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-258">Alias Lyncdiscoverinternal.contoso.com para Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-259">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-260">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f51e-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-264">Alias Lyncdiscover.contoso.com para Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-265">Alias Lyncdiscover.contoso.com para Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-266">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-267">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f51e-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-271">Alias Scheduler.contoso.com para Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-272">Alias Scheduler.contoso.com para Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-273">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-274">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f51e-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-278">Alias Scheduler.contoso.com para Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0f51e-279">Alias Scheduler.contoso.com para Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f51e-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f51e-280">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="0f51e-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0f51e-281">Usar primário, conectar ao secundário se houver falha</span><span class="sxs-lookup"><span data-stu-id="0f51e-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="0f51e-282">Balanceamento de carga do DNS</span><span class="sxs-lookup"><span data-stu-id="0f51e-282">DNS Load Balancing</span></span>

<span data-ttu-id="0f51e-283">O balanceamento de carga do DNS normalmente é implementado no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f51e-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="0f51e-284">O aplicativo (por exemplo, um cliente executando o Lync), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados da consulta de gravação DNS A e AAAA (se o endereçamento IPv6 for usado) para o nome de domínio totalmente qualificado (FQDN) do pool.</span><span class="sxs-lookup"><span data-stu-id="0f51e-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="0f51e-285">Por exemplo, se houver três servidores front end em um pool chamado pool01.contoso.com, acontecerá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f51e-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="0f51e-286">Clientes que executam o DNS de consulta do Lync para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="0f51e-287">A consulta retorna três endereços IP e os armazena em cache da seguinte maneira (não necessariamente nesta ordem):</span><span class="sxs-lookup"><span data-stu-id="0f51e-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="0f51e-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="0f51e-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="0f51e-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="0f51e-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="0f51e-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="0f51e-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="0f51e-291">O cliente tenta estabelecer uma conexão TCP (Transmission Control Protocol) a um dos endereços IP.</span><span class="sxs-lookup"><span data-stu-id="0f51e-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="0f51e-292">Em caso de falha, o cliente tenta o próximo endereço IP em cache.</span><span class="sxs-lookup"><span data-stu-id="0f51e-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="0f51e-293">Se a conexão TCP for bem sucedida, o cliente negocia o TLS para se conectar ao registrador principal no pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0f51e-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="0f51e-294">Se o cliente tentar todas as entradas em cache sem uma conexão bem-sucedida, o usuário será notificado de que nenhum servidor executando o Lync Server 2013 está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="0f51e-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f51e-295">O balanceamento de carga baseado em DNS é diferente do round robin de DNS (DNS RR), que normalmente faz referência ao balanceamento de carga confiando no DNS para fornecer uma ordem diferente de endereços IP correspondentes aos servidores em um pool.</span><span class="sxs-lookup"><span data-stu-id="0f51e-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="0f51e-296">Normalmente o DNS RR só habilita a distribuição de carga, mas não habilita o failover.</span><span class="sxs-lookup"><span data-stu-id="0f51e-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="0f51e-297">Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A e AAAA (se você estiver usando endereçamento IPv6) falhar, a conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="0f51e-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="0f51e-298">Portanto, o round robin de DNS por si só é menos confiável do que o balanceamento de carga baseado em DNS.</span><span class="sxs-lookup"><span data-stu-id="0f51e-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="0f51e-299">O round robin de DNS pode ser usado em conjunto com o balanceamento de carga do DNS.</span><span class="sxs-lookup"><span data-stu-id="0f51e-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="0f51e-300">O balanceamento de carga do DNS é usado para:</span><span class="sxs-lookup"><span data-stu-id="0f51e-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="0f51e-301">Balanceamento de carga para SIP de servidor para servidor para os servidores de borda</span><span class="sxs-lookup"><span data-stu-id="0f51e-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="0f51e-302">Balanceamento de carga de aplicativos de Serviços de Aplicativos de Comunicações Unificadas (UCAS), como o Atendedor Automático de Conferências, Grupo de Resposta e Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="0f51e-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="0f51e-303">Evitar novas conexões a aplicativos UCAS (também conhecido como "drenagem")</span><span class="sxs-lookup"><span data-stu-id="0f51e-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="0f51e-304">Balanceamento de carga de todo o tráfego cliente-para-servidor entre clientes e Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="0f51e-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="0f51e-305">O balanceamento de carga do DNS não pode ser usado para:</span><span class="sxs-lookup"><span data-stu-id="0f51e-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="0f51e-306">Tráfego da Web de cliente para servidor para o diretor ou servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0f51e-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="0f51e-307">Balanceamento de carga do DNS e tráfego federado:</span><span class="sxs-lookup"><span data-stu-id="0f51e-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="0f51e-308">Se vários registros DNS forem retornados por uma consulta SRV DNS, o serviço de borda de acesso sempre escolhe o registro SRV DNS com a prioridade numérica mais baixa e a maior espessura numérica.</span><span class="sxs-lookup"><span data-stu-id="0f51e-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="0f51e-309">O documento "um RR DNS para especificar o local dos serviços (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> da força de tarefas de engenharia da Internet especifica que, se houver vários registros SRV DNS definidos, a prioridade será usada primeiro e, em seguida, peso.</span><span class="sxs-lookup"><span data-stu-id="0f51e-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="0f51e-310">Por exemplo, o registro SRV DNS A tem um peso de 20 e uma prioridade de 40 e o registro de SRV DNS B tem um peso de 10 e prioridade de 50.</span><span class="sxs-lookup"><span data-stu-id="0f51e-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="0f51e-311">O registro SRV do DNS A com prioridade 40 será selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f51e-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="0f51e-312">As regras a seguir se aplicam à seleção de registro SRV de DNS:</span><span class="sxs-lookup"><span data-stu-id="0f51e-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="0f51e-313">A prioridade é considerada primeiro.</span><span class="sxs-lookup"><span data-stu-id="0f51e-313">Priority is considered first.</span></span> <span data-ttu-id="0f51e-314">Um cliente deve tentar entrar em contato com o host de destino definido pelo registro SRV de DNS com a prioridade de número mais baixo possível.</span><span class="sxs-lookup"><span data-stu-id="0f51e-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="0f51e-315">Os destinos com a mesma prioridade devem ser tentados em uma ordem definida pelo campo weight.</span><span class="sxs-lookup"><span data-stu-id="0f51e-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="0f51e-316">O campo peso especifica um peso relativo para entradas com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="0f51e-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="0f51e-317">Pesos maiores devem receber uma maior probabilidade de ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f51e-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="0f51e-318">Os administradores DNS devem usar peso 0 quando não houver nenhuma seleção de servidor para fazer.</span><span class="sxs-lookup"><span data-stu-id="0f51e-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="0f51e-319">Na presença de registros contendo pesos maiores que 0, os registros com peso 0 devem ter uma chance muito pequena de serem selecionados.</span><span class="sxs-lookup"><span data-stu-id="0f51e-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="0f51e-320">Se vários registros SRV DNS com prioridade e peso iguais forem retornados, o serviço de borda de acesso selecionará o registro SRV que foi recebido primeiro do servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="0f51e-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

