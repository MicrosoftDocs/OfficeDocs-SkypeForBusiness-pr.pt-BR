---
title: 'Lync Server 2013: Roteamento entre troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaa41fe229e9246506fd92eb9f48767994997e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="d80d5-102">Roteamento entre troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d80d5-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80d5-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d80d5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d80d5-104">O Lync Server 2013 pode interconectar um IP-PBX a um gateway PSTN (rede telefônica pública comutada) para que as chamadas de um telefone PBX possam ser roteadas para a PSTN, e chamadas PSTN de entrada possam ser roteadas para um telefone PBX (central privada de intercâmbio).</span><span class="sxs-lookup"><span data-stu-id="d80d5-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="d80d5-105">Da mesma forma, o Lync Server 2013 pode interconectar dois ou mais sistemas de PBX IP para que as chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d80d5-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="d80d5-106">Este recurso de roteamento de intertronco pode ser configurado usando o cmdlet do Shell de gerenciamento do Lync Server, **set-CsTrunkConfiguration**, com o novo parâmetro PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="d80d5-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="d80d5-107">Esse parâmetro especifica o conjunto de registros de uso PSTN a ser usado.</span><span class="sxs-lookup"><span data-stu-id="d80d5-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="d80d5-108">Um tronco usa esse uso de PSTN para determinar uma rota e para direcionar todas as chamadas de entrada de acordo.</span><span class="sxs-lookup"><span data-stu-id="d80d5-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="d80d5-109">O diagrama a seguir ilustra o Lync Server 2013 fornecendo interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d80d5-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="d80d5-110">**Roteamento entre troncos entre gateway e PBX IP**</span><span class="sxs-lookup"><span data-stu-id="d80d5-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="d80d5-111">![O servidor do Lync conectando o diagrama PSTN gateway/IP-PBX](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "O servidor do Lync conectando o diagrama PSTN gateway/IP-PBX")</span><span class="sxs-lookup"><span data-stu-id="d80d5-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="d80d5-112">O diagrama a seguir ilustra o Lync Server 2013 interconectando dois sistemas de PBX IP.</span><span class="sxs-lookup"><span data-stu-id="d80d5-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="d80d5-113">**Roteamento entre troncos entre dois PBXs de IP**</span><span class="sxs-lookup"><span data-stu-id="d80d5-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="d80d5-114">![Diagrama de sistemas IP-PAX de interconexão do Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de sistemas IP-PAX de interconexão do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="d80d5-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

