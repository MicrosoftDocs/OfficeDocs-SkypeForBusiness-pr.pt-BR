---
title: 'Lync Server 2013: Solicitar certificados para componentes de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e848e5fb8ea120bab2251dff776e2c9c27eacca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="2146b-102">Solicitar certificados para componentes de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2146b-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2146b-103">_**Tópico da última modificação:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="2146b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="2146b-104">Os certificados necessários para dar suporte a acesso externo a usuários incluem certificados emitidos por uma CA (autoridade de certificação) pública e certificados emitidos por uma CA corporativa interna:</span><span class="sxs-lookup"><span data-stu-id="2146b-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="2146b-105">Os certificados necessários para a interface externa do servidor de borda e o proxy reverso devem ser emitidos por uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="2146b-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="2146b-106">Os certificados necessários para a interface interna podem ser emitidos por uma CA pública ou por uma CA corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="2146b-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="2146b-107">Recomendamos o uso de uma autoridade de certificação interna do Windows Server 2008, da autoridade de certificação do Windows Server 2008 R2, da autoridade de certificação do Windows Server 2012 ou da autoridade de certificação do Windows Server 2012 R2 para a criação desses certificados para economizar na despesa de usar certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="2146b-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2146b-108">Pode levar tempo para processar solicitações de certificado, especialmente solicitações para CAs públicas, portanto, você deve solicitar certificados para seus servidores de borda cedo o suficiente para garantir que estejam disponíveis quando você iniciar a implantação de seus componentes de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2146b-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="2146b-109">Para obter um resumo dos requisitos de certificado para servidores de borda, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisitos de certificado para acesso de usuários externos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2146b-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2146b-110">Embora você possa optar por usar uma autoridade de certificação pública para o certificado de borda interno, recomendamos que use uma CA corporativa interna para esses outros certificados, em vez de minimizar o custo dos certificados.</span><span class="sxs-lookup"><span data-stu-id="2146b-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="2146b-111">Para obter um resumo dos requisitos de certificado para servidores de borda, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2146b-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2146b-112">Quando você instala um servidor de borda, o programa de instalação inclui um assistente de certificado que facilita as tarefas de solicitação, atribuição e instalação de certificados, conforme descrito na seção <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados de borda para o Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="2146b-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="2146b-113">Se você deseja solicitar certificados antes de instalar um servidor de borda (por exemplo, para economizar tempo durante a implantação real dos componentes do servidor de borda), é possível fazer isso usando servidores internos, desde que você garanta que os certificados sejam exportáveis e contenham todos os nomes alternativos de assunto obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="2146b-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="2146b-114">Esta documentação não fornece procedimentos para usar servidores internos para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="2146b-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="2146b-115">Solicitar certificados de uma CA pública</span><span class="sxs-lookup"><span data-stu-id="2146b-115">Request certificates from a public CA</span></span>

<span data-ttu-id="2146b-116">A implantação do servidor de borda requer um único certificado público para as interfaces externas de servidores de borda, que é usada para o serviço de borda de acesso, o serviço de borda de Webconferência e para o serviço de autenticação A/V.</span><span class="sxs-lookup"><span data-stu-id="2146b-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="2146b-117">Esse certificado deve ter uma chave privada exportável para garantir que o serviço de autenticação A/V use as mesmas chaves em todos os servidores de borda em um pool.</span><span class="sxs-lookup"><span data-stu-id="2146b-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="2146b-118">O proxy inverso, que é usado com o Microsoft Internet Security and Acceleration (ISA) Server 2006 ou o Microsoft Forefront Threat Management Gateway 2010, também requer um certificado público.</span><span class="sxs-lookup"><span data-stu-id="2146b-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="2146b-119">Solicitar certificados de uma CA corporativa interna</span><span class="sxs-lookup"><span data-stu-id="2146b-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="2146b-120">Os certificados necessários para a interface de borda interna podem ser emitidos por uma CA (autoridade de certificação) pública ou uma CA interna.</span><span class="sxs-lookup"><span data-stu-id="2146b-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="2146b-121">Você pode usar uma CA corporativa interna para ajudar a minimizar o custo dos certificados.</span><span class="sxs-lookup"><span data-stu-id="2146b-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="2146b-122">Se a sua organização tiver uma CA interna implantada, os certificados para a borda interna deverão ser emitidos pela CA interna.</span><span class="sxs-lookup"><span data-stu-id="2146b-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="2146b-123">Usar uma CA corporativa interna para certificados internos pode reduzir o custo dos certificados.</span><span class="sxs-lookup"><span data-stu-id="2146b-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="2146b-124">Para obter um resumo dos requisitos de certificado para componentes de extremidade, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2146b-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="2146b-125">Para obter detalhes sobre como usar uma autoridade de certificação pública para obter certificados, consulte [solicitar certificados para componentes Edge no Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="2146b-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="2146b-126">Para obter detalhes sobre como solicitar, instalar e atribuir certificados, consulte [configurar certificados de borda para o Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2146b-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

