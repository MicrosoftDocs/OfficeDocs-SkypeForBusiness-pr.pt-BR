---
title: Gerenciar dispositivos de Salas do Microsoft Teams com o Monitor do Azure
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
description: Este artigo aborda como gerenciar dispositivos de Salas do Microsoft Teams de maneira integrada usando o Monitor do Azure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662046"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Gerenciar dispositivos de Salas do Microsoft Teams com o Monitor do Azure

Este artigo aborda como gerenciar dispositivos de Salas do Microsoft Teams de maneira integrada usando o Monitor do Azure.

Você pode configurar o Monitor do Azure para fornecer telemetria básica para ajudá-lo a gerenciar dispositivos de sala de reunião do Skype. Consulte [Planejar o gerenciamento de Salas do Microsoft Teams com o Monitor do Azure](azure-monitor-plan.md) e Implantar o gerenciamento de Salas do [Microsoft Teams com o Monitor do Azure](azure-monitor-deploy.md) para obter detalhes. À medida que sua solução de gerenciamento é madura, você pode usar recursos adicionais de gerenciamento e dados para criar uma visão mais detalhada do desempenho do dispositivo.

## <a name="understand-the-log-entries"></a>Entenda as entradas do log

As descrições de eventos a seguir são inseridas no campo de descrição do log de eventos a cada cinco minutos, quando o aplicativo Salas do Microsoft Teams registra as informações correspondentes no log de eventos do Windows. O Agente de Monitoramento da Microsoft passa esses registros para a Análise de Log no Monitor do Azure, que os analisará no painel que você criou no gerenciamento implantar salas do Microsoft Teams com o [Monitor do Azure.](azure-monitor-deploy.md) Com o painel, você pode ver entradas individuais do log para determinar os cursos de ação, se necessário.

As IDs de evento 2000 e 3000 indicam que o dispositivo em questão está funcionando conforme o esperado. As IDs de evento 2001 e 3001 indicam que um problema foi encontrado. A ID do evento 4000 pode exigir ação se vista com mais frequência do que o esperado, em comparação com uma linha de base definida ou com outros dispositivos implantados em sua organização.

Se você entender essas descrições de eventos, será alertado rapidamente sobre problemas e terá um ponto inicial para a solução de problemas.

| Nível &nbsp; de ID do &nbsp; Evento|Comportamento do &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrição do &nbsp; Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informações | Este é um evento de pulsação íntegra. A cada 5 minutos, as Salas do Microsoft Teams verificam se ela está conectada ao Microsoft Teams ou ao Skype for Business e tem conectividade de rede e do Exchange. <br> Se todos os três fatores são verdadeiros, ele grava a ID do Evento 2000 no log de eventos a cada 5 minutos até que o dispositivo seja offline ou uma ou mais das condições não sejam atendidas. | {"Descrição":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Nome para exibição", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"Endereço IP v6"} <br><br> Neste exemplo, todas as condições de coração foram atendidas e o dispositivo Salas do Microsoft Teams foi marcado como saudável. Se tivessem ocorrido erros, o aplicativo teria registrado a ID do Evento 2001. |
| 2001  <br> Erro | Este é um evento de erro do aplicativo. A cada 5 minutos, as Salas do Microsoft Teams verificam se ela está conectada ao Microsoft Teams ou ao Skype for Business com conectividade de rede e do Exchange. Se um ou mais fatores não são verdadeiros, ele grava EventID 2001 no log de eventos a cada 5 minutos até que o dispositivo seja offline ou todas as condições sejam atendidas novamente.  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ", "ResourceState":"Não Saudável", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Nome de exibição", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"} <br><br>  Neste exemplo, as Salas do Microsoft Teams determinaram que a conexão de rede era saudável e que o aplicativo estava conectado ao Exchange, mas a parte em negrito indica que o aplicativo não está conectado. Pode ser um problema de configuração no dispositivo ou no host.  <br> <br> O status da rede é como Saudável ou Não Saudável. Se o status não for saudável, você pode ter um problema de rede ou o dispositivo pode ter sido desconectado (mas, em seguida, provavelmente também teria erros do Exchange e do Microsoft Teams ou do Skype for Business).  <br><br> O Status do Exchange mostra como Conectado ou um dos seguintes: Desconectado, Conectando, AutoDiscoveryError (o erro mais visto), GeneralError ou ServerVersionNotSupported. Se o status for Connecting, aguarde até que a próxima mensagem de integridade seja enviada; para outros erros, mencione o problema a um administrador com experiência em resolução de problemas do Exchange.  <br><br>  O status de Signin (indicando que o aplicativo está dentro) é indicado como Saudável ou Não Saudável. Se o status for não íntegro, peça para um técnico investigar melhor. |
| 3000  <br> Informações | Este evento verifica se uma verificação de hardware foi executado e se achou saudável. A cada 5 minutos, as Salas do Microsoft Teams verificam se os componentes de hardware configurados, como a tela frontal da sala, o microfone, o alto-falante e a câmera estão conectados e funcionando. Se todos os componentes estão saudáveis, ele grava EventID 3000 no log de eventos. Este evento é escrito a cada 5 minutos, a menos que haja um problema com um dispositivo conectado.  <br> | {"Description":"HardwareCheckEngine is healthy.", "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Nome de exibição", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"endereço ip v6"}  <br><br> Neste exemplo, todas as verificações de hardware foram positivas. Se houver erros, o aplicativo gravaria a ID do Evento 3001. |
| 3001  <br> Evento de Erro  | Este é um evento de erro de hardware. O aplicativo Salas do Microsoft Teams tem um processo que verifica a saúde dos componentes de hardware conectados (frente da sala, microfone, alto-falante, câmera) a cada 5 minutos. Se um ou mais dos componentes não são saudáveis, ele grava EventID 3001 no log de eventos. Este evento é escrito a cada 5 minutos até que o problema com o dispositivo seja corrigido.   | {"Descrição":" Status de exibição na **frente da sala: Não saudável.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Status da câmera: Healthy.", "ResourceState":"Healthyy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Sala de conferência Yosemite", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"} <br><br>  Os periféricos de hardware são mostrados como Healthy ou Unhealthy. <br> Neste exemplo, há duas telas frontais da sala configuradas e, no momento, nenhuma delas está disponível. O status do microfone de conferência não é saudável, o que pode ter várias causas possíveis. Como pelo menos um recurso não passou na verificação, ResourceState é listado como Unhealthy. Peça para um técnico investigar melhor. |
| 4000  <br> Informações  <br> | Este é um evento de reinício do aplicativo. Sempre que o aplicativo é reiniciado, esse evento é registrado no log de eventos do Windows.  <br> | {"Descrição":"O aplicativo reinicia.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @domain.com", "DisplayName":"Nome de exibição", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"endereço ip v6"} <br><br> O aplicativo pode ser reiniciado por vários motivos. Compare a frequência de reinicialização de dispositivos no mesmo prédio e em edifícios diferentes. Lembre-se de problemas conhecidos, como flutuações de energia e falhas, pois isso pode fornecer dicas para problemas de infraestrutura.|

## <a name="related-topics"></a>Tópicos relacionados
 

[Planejar o gerenciamento de Salas do Microsoft Teams com o Monitor do Azure](azure-monitor-plan.md)

[Implantar o gerenciamento de Salas do Microsoft Teams com o Monitor do Azure](azure-monitor-deploy.md)
