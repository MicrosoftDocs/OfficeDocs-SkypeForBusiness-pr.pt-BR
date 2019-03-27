---
title: Monitorar e solucionar problemas do Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Este artigo descreve como monitorar e solucionar problemas de configuração de roteamento direto.
ms.openlocfilehash: 89cbf47433fb26867ff2546a98360e1fa715e349
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894241"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Monitorar e solucionar problemas do Roteamento Direto

Este artigo descreve como monitorar e solucionar problemas de configuração de roteamento direto. 

A capacidade de fazer e receber chamadas usando o roteamento direto envolve os seguintes componentes: 

- Controladores de borda de sessão (SBCs) 
- Componentes de roteamento diretos no Microsoft Cloud 
- Troncos de telecomunicações 

Se você tiver dificuldades para solução de problemas, abra um caso de suporte com seu fornecedor SBC ou o Microsoft. 

Microsoft está trabalhando em fornecer mais ferramentas para o monitoramento e solução de problemas. Verifique a documentação periodicamente para atualizações. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitorar a disponibilidade dos controladores de borda de sessão usando mensagens de opções de protocolo de iniciação de sessão (SIP)

Roteamento direto usa opções SIP enviadas pelos controladores de borda de sessão para monitorar a integridade SBC. Não há nenhuma ação necessária do administrador do locatário para habilitar o monitoramento de SIP Options. As informações coletadas sejam levadas em consideração quando as decisões de roteamento são feitas. 

Por exemplo, se, para um usuário específico, existem várias SBCs disponíveis para encaminhar uma chamada, roteamento direto considera que as informações de SIP Options recebidas de cada SBC para determinar o roteamento. 

O diagrama a seguir mostra um exemplo da configuração: 

![Exemplo de configuração de opções de SIP](media/sip-options-config-example.png)

Quando um usuário faz uma chamada para o número +1 425 \<qualquer digits> sete, roteamento direto avalia a rota. Existem dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com. Ambos os SBCs possuem prioridade iguais na rota. Antes de separação um SBC, o mecanismo de circulação avalia a integridade dos SBCs com base em quando o SBC enviadas as opções de SIP última vez. 

Um SBC é considerado Íntegro se estatísticas no momento do envio de chamada mostra que o SBC envia opções em um intervalo regular.  

Roteamento direto calcula a intervalos regulares de acordo com a média de duas vezes quando o SBC envia opções antes de fazer a chamada e adicionar cinco minutos. 

Por exemplo, suponha que o seguinte: 

- Um SBC está configurado para enviar opções cada minuto. 
- O SBC foi emparelhado às 11.00 AM.  
- O SBC envia opções nos 11.01 AM, 11.02 AM e assim por diante.  
- No 11.15, um usuário faz uma chamada e o mecanismo de circulação seleciona esta SBC. 

A lógica a seguir é aplicada: duas vezes o intervalo de médio quando o SBC envia opções (um minuto mais um minuto = dois minutos) e mais de cinco minutos = sete minutos. Esse é o valor do intervalo para o SBC regular.
 
Se o SBC em nosso exemplo enviada opções em qualquer período entre 11.08 AM e 11.15 AM (o tempo que a chamada foi feita), ele é considerado íntegro. Caso contrário, o SBC vai ser rebaixado da rota. 

Rebaixamento significa que o SBC não será testado pela primeira vez. Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com prioridade igual.  

Se sbc1.contoso.com não enviar SIP Options em intervalos regulares, conforme descrito acima, ele será rebaixado. Em seguida, sbc2.contoso.com tentará para a chamada. Se sbc2.contoso.con não é possível entregar a chamada, o sbc1.contoso.com (rebaixado) for testado novamente antes que uma falha seja gerada. 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitore os logs SBC e painel de análise de qualidade de chamada 
 
Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados à configuração incorreta dos SBCs e/ou o serviço de roteamento direto. 

Você pode usar as seguintes ferramentas para monitorar sua configuração:  
 
- Painel de Qualidade da Chamada 
- Logs SBC 

O serviço de roteamento direto tem os códigos de erro de muito descritivo reportados para análise de chamada ou os logs SBC. 

O painel de controle de qualidade de chamada fornece informações sobre a qualidade da chamada e a confiabilidade. Para saber mais sobre como solucionar problemas usando a análise de chamada, consulte [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e [Análise de uso chamada solucionar problemas de qualidade de chamadas ruins](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

No caso de falhas de chamada, chamada Analytics fornece códigos SIP padrão para ajudar a solucionar problemas. 

![Exemplos de código SIP de falha de ligação](media/failed-response-code.png)

No entanto, chamar Analytics só pode ajudar quando chamadas alcançar os componentes internos do roteamento direto e falharem. No caso de problemas com pareamento de SBC ou onde SIP "Convidar" foi rejeitada (por exemplo, o nome do tronco que FQDN foi definida incorretamente), análise de chamada não ajudará. Nesse caso, consulte os logs SBC. Roteamento direto envia uma descrição detalhada de problemas para os SBCs; Esses problemas podem ser lidas dos logs SBC. 
