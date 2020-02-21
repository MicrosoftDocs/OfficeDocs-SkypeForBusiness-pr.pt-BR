---
title: 'Lync Server 2013: requisitos de configuração para proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13026da5515615610c960fe4648d5c58f64f99fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="1f3a0-102">Requisitos de configuração para o proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f3a0-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f3a0-103">_**Última modificação do tópico:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="1f3a0-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="1f3a0-104">O Lync Server 2013 impõe alguns requisitos em comunicações do cliente externo que são passados para os serviços Web externos hospedados no diretor, pool de diretores, servidor front-end ou pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="1f3a0-105">O proxy reverso também é responsável por publicar o servidor do Office Web Apps, se você estiver oferecendo conferência para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f3a0-106">O Lync Server 2013 não especifica um determinado proxy reverso que você deve usar.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="1f3a0-107">O Lync Server 2013 só define os requisitos operacionais que o proxy reverso deve ser capaz de fazer.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="1f3a0-108">Normalmente, o proxy reverso que você já implantou em sua infraestrutura pode ser capaz de atender aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="1f3a0-109">Requisitos de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="1f3a0-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="1f3a0-110">As operações funcionais que o Lync Server 2013 esperam que um proxy reverso seja executado são:</span><span class="sxs-lookup"><span data-stu-id="1f3a0-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="1f3a0-111">Use SSL (Secure Socket Layer) e TLS (Transport Layer Security) implementados usando certificados adquiridos de uma autoridade de certificação pública para se conectar aos serviços Web externos publicados do diretor, pool de diretores, servidor front-end ou pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="1f3a0-112">O diretor e o servidor front-end podem estar em um pool com balanceamento de carga usando balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="1f3a0-113">É possível publicar sites internos usando certificados para criptografia ou publicá-los por meio de um meio não criptografado, se necessário.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="1f3a0-114">Capaz de publicar um site da Web hospedado internamente externamente usando um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="1f3a0-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="1f3a0-115">Capaz de publicar todo o conteúdo do site hospedado.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="1f3a0-116">Por padrão, você pode usar a \*\* / \*\* diretiva, que é reconhecida pela maioria dos servidores Web para significar "publicar todo o conteúdo no servidor Web".</span><span class="sxs-lookup"><span data-stu-id="1f3a0-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="1f3a0-117">Você também pode modificar a diretiva — por exemplo, **/Uwca/\***, que significa "publicar todo o conteúdo sob o diretório virtual Ucwa."</span><span class="sxs-lookup"><span data-stu-id="1f3a0-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="1f3a0-118">Deve ser configurável para exigir conexões SSL (Secure Sockets Layer) e/ou TLS (Transport Layer Security) com clientes que solicitam conteúdo de um site publicado.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="1f3a0-119">Deve aceitar certificados com entradas de nome alternativo de entidade (SAN).</span><span class="sxs-lookup"><span data-stu-id="1f3a0-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="1f3a0-120">Deve ser capaz de permitir a associação de um certificado a um ouvinte ou a uma interface por meio da qual o FQDN de serviços Web externos resolverá.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="1f3a0-121">As configurações de escuta são preferidas para interfaces.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="1f3a0-122">Muitos ouvintes podem ser configurados em uma única interface.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="1f3a0-123">Deve permitir a configuração do controle de cabeçalho de host.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="1f3a0-124">Geralmente, o cabeçalho de host original enviado pelo cliente solicitante deve ser passado de forma transparente, em vez de ser modificado pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="1f3a0-125">Ponte de tráfego SSL e TLS de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="1f3a0-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="1f3a0-126">O proxy reverso pode descriptografar o pacote no recebimento e, em seguida, criptografar novamente o pacote no envio.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="1f3a0-127">A ponte de tráfego TCP não criptografado de uma porta (por exemplo, TCP 80) para outra (por exemplo, TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="1f3a0-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="1f3a0-128">Permitir a configuração ou aceitar a autenticação NTLM, sem autenticação e autenticação de passagem.</span><span class="sxs-lookup"><span data-stu-id="1f3a0-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

