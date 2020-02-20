---
title: 'Lync Server 2013: configurar certificados para o proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d03cec1dd2397b8471788f5c4661305e7ea93e42
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="a7ffb-102">Configurar certificados para o proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ffb-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7ffb-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a7ffb-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a7ffb-p101">Cada servidor proxy reverso requer um certificado de servidor Web para ser usado pelo serviço de escuta. O certificado de servidor Web deve ser emitido por uma autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="a7ffb-106">Para obter detalhes sobre esse e outros requisitos de certificado, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a7ffb-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="a7ffb-107">Para configurar um certificado de Serviços Web para o proxy reverso</span><span class="sxs-lookup"><span data-stu-id="a7ffb-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="a7ffb-108">Você já deve ter configurado seu proxy reverso, incluindo a configuração do certificado de Serviços Web.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="a7ffb-109">Se você não fez isso antes de iniciar a implantação dos servidores de borda, use os procedimentos para [Configurar servidores de proxy reverso para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para criar uma solicitação e instalar o certificado de serviços Web e, em seguida, criar cada regra de publicação da Web e configurá-la para usar o certificado.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

