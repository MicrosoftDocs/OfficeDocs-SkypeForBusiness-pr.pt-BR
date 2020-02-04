---
title: 'Lync Server 2013: Visão geral de E9-1-1'
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
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="887d5-102">Visão geral de E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887d5-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="887d5-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="887d5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="887d5-104">O Microsoft Lync Server 2013 dá suporte à chamada Enhanced 9-1-1 (E9-1-1) dos clientes do Lync e dos dispositivos Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="887d5-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="887d5-105">Quando você configura o Lync Server para E9-1-1, as chamadas de emergência feitas pelo Lync 2013 ou pelo Lync Phone Edition incluem informações de local de resposta de emergência (ERL) do banco de dados do serviço de informações de localização.</span><span class="sxs-lookup"><span data-stu-id="887d5-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="887d5-106">ERLs consistem em endereços cívicos (rua) e outras informações que ajudam a identificar a localização mais precisa em prédios de escritórios e outras instalações com vários locatários.</span><span class="sxs-lookup"><span data-stu-id="887d5-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="887d5-107">Quando um usuário faz uma chamada de emergência, o Lync Server roteia o áudio da chamada, juntamente com o local e as informações de retorno de chamada, por meio de um servidor de mediação para um provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="887d5-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="887d5-108">O provedor de serviços E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada para PSAP (Ponto de Atendimento Público Seguro), que atende à localização do chamador e envia também uma ESQK (Chave de Consulta de Serviço de Emergência) que PSAP usa para procurar a ERL do chamador.</span><span class="sxs-lookup"><span data-stu-id="887d5-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="887d5-109">O Lync Server tem suporte para dois métodos de roteamento de chamadas de emergência para um provedor de serviços E9-1-1:</span><span class="sxs-lookup"><span data-stu-id="887d5-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="887d5-110">Uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado</span><span class="sxs-lookup"><span data-stu-id="887d5-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="887d5-111">Um gateway ELIN (para um provedor de serviços E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)</span><span class="sxs-lookup"><span data-stu-id="887d5-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="887d5-112">Quando você usa um provedor de serviço E9 de tronco SIP-1-1, adiciona ERLs ao banco de dados do serviço de informações de localização e, em seguida, valida os locais em relação a uma guia de endereço mestre (MSAG) mantida pelo provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="887d5-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="887d5-113">Se um provedor de serviços E9-1-1 receber uma chamada sem informações sobre o local ou com um local não validado com o MSAG, o provedor de serviços E9-1-1 encaminhará a chamada a um ECRC (Centro de Resposta a Chamadas de Emergência) nacional/regional, que conta com pessoas especialmente treinadas para obter verbalmente o local do chamador, se possível, e encaminhar manualmente a chamada ao PSAP apropriado.</span><span class="sxs-lookup"><span data-stu-id="887d5-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="887d5-114">(Alguns provedores de serviços E9-1-1 de tronco SIP também fornecem aos clientes um número DID (discagem direta interna) de PSTN ao ECRC, que é um meio alternativo de encaminhar as chamadas 9-1-1 se um tronco SIP falhar por algum motivo).</span><span class="sxs-lookup"><span data-stu-id="887d5-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="887d5-115">Ao contrário dos telefones de bifurcação de divisão de tempo (TDM) e de PBX (intercâmbio privado) baseados em IP, que têm locais fixos, um ponto de extremidade do Lync pode ser muito móvel.</span><span class="sxs-lookup"><span data-stu-id="887d5-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="887d5-116">Quando você implanta o recurso E9-1-1, o Lync Server ajuda a garantir que não importa onde um chamador esteja localizado, a chamada de emergência pode ser roteada para o PSAP que serve o local do autor do usuário.</span><span class="sxs-lookup"><span data-stu-id="887d5-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="887d5-117">Por exemplo, se a sede de um usuário estiver localizada em Redmond, em Washington, mas o usuário fizer uma chamada de emergência de um computador em uma filial em Wichita, no Kansas, o tronco SIP ou o provedor de serviços E9-1-1 com base em PSTN encaminhará a chamada para o PSAP de Wichita, e não para o PSAP de Redmond.</span><span class="sxs-lookup"><span data-stu-id="887d5-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="887d5-118">Ao usar um gateway ELIN, você também adiciona ERLs ao banco de dados do serviço de informações de localização, mas também inclui um número ELIN para cada local.</span><span class="sxs-lookup"><span data-stu-id="887d5-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="887d5-119">O número ELIN se torna o número de discagem de emergência durante a chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="887d5-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="887d5-120">Em seguida, é necessário verificar se a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação Automática de Local).</span><span class="sxs-lookup"><span data-stu-id="887d5-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="887d5-121">O Lync-dispositivos analógicos conectados não pode receber informações de localização do serviço de informações de localização ou local de transmissão para o provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="887d5-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="887d5-122">Se usar a opção do provedor de serviços E9-1-1 do tronco SIP e precisar dar suporte a E9-1-1 por meio de telefones analógicos, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="887d5-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="887d5-123"><STRONG></STRONG>&nbsp;Opção&nbsp;PS&nbsp;-ali tradicional se você tiver gateways PSTN locais em cada site em que os telefones analógicos são implantados e cada telefone analógico tiver um, você pode provisionar a localização do dispositivo analógico diretamente com um provedor de serviços de comutador privado/identificação automática de local (PS-ali).</span><span class="sxs-lookup"><span data-stu-id="887d5-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="887d5-124">Nesse caso, você configura políticas de voz do Lync especialmente criadas e as atribui aos objetos de contato do dispositivo analógico para que as chamadas E9-1-1 desses telefones sejam roteadas diretamente por meio do gateway local para o provedor de PSTN que presta serviços ao site (em vez de direcionar o chamada para um tronco SIP do provedor de serviços E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="887d5-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="887d5-125">Quando uma chamada de emergência é efetuada, um banco de dados em um provedor de PS-ALI associado ao tronco PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP.</span><span class="sxs-lookup"><span data-stu-id="887d5-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="887d5-126">Esses registros precisam ser atualizados com o provedor de serviços PS-ALI sempre que os telefones são movidos para ERLs diferentes.</span><span class="sxs-lookup"><span data-stu-id="887d5-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="887d5-127"><STRONG></STRONG>&nbsp;Opção&nbsp;de&nbsp;provedor de serviços E9-1-1 você pode registrar o DIDs de telefone analógico e seus ERLs correspondentes com o provedor de serviços E9-1-1, caso isso seja compatível com o provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="887d5-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="887d5-128">Se o provedor receber uma chamada do Lync Server que não inclui dados do PIDF-LO, o provedor poderá ver se há um banco de dados correspondente no número do participante da chamada.</span><span class="sxs-lookup"><span data-stu-id="887d5-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="887d5-129">Usando a ERL recuperada de seu banco de dados, o provedor pode encaminhar automaticamente a chamada de emergência para o PSAP correto, e o PSAP receberá o DID do dispositivo analógico e um registro ESQK que permite ao dispatcher procurar o local do chamador.</span><span class="sxs-lookup"><span data-stu-id="887d5-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="887d5-p108">Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível provisionar o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.</span><span class="sxs-lookup"><span data-stu-id="887d5-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="887d5-131">De uma perspectiva do Lync Server, o processo E9-1-1 pode ser separado em dois estágios:</span><span class="sxs-lookup"><span data-stu-id="887d5-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="887d5-132">Estágio 1: aquisição de local</span><span class="sxs-lookup"><span data-stu-id="887d5-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="887d5-133">Estágio 2: encaminhamento de chamada de emergência para um provedor de serviços E9-1-1</span><span class="sxs-lookup"><span data-stu-id="887d5-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="887d5-134">Esta seção descreve como esses estágios funcionam.</span><span class="sxs-lookup"><span data-stu-id="887d5-134">This section describes how these stages work.</span></span>

<span data-ttu-id="887d5-135">Se planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores para os locais.</span><span class="sxs-lookup"><span data-stu-id="887d5-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="887d5-136">Para obter detalhes sobre as possíveis opções, consulte [definindo os elementos de rede usados para determinar o local no Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="887d5-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="887d5-137">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="887d5-137">In This Section</span></span>

  - [<span data-ttu-id="887d5-138">Adquirindo um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887d5-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="887d5-139">Roteamento de chamadas E9-1-1 usando tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887d5-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="887d5-140">Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887d5-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

