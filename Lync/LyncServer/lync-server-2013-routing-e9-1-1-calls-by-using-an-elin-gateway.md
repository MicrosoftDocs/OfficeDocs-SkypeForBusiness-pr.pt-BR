---
title: 'Lync Server 2013: roteamento de chamadas E9-1-1 usando um gateway ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7382411774fb9fcb51bf7ade7d64795781c0ebb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="44660-102">Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44660-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44660-103">_**Última modificação do tópico:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="44660-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="44660-104">Alguns parceiros do Programa de interoperabilidade aberta de comunicações unificadas fornecem gateways ELIN (Emergency Location Identification Number) qualificados, que podem servir como uma alternativa para uma conexão de tronco SIP para um provedor de serviços E9-1-1 qualificado.</span><span class="sxs-lookup"><span data-stu-id="44660-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="44660-105">Os gateways ELIN suportam conectividade ISDN ou CAMA (Centralized Automatic Message Accounting) para os serviços E9-1-1 baseados em PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="44660-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="44660-106">Para obter detalhes sobre os parceiros que fornecem gateways ELIN e links para sua documentação [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425), consulte.</span><span class="sxs-lookup"><span data-stu-id="44660-106">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="44660-107">Como conexões de tronco SIP para provedores de serviço E9-1-1, os gateways do ELIN também fornecem o meio de roteamento de uma chamada de emergência para o ponto de resposta de segurança pública (PSAP) mais apropriado do chamador, mas esses gateways usam um ELIN como o identificador de local.</span><span class="sxs-lookup"><span data-stu-id="44660-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="44660-108">Você define ELINs para cada local de resposta de emergência (ERL) em sua organização (para obter detalhes, consulte [Managing locations for Elin gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="44660-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="44660-109">Quando você usa um gateway ELIN para chamadas de emergência, usa a mesma infraestrutura do Lync Server E9-1 que você usaria para uma conexão de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="44660-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="44660-110">Ou seja, o banco de dados do serviço de informações de local fornece o local para o cliente do Lync Server e a política de local habilita o recurso e define o roteamento.</span><span class="sxs-lookup"><span data-stu-id="44660-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="44660-111">Com um gateway ELIN, no entanto, você precisa adicionar o ELINs ao banco de dados do serviço de informações de local e fazer com que sua operadora de PSTN o carregue no banco de dados de identificação de local automática (ALI).</span><span class="sxs-lookup"><span data-stu-id="44660-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="44660-112">Quando um cliente do Lync obtém seu local do serviço de informações de local, o local inclui o ELIN.</span><span class="sxs-lookup"><span data-stu-id="44660-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="44660-113">Durante uma chamada de emergência, o ELIN é incluído com a localização enviada para o gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="44660-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="44660-114">O gateway ELIN identifica a chamada como uma chamada de emergência e troca o número do chamador pela Elin.</span><span class="sxs-lookup"><span data-stu-id="44660-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="44660-115">O gateway ELIN, em seguida, encaminha a chamada para o PSTN com o ELIN como o número de chamada.</span><span class="sxs-lookup"><span data-stu-id="44660-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="44660-116">O provedor E9-1-1 do PSTN procura o ELIN no banco de dados ALI, que é um banco de dados que acompanha o banco de dados MSAG (Catálogo de Endereços Principal).</span><span class="sxs-lookup"><span data-stu-id="44660-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="44660-117">O PSTN envia a chamada para o PSAP mais apropriado com base na pesquisa ALI, e o PSAP envia socorristas para a localização do chamador com base na pesquisa ALI.</span><span class="sxs-lookup"><span data-stu-id="44660-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="44660-118">O número da chamada é armazenado em cache no gateway ELIN por uma quantidade de tempo pré-definida para retorno de chamadas.</span><span class="sxs-lookup"><span data-stu-id="44660-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="44660-119">Durante uma chamada de retorno, o PSAP alcança o gateway ELIN, que troca o Elin pelo número da DID (discagem direta interna).</span><span class="sxs-lookup"><span data-stu-id="44660-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="44660-120">O gateway ELIN suporta chamadas de emergência somente de dentro da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="44660-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="44660-121">Eles não suportam chamadas de emergência feitas de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="44660-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44660-122">Para obter detalhes sobre como usar uma conexão de tronco SIP para chamadas de emergência, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP Trunk in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="44660-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="44660-123">O diagrama a seguir mostra como uma chamada de emergência é roteada do Lync Server para o PSAP quando você usa um gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="44660-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="44660-124">**Encaminhando chamadas de E9-1-1 com um gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="44660-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="44660-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="44660-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="44660-126">Um SIP INVITE que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44660-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="44660-127">O Lync Server corresponde ao número de emergência e encaminha a chamada (com base no valor de **uso do PSTN** definido na política de local aplicável) para um servidor de mediação e, a partir daí, para um gateway do Elin.</span><span class="sxs-lookup"><span data-stu-id="44660-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="44660-128">O gateway ELIN encaminha a chamada para o PSTN através de um tronco CAMA ou ISDN.</span><span class="sxs-lookup"><span data-stu-id="44660-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="44660-p106">O PSTN identifica a chamada como uma chamada de emergência e a encaminha para um roteador E9-1-1 seletivo na rede. O roteador E9-1-1 seletivo pesquisa o número do chamador no banco de dados ALI para obter o local geográfico. O roteador E9-1-1 seletivo envia a chamada para o PSAP mais apropriado com base nas informações de local que foram recuperadas do banco de dados ALI.</span><span class="sxs-lookup"><span data-stu-id="44660-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="44660-132">Se você configurou a política de local para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem instantânea especial de notificação de emergência do Lync.</span><span class="sxs-lookup"><span data-stu-id="44660-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="44660-133">Essa mensagem sempre aparecerá na(s) tela(s) dos funcionários de segurança e contém o nome, o número de telefone, a hora e o local do chamador, permitindo que o pessoal de segurança atenda rapidamente o chamador de emergência usando uma mensagem instantânea ou voz.</span><span class="sxs-lookup"><span data-stu-id="44660-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="44660-p108">Se a chamada for interrompida prematuramente, o PSAP usa o ELIN para entrar diretamente em contato com o chamador. O gateway ELIN troca o ELIN pela DID do chamador.</span><span class="sxs-lookup"><span data-stu-id="44660-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

