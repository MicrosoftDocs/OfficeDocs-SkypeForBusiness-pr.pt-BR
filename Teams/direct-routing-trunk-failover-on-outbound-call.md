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
# <a name="trunk-failover-on-outbound-calls"></a>Failover de tronco em chamadas de saída

Este tópico descreve como evitar failovers de tronco em chamadas de saída – de equipes para o controlador de borda de sessão (SBC).

## <a name="failover-on-network-errors"></a>Failover em caso de erros de rede

Se um tronco não pode ser conectado por qualquer motivo, a conexão a um tronco mesmo será tentado a partir de um Datacenter da Microsoft diferentes. Um tronco não pode ser conectado, por exemplo, se uma conexão for recusada, se não houver um tempo limite TLS, ou se há algum outro problema de nível de rede.
Por exemplo, uma conexão pode falhar se um administrador limita o acesso ao SBC somente de endereços IP conhecidos, mas esquece de colocar os endereços IP de todos os datacenters de roteamento direto da Microsoft na lista de controle de acesso (ACL) do SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover de códigos específicos de SIP recebida do controlador de borda de sessão (SBC)

Se o roteamento direto recebe quaisquer códigos de erro SIP 4xx ou 6xx em resposta a um convite de saída, a chamada é considerada concluída por padrão. Significa que uma chamada de um cliente de equipes para o comutação telefônica PSTN (rede pública) com o seguinte fluxo de tráfego de saída: cliente equipes- gt _ roteamento direto- gt _ SBC- gt _ rede de telefonia.

A lista dos códigos de SIP pode ser encontrada no [Protocolo de iniciação de sessão (SIP) RFC](https://tools.ietf.org/html/rfc3261).

Suponha uma situação em que um SBC respondido em um convite de entrada com o código "tempo limite de solicitação 408: O servidor não pôde produzir uma resposta dentro de uma quantidade adequada de tempo, por exemplo, se ele não foi possível determinar o local do usuário em tempo. O cliente pode repetir a solicitação sem modificações a qualquer momento posterior."

Este SBC específico pode estar tendo dificuldades para conectar-se para o receptor – talvez por causa um erro de configuração de rede ou outro tipo de erro. No entanto, há um SBC mais na rota que pode ser capaz de alcançar o receptor.

No diagrama a seguir, quando um usuário faz uma chamada para um número de telefone, há dois SBCs na rota capaz de fornecer essa chamada. Inicialmente, SBC1.contoso.com estiver selecionado para a chamada, mas SBC1.contoso.com não puder acessar uma rede PTSN devido a um problema de rede.
Por padrão, a chamada será concluída neste momento. 
 
![Mostra o SBC não consegue acessar a PSTN devido a problema de rede](media/direct-routing-failover-response-codes1.png)

Mas não há um SBC mais na rota que potencialmente pode oferecer a chamada.
Se você configurar o parâmetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, o segundo SBC será tentado – SBC2.contoso.com no diagrama a seguir:

![Mostra o roteamento para o segundo SBC](media/direct-routing-failover-response-codes2.png)

Definindo o parâmetro - FailoverResponseCodes e especificando os códigos de ajuda você a tudo bem ajustar seu roteamento e evitar possíveis problemas quando um SBC não pode fazer uma chamada devido a problemas de rede ou outros.

Os valores padrão: 408, 503, 504

