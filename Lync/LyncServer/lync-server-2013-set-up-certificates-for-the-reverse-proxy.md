---
title: 'Lync Server 2013: Configurar certificados para o proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="be4bd-102">Configurar certificados para o proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be4bd-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be4bd-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="be4bd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="be4bd-104">Cada servidor proxy reverso exige um certificado de servidor Web para ser usado pelo serviço de escuta.</span><span class="sxs-lookup"><span data-stu-id="be4bd-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="be4bd-105">O certificado do servidor Web deve ser emitido por uma autoridade de certificação pública (CA).</span><span class="sxs-lookup"><span data-stu-id="be4bd-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="be4bd-106">Para obter detalhes sobre esse e outros requisitos de certificado, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="be4bd-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="be4bd-107">Para configurar um certificado de serviços Web para o proxy reverso</span><span class="sxs-lookup"><span data-stu-id="be4bd-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="be4bd-108">Você já deve ter configurado seu proxy reverso, incluindo a configuração do certificado de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="be4bd-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="be4bd-109">Se você não fez isso antes de iniciar a implantação de seus servidores de borda, use os procedimentos [para configurar servidores proxy inversos para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para criar uma solicitação e instalar o certificado de serviços Web e, em seguida, criar cada regra de publicação da Web e Configure-o para usar o certificado.</span><span class="sxs-lookup"><span data-stu-id="be4bd-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

