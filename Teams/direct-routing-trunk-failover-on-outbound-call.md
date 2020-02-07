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
description: Leia este tópico para saber como manipular failovers de tronco em chamadas de saída do teams para o controlador de borda de sessão (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836173"
---
# <a name="trunk-failover-on-outbound-calls"></a>Failover de tronco em chamadas de saída

Este tópico descreve como evitar failovers de tronco em chamadas de saída--de equipes para o controlador de borda de sessão (SBC).

## <a name="failover-on-network-errors"></a>Failover em erros de rede

Se um tronco não puder ser conectado por algum motivo, a conexão com o mesmo tronco será tentada em um datacenter diferente da Microsoft. Um tronco pode não ser conectado, por exemplo, se uma conexão for recusada, se houver um tempo limite de TLS ou se houver outros problemas no nível de rede.
Por exemplo, uma conexão pode falhar se um administrador limita o acesso ao SBC somente de endereços IP conhecidos, mas se esquece de colocar os endereços IP de todos os datacenters de roteamento direto da Microsoft na ACL (lista de controle de acesso) do SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover de códigos SIP específicos recebidos do controlador de borda de sessão (SBC)

Se o roteamento direto receber qualquer código de erro 4xx ou 6xx SIP em resposta a um convite de saída, a chamada será considerada concluída por padrão. Saída significa uma chamada de um cliente de equipes para a rede telefônica pública comutada (PSTN) com o fluxo de tráfego a seguir: cliente do teams-> Direct Routing-> SBC-> Telephony Network.

A lista de códigos SIP pode ser encontrada na [RFC de protocolo de iniciação de sessão (SIP)](https://tools.ietf.org/html/rfc3261).

Suponha que uma situação em que um SBC respondeu em um convite de entrada com o código "408 tempo limite de solicitação: o servidor não pôde produzir uma resposta dentro de um período de tempo adequado, por exemplo, se não pôde determinar a localização do usuário no tempo. O cliente pode repetir a solicitação sem modificações a qualquer momento mais tarde. "

Esse SBC específico pode estar com dificuldades para se conectar ao chamador--talvez devido a um erro de configuração de rede ou outro erro. No entanto, há mais um SBC na rota que pode ser capaz de alcançar o chamador.

No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota que podem entregar essa chamada. Inicialmente, SBC1.contoso.com é selecionado para a chamada, mas SBC1.contoso.com não consegue alcançar uma rede PTSN devido a um problema de rede.
Por padrão, a chamada será completada no momento. 
 
![Diagrama mostrando o SBC não é possível alcançar a PSTN devido a um problema de rede](media/direct-routing-failover-response-codes1.png)

Mas há mais um SBC na rota que pode ser capaz de entregar a chamada.
Se você configurar o parâmetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, o segundo SBC será tentado--SBC2.contoso.com no seguinte diagrama:

![Diagrama mostrando o roteamento para segundo SBC](media/direct-routing-failover-response-codes2.png)

Definir o parâmetro-FailoverResponseCodes e especificar os códigos ajuda você a ajustar seu roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido a problemas de rede ou de outros problemas.

Valores padrão: 408, 503, 504

