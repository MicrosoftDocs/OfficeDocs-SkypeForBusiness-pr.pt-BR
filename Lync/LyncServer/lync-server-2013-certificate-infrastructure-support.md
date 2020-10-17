---
title: Suporte à infraestrutura de certificado do Lync Server 2013
description: Suporte à infraestrutura de certificado do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544227"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="87546-103">Suporte à infraestrutura de certificado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87546-103">Certificate infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87546-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="87546-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="87546-105">O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para suportar conexões de TLS e TLS mútuo (MTLS).</span><span class="sxs-lookup"><span data-stu-id="87546-105">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="87546-106">Por padrão, o Lync Server 2013 é configurado para usar o TLS para conexões de cliente para servidor.</span><span class="sxs-lookup"><span data-stu-id="87546-106">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="87546-107">O MTLS é usado para conexões entre servidores.</span><span class="sxs-lookup"><span data-stu-id="87546-107">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="87546-108">Os certificados MTLS devem ser emitidos por autoridades de certificação confiáveis (CAs) para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87546-108">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="87546-109">O Lync Server oferece suporte a certificados emitidos por meio das seguintes autoridades de certificação:</span><span class="sxs-lookup"><span data-stu-id="87546-109">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="87546-110">Certificados emitidos por uma autoridade de certificação interna</span><span class="sxs-lookup"><span data-stu-id="87546-110">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="87546-111">A autoridade de certificação do sistema operacional Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="87546-111">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="87546-112">A autoridade de certificação do sistema operacional Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="87546-112">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="87546-113">A CA do sistema operacional Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="87546-113">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="87546-114">A autoridade de certificação do sistema operacional Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="87546-114">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="87546-115">A CA do sistema operacional Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="87546-115">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="87546-116">Certificados emitidos por uma autoridade de certificação pública</span><span class="sxs-lookup"><span data-stu-id="87546-116">Certificates issued from a public CA</span></span>

<span data-ttu-id="87546-117">A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos.</span><span class="sxs-lookup"><span data-stu-id="87546-117">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="87546-118">Para a versão 2013, Lync Server 2013 e outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o SharePoint Server, dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="87546-118">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="87546-119">Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="87546-119">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="87546-120">Para conexões de clientes que executam o sistema operacional Windows 7, o sistema operacional Windows Server 2008 R2 e o Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 inclui suporte para (mas não exige) certificados assinados usando a função de hash de criptografia SHA-256.</span><span class="sxs-lookup"><span data-stu-id="87546-120">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="87546-121">Para suportar acesso externo usando SHA-256, o certificado externo é emitido por um AC público usando SHA-256.</span><span class="sxs-lookup"><span data-stu-id="87546-121">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="87546-122">Para obter detalhes sobre os requisitos de certificado, consulte [Certificate Infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="87546-122">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="87546-123">Para obter detalhes sobre o uso de caracteres curinga com certificados, confira [suporte a certificados curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="87546-123">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

