---
title: Monitorar o Roteamento Direto
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
description: Saiba como monitorar e solucionar problemas de configuração de Roteamento Direto, incluindo controladores de borda de sessão, componentes de roteamento direto e troncos de telecomunicações.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657241"
---
# <a name="monitor-direct-routing"></a>Monitorar o Roteamento Direto

Este artigo descreve como monitorar e solucionar problemas de sua configuração de Roteamento Direto. 

A capacidade de fazer e receber chamadas usando o Roteamento Direto envolve os seguintes componentes: 

- Controladores de borda de sessão (SBCs) 
- Componentes de Roteamento Direto no Microsoft Cloud 
- Troncos de telecomunicações 

Se você tiver dificuldades para solucionar problemas, poderá abrir um caso de suporte com seu fornecedor SBC ou a Microsoft. 

A Microsoft está trabalhando para fornecer mais ferramentas para solução de problemas e monitoramento. Verifique a documentação periodicamente para obter atualizações. 

## <a name="troubleshoot-direct-routing"></a>Solucionar problemas de roteamento direto

Para solucionar problemas de Roteamento Direto, [consulte Diagnosticar problemas com o Roteamento Direto](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitorando a disponibilidade de controladores de borda de sessão usando mensagens de opções do PROTOCOLO SIP

O Roteamento Direto usa opções SIP enviadas pelos Controladores de Borda de Sessão para monitorar a integridade do SBC. Não há nenhuma ação necessária do administrador de locatários para habilitar o monitoramento de opções SIP. As informações coletadas são levadas em consideração quando decisões de roteamento são tomadas. 

Por exemplo, se, para um usuário específico, houver vários SBCs disponíveis para rotear uma chamada, o Roteamento Direto considerará as informações de opções SIP recebidas de cada SBC para determinar o roteamento. 

O diagrama a seguir mostra um exemplo da configuração: 

![Exemplo de configuração de opções SIP.](media/sip-options-config-example.png)

Quando um usuário faz uma chamada para o número +1 425 \<any seven digits>, o Roteamento Direto avalia a rota. Há dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com. Ambos os SBCs têm prioridade igual na rota. Antes de escolher um SBC, o mecanismo de roteamento avalia a integridade dos SBCs com base em quando o SBC enviou as opções SIP da última vez. 

Um SBC será considerado íntegro se as estatísticas no momento do envio da chamada mostrarem que o SBC envia opções a cada minuto.  

Quando uma chamada é feita, a seguinte lógica se aplica:

- O SBC foi emparelhado às 11h.  
- O SBC envia opções às 11h01, 11h02 e assim por diante.  
- Às 11:15, um usuário faz uma chamada e o mecanismo de roteamento seleciona esse SBC. 

O Roteamento Direto usa as opções de intervalo regular três vezes (o intervalo regular é de um minuto). Se as opções foram enviadas durante os últimos três minutos, o SBC é considerado íntegro.

Se o SBC no exemplo enviou opções em qualquer período entre 11h12 e 11h15 (hora em que a chamada foi feita), ela será considerada íntegra. Caso contrário, o SBC será rebaixado da rota. 

Rebaixamento significa que o SBC não será tentado primeiro. Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com prioridade igual.  

Se sbc1.contoso.com não enviar opções SIP em um intervalo regular, conforme descrito anteriormente, ele será rebaixado. Em seguida, sbc2.contoso.com tenta a chamada. Se sbc2.contoso.con não puder entregar a chamada, o sbc1.contoso.com (rebaixado) será tentado novamente antes que uma falha seja gerada. 

Se dois (ou mais) SBCs em uma rota forem considerados íntegros e iguais, Fisher-Yates ordem aleatória será aplicada para distribuir as chamadas entre os SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorar o painel do Análise de Qualidade de Chamadas e logs SBC 
 
Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados à configuração incorreta dos SBCs ou do serviço de Roteamento Direto. 

Você pode usar as seguintes ferramentas para monitorar sua configuração:  
 
- Painel de Qualidade da Chamada 
- Logs SBC 

O serviço de Roteamento Direto tem códigos de erro descritivos relatados para a Análise de Chamadas ou os logs SBC.

O Painel de Qualidade de Chamadas fornece informações sobre qualidade e confiabilidade de chamadas. Para saber mais sobre como solucionar problemas usando a Análise de Chamadas, consulte Ativar e usar o Painel de Qualidade de Chamadas para [o Microsoft Teams e o Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e usar a Análise de Chamadas para solucionar problemas de baixa qualidade de [chamadas](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

Em caso de falhas de chamada, a Análise de Chamadas fornece códigos SIP padrão para ajudá-lo com a solução de problemas. 

![Exemplo de código SIP para falha de chamada.](media/failed-response-code.png)

No entanto, a Análise de Chamadas só pode ajudar quando as chamadas chegam aos componentes internos do Roteamento Direto e falham. Em caso de problemas com o emparelhamento SBC ou problemas em que SIP "Invite" foi rejeitado (por exemplo, o nome do FQDN do tronco está configurado incorretamente), a Análise de Chamadas não ajudará. Nesse caso, consulte os logs SBC. O Roteamento Direto envia uma descrição detalhada dos problemas para os SBCs; esses problemas podem ser lidos nos logs SBC.
