---
title: Requisitos de infraestrutura de certificado do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b64f06d9ca879236c0842554c1779fb7bbc1cbe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="ae1b9-102">Requisitos de infraestrutura de certificado para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae1b9-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae1b9-103">_**Última modificação do tópico:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="ae1b9-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="ae1b9-104">O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para suportar conexões TLS e TLS mútuo (MTLS).</span><span class="sxs-lookup"><span data-stu-id="ae1b9-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="ae1b9-105">O Lync Server usa certificados para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="ae1b9-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="ae1b9-106">Conexões TLS entre cliente e servidor</span><span class="sxs-lookup"><span data-stu-id="ae1b9-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="ae1b9-107">Conexões MTLS entre servidores</span><span class="sxs-lookup"><span data-stu-id="ae1b9-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="ae1b9-108">Federação usando a descoberta automática de parceiros no DNS</span><span class="sxs-lookup"><span data-stu-id="ae1b9-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="ae1b9-109">Acesso de usuários remotos a IM (mensagens instantâneas)</span><span class="sxs-lookup"><span data-stu-id="ae1b9-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="ae1b9-110">Acesso de usuário externo a sessões A/V (áudio/vídeo), compartilhamento de aplicativos e conferência</span><span class="sxs-lookup"><span data-stu-id="ae1b9-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="ae1b9-111">Solicitações móveis utilizando descoberta automática de Serviços Web</span><span class="sxs-lookup"><span data-stu-id="ae1b9-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="ae1b9-112">Para o Lync Server, os seguintes requisitos comuns se aplicam:</span><span class="sxs-lookup"><span data-stu-id="ae1b9-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="ae1b9-113">Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).</span><span class="sxs-lookup"><span data-stu-id="ae1b9-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="ae1b9-114">Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).</span><span class="sxs-lookup"><span data-stu-id="ae1b9-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="ae1b9-115">Todos os certificados devem ser assinados usando um algoritmo de assinatura suportado pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="ae1b9-116">O Lync Server 2013 suporta o pacote de resumos SHA-1 e SHA-2 (224, 256, 384 e 512 bits) e atende ou supera os requisitos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="ae1b9-117">Para suporte ao sistema operacional, [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)consulte.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae1b9-118">O uso do algoritmo de assinatura RSASSA-PSS não é suportado e pode levar a erros em problemas de encaminhamento de chamadas e login, entre outros problemas.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="ae1b9-119">O registro automático é suportado para servidores internos que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="ae1b9-120">O registro automático não é suportado para servidores de borda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="ae1b9-121">Quando você envia uma solicitação de certificado baseado em web para uma AC Windows Server 2003, você deve submete-la de um computador que esteja executando Windows Server 2003 com SP2 ou Windows XP.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="ae1b9-122">Observe que, embora o KB922706 oferece suporte para resolver problemas com o registro de certificados de web contra registro de web de Serviços de Certificado do Windows Server 2003, ele não torna possível utilizar o Windows Server 2008, Windows Vista, ou Windows 7 para solicitar um certificado de uma AC Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="ae1b9-123">Há suporte para os comprimentos de chave de criptografia de 1024, 2048 e 4096.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="ae1b9-124">São recomendados os comprimentos de chave de 2048 e superior.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="ae1b9-125">A compilação padrão ou a assinatura de hash, algoritmo é RSA.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="ae1b9-126">Os algoritmos ECDH\_P256\_, ECDH P384 e\_ECDH P521 também têm suporte.</span><span class="sxs-lookup"><span data-stu-id="ae1b9-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="ae1b9-127">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ae1b9-127">In This Section</span></span>

  - [<span data-ttu-id="ae1b9-128">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae1b9-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="ae1b9-129">Requisitos de certificado para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae1b9-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="ae1b9-130">Requisitos de certificado para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae1b9-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="ae1b9-131">Requisitos de certificado para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae1b9-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

