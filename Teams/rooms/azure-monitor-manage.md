---
title: Monitorar Salas do Microsoft Teams com o Azure Monitor
ms.author: dstrome
author: dstrome
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
description: Este artigo discute como monitorar dispositivos Salas do Microsoft Teams de maneira integrada usando o Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82193bfae50bc2aafeb9f00425ab6eb69fec394
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761263"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Monitorar Salas do Microsoft Teams com o Azure Monitor

Este artigo discute como monitorar o Salas do Microsoft Teams de maneira integrada usando o Azure Monitor.

Você pode configurar o Azure Monitor para fornecer telemetria básica para ajudá-lo a monitorar Microsoft Teams dispositivos de salas de reunião. Consulte [Planejar Salas do Microsoft Teams gerenciamento com o Azure Monitor](azure-monitor-plan.md) e implantar [o Salas do Microsoft Teams com o Azure Monitor](azure-monitor-deploy.md) para obter detalhes. À medida que sua solução de monitoramento amadurece, você pode usar outros recursos de dados e monitoramento para criar uma exibição mais detalhada do desempenho do dispositivo.

## <a name="understand-the-log-entries"></a>Entenda as entradas do log

As descrições de evento a seguir são inseridas no campo de descrição do log de eventos a cada cinco minutos, quando o aplicativo Salas do Microsoft Teams registra as informações correspondentes no log de Windows eventos. O Microsoft Monitoring Agent passa esses registros para o Log Analytics no Azure Monitor, que os analisa no painel criado em Implantar [Salas do Microsoft Teams monitoramento com o Azure Monitor](azure-monitor-deploy.md). Com o painel, você pode examinar entradas de log individuais para determinar os cursos de ação, se necessário.

As IDs de evento 2000 e 3000 indicam que Salas do Teams está funcionando conforme o esperado. As IDs de evento 2001 e 3001 indicam que um problema foi encontrado. A ID do evento 4000 pode exigir ação se for vista com mais frequência do que o esperado, em comparação com uma linha de base definida ou com outros dispositivos implantados em sua organização.

Se você entender essas descrições de eventos, será alertado rapidamente sobre problemas e terá um ponto inicial para a solução de problemas.

| Nível da&nbsp;ID do&nbsp;evento|Comportamento do&nbsp;evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrição do&nbsp;evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informações | Este é um evento de pulsação íntegra. A cada 5 minutos, Salas do Microsoft Teams verifica se ele está conectado ao Microsoft Teams ou Skype for Business e tem conectividade de rede e Exchange cliente. <br> Se todos os três fatores forem verdadeiros, ele gravará a ID do Evento 2000 no log de eventos a cada 5 minutos até que o dispositivo esteja offline ou uma ou mais das condições não sejam mais atendidas. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> Neste exemplo, todas as condições de pulsação foram atendidas e Salas do Microsoft Teams dispositivo foi marcado como íntegro. Se tivessem ocorrido erros, o aplicativo teria registrado a ID do Evento 2001. |
| 2001  <br> Erro | Este é um evento de erro do aplicativo. A cada 5 minutos, Salas do Microsoft Teams verifica se ele está conectado ao Microsoft Teams ou Skype for Business com conectividade Exchange rede. Se um ou mais fatores não forem verdadeiros, ele gravará EventID 2001 no log de eventos a cada 5 minutos até que o dispositivo esteja offline ou todas as condições sejam atendidas novamente.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. Teams Signin status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  Neste exemplo, Salas do Microsoft Teams determinou que a conexão de rede estava íntegra e que o aplicativo estava conectado ao Exchange, mas a parte em negrito indica que o aplicativo não está conectado. Pode ser um problema de configuração no dispositivo ou no host.  <br> <br> O status de rede é exibido como Íntegro ou não íntegro. Se o status não estiver íntegro, talvez você tenha um problema de rede ou o dispositivo possa ter sido desconectado (mas, provavelmente, você também teria Exchange e Microsoft Teams ou Skype for Business erros).  <br><br> O Exchange status é mostrado como Conectado ou um dos seguintes: Desconectado, Conectando, AutodiscoveryError (o erro mais comumente visto), GeneralError ou ServerVersionNotSupported. Se o status for Connecting, aguarde até que a próxima mensagem de integridade seja enviada; para outros erros, mencione o problema a um administrador com experiência em resolução de problemas do Exchange.  <br><br>  O _status de entrada_/ _Teams status_ de entrada (indicando que o aplicativo está conectado) é exibido como Íntegro _ou Não íntegro_. Se o status for não íntegro, peça para um técnico investigar melhor. |
| 3000  <br> Informações | Esse evento verifica se uma verificação de hardware foi executada e está íntegra. A cada 5 Salas do Microsoft Teams verifica se os componentes de hardware configurados, como tela frontal da sala, microfone, alto-falante e câmera, estão conectados e funcionando. Se todos os componentes forem íntegros, ele gravará EventID 3000 no log de eventos. Esse evento é gravado a cada 5 minutos, a menos que haja um problema com um dispositivo conectado.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Neste exemplo, todas as verificações de hardware foram positivas. Se houvesse erros, o aplicativo gravaria a ID do Evento 3001. |
| 3001  <br> Evento error  | Este é um evento de erro de hardware. O Salas do Microsoft Teams aplicativo tem um processo que verifica a integridade dos componentes de hardware conectados (frente da sala, microfone, alto-falante, câmera) a cada 5 minutos. Se um ou mais dos componentes não estiverem íntegros, ele gravará EventID 3001 no log de eventos. Esse evento é gravado a cada 5 minutos até que o problema com o dispositivo seja corrigido.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Os periféricos de hardware são mostrados como Healthy ou Unhealthy.  <br> Neste exemplo, há duas _exibições de_ frente de sala configuradas e, no momento, nenhuma delas está disponível. O _status do Microfone de Conferência_ _não está íntegro_, o que pode ter várias causas possíveis. Como pelo menos um recurso não passou na verificação, ResourceState é listado como Unhealthy. Peça para um técnico investigar melhor. |
| 4000  <br> Informações  <br> | Este é um evento de reinício do aplicativo. Sempre que o aplicativo é reiniciado, esse evento é registrado no log de eventos do Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> O aplicativo pode ser reiniciado por vários motivos. Compare a frequência de reinicialização de dispositivos no mesmo prédio e em edifícios diferentes. Tenha em mente problemas conhecidos, como flutuações de energia e falhas, pois isso pode fornecer pistas para problemas de infraestrutura.|

## <a name="related-topics"></a>Tópicos relacionados
 

[Planejar Salas do Microsoft Teams monitoramento com o Azure Monitor](azure-monitor-plan.md)

[Implantar Salas do Microsoft Teams monitoramento com o Azure Monitor](azure-monitor-deploy.md)
