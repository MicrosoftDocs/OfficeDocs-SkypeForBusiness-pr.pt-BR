---
title: Gerenciar dispositivos de Salas do Microsoft Teams com o Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: Este artigo discute como gerenciar dispositivos de Salas do Microsoft Teams de forma integrada usando o Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41375c313940099b6ed6e102e2452290e0817bec
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874761"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Gerenciar dispositivos de Salas do Microsoft Teams com o Azure Monitor

Este artigo discute como gerenciar dispositivos de Salas do Microsoft Teams de forma integrada usando o Azure Monitor.

Você pode configurar o Monitor do Azure para fornecer telemetria básica para ajudá-lo a gerenciar dispositivos de salas de reunião do Microsoft Teams. Confira [Planejar o gerenciamento de Salas do Microsoft Teams com o Azure Monitor](azure-monitor-plan.md) e Implantar o gerenciamento de Salas do Microsoft Teams com o [Azure Monitor](azure-monitor-deploy.md) para obter detalhes. À medida que sua solução de gerenciamento amadurece, você pode usar recursos adicionais de gerenciamento e dados para criar uma exibição mais detalhada do desempenho do dispositivo.

## <a name="understand-the-log-entries"></a>Entenda as entradas do log

As descrições de eventos a seguir são inseridas no campo de descrição do log de eventos a cada cinco minutos, quando o aplicativo Salas do Microsoft Teams registra as informações correspondentes no log de eventos do Windows. O Agente de Monitoramento da Microsoft passa esses registros para o Log Analytics no Azure Monitor, que os analisará no painel criado em Implantar o gerenciamento de Salas do Microsoft Teams com o [Azure Monitor](azure-monitor-deploy.md). Com o painel, você pode procurar entradas de log individuais para determinar cursos de ação, se necessário.

As IDs de evento 2000 e 3000 indicam que o dispositivo em questão está funcionando conforme esperado. As IDs de evento 2001 e 3001 indicam que um problema foi encontrado. A ID do evento 4000 pode exigir ação se for vista com mais frequência do que você espera, em comparação com uma linha de base definida ou com outros dispositivos implantados em sua organização.

Se você entender essas descrições de eventos, será alertado rapidamente sobre problemas e terá um ponto inicial para a solução de problemas.

| Nível &nbsp; de ID do &nbsp; evento|Comportamento do &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrição do &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informações | Este é um evento de pulsação íntegra. A cada 5 minutos, as Salas do Microsoft Teams verificam se ela está conectada ao Microsoft Teams ou ao Skype for Business e tem conectividade de rede e Exchange. <br> Se todos os 3 fatores são verdadeiros, ele grava a ID do Evento 2000 no log de eventos a cada 5 minutos até que o dispositivo seja offline ou uma ou mais das condições não sejam mais atendidas. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> Neste exemplo, todas as condições de pulsação foram atendidas e o dispositivo salas do Microsoft Teams foi marcado como saudável. Se tivessem ocorrido erros, o aplicativo teria registrado a ID do Evento 2001. |
| 2001  <br> Erro | Este é um evento de erro do aplicativo. A cada 5 minutos, as Salas do Microsoft Teams verificam se ela está conectada ao Microsoft Teams ou ao Skype for Business com conectividade de rede e Exchange. Se um ou mais fatores não são verdadeiros, ele grava EventID 2001 no log de eventos a cada 5 minutos até que o dispositivo seja offline ou todas as condições sejam atendidas novamente.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  Neste exemplo, as Salas do Microsoft Teams determinaram que a conexão de rede era saudável e que o aplicativo estava conectado ao Exchange, mas a parte em negrito indica que o aplicativo não está conectado. Pode ser um problema de configuração no dispositivo ou no host.  <br> <br> O status de rede mostra como Healthy ou Unhealthy. Se o status não estiver 100%, você pode ter um problema de rede ou o dispositivo pode ter sido desconectado (mas provavelmente você também teria erros do Exchange e do Microsoft Teams ou do Skype for Business).  <br><br> O Status do Exchange mostra como Conectado ou um dos seguintes: Desconectado, Conectando, AutodiscoveryError (o erro mais comumente visto), GeneralError ou ServerVersionNotSupported. Se o status for Connecting, aguarde até que a próxima mensagem de integridade seja enviada; para outros erros, mencione o problema a um administrador com experiência em resolução de problemas do Exchange.  <br><br>  O _status signin_ (indicando que o aplicativo está assinado) mostra como _Healthy_ ou _Unhealthy_. Se o status for não íntegro, peça para um técnico investigar melhor. |
| 3000  <br> Informações | Esse evento verifica se uma verificação de hardware foi executado e se encontrou saudável. A cada 5 minutos, as Salas do Microsoft Teams verifica se os componentes de hardware configurados, como a tela frontal da sala, o microfone, o alto-falante e a câmera estão conectados e funcionando. Se todos os componentes estão íntegrees, ele grava o EventID 3000 no log de eventos. Esse evento é escrito a cada 5 minutos, a menos que haja um problema com um dispositivo conectado.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Neste exemplo, todas as verificações de hardware foram positivas. Se houvesse erros, o aplicativo gravaria a ID do Evento 3001. |
| 3001  <br> Evento Error  | Este é um evento de erro de hardware. O aplicativo salas do Microsoft Teams tem um processo que verifica a saúde dos componentes de hardware conectados (frente da sala, microfone, alto-falante, câmera) a cada 5 minutos. Se um ou mais componentes não são íntee, ele grava EventID 3001 no log de eventos. Esse evento é gravado a cada 5 minutos até que o problema com o dispositivo seja corrigido.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Os periféricos de hardware são mostrados como Healthy ou Unhealthy.  <br> Neste exemplo, há duas _exibições front of room_ configuradas e, no momento, nenhuma delas está disponível. O _status do Microfone de Conferência_ não está _100%_ 100% 100% 100%, o que pode ter várias causas possíveis. Como pelo menos um recurso não passou na verificação, ResourceState é listado como Unhealthy. Peça para um técnico investigar melhor. |
| 4000  <br> Informações  <br> | Este é um evento de reinício do aplicativo. Sempre que o aplicativo é reiniciado, esse evento é registrado no log de eventos do Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> O aplicativo pode ser reiniciado por vários motivos. Compare a frequência de reinicialização de dispositivos no mesmo edifício e em edifícios diferentes. Lembre-se de problemas conhecidos, como flutuações e falhas de energia, pois isso pode fornecer pistas para problemas de infraestrutura.|

## <a name="related-topics"></a>Tópicos relacionados
 

[Planejar o gerenciamento de Salas do Microsoft Teams com o Azure Monitor](azure-monitor-plan.md)

[Implantar o gerenciamento de Salas do Microsoft Teams com o Azure Monitor](azure-monitor-deploy.md)
