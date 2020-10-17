---
title: 'Lync Server 2013: lista de verificação de implantação de tronco SIP'
description: 'Lync Server 2013: lista de verificação da implantação de tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559037"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="d38f3-103">Lista de verificação de implantação de tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d38f3-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d38f3-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d38f3-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d38f3-105">Antes de implantar um tronco SIP, você e seu provedor de serviços devem trocar algumas informações básicas de conexão sobre seus respectivos pontos de extremidade de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="d38f3-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="d38f3-106">Obtenha as informações a seguir para cada gateway ITSP com o qual você se conectará:</span><span class="sxs-lookup"><span data-stu-id="d38f3-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="d38f3-107">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="d38f3-107">IP address</span></span>

  - <span data-ttu-id="d38f3-108">FQDN (nome de domínio totalmente qualificado)</span><span class="sxs-lookup"><span data-stu-id="d38f3-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d38f3-109">O provedor de serviços pode pedir a você que se conecte a mais de um gateway ITSP.</span><span class="sxs-lookup"><span data-stu-id="d38f3-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="d38f3-110">Nesse caso, você deve configurar uma conexão entre cada gateway do ITSP e cada servidor de mediação em seu pool.</span><span class="sxs-lookup"><span data-stu-id="d38f3-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="d38f3-111">As informações que você fornece aos seu provedor de serviços dependem do tipo de conexão do seu tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="d38f3-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="d38f3-112">Para MPLS (Multiprotocol Label Switching) ou conexões de rede privada, forneça ao ITSP o Endereço IP roteável publicamente do roteador em sua rede de perímetro (também conhecida como sub-rede filtrada).</span><span class="sxs-lookup"><span data-stu-id="d38f3-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="d38f3-113">Verifique se o gateway ou Controlador de Borda de Sessão no ITSP pode alcançar este endereço.</span><span class="sxs-lookup"><span data-stu-id="d38f3-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="d38f3-114">Além disso, forneça ao ITSP o FQDN do seu servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d38f3-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="d38f3-115">Para conexões VPN (rede virtual privada ), forneça ao ITSP o endereço IP do seu servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="d38f3-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="d38f3-116">Considerações de Certificado</span><span class="sxs-lookup"><span data-stu-id="d38f3-116">Certificate Considerations</span></span>

<span data-ttu-id="d38f3-117">Para determinar se você precisa de um certificado para tronco SIP, verifique com seu ITSP sobre suporte de protocolo:</span><span class="sxs-lookup"><span data-stu-id="d38f3-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="d38f3-118">Se seu ITSP oferecer suporte somente ao protocolo TCP, não será necessário um certificado.</span><span class="sxs-lookup"><span data-stu-id="d38f3-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="d38f3-119">Se seu ITSP oferecer suporte ao protocolo TLS, o ITSP deverá fornecer um certificado a você.</span><span class="sxs-lookup"><span data-stu-id="d38f3-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d38f3-120">O SIP funciona em conjunto com protocolo RTP ou SRTP, os protocolos que gerenciam os dados de voz reais em chamadas VoIP.</span><span class="sxs-lookup"><span data-stu-id="d38f3-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="d38f3-121">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="d38f3-121">Deployment Process</span></span>

<span data-ttu-id="d38f3-122">Para implementar o lado do Lync Server da conexão do tronco SIP, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d38f3-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="d38f3-123">Usando o construtor de topologias do Lync Server, crie e configure a topologia do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="d38f3-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="d38f3-124">Para obter detalhes, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d38f3-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="d38f3-125">Usando o painel de controle do Lync Server, configure o roteamento de voz para o novo domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="d38f3-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="d38f3-126">Para obter detalhes, consulte [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d38f3-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="d38f3-127">Teste a conectividade usando o cmdlet **Test-CsPstnOutboundCall**.</span><span class="sxs-lookup"><span data-stu-id="d38f3-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="d38f3-128">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server ou a ajuda do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d38f3-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

