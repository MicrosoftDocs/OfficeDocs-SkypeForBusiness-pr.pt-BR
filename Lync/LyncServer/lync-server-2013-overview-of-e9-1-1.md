---
title: 'Lync Server 2013: visão geral de E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1c97914abf8e5db393cd932c0a453885e86a5c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530618"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="1f1e2-102">Visão geral do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1e2-102">Overview of E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f1e2-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1f1e2-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1f1e2-104">O Microsoft Lync Server 2013 oferece suporte à chamada avançada 9-1-1 (E9-1-1) de clientes Lync e dispositivos do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="1f1e2-105">Ao configurar o Lync Server para E9-1-1, as chamadas de emergência feitas do Lync 2013 ou do Lync Phone Edition incluem informações de local de resposta de emergência (ERL) do banco de dados de serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="1f1e2-106">ERLs são compostos por endereços cívicos (rua) e outras informações que ajudam a identificar um local mais preciso em escritórios em edifícios e em outras instalações com vários locatários.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="1f1e2-107">Quando um usuário faz uma chamada de emergência, o Lync Server roteia o áudio da chamada, juntamente com as informações de local e de retorno de chamada, por meio de um servidor de mediação para um provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="1f1e2-108">O provedor de serviço E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada ao PSAP (Ponto de atendimento público seguro) que atende ao local do chamador e envia também uma ESQK (Chave de consulta de serviço de emergência) que o PSAP usa para procurar o ERL do chamador.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="1f1e2-109">O Lync Server suporta dois métodos para rotear chamadas de emergência para um provedor de serviços E9-1-1:</span><span class="sxs-lookup"><span data-stu-id="1f1e2-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="1f1e2-110">Uma conexão de tronco SIP com um provedor de serviço qualificado E9-1-1</span><span class="sxs-lookup"><span data-stu-id="1f1e2-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="1f1e2-111">Um gateway ELIN (para um provedor de serviço E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)</span><span class="sxs-lookup"><span data-stu-id="1f1e2-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="1f1e2-112">Quando você usa um provedor de serviços E9-1-1 do tronco SIP, você adiciona ERLs ao banco de dados do serviço de informações de local e, em seguida, valida os locais em relação a uma guia de endereço mestre (MSAG) que é mantida pelo provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="1f1e2-113">Se um provedor de serviço E9-1-1 recebe uma chamada sem informações sobre o local ou com um local que não foi validado com o MSAG, o provedor de serviço E9-1-1 encaminha a chamada a um ECRC (Centro de resposta à chamada de emergência) nacional/regional, equipado com pessoas especialmente treinadas que obtém verbalmente o local do chamador, se for possível, e encaminha manualmente a chamada ao PSAP apropriado.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="1f1e2-114">(Alguns provedores de serviço E9-1-1 de tronco SIP também fornecem aos clientes um DID (discagem direta interna) de PSTN ao ECRC, o que proporciona um meio alternativo de encaminhar as chamadas de 9-1-1, se um tronco SIP falhar por qualquer motivo).</span><span class="sxs-lookup"><span data-stu-id="1f1e2-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="1f1e2-115">Diferentemente dos telefones de multiplexação de divisão de tempo (TDM) e de PBX (central privada de comutação telefônica) com base em IP, que têm locais fixos, um ponto de extremidade do Lync pode ser muito móvel.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="1f1e2-116">Quando você implanta o recurso E9-1-1, o Lync Server ajuda a garantir que não importa onde um chamador esteja localizado, a chamada de emergência pode ser roteada para o PSAP que serve o local do chamador.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="1f1e2-117">Por exemplo, se a sede de um usuário fica localizada em Redmond, Washington, mas o usuário faz uma chamada de emergência de um computador em uma filial em Wichita, Kansas, o tronco SIP ou o provedor de serviço E9-1-1 com base em PSTN encaminhará a chamada ao PSAP em Wichita, não ao PSAP em Redmond.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="1f1e2-118">Ao usar um gateway ELIN, você também adiciona ERLs ao banco de dados do serviço de informações de local, mas também inclui um número ELIN para cada local.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="1f1e2-119">O número ELIN se torna o número de discagem de emergência durante a chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="1f1e2-120">Em seguida, é necessário certificar-se de que a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação automática de local).</span><span class="sxs-lookup"><span data-stu-id="1f1e2-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f1e2-121">Os dispositivos analógicos conectados ao Lync não podem receber informações de local do serviço de informações de local ou local de transmissão para o provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="1f1e2-122">Se você usar a opção do provedor de serviço E9-1-1 do tronco SIP e precisar oferecer suporte ao E9-1-1 a partir de telefones analógicos, terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="1f1e2-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1f1e2-123">Opção PS- <STRONG>ali tradicional</STRONG> &nbsp; &nbsp; &nbsp; Se você tiver gateways PSTN locais em cada site em que os telefones analógicos são implantados e cada telefone analógico tiver um, você poderá provisionar o local do dispositivo analógico diretamente com um provedor de serviços de comutador de local privado/identificação automática (PS-ALI).</span><span class="sxs-lookup"><span data-stu-id="1f1e2-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="1f1e2-124">Nesse caso, você configura políticas de voz do Lync criadas especialmente e as atribui aos objetos de contato com o dispositivo analógico, de modo que as chamadas E9-1-1 desses telefones sejam encaminhadas diretamente pelo gateway local para o provedor de PSTN que atende ao site (em vez de encaminhá-las ao tronco SIP de um provedor de serviço E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="1f1e2-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="1f1e2-125">Quando uma chamada de emergência é feita, um banco de dados em um provedor PS-ALI associado ao tronco do PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="1f1e2-126">Esses registros precisam ser atualizados com o provedor de serviço PS-ALI sempre que os telefones são movidos para ERLs diferentes.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="1f1e2-127">Opção de provedor <STRONG>de serviços E9-1-1</STRONG> &nbsp; &nbsp; &nbsp; Você pode registrar o DIDs de telefone analógico e o ERLs correspondente com o provedor de serviço E9-1-1, se houver suporte para o provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="1f1e2-128">Se o provedor receber uma chamada do Lync Server que não inclui os dados do PIDF-LO, o provedor poderá ver se há uma correspondência de banco de dados no número do participante da chamada.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="1f1e2-129">Usando o ERL recuperado de seu banco de dados, o provedor pode rotear automaticamente a chamada de emergência para o PSAP correto, e o PSAP receberá o DID do dispositivo analógico e um registro ESQK que permite ao despachante procurar o local do chamador.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="1f1e2-p108">Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível prover o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="1f1e2-131">A partir de uma perspectiva do Lync Server, o processo E9-1-1 pode ser separado em dois estágios:</span><span class="sxs-lookup"><span data-stu-id="1f1e2-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="1f1e2-132">Estágio 1: adquirindo um local</span><span class="sxs-lookup"><span data-stu-id="1f1e2-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="1f1e2-133">Estágio 2: roteando a chamada de emergência para um provedor de serviço E9-1-1</span><span class="sxs-lookup"><span data-stu-id="1f1e2-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="1f1e2-134">Esta seção descreve como esses estágios funcionam.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-134">This section describes how these stages work.</span></span>

<span data-ttu-id="1f1e2-135">Se você planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores aos locais.</span><span class="sxs-lookup"><span data-stu-id="1f1e2-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="1f1e2-136">Para obter detalhes sobre as opções possíveis, consulte [definindo os elementos de rede usados para determinar o local no Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="1f1e2-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1f1e2-137">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1f1e2-137">In This Section</span></span>

  - [<span data-ttu-id="1f1e2-138">Adquirindo um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1e2-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="1f1e2-139">Roteamento de chamadas E9-1-1 usando um tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1e2-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="1f1e2-140">Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1e2-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

