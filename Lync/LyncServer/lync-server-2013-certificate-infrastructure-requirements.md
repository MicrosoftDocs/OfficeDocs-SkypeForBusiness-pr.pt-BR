---
title: Requisitos de infraestrutura de certificado do Lync Server 2013
description: Requisitos de infraestrutura de certificado do Lync Server 2013.
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
ms.openlocfilehash: 02c7e69f272c29f0ba9386f403db326b4d39bbff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544287"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="9eced-103">Requisitos de infraestrutura de certificado para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eced-103">Certificate infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eced-104">_**Última modificação do tópico:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="9eced-104">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="9eced-105">O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para suportar conexões TLS e TLS mútuo (MTLS).</span><span class="sxs-lookup"><span data-stu-id="9eced-105">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="9eced-106">O Lync Server usa certificados para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="9eced-106">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="9eced-107">Conexões TLS entre cliente e servidor</span><span class="sxs-lookup"><span data-stu-id="9eced-107">TLS connections between client and server</span></span>

  - <span data-ttu-id="9eced-108">Conexões MTLS entre servidores</span><span class="sxs-lookup"><span data-stu-id="9eced-108">MTLS connections between servers</span></span>

  - <span data-ttu-id="9eced-109">Federação usando a descoberta automática de parceiros no DNS</span><span class="sxs-lookup"><span data-stu-id="9eced-109">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="9eced-110">Acesso de usuários remotos a IM (mensagens instantâneas)</span><span class="sxs-lookup"><span data-stu-id="9eced-110">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="9eced-111">Acesso de usuário externo a sessões A/V (áudio/vídeo), compartilhamento de aplicativos e conferência</span><span class="sxs-lookup"><span data-stu-id="9eced-111">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="9eced-112">Solicitações móveis utilizando descoberta automática de Serviços Web</span><span class="sxs-lookup"><span data-stu-id="9eced-112">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="9eced-113">Para o Lync Server, os seguintes requisitos comuns se aplicam:</span><span class="sxs-lookup"><span data-stu-id="9eced-113">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="9eced-114">Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).</span><span class="sxs-lookup"><span data-stu-id="9eced-114">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="9eced-115">Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).</span><span class="sxs-lookup"><span data-stu-id="9eced-115">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="9eced-116">Todos os certificados devem ser assinados usando um algoritmo de assinatura suportado pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9eced-116">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="9eced-117">O Lync Server 2013 suporta o pacote de resumos SHA-1 e SHA-2 (224, 256, 384 e 512 bits) e atende ou supera os requisitos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9eced-117">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="9eced-118">Para suporte ao sistema operacional, consulte [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .</span><span class="sxs-lookup"><span data-stu-id="9eced-118">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9eced-119">O uso do algoritmo de assinatura RSASSA-PSS não é suportado e pode levar a erros em problemas de encaminhamento de chamadas e login, entre outros problemas.</span><span class="sxs-lookup"><span data-stu-id="9eced-119">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="9eced-120">O registro automático é suportado para servidores internos que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9eced-120">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="9eced-121">O registro automático não é suportado para servidores de borda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9eced-121">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="9eced-122">Quando você envia uma solicitação de certificado baseado em web para uma AC Windows Server 2003, você deve submete-la de um computador que esteja executando Windows Server 2003 com SP2 ou Windows XP.</span><span class="sxs-lookup"><span data-stu-id="9eced-122">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="9eced-123">Observe que, embora o KB922706 oferece suporte para resolver problemas com o registro de certificados de web contra registro de web de Serviços de Certificado do Windows Server 2003, ele não torna possível utilizar o Windows Server 2008, Windows Vista, ou Windows 7 para solicitar um certificado de uma AC Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="9eced-123">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="9eced-124">Há suporte para os comprimentos de chave de criptografia de 1024, 2048 e 4096.</span><span class="sxs-lookup"><span data-stu-id="9eced-124">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="9eced-125">São recomendados os comprimentos de chave de 2048 e superior.</span><span class="sxs-lookup"><span data-stu-id="9eced-125">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="9eced-126">A compilação padrão ou a assinatura de hash, algoritmo é RSA.</span><span class="sxs-lookup"><span data-stu-id="9eced-126">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="9eced-127">Os \_ algoritmos ECDH P256, ECDH \_ P384 e ECDH \_ P521 também têm suporte.</span><span class="sxs-lookup"><span data-stu-id="9eced-127">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="9eced-128">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9eced-128">In This Section</span></span>

  - [<span data-ttu-id="9eced-129">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eced-129">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="9eced-130">Requisitos de certificado para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eced-130">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="9eced-131">Requisitos de certificado para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eced-131">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="9eced-132">Requisitos de certificado para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eced-132">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

