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
# <a name="trunk-failover-on-outbound-calls"></a>Failover de tronco em chamadas de saída

Este tópico descreve como evitar failovers de tronco em chamadas de saída— de Teams para o Controlador de Borda de Sessão (SBC).

## <a name="failover-on-network-errors"></a>Failover em erros de rede

Se um tronco não puder ser conectado por qualquer motivo, a conexão com o mesmo tronco será tentada de um Datacenter da Microsoft diferente. Um tronco pode não estar conectado, por exemplo, se uma conexão for recusada, se houver um tempo de tempo de TLS ou se houver outros problemas de nível de rede.
Por exemplo, uma conexão pode falhar se um administrador limitar o acesso ao SBC somente a partir de endereços IP conhecidos, mas se esquecer de colocar os endereços IP de todos os datacenters de Roteamento Direto da Microsoft na Lista de Controle de Acesso (ACL) do SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover de códigos SIP específicos recebidos do Controlador de Borda de Sessão (SBC)

Se o Roteamento Direto receber quaisquer códigos de erro SIP 4xxx ou 6xx em resposta a um Convite de saída, a chamada será considerada concluída por padrão. A saída significa uma chamada de um cliente Teams para a Rede Telefônica Pública Comutado (PSTN) com o seguinte fluxo de tráfego: Teams Client -> Direct Routing -> SBC -> Telefonia.

A lista de Códigos SIP pode ser encontrada em [Sip Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).

Suponha uma situação em que um SBC respondeu em um convite de entrada com o código "Tempo de tempo de solicitação 408: o servidor não pôde produzir uma resposta dentro de um período adequado, por exemplo, se não pudesse determinar o local do usuário a tempo. O cliente PODE repetir a solicitação sem modificações posteriormente."

Esse SBC específico pode estar com dificuldades para se conectar ao chamador, talvez devido a um erro de configuração de rede ou outro erro. No entanto, há mais um SBC na rota que pode ser capaz de alcançar o chamador.

No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota que podem entregar essa chamada. Inicialmente, SBC1.contoso.com está selecionado para a chamada, mas SBC1.contoso.com não é capaz de alcançar uma rede PTSN devido a um problema de rede.
Por padrão, a chamada será concluída neste momento. 
 
![Diagrama mostrando que o SBC não consegue alcançar o PSTN devido a um problema de rede](media/direct-routing-failover-response-codes1.png)

Mas há mais um SBC na rota que potencialmente pode entregar a chamada.
Se você configurar o parâmetro , o segundo SBC será `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC2.contoso.com no diagrama a seguir:

![Diagrama mostrando o roteamento para o segundo SBC](media/direct-routing-failover-response-codes2.png)

Definir o parâmetro -FailoverResponseCodes e especificar os códigos ajuda você a ajustar o roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido a problemas de rede ou outros problemas.

Valores padrão: 408, 503, 504

