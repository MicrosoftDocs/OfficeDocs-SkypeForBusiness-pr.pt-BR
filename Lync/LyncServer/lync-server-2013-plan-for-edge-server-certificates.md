---
title: 'Lync Server 2013: planejar certificados do servidor de borda'
description: 'Lync Server 2013: planejar certificados do servidor de borda.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578187"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="ca722-103">Planejar certificados de servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca722-103">Plan for Edge Server certificates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca722-104">_**Última modificação do tópico:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="ca722-104">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="ca722-105">A criação de certificado para borda é simplificada no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca722-105">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="ca722-106">**Fluxograma de certificados do Servidor de Borda**</span><span class="sxs-lookup"><span data-stu-id="ca722-106">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="ca722-107">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="ca722-107">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="ca722-108">Criar um certificado público único, certificar-se de ter uma chave privada de exportação definida para o certificado e atribui-lo às seguintes interfaces externas do Servidor de Borda usando o assistente de certificado:</span><span class="sxs-lookup"><span data-stu-id="ca722-108">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca722-109">Não há suporte para certificados curinga no Lync Server, exceto onde usados para resumir as URLs simples através do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="ca722-109">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="ca722-110">Você deve definir nomes alternativos de entidades distintos (SANs) para cada nome de domínio SIP, serviço de borda de webconferência, serviço de borda A/V e domínio XMPP oferecidos por sua implantação.</span><span class="sxs-lookup"><span data-stu-id="ca722-110">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ca722-111">Introduzido no Lync Server 2013, a preparação de certificados de autenticação de áudio/vídeo com antecedência do tempo de expiração do certificado atual requer alguns planejamentos adicionais.</span><span class="sxs-lookup"><span data-stu-id="ca722-111">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="ca722-112">Em vez de um certificado com várias finalidades para a interface de borda externa, você precisará de dois certificados, um atribuído ao serviço de borda de acesso e serviço de borda de Webconferência e um certificado para o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="ca722-112">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="ca722-113">Para obter detalhes adicionais, consulte <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">preparando o AV e certificados OAuth no Lync Server 2013 using-rolo in Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="ca722-113">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca722-114">No caso de um pool de servidores de borda, exporte o certificado com a chave privada para cada servidor de borda e atribua o certificado a cada serviço do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ca722-114">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="ca722-115">Faça o mesmo para o certificado de servidor de borda interno, exportando o certificado com a chave privada e atribuindo a cada interface de borda interna.</span><span class="sxs-lookup"><span data-stu-id="ca722-115">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="ca722-116">Certificar-se de ter uma chave privada de exportação atribuída ao certificado</span><span class="sxs-lookup"><span data-stu-id="ca722-116">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="ca722-117">Serviço de borda de acesso (chamado de **borda de acesso SIP externa** no assistente de certificado)</span><span class="sxs-lookup"><span data-stu-id="ca722-117">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="ca722-118">Serviço de borda de Webconferência (referido como **borda de Webconferência externa** no assistente de certificado)</span><span class="sxs-lookup"><span data-stu-id="ca722-118">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="ca722-119">Serviço de Autenticação A/V (referido como **Borda A/V externa** no assistente de certificado)</span><span class="sxs-lookup"><span data-stu-id="ca722-119">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="ca722-120">Criar um certificado interno único com chave privada de exportação, copiá-lo e atribui-lo a cada uma das interfaces internas do Servidor de Borda:</span><span class="sxs-lookup"><span data-stu-id="ca722-120">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="ca722-121">Servidor de Borda (referido como **Borda interna** no assistente de certificado)</span><span class="sxs-lookup"><span data-stu-id="ca722-121">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca722-122">É possível usar certificados separados e distintos para cada serviço de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ca722-122">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="ca722-123">Um bom motivo para escolher certificados separados é se você deseja usar o novo recurso de certificado de reversão para o certificado de serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="ca722-123">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="ca722-124">No caso desse recurso, é recomendável desacoplar o certificado de serviço de borda a/V do serviço de borda de acesso e do serviço de borda de Webconferência.</span><span class="sxs-lookup"><span data-stu-id="ca722-124">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="ca722-125">Se você optar por solicitar, adquirir e atribuir certificados separados para cada serviço, deverá solicitar que a chave privada seja exportável para o serviço de borda A/V (novamente, isso estará na realidade o serviço de autenticação A/V) e atribuir o mesmo certificado à interface externa de borda A/V em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ca722-125">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca722-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="ca722-126">See Also</span></span>


[<span data-ttu-id="ca722-127">Preparando certificados AV e OAuth no Lync Server 2013 usando-o-rolo no set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="ca722-127">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="ca722-128">Alterações no Lync Server 2013 que afetam o planejamento do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ca722-128">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

