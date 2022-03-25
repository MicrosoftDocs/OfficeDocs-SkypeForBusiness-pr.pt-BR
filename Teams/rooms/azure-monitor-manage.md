---
title: Monitorar Salas do Microsoft Teams dispositivos com o Monitor do Azure
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: Este artigo discute como monitorar Salas do Microsoft Teams dispositivos de forma integrada usando o Monitor do Azure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a19a6be8f48bedca228457f7e5c2c85be1ef8374
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63761895"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Monitorar Salas do Microsoft Teams dispositivos com o Monitor do Azure

Este artigo discute como monitorar Salas do Microsoft Teams de forma integrada usando o Azure Monitor.

Você pode configurar o Monitor do Azure para fornecer telemetria básica para ajudá-lo a monitorar Microsoft Teams dispositivos de salas de reunião. Consulte [Plan Salas do Microsoft Teams management with Azure Monitor](azure-monitor-plan.md) and [Deploy Salas do Microsoft Teams management with Azure Monitor](azure-monitor-deploy.md) para obter detalhes. À medida que sua solução de monitoramento amadurece, você pode usar dados adicionais e recursos de monitoramento para criar uma exibição mais detalhada do desempenho do dispositivo.

## <a name="understand-the-log-entries"></a>Entenda as entradas do log

As descrições de eventos a seguir são inseridas no campo de descrição do log de eventos a cada cinco minutos, quando o aplicativo Salas do Microsoft Teams registra as informações correspondentes no log Windows evento. O Microsoft Monitoring Agent passa esses registros para o Log Analytics no Azure Monitor, que os analisará no painel criado em Implantar Salas do Microsoft Teams monitoramento com o [Azure Monitor](azure-monitor-deploy.md). Com o painel, você pode procurar entradas de log individuais para determinar cursos de ação, se necessário.

As IDs de evento 2000 e 3000 indicam que Salas do Teams está funcionando conforme esperado. As IDs de evento 2001 e 3001 indicam que um problema foi encontrado. A ID do evento 4000 pode exigir ação se for vista com mais frequência do que você espera, em comparação com uma linha de base definida ou com outros dispositivos implantados em sua organização.

Se você entender essas descrições de eventos, será alertado rapidamente sobre problemas e terá um ponto inicial para a solução de problemas.

| EventIDlevel&nbsp;&nbsp;|Eventbehavior&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EventDescription&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informações | Este é um evento de pulsação íntegra. A cada 5 minutos, Salas do Microsoft Teams verifica se ele está conectado Microsoft Teams ou Skype for Business e tem conectividade de rede e Exchange. <br> Se todos os 3 fatores são verdadeiros, ele grava a ID do Evento 2000 no log de eventos a cada 5 minutos até que o dispositivo seja offline ou uma ou mais das condições não sejam mais atendidas. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> Neste exemplo, todas as condições de pulsação foram atendidas e o dispositivo Salas do Microsoft Teams foi marcado como saudável. Se tivessem ocorrido erros, o aplicativo teria registrado a ID do Evento 2001. |
| 2001  <br> Erro | Este é um evento de erro do aplicativo. A cada 5 minutos, Salas do Microsoft Teams verifica se ele está conectado Microsoft Teams ou Skype for Business com conectividade de rede e Exchange. Se um ou mais fatores não são verdadeiros, ele grava EventID 2001 no log de eventos a cada 5 minutos até que o dispositivo seja offline ou todas as condições sejam atendidas novamente.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. Teams Signin status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  Neste exemplo, Salas do Microsoft Teams determinou que a conexão de rede estava saudável e que o aplicativo estava conectado ao Exchange, mas a parte em negrito indica que o aplicativo não está conectado. Pode ser um problema de configuração no dispositivo ou no host.  <br> <br> O status de rede mostra como Healthy ou Unhealthy. Se o status não estiver 100%, você pode ter um problema de rede ou o dispositivo pode ter sido desconectado (mas, em seguida, você provavelmente também teria Exchange e Microsoft Teams ou Skype for Business erros).  <br><br> O Exchange Status mostra como Conectado ou um dos seguintes: Desconectado, Conectando, AutodiscoveryError (o erro mais comumente visto), GeneralError ou ServerVersionNotSupported. Se o status for Connecting, aguarde até que a próxima mensagem de integridade seja enviada; para outros erros, mencione o problema a um administrador com experiência em resolução de problemas do Exchange.  <br><br>  O _status de signin_/ _Teams status signin_ (indicando que o aplicativo está ingressado) mostra como _Saudável_ ou _Não Saudável_. Se o status for não íntegro, peça para um técnico investigar melhor. |
| 3000  <br> Informações | Esse evento verifica se uma verificação de hardware foi executado e se encontrou saudável. A cada 5 Salas do Microsoft Teams verifica se os componentes de hardware configurados, como tela frontal da sala, microfone, alto-falante e câmera estão conectados e funcionando. Se todos os componentes estão íntegrees, ele grava o EventID 3000 no log de eventos. Esse evento é escrito a cada 5 minutos, a menos que haja um problema com um dispositivo conectado.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Neste exemplo, todas as verificações de hardware foram positivas. Se houvesse erros, o aplicativo gravaria a ID do Evento 3001. |
| 3001  <br> Evento Error  | Este é um evento de erro de hardware. O Salas do Microsoft Teams app tem um processo que verifica a saúde dos componentes de hardware conectados (frente da sala, microfone, alto-falante, câmera) a cada 5 minutos. Se um ou mais componentes não são íntee, ele grava EventID 3001 no log de eventos. Esse evento é gravado a cada 5 minutos até que o problema com o dispositivo seja corrigido.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Os periféricos de hardware são mostrados como Healthy ou Unhealthy.  <br> Neste exemplo, há duas _exibições front of room_ configuradas e, no momento, nenhuma delas está disponível. O _status do Microfone de Conferência_ _não é 100_%, o que pode ter várias causas possíveis. Como pelo menos um recurso não passou na verificação, ResourceState é listado como Unhealthy. Peça para um técnico investigar melhor. |
| 4000  <br> Informações  <br> | Este é um evento de reinício do aplicativo. Sempre que o aplicativo é reiniciado, esse evento é registrado no log de eventos do Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> O aplicativo pode ser reiniciado por vários motivos. Compare a frequência de reinicialização de dispositivos no mesmo edifício e em edifícios diferentes. Lembre-se de problemas conhecidos, como flutuações e falhas de energia, pois isso pode fornecer pistas para problemas de infraestrutura.|

## <a name="related-topics"></a>Tópicos relacionados
 

[Planejar Salas do Microsoft Teams monitoramento com o Azure Monitor](azure-monitor-plan.md)

[Implantar Salas do Microsoft Teams monitoramento com o Azure Monitor](azure-monitor-deploy.md)
