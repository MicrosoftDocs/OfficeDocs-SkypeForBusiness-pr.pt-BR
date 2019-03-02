---
title: Failover de tronco em chamadas de saída
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Leia este tópico para saber como lidar com failovers de tronco em chamadas de saída de equipes para o controlador de borda de sessão (SBC).
ms.openlocfilehash: 1a40cc3fa94bfba3c637769774f5f5b829d29ed4
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351102"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="60fc8-103">Failover de tronco em chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="60fc8-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="60fc8-104">Este tópico descreve como evitar failovers de tronco em chamadas de saída – de equipes para o controlador de borda de sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="60fc8-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="60fc8-105">Failover em caso de erros de rede</span><span class="sxs-lookup"><span data-stu-id="60fc8-105">Failover on network errors</span></span>

<span data-ttu-id="60fc8-106">Se um tronco não pode ser conectado por qualquer motivo, a conexão a um tronco mesmo será tentado a partir de um Datacenter da Microsoft diferentes.</span><span class="sxs-lookup"><span data-stu-id="60fc8-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="60fc8-107">Um tronco não pode ser conectado, por exemplo, se uma conexão for recusada, se não houver um tempo limite TLS, ou se há algum outro problema de nível de rede.</span><span class="sxs-lookup"><span data-stu-id="60fc8-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="60fc8-108">Por exemplo, uma conexão pode falhar se um administrador limita o acesso ao SBC somente de endereços IP conhecidos, mas esquece de colocar os endereços IP de todos os datacenters de roteamento direto da Microsoft na lista de controle de acesso (ACL) do SBC.</span><span class="sxs-lookup"><span data-stu-id="60fc8-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="60fc8-109">Failover de códigos específicos de SIP recebida do controlador de borda de sessão (SBC)</span><span class="sxs-lookup"><span data-stu-id="60fc8-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="60fc8-110">Se o roteamento direto recebe quaisquer códigos de erro SIP 4xx ou 6xx em resposta a um convite de saída, a chamada é considerada concluída por padrão.</span><span class="sxs-lookup"><span data-stu-id="60fc8-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="60fc8-111">Significa que uma chamada de um cliente de equipes para o comutação telefônica PSTN (rede pública) com o seguinte fluxo de tráfego de saída: cliente equipes- gt _ roteamento direto- gt _ SBC- gt _ rede de telefonia.</span><span class="sxs-lookup"><span data-stu-id="60fc8-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="60fc8-112">A lista dos códigos de SIP pode ser encontrada no [Protocolo de iniciação de sessão (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="60fc8-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="60fc8-113">Suponha uma situação em que um SBC respondido em um convite de entrada com o código "tempo limite de solicitação 408: O servidor não pôde produzir uma resposta dentro de uma quantidade adequada de tempo, por exemplo, se ele não foi possível determinar o local do usuário em tempo.</span><span class="sxs-lookup"><span data-stu-id="60fc8-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="60fc8-114">O cliente pode repetir a solicitação sem modificações a qualquer momento posterior."</span><span class="sxs-lookup"><span data-stu-id="60fc8-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="60fc8-115">Este SBC específico pode estar tendo dificuldades para conectar-se para o receptor – talvez por causa um erro de configuração de rede ou outro tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="60fc8-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="60fc8-116">No entanto, há um SBC mais na rota que pode ser capaz de alcançar o receptor.</span><span class="sxs-lookup"><span data-stu-id="60fc8-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="60fc8-117">No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota capaz de fornecer essa chamada.</span><span class="sxs-lookup"><span data-stu-id="60fc8-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="60fc8-118">Inicialmente, SBC1.contoso.com estiver selecionado para a chamada, mas SBC1.contoso.com não puder acessar uma rede PTSN devido a um problema de rede.</span><span class="sxs-lookup"><span data-stu-id="60fc8-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="60fc8-119">Por padrão, a chamada será concluída neste momento.</span><span class="sxs-lookup"><span data-stu-id="60fc8-119">By default, the call will be completed at this moment.</span></span> 
 
![Mostra o SBC não consegue acessar a PSTN devido a problema de rede](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="60fc8-121">Mas não há um SBC mais na rota que potencialmente pode oferecer a chamada.</span><span class="sxs-lookup"><span data-stu-id="60fc8-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="60fc8-122">Se você configurar o parâmetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, o segundo SBC será tentado – SBC2.contoso.com no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="60fc8-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Mostra o roteamento para o segundo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="60fc8-124">Definindo o parâmetro - FailoverResponseCodes e especificando os códigos de ajuda você a tudo bem ajustar seu roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido a problemas de rede ou outros.</span><span class="sxs-lookup"><span data-stu-id="60fc8-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="60fc8-125">Os valores padrão: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="60fc8-125">Default values:  408, 503, 504</span></span>

