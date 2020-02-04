---
title: 'Lync Server 2013: Lista de verificação de tronco SIP'
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
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="ee677-102">Lista de verificação de tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee677-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee677-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ee677-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ee677-104">Antes de poder implantar um tronco SIP, você e seu provedor de serviços devem trocar informações básicas de conexão sobre seus respectivos pontos de extremidade de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="ee677-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="ee677-105">Obtenha as seguintes informações para cada gateway do ITSP ao qual você irá se conectar:</span><span class="sxs-lookup"><span data-stu-id="ee677-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="ee677-106">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="ee677-106">IP address</span></span>

  - <span data-ttu-id="ee677-107">FQDN (nome de domínio totalmente qualificado)</span><span class="sxs-lookup"><span data-stu-id="ee677-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee677-108">O provedor de serviço pode solicitar que você se conecte a mais de um gateway do ITSP.</span><span class="sxs-lookup"><span data-stu-id="ee677-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="ee677-109">Nesse caso, você deve configurar uma conexão entre cada gateway do ITSP e cada servidor de mediação em seu pool.</span><span class="sxs-lookup"><span data-stu-id="ee677-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="ee677-110">As informações que você fornece ao seu provedor de serviço dependem do seu tipo de conexão de tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="ee677-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="ee677-111">Para conexões de rótulo de multiprotocolo (MPLS) ou de rede privada, forneça ao ITSP o endereço IP publicamente roteável do roteador em sua rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada).</span><span class="sxs-lookup"><span data-stu-id="ee677-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="ee677-112">Verifique se o gateway ou o controle de borda de sessão (SBC) no ITSP pode chegar a este endereço.</span><span class="sxs-lookup"><span data-stu-id="ee677-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="ee677-113">Além disso, dê ao ITSP o FQDN do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ee677-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="ee677-114">Para conexões VPN (rede virtual privada), dê ao ITSP o endereço IP do seu servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="ee677-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="ee677-115">Considerações sobre certificado</span><span class="sxs-lookup"><span data-stu-id="ee677-115">Certificate Considerations</span></span>

<span data-ttu-id="ee677-116">Para determinar se você precisa de um certificado para o entroncamento SIP, consulte o ITSP sobre o suporte ao protocolo:</span><span class="sxs-lookup"><span data-stu-id="ee677-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="ee677-117">Se o seu ITSP der suporte somente para TCP (Transmission Control Protocol), você não precisará de um certificado.</span><span class="sxs-lookup"><span data-stu-id="ee677-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="ee677-118">Se o seu ITSP suporta TLS (Transport Layer Security), o ITSP deve fornecer um certificado.</span><span class="sxs-lookup"><span data-stu-id="ee677-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee677-119">O SIP funciona em conjunto com o protocolo de transporte em tempo real (RTP) ou SSTP (protocolo de transporte em tempo real seguro), os protocolos que gerenciam os dados de voz reais nas chamadas de protocolo de voz pela Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="ee677-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="ee677-120">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="ee677-120">Deployment Process</span></span>

<span data-ttu-id="ee677-121">Para implementar o lado do Lync Server da conexão do tronco SIP, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ee677-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="ee677-122">Usando o construtor de topologias do Lync Server, crie e configure a topologia de domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="ee677-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="ee677-123">Para obter detalhes, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ee677-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="ee677-124">Usando o painel de controle do Lync Server, configure o roteamento de voz para o novo domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="ee677-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="ee677-125">Para obter detalhes, consulte [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ee677-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="ee677-126">Testar a conectividade usando o cmdlet **Test-CsPstnOutboundCall** .</span><span class="sxs-lookup"><span data-stu-id="ee677-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="ee677-127">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server ou a ajuda do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee677-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

