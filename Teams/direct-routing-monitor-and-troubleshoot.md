---
title: Monitorar e solucionar problemas do Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como monitorar e solucionar problemas de configuração de Roteamento Direto, incluindo Controladores de Borda de Sessão, componentes de Roteamento Direto e troncos de Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901906"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Monitorar e solucionar problemas do Roteamento Direto

Este artigo descreve como monitorar e solucionar problemas de sua configuração de Roteamento Direto. 

A capacidade de fazer e receber chamadas usando o Roteamento Direto envolve os seguintes componentes: 

- Controladores de Borda de Sessão (SBCs) 
- Componentes de Roteamento Direto no Microsoft Cloud 
- Troncos de telecomunicações 

Se você tiver dificuldades para solucionar problemas, poderá abrir um caso de suporte com seu fornecedor SBC ou a Microsoft. 

A Microsoft está trabalhando para fornecer mais ferramentas para solução de problemas e monitoramento. Verifique periodicamente a documentação para ver se há atualizações. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitorar a disponibilidade dos Controladores de Borda de Sessão usando mensagens de opções do PROTOCOLO

O Roteamento Direto usa as opções SIP enviadas pelos Controladores de Borda de Sessão para monitorar a saúde do SBC. Não são necessárias ações do administrador do locatário para habilitar o monitoramento de opções SIP. As informações coletadas são consideradas quando as decisões de roteamento são tomadas. 

Por exemplo, se, para um usuário específico, houver vários SBCs disponíveis para rotear uma chamada, o Roteamento Direto considerará as informações de opções SIP recebidas de cada SBC para determinar o roteamento. 

O diagrama a seguir mostra um exemplo da configuração: 

![Exemplo de configuração de opções SIP](media/sip-options-config-example.png)

Quando um usuário faz uma chamada para o número +1 425 a qualquer>, o Roteamento \< Direto avalia a rota. Há dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com. Ambos os SBCs têm prioridade igual na rota. Antes de escolher um SBC, o mecanismo de roteamento avalia a saúde dos SBCs com base em quando o SBC enviou as opções SIP da última vez. 

Um SBC será considerado saudável se as estatísticas no momento do envio da chamada mostrarem que o SBC envia opções a cada minuto.  

Quando uma chamada é feita, aplica-se a seguinte lógica:

- O SBC foi emparelhado às 11:00.  
- O SBC envia opções às 11:01, 11:02 e assim por diante.  
- Às 11:15, um usuário faz uma chamada e o mecanismo de roteamento seleciona esse SBC. 

O Roteamento Direto assume as opções de intervalo regular três vezes (o intervalo regular é de um minuto). Se as opções foram enviar durante os últimos três minutos, o SBC será considerado saudável.

Se o SBC nas opções de exemplo enviadas em qualquer período entre 11:12 e 11:15 (hora em que a chamada foi feita), ela será considerada saudável. Caso não, o SBC será rebaixado da rota. 

Desmoção significa que o SBC não será tentado primeiro. Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com igual prioridade.  

Se sbc1.contoso.com não enviar opções SIP em um intervalo regular conforme descrito anteriormente, ele será rebaixado. Em seguida, sbc2.contoso.com tenta a chamada. Se sbc2.contoso.con não conseguir entregar a chamada, a sbc1.contoso.com (rebaixada) será tentada novamente antes que uma falha seja gerada. 

Se dois (ou mais) SBCs em uma rota são considerados saudáveis e iguais, a Fisher-Yates aleatória é aplicada para distribuir as chamadas entre os SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorar o painel análise de qualidade de chamada e logs SBC 
 
Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados a erros de configuração dos SBCs ou do serviço de Roteamento Direto. 

Você pode usar as seguintes ferramentas para monitorar sua configuração:  
 
- Painel de Qualidade da Chamada 
- Logs SBC 

O serviço roteamento direto tem códigos de erro muito descritivos relatados à Análise de Chamadas ou aos logs SBC. 

O Painel de Qualidade da Chamada fornece informações sobre qualidade e confiabilidade de chamada. Para saber mais sobre como solucionar problemas usando o Recurso de Análise de Chamadas, consulte Como ligar e usar o Painel de Qualidade de Chamada do Microsoft Teams e do [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e usar a Análise de Chamadas para solucionar problemas de baixa qualidade de [chamadas.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

Em caso de falhas de chamada, a Análise de Chamada fornece códigos SIP padrão para ajudá-lo na solução de problemas. 

![Exemplo de código SIP para falha de chamada](media/failed-response-code.png)

No entanto, a Análise de Chamadas só pode ajudar quando as chamadas atingem os componentes internos do Roteamento Direto e falham. Em caso de problemas com o emparelhamento SBC ou problemas em que o "Convite" SIP foi rejeitado (por exemplo, o nome do FQDN do tronco está configurado indefigurado), a Análise de Chamada não ajudará. Nesse caso, consulte os logs SBC. O Roteamento Direto envia uma descrição detalhada dos problemas para os SBCs; esses problemas podem ser lidos nos logs SBC. 
