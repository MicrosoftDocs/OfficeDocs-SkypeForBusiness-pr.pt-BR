---
title: 'Lync Server 2013: Visão geral do tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 340c27b3e874ea3d9f55aac2b415bd1a440aab9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="37099-102">Visão geral do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37099-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37099-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="37099-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="37099-p101">A implantação de troncos SIP pode ser um grande passo para a simplificação das telecomunicações da sua organização e a preparação para as melhorias atuais nas comunicações em tempo real. Umas das principais vantagens do tronco SIP é que você pode consolidar as conexões da sua organização com a PSTN (Rede Telefônica Pública Comutada) em um local central, ao contrário de seu predecessor, o tronco TDM, que normalmente requer um tronco separado de cada filial.</span><span class="sxs-lookup"><span data-stu-id="37099-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="37099-106">Entroncamento SIP no Lync Server</span><span class="sxs-lookup"><span data-stu-id="37099-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="37099-107">Os recursos de entroncamento SIP do Lync Server 2013 permitem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="37099-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="37099-108">Um usuário empresarial, dentro ou fora do firewall corporativo, pode fazer uma chamada local ou uma chamada de longa distância especificada por um número em conformidade com o E. 164 que é encerrado na PSTN como um serviço do provedor de serviços correspondente.</span><span class="sxs-lookup"><span data-stu-id="37099-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="37099-109">Qualquer assinante PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo, discando um número do Direct Inward Dialing (DID) associado a esse usuário da empresa.</span><span class="sxs-lookup"><span data-stu-id="37099-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="37099-110">Redução de custo</span><span class="sxs-lookup"><span data-stu-id="37099-110">Cost Savings</span></span>

<span data-ttu-id="37099-111">As reduções de custo associadas ao tronco SIP podem ser substanciais:</span><span class="sxs-lookup"><span data-stu-id="37099-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="37099-112">Geralmente, as chamadas de longa distância custam menos através de um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="37099-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="37099-113">Você pode cortar os custos de gerenciamento e reduzir a complexidade da implementação.</span><span class="sxs-lookup"><span data-stu-id="37099-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="37099-p102">A interface de tarifa básica (BRI) e a interface de tarifa primária (PRI) podem ser eliminadas se você conectar um tronco SIP diretamente ao ITSP, por um custo significativamente inferior. Nos troncos TDM, os provedores de serviço cobram as chamadas por minuto. O custo do tronco SIP pode ser baseado no uso da largura de banda, e você pode comprar incrementos menores e mais econômicos. (O custo real depende do modelo de serviço do que você escolhe).</span><span class="sxs-lookup"><span data-stu-id="37099-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="37099-118">Tronco SIP vs. hospedagem de um gateway PSTN ou IP-PBX</span><span class="sxs-lookup"><span data-stu-id="37099-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="37099-p103">Uma vez que os troncos SIP se conectam diretamente ao provedor de serviço, você pode eliminar os seus gateways PSTN e seu custo de gerenciamento e complexidade. O uso de um tronco SIP pode levar a cortes substanciais no custo, através da manutenção e administração reduzida.</span><span class="sxs-lookup"><span data-stu-id="37099-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="37099-121">Serviços de VoIP expandidos</span><span class="sxs-lookup"><span data-stu-id="37099-121">Expanded VoIP Services</span></span>

<span data-ttu-id="37099-122">Os recursos de voz são frequentemente a principal motivação para implantar o tronco SIP, mas o suporte de voz é apenas a primeira etapa.</span><span class="sxs-lookup"><span data-stu-id="37099-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="37099-123">Com o entroncamento SIP, você pode estender os recursos de VoIP e habilitar o Lync Server 2013 para fornecer um conjunto mais rico de serviços.</span><span class="sxs-lookup"><span data-stu-id="37099-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="37099-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="37099-124">For example:</span></span>

  - <span data-ttu-id="37099-125">A detecção de presença avançada para dispositivos que não estão executando o Lync Server 2013 pode oferecer uma melhor integração com telefones celulares, permitindo que você veja quando um usuário está em uma chamada de celular.</span><span class="sxs-lookup"><span data-stu-id="37099-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="37099-126">As chamadas de emergência E9-1-1 permitem que as autoridades que atendem às chamadas 911 determinem o local do chamador a partir do número de telefone.</span><span class="sxs-lookup"><span data-stu-id="37099-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37099-127">Consulte o ITSP para obter uma lista de serviços que eles suportam e podem habilitar para sua organização.</span><span class="sxs-lookup"><span data-stu-id="37099-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

