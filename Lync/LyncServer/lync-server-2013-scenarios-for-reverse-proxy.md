---
title: 'Lync Server 2013: Cenários de proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="aee85-102">Cenários de proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee85-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aee85-103">_**Tópico da última modificação:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="aee85-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="aee85-104">Proxies invertidos são necessários no Lync Server 2013 para fornecer acesso a serviços e recursos, como a reunião e URLs de discagem, o catálogo de endereços, o conteúdo da reunião, a expansão da lista de distribuição, os serviços de mobilidade e outros.</span><span class="sxs-lookup"><span data-stu-id="aee85-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="aee85-105">O cenário de proxy reverso típico no Lync Server 2013 é permitir que clientes externos (por exemplo, o cliente da área de trabalho ou o cliente do Lync Web App) acessem o diretor ou serviços Web externos do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="aee85-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="aee85-106">**Proxy reverso e serviços Web externos**</span><span class="sxs-lookup"><span data-stu-id="aee85-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="aee85-107">![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="aee85-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="aee85-108">Durante a fase de planejamento, você define os requisitos para o proxy reverso em uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee85-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="aee85-109">O proxy reverso habilita o acesso aos recursos para os seguintes clientes externos:</span><span class="sxs-lookup"><span data-stu-id="aee85-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="aee85-110">Cliente de desktop Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="aee85-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="aee85-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="aee85-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="aee85-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="aee85-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="aee85-113">Aplicativo Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="aee85-113">Lync Windows Store app</span></span>

<span data-ttu-id="aee85-114">Ao planejar a implantação do Lync Server 2013, você mapeia os requisitos reais do Lync Server 2013 para os recursos de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="aee85-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="aee85-115">Os clientes externos se conectarão ao proxy reverso na porta TCP 443 e usarão Secure Socket Layer (SSL) ou Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="aee85-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="aee85-116">Os clientes móveis do Microsoft Lync podem se conectar na porta TCP 80, mas somente quando você executa a conexão inicial com os serviços de descoberta do Lync e o administrador configurou os registros CNAME (ou alias) apropriados do sistema de nomes de domínio (DNS) e aceita que essa a comunicação não será criptografada.</span><span class="sxs-lookup"><span data-stu-id="aee85-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="aee85-117">Serviços Web externos do Lync Server 2013 (implantados no servidor front-end e/ou no director) esperam uma conexão de um proxy reverso na porta TCP 4443 e espera que a conexão seja SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="aee85-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aee85-118">As portas de escuta padrão sugeridas para os serviços Web externos são TCP 8080 para tráfego HTTP e TCP 4443 para tráfego HTTPS.</span><span class="sxs-lookup"><span data-stu-id="aee85-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="aee85-119">O construtor de topologias oferece uma oportunidade de substituir os padrões e definir suas próprias portas de escuta para os serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="aee85-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="aee85-120">É importante observar que o proxy reverso se comunica com os serviços Web externos, e os clientes externos se comunicam com o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="aee85-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="aee85-121">O cliente externo se comunica com o proxy reverso na porta TCP 443, mas você pode redefinir a porta em que o proxy reverso se comunica com os serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="aee85-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="aee85-122">As opções no construtor de topologia para substituir as portas de escuta padrão dos serviços Web permitem que você solucione conflitos de portas de escuta que possam surgir na sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="aee85-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="aee85-123">Os serviços Web externos do Lync Server 2013 esperam um cabeçalho de host não modificado do cliente para identificar qual serviço e diretório do servidor Web o cliente está tentando usar.</span><span class="sxs-lookup"><span data-stu-id="aee85-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="aee85-124">As solicitações devem aparecer como se tivessem vindo do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="aee85-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="aee85-125">Os serviços Web externos usam diretórios virtuais do servidor Web (vDir) definidos que fornecem os serviços oferecidos aos clientes.</span><span class="sxs-lookup"><span data-stu-id="aee85-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="aee85-126">Os serviços Web de identificação externa específicos são:</span><span class="sxs-lookup"><span data-stu-id="aee85-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="aee85-127">O vDir "reunião" para reuniões de conferência via Web</span><span class="sxs-lookup"><span data-stu-id="aee85-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="aee85-128">O vDir de "discagem" para acesso por telefone e conferência telefônica</span><span class="sxs-lookup"><span data-stu-id="aee85-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="aee85-129">O vDir de "descoberta automática" do aplicativo Lync da Windows Store, do Lync Mobile e do cliente de desktop Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="aee85-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="aee85-130">A descoberta automática no Lync Server 2013 é conhecida pelo nome DNS "lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="aee85-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="aee85-131">Os serviços não definidos são acessados pelo cliente externo por meio de chamadas diretas para os serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="aee85-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="aee85-132">Por exemplo, a expansão do grupo de distribuição (DLX) e o serviço de catálogo de endereços (ABS) são acessados por chamadas diretas para os serviços Web externos e vDirs associados.</span><span class="sxs-lookup"><span data-stu-id="aee85-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="aee85-133">O cliente conhece o caminho real para o vDir e constrói um Uniform Record Locator (URL) com base nessas informações.</span><span class="sxs-lookup"><span data-stu-id="aee85-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="aee85-134">O cliente acessaria o serviço de catálogo de endereços usando uma URL semelhante a`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="aee85-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="aee85-135">O Office Web Apps Server quando a conferência é definida e configurada como parte da topologia do Lync Server</span><span class="sxs-lookup"><span data-stu-id="aee85-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aee85-136">O Office Web Apps Server é um servidor de funções separado e não está configurado como parte dos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="aee85-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="aee85-137">Este servidor é publicado separadamente para acesso de cliente.</span><span class="sxs-lookup"><span data-stu-id="aee85-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="aee85-138">Defina a ponte SSL para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="aee85-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="aee85-139">A porta externa TCP 443 é mapeada para a porta de serviços Web externos do TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="aee85-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="aee85-140">Para HTTP não criptografado, a porta TCP 80 é mapeada para a porta TCP 8080 dos serviços Web externos</span><span class="sxs-lookup"><span data-stu-id="aee85-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="aee85-141">Planejar os ouvintes de proxy reverso para publicar recursos do servidor Web</span><span class="sxs-lookup"><span data-stu-id="aee85-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="aee85-142">Solicite e configure o certificado para o proxy reverso com base nos serviços que serão oferecidos.</span><span class="sxs-lookup"><span data-stu-id="aee85-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="aee85-143">Se configurado com os nomes alternativos de entidades corretos, este certificado pode ser compartilhado por todos os ouvintes configurados no servidor proxy reverso</span><span class="sxs-lookup"><span data-stu-id="aee85-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="aee85-144">Recursos disponíveis para planejar sua implantação de proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="aee85-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="aee85-145">Coleta de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee85-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="aee85-146">Resumo de certificado - Proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee85-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="aee85-147">Resumo de porta - Proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee85-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="aee85-148">Resumo de DNS - Proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee85-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

