---
title: Monitorar e solucionar problemas do Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como monitorar e solucionar problemas de configuração de Roteamento Direto, incluindo Controladores de Borda de Sessão, Componentes de Roteamento Direto e Troncos de Telecomunicações.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeff22bf3558c64111f0d1b66c2fd76288f81477
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726880"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Monitorar e solucionar problemas do Roteamento Direto

Este artigo descreve como monitorar e solucionar problemas de sua configuração de Roteamento Direto. 

A capacidade de fazer e receber chamadas usando Roteamento Direto envolve os seguintes componentes: 

- Controladores de Borda de Sessão (SBCs) 
- Componentes de Roteamento Direto no Microsoft Cloud 
- Troncos de telecomunicações 

Se você tiver dificuldades para solucionar problemas, poderá abrir um caso de suporte com o fornecedor SBC ou a Microsoft. 

A Microsoft está trabalhando no fornecimento de mais ferramentas para solução de problemas e monitoramento. Verifique periodicamente a documentação para atualizações. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitorando a disponibilidade de controladores de borda de sessão usando mensagens de opções SIP (Session Initiation Protocol)

O Roteamento Direto usa opções SIP enviadas pelos Controladores de Borda de Sessão para monitorar a saúde do SBC. Não há ações necessárias do administrador de locatários para habilitar o monitoramento de opções SIP. As informações coletadas são levadas em consideração quando as decisões de roteamento são tomadas. 

Por exemplo, se, para um usuário específico, houver vários SBCs disponíveis para rotear uma chamada, o Roteamento Direto considerará as informações de opções SIP recebidas de cada SBC para determinar o roteamento. 

O diagrama a seguir mostra um exemplo da configuração: 

![Exemplo de configuração de opções SIP.](media/sip-options-config-example.png)

Quando um usuário faz uma chamada para o número +1 425, \<any seven digits> o Roteamento Direto avalia a rota. Há dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com. Ambos os SBCs têm prioridade igual na rota. Antes de escolher um SBC, o mecanismo de roteamento avalia a saúde dos SBCs com base em quando o SBC enviou as opções SIP da última vez. 

Um SBC é considerado saudável se as estatísticas no momento do envio da chamada mostrarem que o SBC envia opções a cada minuto.  

Quando uma chamada é feita, a seguinte lógica se aplica:

- O SBC foi emparelhado às 11:00.  
- O SBC envia opções às 11:01, 11:02 e assim por diante.  
- Às 11:15, um usuário faz uma chamada e o mecanismo de roteamento seleciona esse SBC. 

O Roteamento Direto assume as opções de intervalo regular três vezes (o intervalo regular é de um minuto). Se as opções foram enviar durante os últimos três minutos, o SBC será considerado saudável.

Se o SBC no exemplo enviou opções em qualquer período entre 11:12 e 11:15 (a hora em que a chamada foi feita), ela será considerada saudável. Caso não seja, o SBC será rebaixado da rota. 

Rebaixamento significa que o SBC não será tentado primeiro. Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com prioridade igual.  

Se sbc1.contoso.com não enviar opções SIP em um intervalo regular conforme descrito anteriormente, ele será rebaixado. Em seguida, sbc2.contoso.com tenta a chamada. Se sbc2.contoso.con não puder entregar a chamada, a sbc1.contoso.com (rebaixada) será tentada novamente antes que uma falha seja gerada. 

Se dois (ou mais) SBCs em uma rota são considerados ínteeis e iguais, Fisher-Yates embaralhar é aplicado para distribuir as chamadas entre os SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorar painéis de Análise de Qualidade de Chamadas e logs SBC 
 
Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados a erros de configuração dos SBCs ou do serviço de Roteamento Direto. 

Você pode usar as seguintes ferramentas para monitorar sua configuração:  
 
- Painel de Qualidade da Chamada 
- Logs SBC 

O serviço de Roteamento Direto tem códigos de erro muito descritivos relatados ao Call Analytics ou aos logs SBC. 

O Painel de Qualidade de Chamada fornece informações sobre qualidade e confiabilidade de chamada. Para saber mais sobre como solucionar problemas usando a Análise de Chamada, consulte [Acione](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e use o Painel de Qualidade de Chamada para Microsoft Teams e Skype for Business Online e Use a Análise de Chamada para solucionar problemas de baixa qualidade de [chamada.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

Em caso de falhas de chamada, a Análise de Chamada fornece códigos SIP padrão para ajudá-lo na solução de problemas. 

![Exemplo de código SIP para falha de chamada.](media/failed-response-code.png)

No entanto, o Call Analytics só pode ajudar quando as chamadas chegam aos componentes internos do Roteamento Direto e falham. Em caso de problemas com o emparelhamento SBC ou problemas em que SIP "Invite" foi rejeitado (por exemplo, o nome do FQDN do tronco está mal configurado), a Análise de Chamada não ajudará. Nesse caso, consulte os logs SBC. Roteamento Direto envia uma descrição detalhada de problemas para os SBCs; esses problemas podem ser lidos nos logs SBC.