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
description: Leia este tópico para saber como manipular failovers de tronco em chamadas de saída do teams para o controlador de borda de sessão (SBC).
ms.openlocfilehash: a5462de971fed32a0618800b257b9c6e37b462af
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572119"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="bcfdf-103">Failover de tronco em chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="bcfdf-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="bcfdf-104">Este tópico descreve como evitar failovers de tronco em chamadas de saída--de equipes para o controlador de borda de sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="bcfdf-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="bcfdf-105">Failover em erros de rede</span><span class="sxs-lookup"><span data-stu-id="bcfdf-105">Failover on network errors</span></span>

<span data-ttu-id="bcfdf-106">Se um tronco não puder ser conectado por algum motivo, a conexão com o mesmo tronco será tentada em um datacenter diferente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="bcfdf-107">Um tronco pode não ser conectado, por exemplo, se uma conexão for recusada, se houver um tempo limite de TLS ou se houver outros problemas no nível de rede.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="bcfdf-108">Por exemplo, uma conexão pode falhar se um administrador limita o acesso ao SBC somente de endereços IP conhecidos, mas se esquece de colocar os endereços IP de todos os datacenters de roteamento direto da Microsoft na ACL (lista de controle de acesso) do SBC.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="bcfdf-109">Failover de códigos SIP específicos recebidos do controlador de borda de sessão (SBC)</span><span class="sxs-lookup"><span data-stu-id="bcfdf-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="bcfdf-110">Se o roteamento direto receber qualquer código de erro 4xx ou 6xx SIP em resposta a um convite de saída, a chamada será considerada concluída por padrão.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="bcfdf-111">Saída significa uma chamada de um cliente de equipes para a rede telefônica pública comutada (PSTN) com o fluxo de tráfego a seguir: cliente do teams-> Direct Routing-> SBC-> Telephony Network.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="bcfdf-112">A lista de códigos SIP pode ser encontrada na [RFC de protocolo de iniciação de sessão (SIP)](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="bcfdf-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="bcfdf-113">Suponha que uma situação em que um SBC respondeu em um convite de entrada com o código "408 tempo limite de solicitação: o servidor não pôde produzir uma resposta dentro de um período de tempo adequado, por exemplo, se não pôde determinar a localização do usuário no tempo.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="bcfdf-114">O cliente pode repetir a solicitação sem modificações a qualquer momento mais tarde. "</span><span class="sxs-lookup"><span data-stu-id="bcfdf-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="bcfdf-115">Esse SBC específico pode estar com dificuldades para se conectar ao chamador--talvez devido a um erro de configuração de rede ou outro erro.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="bcfdf-116">No entanto, há mais um SBC na rota que pode ser capaz de alcançar o chamador.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="bcfdf-117">No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota que podem entregar essa chamada.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="bcfdf-118">Inicialmente, SBC1.contoso.com é selecionado para a chamada, mas SBC1.contoso.com não consegue alcançar uma rede PTSN devido a um problema de rede.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="bcfdf-119">Por padrão, a chamada será completada no momento.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagrama mostrando o SBC não é possível alcançar a PSTN devido a um problema de rede](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="bcfdf-121">Mas há mais um SBC na rota que pode ser capaz de entregar a chamada.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="bcfdf-122">Se você configurar o parâmetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, o segundo SBC será tentado--SBC2.contoso.com no seguinte diagrama:</span><span class="sxs-lookup"><span data-stu-id="bcfdf-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagrama mostrando o roteamento para segundo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="bcfdf-124">Definir o parâmetro-FailoverResponseCodes e especificar os códigos ajuda você a ajustar seu roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido a problemas de rede ou de outros problemas.</span><span class="sxs-lookup"><span data-stu-id="bcfdf-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="bcfdf-125">Valores padrão: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="bcfdf-125">Default values:  408, 503, 504</span></span>

