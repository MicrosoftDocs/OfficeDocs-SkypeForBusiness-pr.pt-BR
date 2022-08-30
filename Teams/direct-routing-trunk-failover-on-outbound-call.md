---
title: Failover de tronco em chamadas de saída
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leia este tópico para saber como lidar com failovers de tronco em chamadas de saída do Teams para o SBC (Controlador de Borda de Sessão).
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457131"
---
# <a name="trunk-failover-on-outbound-calls"></a>Failover de tronco em chamadas de saída

Este tópico descreve como evitar failovers de tronco em chamadas de saída– do Teams para o SBC (Controlador de Borda de Sessão).

## <a name="failover-on-network-errors"></a>Failover em erros de rede

Se um tronco não puder ser conectado por qualquer motivo, a conexão com o mesmo tronco será tentada em um Datacenter da Microsoft diferente. O datacenter pode estar localizado em uma região geográfica diferente, fora da atual. Um tronco pode não estar conectado se uma conexão for recusada, se houver um tempo limite de TLS ou se houver outros problemas no nível da rede.

Por exemplo, uma conexão poderá falhar se um administrador limitar o acesso ao SBC somente de endereços IP conhecidos, mas esquecer de colocar os endereços IP de todos os datacenters de Roteamento Direto da Microsoft na ACL (lista de Controle de Acesso) do SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover de códigos SIP específicos recebidos do Controlador de Borda de Sessão (SBC)

Se o Roteamento Direto receber códigos de erro SIP 4xx ou 6xx em resposta a um Convite de saída, a chamada será considerada concluída por padrão. A saída significa uma chamada de um cliente do Teams para a rede telefônica pública comunada (PSTN) com o seguinte fluxo de tráfego: Cliente do Teams -> Roteamento Direto -> SBC -> Rede de Telefonia.

A lista de códigos SIP pode ser encontrada no [protocolo SIP](https://tools.ietf.org/html/rfc3261).

Suponha uma situação em que um SBC respondeu em um convite de entrada com o código "Tempo limite de solicitação 408: o servidor não poderia produzir uma resposta dentro de um período de tempo adequado, por exemplo, se não pudesse determinar o local do usuário no tempo. O cliente PODE repetir a solicitação sem modificações posteriormente."

Esse SBC específico pode estar tendo dificuldades para se conectar ao computador chamado , talvez devido a um erro de configuração de rede ou outro erro. No entanto, há mais um SBC na rota que pode ser capaz de acessar o receptor da chamada.

No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota que podem potencialmente entregar essa chamada. Inicialmente, SBC1.contoso.com é selecionado para a chamada, mas SBC1.contoso.com não consegue acessar uma rede PTSN devido a um problema de rede.
Por padrão, a chamada será concluída neste momento. 
 
![Diagrama mostrando que o SBC não consegue acessar o PSTN devido a um problema de rede.](media/direct-routing-failover-response-codes1.png)

Há mais um SBC na rota que pode entregar a chamada.
Se você configurar o parâmetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, o segundo SBC será tentado (SBC2.contoso.com no diagrama a seguir):

![Diagrama mostrando o roteamento para o segundo SBC.](media/direct-routing-failover-response-codes2.png)

Definir o parâmetro -FailoverResponseCodes e especificar os códigos ajuda a ajustar o roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido à rede ou a outros problemas.

Valores padrão: 408, 503, 504

