---
title: Controle de admissão de chamada com um gateway de PSTN de terceiros ou PBX
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="083d8-102">Controle de admissão de chamada no Lync Server 2013 com um gateway de PSTN de terceiros ou PBX</span><span class="sxs-lookup"><span data-stu-id="083d8-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="083d8-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="083d8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="083d8-104">Este tópico descreve exemplos de como o controle de admissão de chamada (CAC) pode ser implantado no link entre a interface do gateway do Servidor de Mediação e um gateway PSTN ou PBX de terceiros.</span><span class="sxs-lookup"><span data-stu-id="083d8-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="083d8-105">Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="083d8-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="083d8-106">O CAC pode ser implantado no link WAN da interface do gateway do Servidor de Mediação para um PBX de terceiros ou gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="083d8-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="083d8-107">**Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN**</span><span class="sxs-lookup"><span data-stu-id="083d8-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="083d8-108">![Caso 1: CAC entre o gateway PSTN do servidor de mediação](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: CAC entre o gateway PSTN do servidor de mediação")</span><span class="sxs-lookup"><span data-stu-id="083d8-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="083d8-109">Neste exemplo, o CAC é aplicado entre o servidor de mediação e um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="083d8-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="083d8-110">Se um usuário do cliente do Lync no site da rede 1 colocar uma chamada PSTN por meio do gateway PSTN no site de rede 2, a mídia fluirá pelo link de WAN.</span><span class="sxs-lookup"><span data-stu-id="083d8-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="083d8-111">Portanto, duas verificações CAC são executadas para cada sessão PSTN:</span><span class="sxs-lookup"><span data-stu-id="083d8-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="083d8-112">Entre o aplicativo cliente do Lync e o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="083d8-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="083d8-113">Entre o servidor de mediação e o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="083d8-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="083d8-114">Isto funciona para as chamadas PSTN de entrada para um cliente no Local de Rede 1 e para chamadas PSTN de saída provenientes de um aplicativo cliente no Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="083d8-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="083d8-115">Certifique-se de que a sub-rede do IP ao qual o gateway PSTN pertence está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="083d8-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="083d8-116">Verifique se a sub-rede IP à qual as duas interfaces do servidor de mediação pertence está configurada e associada ao local de rede 1.</span><span class="sxs-lookup"><span data-stu-id="083d8-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="083d8-117">Para obter detalhes, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="083d8-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="083d8-118">Caso 2: CAC entre o servidor de mediação e um PBX de terceiros com ponto de terminação de mídia</span><span class="sxs-lookup"><span data-stu-id="083d8-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="083d8-119">Esta configuração é similar ao Caso 1.</span><span class="sxs-lookup"><span data-stu-id="083d8-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="083d8-120">Nos dois casos, o servidor de mediação sabe qual dispositivo termina a mídia na extremidade oposta do link de WAN, e o endereço IP do gateway PSTN ou PBX com ponto de terminação de mídia (MTP) está configurado no servidor de mediação como o próximo nó.</span><span class="sxs-lookup"><span data-stu-id="083d8-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="083d8-121">**Caso 2: CAC entre o Servidor de Mediação e um PBX de terceiros com MTP**</span><span class="sxs-lookup"><span data-stu-id="083d8-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="083d8-122">![Caso 2: CAC entre o PBX do servidor de mediação com MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: CAC entre o PBX do servidor de mediação com MTP")</span><span class="sxs-lookup"><span data-stu-id="083d8-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="083d8-123">Neste exemplo, o CAC é aplicado entre o servidor de mediação e o PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="083d8-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="083d8-124">Se um usuário cliente do Lync no site de rede 1 colocar uma chamada PSTN por meio do PBX/MTP localizado no site de rede 2, a mídia fluirá pelo link de WAN.</span><span class="sxs-lookup"><span data-stu-id="083d8-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="083d8-125">Portanto, para cada sessão PSTN duas verificações CAC são executadas:</span><span class="sxs-lookup"><span data-stu-id="083d8-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="083d8-126">Entre o aplicativo cliente do Lync e o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="083d8-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="083d8-127">Entre o servidor de mediação e o PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="083d8-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="083d8-128">Isto funciona para ambas, chamadas PSTN de entrada para um cliente no Local de Rede 1 e chamadas PSTN de saída provenientes de um cliente no Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="083d8-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="083d8-129">Certifique-se de que a sub-rede do IP à qual o MTP pertence está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="083d8-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="083d8-130">Verifique se a sub-rede IP à qual as duas interfaces do servidor de mediação pertence está configurada e associada ao local de rede 1.</span><span class="sxs-lookup"><span data-stu-id="083d8-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="083d8-131">Para obter detalhes, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="083d8-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="083d8-132">Caso 3: CAC entre o servidor de mediação e um PBX de terceiros sem um ponto de terminação de mídia</span><span class="sxs-lookup"><span data-stu-id="083d8-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="083d8-133">O Caso 3 é um ligeiramente diferente dos dois primeiros.</span><span class="sxs-lookup"><span data-stu-id="083d8-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="083d8-134">Se não houver MTP no PBX de terceiros, para uma solicitação de sessão de saída para o PBX de terceiros, o servidor de mediação não saberá onde a mídia será encerrada no limite do PBX.</span><span class="sxs-lookup"><span data-stu-id="083d8-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="083d8-135">Nesse caso, a mídia flui diretamente entre o servidor de mediação e o dispositivo de ponto de extremidade de terceiros.</span><span class="sxs-lookup"><span data-stu-id="083d8-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="083d8-136">**Caso 3: CAC entre o Servidor de Mediação e um PBX de terceiros sem MTP**</span><span class="sxs-lookup"><span data-stu-id="083d8-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="083d8-137">![Caso 3: CAC entre o PBX do servidor de mediação sem MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: CAC entre o PBX do servidor de mediação sem MTP")</span><span class="sxs-lookup"><span data-stu-id="083d8-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="083d8-138">Neste exemplo, se um usuário cliente do Lync no site da rede 1 colocar uma chamada para um usuário por meio do PBX, o servidor de mediação poderá executar o CAC verifica somente no trecho do proxy (entre o aplicativo cliente do Lync e o servidor de mediação).</span><span class="sxs-lookup"><span data-stu-id="083d8-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="083d8-139">Como o servidor de mediação não tem informações sobre o dispositivo de ponto de extremidade enquanto a sessão está sendo solicitada, as verificações de CAC não podem ser executadas no link de WAN (entre o servidor de mediação e o ponto de extremidade de terceiros) antes do estabelecimento da chamada.</span><span class="sxs-lookup"><span data-stu-id="083d8-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="083d8-140">No entanto, depois que a sessão for estabelecida, o servidor de mediação facilitará a contabilidade para a largura de banda usada no tronco.</span><span class="sxs-lookup"><span data-stu-id="083d8-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="083d8-141">Para chamadas originadas no ponto de extremidade de terceiros, as informações sobre esse dispositivo de ponto de extremidade estão disponíveis no momento da solicitação de sessão, e a verificação de CAC pode ser executada nos dois lados do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="083d8-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="083d8-142">Certifique-se de que a sub-rede do IP à qual os dispositivos de ponto de extremidade pertencem está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="083d8-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="083d8-143">Verifique se a sub-rede IP à qual as duas interfaces do servidor de mediação pertence está configurada e associada ao local de rede 1.</span><span class="sxs-lookup"><span data-stu-id="083d8-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="083d8-144">Para obter detalhes, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="083d8-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

