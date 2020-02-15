---
title: 'Lync Server 2013: rotas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 350b64c15b0819813b8287bb9b40272845f3a285
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="1099c-102">Rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1099c-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1099c-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1099c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1099c-104">As rotas de chamada especificam como o Lync Server trata as chamadas de saída feitas por usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1099c-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="1099c-105">Quando um usuário disca um número, o servidor front-end normaliza a cadeia de caracteres de discagem para o formato E. 164, se necessário, e tenta fazer a correspondência com um URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="1099c-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="1099c-106">Se o servidor não conseguir fazer a correspondência, aplicará a lógica de encaminhamento de chamadas realizadas com base no número.</span><span class="sxs-lookup"><span data-stu-id="1099c-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="1099c-107">A etapa final na definição dessa lógica é a criação de uma rota de chamada nomeada separada para cada conjunto de números de telefone listados em cada plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="1099c-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="1099c-108">Antes de definir as rotas de chamadas de saída, você deve concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1099c-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="1099c-109">Implantar um ou mais troncos.</span><span class="sxs-lookup"><span data-stu-id="1099c-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="1099c-110">Criar planos de discagem conforme a necessidade para sites, indivíduos e objetos de Contato.</span><span class="sxs-lookup"><span data-stu-id="1099c-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="1099c-111">Criar registros de uso de rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="1099c-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="1099c-p102">Além disso, para habilitar o roteamento de chamadas de saída, você deve criar e atribuir uma ou mais políticas de voz. Você pode fazer isso antes ou depois de definir as rotas das chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="1099c-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="1099c-114">Para cada rota, você deve especificar:</span><span class="sxs-lookup"><span data-stu-id="1099c-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="1099c-115">Um nome pelo qual a rota possa ser facilmente identificada.</span><span class="sxs-lookup"><span data-stu-id="1099c-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="1099c-116">Uma descrição opcional, caso apenas o nome não seja suficiente para descrevê-la.</span><span class="sxs-lookup"><span data-stu-id="1099c-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="1099c-117">O padrão de correspondência da expressão regular que identifica os números de telefone de destino aos quais a rota será aplicada, junto com as exceções às quais o padrão de correspondência não será aplicado.</span><span class="sxs-lookup"><span data-stu-id="1099c-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="1099c-118">Um ou mais troncos que você desejar atribuir à rota.</span><span class="sxs-lookup"><span data-stu-id="1099c-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="1099c-119">Os registros de uso do PSTN que os usuários devem ter para fazer chamadas para números que correspondam à expressão regular do número de telefone de destino.</span><span class="sxs-lookup"><span data-stu-id="1099c-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="1099c-120">Você pode especificar rotas de chamadas no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1099c-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="1099c-121">Essas rotas de chamadas preenchem a tabela de roteamento do servidor, que o Lync Server usa para rotear chamadas destinadas à PSTN.</span><span class="sxs-lookup"><span data-stu-id="1099c-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="1099c-122">Suporte de Tronco M:N</span><span class="sxs-lookup"><span data-stu-id="1099c-122">M:N Trunk Support</span></span>

<span data-ttu-id="1099c-123">O Lync Server oferece flexibilidade em como as chamadas são encaminhadas para o PSTN.</span><span class="sxs-lookup"><span data-stu-id="1099c-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="1099c-124">Uma rota de voz especifica um conjunto de troncos ao PSTN que pode ser usado para uma chamada de voz específica.</span><span class="sxs-lookup"><span data-stu-id="1099c-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="1099c-125">Um tronco associa um servidor de mediação e um número de porta com um gateway PSTN e um número de porta de escuta.</span><span class="sxs-lookup"><span data-stu-id="1099c-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="1099c-126">Essa associação lógica permite que um servidor de mediação seja associado a vários gateways e tenha várias conexões com o mesmo gateway.</span><span class="sxs-lookup"><span data-stu-id="1099c-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="1099c-127">Ao definir uma rota de chamada, você especifica os troncos associados a essa rota, mas não especifica quais servidores de mediação estão associados à rota.</span><span class="sxs-lookup"><span data-stu-id="1099c-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="1099c-128">Para criar troncos definindo as relações entre os servidores de mediação e os gateways PSTN, IP-PBXs e SBCs (controladores de borda de sessão), use o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1099c-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="1099c-129">Roteamento de Custo Mínimo</span><span class="sxs-lookup"><span data-stu-id="1099c-129">Least-Cost Routing</span></span>

