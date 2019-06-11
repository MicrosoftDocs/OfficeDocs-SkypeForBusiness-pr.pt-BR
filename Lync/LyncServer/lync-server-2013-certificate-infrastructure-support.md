---
title: 'Lync Server 2013: Suporte à infraestrutura de certificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13e04e2e6746dac9c40eaa6df0c3b33d52c6a547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="6d1e5-102">Suporte à infraestrutura de certificado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d1e5-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d1e5-103">_**Tópico da última modificação:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6d1e5-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6d1e5-104">O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para dar suporte a conexões de camada de transporte (TLS) e TLS (MTLS) mútua.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="6d1e5-105">Por padrão, o Lync Server 2013 está configurado para usar o TLS para conexões de cliente para servidor.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="6d1e5-106">O MTLS é usado para conexões entre servidores.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="6d1e5-107">Os certificados MTLS devem ser emitidos por autoridades de certificação (CAs) confiáveis para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="6d1e5-108">O Lync Server dá suporte a certificados emitidos a partir das seguintes autoridades de certificação:</span><span class="sxs-lookup"><span data-stu-id="6d1e5-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="6d1e5-109">Certificados emitidos por uma CA interna:</span><span class="sxs-lookup"><span data-stu-id="6d1e5-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="6d1e5-110">A autoridade de certificação do sistema operacional Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="6d1e5-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="6d1e5-111">A autoridade de certificação do sistema operacional Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="6d1e5-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="6d1e5-112">A autoridade de certificação do sistema operacional Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6d1e5-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="6d1e5-113">A autoridade de certificação do sistema operacional Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6d1e5-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="6d1e5-114">A autoridade de certificação do sistema operacional Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6d1e5-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="6d1e5-115">Certificados emitidos por uma autoridade de certificação pública</span><span class="sxs-lookup"><span data-stu-id="6d1e5-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="6d1e5-116">A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="6d1e5-117">Para o lançamento do 2013, Lync Server 2013 e outros produtos do Microsoft Server, incluindo Exchange 2013 e SharePoint Server, suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização do servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="6d1e5-118">Para obter detalhes, consulte Gerenciando a [autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="6d1e5-119">Para conexões de clientes que executam o sistema operacional Windows 7, o sistema operacional Windows Server 2008 R2 e o Microsoft Office Communicator 2007 Phone Edition, o Lync Server 2013 inclui suporte para (mas não exigem) certificados assinados usando o SHA-256 função hash criptográfico.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="6d1e5-120">Para dar suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma autoridade de certificação pública que usa SHA-256.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="6d1e5-121">Para obter detalhes sobre requisitos de certificado, consulte [requisitos de infraestrutura de certificado para o Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="6d1e5-122">Para obter detalhes sobre o uso de caracteres curinga com certificados, consulte [suporte a certificados curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="6d1e5-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

