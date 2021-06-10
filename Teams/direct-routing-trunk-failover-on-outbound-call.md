---
title: Failover de tronco em chamadas de saída
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leia este tópico para saber como lidar com failovers de tronco em chamadas de saída de Teams para o Controlador de Borda de Sessão (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836173"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="5e307-103">Failover de tronco em chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="5e307-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="5e307-104">Este tópico descreve como evitar failovers de tronco em chamadas de saída— de Teams para o Controlador de Borda de Sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="5e307-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="5e307-105">Failover em erros de rede</span><span class="sxs-lookup"><span data-stu-id="5e307-105">Failover on network errors</span></span>

<span data-ttu-id="5e307-106">Se um tronco não puder ser conectado por qualquer motivo, a conexão com o mesmo tronco será tentada de um Datacenter da Microsoft diferente.</span><span class="sxs-lookup"><span data-stu-id="5e307-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="5e307-107">Um tronco pode não estar conectado, por exemplo, se uma conexão for recusada, se houver um tempo de tempo de TLS ou se houver outros problemas de nível de rede.</span><span class="sxs-lookup"><span data-stu-id="5e307-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="5e307-108">Por exemplo, uma conexão pode falhar se um administrador limitar o acesso ao SBC somente a partir de endereços IP conhecidos, mas se esquecer de colocar os endereços IP de todos os datacenters de Roteamento Direto da Microsoft na Lista de Controle de Acesso (ACL) do SBC.</span><span class="sxs-lookup"><span data-stu-id="5e307-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="5e307-109">Failover de códigos SIP específicos recebidos do Controlador de Borda de Sessão (SBC)</span><span class="sxs-lookup"><span data-stu-id="5e307-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="5e307-110">Se o Roteamento Direto receber quaisquer códigos de erro SIP 4xxx ou 6xx em resposta a um Convite de saída, a chamada será considerada concluída por padrão.</span><span class="sxs-lookup"><span data-stu-id="5e307-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="5e307-111">A saída significa uma chamada de um cliente Teams para a Rede Telefônica Pública Comutado (PSTN) com o seguinte fluxo de tráfego: Teams Client -> Direct Routing -> SBC -> Telefonia.</span><span class="sxs-lookup"><span data-stu-id="5e307-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="5e307-112">A lista de Códigos SIP pode ser encontrada em [Sip Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="5e307-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="5e307-113">Suponha uma situação em que um SBC respondeu em um convite de entrada com o código "Tempo de tempo de solicitação 408: o servidor não pôde produzir uma resposta dentro de um período adequado, por exemplo, se não pudesse determinar o local do usuário a tempo.</span><span class="sxs-lookup"><span data-stu-id="5e307-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="5e307-114">O cliente PODE repetir a solicitação sem modificações posteriormente."</span><span class="sxs-lookup"><span data-stu-id="5e307-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="5e307-115">Esse SBC específico pode estar com dificuldades para se conectar ao chamador, talvez devido a um erro de configuração de rede ou outro erro.</span><span class="sxs-lookup"><span data-stu-id="5e307-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="5e307-116">No entanto, há mais um SBC na rota que pode ser capaz de alcançar o chamador.</span><span class="sxs-lookup"><span data-stu-id="5e307-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="5e307-117">No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota que podem entregar essa chamada.</span><span class="sxs-lookup"><span data-stu-id="5e307-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="5e307-118">Inicialmente, SBC1.contoso.com está selecionado para a chamada, mas SBC1.contoso.com não é capaz de alcançar uma rede PTSN devido a um problema de rede.</span><span class="sxs-lookup"><span data-stu-id="5e307-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="5e307-119">Por padrão, a chamada será concluída neste momento.</span><span class="sxs-lookup"><span data-stu-id="5e307-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagrama mostrando que o SBC não consegue alcançar o PSTN devido a um problema de rede](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="5e307-121">Mas há mais um SBC na rota que potencialmente pode entregar a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e307-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="5e307-122">Se você configurar o parâmetro , o segundo SBC será `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC2.contoso.com no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="5e307-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagrama mostrando o roteamento para o segundo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="5e307-124">Definir o parâmetro -FailoverResponseCodes e especificar os códigos ajuda você a ajustar o roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido a problemas de rede ou outros problemas.</span><span class="sxs-lookup"><span data-stu-id="5e307-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="5e307-125">Valores padrão: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="5e307-125">Default values:  408, 503, 504</span></span>

