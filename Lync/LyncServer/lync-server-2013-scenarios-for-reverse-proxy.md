---
title: 'Lync Server 2013: cenários para proxy reverso'
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
ms.openlocfilehash: be05e3b63b73daeecbd4c0b34d9a893a8e27fa83
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="5e38c-102">Cenários de proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e38c-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e38c-103">_**Última modificação do tópico:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="5e38c-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="5e38c-104">Os proxies reversos são necessários no Lync Server 2013 para fornecer acesso a serviços e recursos como as URLs de reunião e discagem, o catálogo de endereços, o conteúdo da reunião, a expansão da lista de distribuição, os serviços de mobilidade e outros.</span><span class="sxs-lookup"><span data-stu-id="5e38c-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="5e38c-105">O cenário de proxy reverso típico no Lync Server 2013 é permitir que clientes externos (por exemplo, o cliente da área de trabalho ou o cliente do Lync Web App) acessem o diretor ou serviços Web externos do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5e38c-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="5e38c-106">**Proxy reverso e serviços Web externos**</span><span class="sxs-lookup"><span data-stu-id="5e38c-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="5e38c-107">![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="5e38c-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="5e38c-108">Durante a fase de planejamento, você define os requisitos para o proxy reverso em uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e38c-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="5e38c-109">O proxy reverso permite o acesso a recursos para os seguintes clientes externos:</span><span class="sxs-lookup"><span data-stu-id="5e38c-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="5e38c-110">Cliente de desktop do Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5e38c-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="5e38c-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5e38c-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="5e38c-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="5e38c-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="5e38c-113">Aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="5e38c-113">Lync Windows Store app</span></span>

<span data-ttu-id="5e38c-114">Ao planejar sua implantação do Lync Server 2013, você mapeia os requisitos reais do Lync Server 2013 para os recursos de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5e38c-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="5e38c-115">Os clientes externos se conectarão ao proxy reverso na porta TCP 443 e usarão Secure Socket Layer (SSL) ou Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="5e38c-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="5e38c-116">Os clientes móveis do Microsoft Lync podem se conectar na porta TCP 80, mas somente quando se executa a conexão inicial com os serviços de descoberta do Lync e o administrador configurou os registros CNAME (ou alias) adequados do sistema de nomes de domínio (DNS) e aceita que este a comunicação não será criptografada.</span><span class="sxs-lookup"><span data-stu-id="5e38c-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="5e38c-117">Lync Server 2013 serviços Web externos (implantados no servidor front-end e/ou no diretor) esperam uma conexão de um proxy reverso na porta TCP 4443 e espera que a conexão seja SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="5e38c-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5e38c-118">As portas de escuta padrão sugeridas para os serviços Web externos são TCP 8080 para tráfego HTTP e TCP 4443 para tráfego HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e38c-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="5e38c-119">O construtor de topologias oferece uma oportunidade de substituir os padrões e definir suas próprias portas de escuta para os serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="5e38c-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="5e38c-120">É importante observar que o proxy reverso se comunica com os serviços Web externos e os clientes externos se comunicam com o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5e38c-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="5e38c-121">O cliente externo se comunica com o proxy reverso na porta TCP 443, mas você pode redefinir de que porta o proxy reverso se comunica com os serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="5e38c-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="5e38c-122">As opções no construtor de topologia para substituir as portas de escuta padrão para os serviços Web permitem resolver conflitos de porta de escuta que podem surgir em sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="5e38c-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="5e38c-123">Lync Server 2013 serviços Web externos esperam um cabeçalho de host não modificado do cliente para identificar qual serviço e diretório de servidor Web o cliente está tentando usar.</span><span class="sxs-lookup"><span data-stu-id="5e38c-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="5e38c-124">As solicitações devem aparecer como se tivessem vindo do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="5e38c-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="5e38c-125">Os serviços Web externos usam diretórios virtuais de servidor Web (vDir) definidos que fornecem os serviços oferecidos aos clientes.</span><span class="sxs-lookup"><span data-stu-id="5e38c-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="5e38c-126">Os serviços Web específicos identificáveis externamente são:</span><span class="sxs-lookup"><span data-stu-id="5e38c-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="5e38c-127">O vDir de "reunião" para reuniões de conferência via Web</span><span class="sxs-lookup"><span data-stu-id="5e38c-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="5e38c-128">O vDir de "discagem" para acesso por telefone e conferência telefônica</span><span class="sxs-lookup"><span data-stu-id="5e38c-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="5e38c-129">O vDir de "descoberta automática" do aplicativo Lync da Windows Store, Lync Mobile e cliente de desktop Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5e38c-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="5e38c-130">A descoberta automática no Lync Server 2013 é conhecida pelo nome DNS "lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="5e38c-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="5e38c-131">Os serviços não definidos são acessados pelo cliente externo por chamadas diretas para os serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="5e38c-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="5e38c-132">Por exemplo, a expansão de grupo de distribuição (DLX) e o serviço de catálogo de endereços (ABS) são acessados por chamadas diretas para os serviços Web externos e vDirs associados.</span><span class="sxs-lookup"><span data-stu-id="5e38c-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="5e38c-133">O cliente sabe o caminho real para o vDir e constrói um localizador de registro uniforme (URL) com base nessas informações.</span><span class="sxs-lookup"><span data-stu-id="5e38c-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="5e38c-134">O cliente acessaria o serviço de catálogo de endereços usando uma URL semelhante à`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="5e38c-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="5e38c-135">O servidor do Office Web Apps quando a conferência é definida e configurada como parte da topologia do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e38c-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5e38c-136">O servidor do Office Web Apps é um servidor de função separado e não está configurado como parte dos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="5e38c-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="5e38c-137">Este servidor é publicado separadamente para acesso para cliente.</span><span class="sxs-lookup"><span data-stu-id="5e38c-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="5e38c-138">Defina ponte SSL para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="5e38c-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="5e38c-139">A porta externa TCP 443 é mapeada para a porta de serviços Web externos de TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="5e38c-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="5e38c-140">Para HTTP não criptografado, a porta TCP 80 é mapeada para a porta TCP 8080 de serviços Web externos</span><span class="sxs-lookup"><span data-stu-id="5e38c-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="5e38c-141">Planejar os ouvintes de proxy reverso para publicar recursos de servidor Web</span><span class="sxs-lookup"><span data-stu-id="5e38c-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="5e38c-142">Solicite e configure o certificado para o proxy reverso com base nos serviços que serão oferecidos.</span><span class="sxs-lookup"><span data-stu-id="5e38c-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="5e38c-143">Se estiver configurado com os nomes alternativos de entidade corretos, esse certificado poderá ser compartilhado por todos os ouvintes configurados no servidor de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="5e38c-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="5e38c-144">Recursos disponíveis para planejar a implantação do seu proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="5e38c-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="5e38c-145">Coleta de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e38c-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="5e38c-146">Resumo de certificado-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e38c-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="5e38c-147">Resumo de porta-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e38c-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="5e38c-148">Resumo de DNS-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e38c-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