<span data-ttu-id="1099c-p105">A capacidade de especificar os troncos para os quais os diversos números são roteados permite determinar as rotas de menor custo e implementá-las adequadamente. A regra geral para selecionar troncos é escolher o tronco com o gateway mais próximo da localidade do número de destino para reduzir as tarifas de interurbano. Por exemplo, caso você esteja em Nova York telefonando para um número em Roma, a chamada seguiria pela rede IP até o tronco com o gateway no escritório de Roma e os custos seriam os de uma chamada local.</span><span class="sxs-lookup"><span data-stu-id="1099c-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="1099c-133">Para um exemplo de como o roteamento de custo mínimo poderia ser usado, considere o seguinte: a Fabrikam decide permitir que os usuários alemães façam chamadas para os números dos EUA usando o tronco norte-americano.</span><span class="sxs-lookup"><span data-stu-id="1099c-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="1099c-134">A Fabrikam também deseja configurar o sistema para que todas as chamadas de usuários do Lync Server dos EUA para a Alemanha e países/regiões adjacentes terminem no tronco com o gateway na Alemanha.</span><span class="sxs-lookup"><span data-stu-id="1099c-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="1099c-135">Este roteamento economizará dinheiro porque uma chamada da Alemanha para a Áustria, por exemplo, é mais barata do que uma chamada dos EUA para a Áustria.</span><span class="sxs-lookup"><span data-stu-id="1099c-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="1099c-136">Como traduzir cadeias de caracteres de discagem de saída</span><span class="sxs-lookup"><span data-stu-id="1099c-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="1099c-137">O Lync Server 2013, como seus predecessores imediatos, exige que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 para o propósito de executar a pesquisa de número reverso (RNL).</span><span class="sxs-lookup"><span data-stu-id="1099c-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="1099c-138">Para troncos com gateways ou PBXs (Private Branch eXchanges) que exigem números convertidos em formatos de discagem locais, o Lync Server 2013 permite que você crie uma ou mais regras que auxiliam na manipulação do número chamado (ou seja, URI de solicitação) antes de roteá-lo para o Trunk.</span><span class="sxs-lookup"><span data-stu-id="1099c-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="1099c-139">Por exemplo, você pode escrever uma regra para remover +44 do início da cadeia de caracteres de discagem e subsituí-lo por 0144.</span><span class="sxs-lookup"><span data-stu-id="1099c-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="1099c-140">Com o Lync Server 2013, é possível criar uma ou mais regras que auxiliam na manipulação do número de chamada antes de encaminhá-lo ao tronco.</span><span class="sxs-lookup"><span data-stu-id="1099c-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="1099c-141">Ao planejar seus troncos que associam gateways: pares de porta com servidor de mediação: pares de porta, pode ser útil agrupar troncos com requisitos de discagem locais semelhantes e, portanto, reduzir o número de regras de conversão necessárias e o tempo necessário para escrevê-las.</span><span class="sxs-lookup"><span data-stu-id="1099c-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="1099c-142">Como configurar o ID de chamador</span><span class="sxs-lookup"><span data-stu-id="1099c-142">Configuring Caller ID</span></span>

<span data-ttu-id="1099c-143">O Lync Server oferece uma maneira de manipular a ID de chamada para chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="1099c-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="1099c-144">Por exemplo, se uma organização deseja mascarar as extensões de discagem direta dos funcionários e substituí-las com o número genérico corporativo ou departamental, um administrador pode fazer isso usando o painel de controle do Lync Server para suprimir a ID de chamadas e substituí-la por uma ID do chamador alternativo especificado.</span><span class="sxs-lookup"><span data-stu-id="1099c-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="1099c-145">Ao planejar a lógica do seu roteamento, considere para quais indivíduos, grupos e sites você deseja essa opção - talvez, mesmo, para todos os funcionários.</span><span class="sxs-lookup"><span data-stu-id="1099c-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1099c-p109">Para chamadas que são roteadas novamente através do PSTN, o ID de chamador genérico será apresentado em vez do ID de chamador original. Isso pode fazer com que a chamada ignore configurações de Não Incomodar ou de privacidade que o receptor possa ter configurado.</span><span class="sxs-lookup"><span data-stu-id="1099c-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="1099c-148">Lógica de roteamento adicional</span><span class="sxs-lookup"><span data-stu-id="1099c-148">Additional Routing Logic</span></span>

<span data-ttu-id="1099c-149">Ao criar rotas de chamadas de saída, você deve estar ciente dos seguintes fatores que podem afetar a lógica de roteamento:</span><span class="sxs-lookup"><span data-stu-id="1099c-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="1099c-150">Onde uma chamada passa por uma fronteira federada, a parte do domínio do URI é usada para rotear a chamada até a empresa responsável por aplicar a lógica de roteamento de saída.</span><span class="sxs-lookup"><span data-stu-id="1099c-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="1099c-151">Se a parte do domínio do URI de solicitação não contiver um domínio suportado para a empresa, o componente de roteamento de saída no servidor não processa a chamada.</span><span class="sxs-lookup"><span data-stu-id="1099c-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="1099c-152">Se um usuário não estiver habilitado para o Enterprise Voice, o servidor aplicará outra lógica de roteamento, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="1099c-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="1099c-p110">Se uma chamada for roteada para um gateway que está completamente ocupado (todas as linhas do tronco estão ocupadas), o gateway rejeita a chamada e a lógica de roteamento de saída a redireciona para a próxima rota de menor custo. Considere isso cuidadosamente, porque um gateway dimensionado para um escritório pequeno no exterior (por exemplo, em Zurique) pode na verdade carregar um volume significativo de tráfego não-local para chamadas internacionais para a Suíça. Se o gateway não for dimensionado corretamente para esse tráfego adicional, as chamadas para a Suíça poderão ser roteadas por um gateway na Alemanha, resultando em tarifas maiores.</span><span class="sxs-lookup"><span data-stu-id="1099c-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

