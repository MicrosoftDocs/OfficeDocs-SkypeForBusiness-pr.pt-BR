---
title: Gerenciar dispositivos do Skype Room Systems v2 com o OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/19/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
description: 'Este artigo descreve como gerenciar os dispositivos do Skype Room Systems v2 de modo integrado e completo usando o Microsoft Operations Management Suite. '
ms.openlocfilehash: 4290e89f2a5faba6fa4efdfb48e57345bc0c35f5
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="manage-skype-room-systems-v2-devices-with-oms"></a>Gerenciar dispositivos do Skype Room Systems v2 com o OMS
 
Este artigo descreve como gerenciar os dispositivos do Skype Room Systems v2 de modo integrado e completo usando o Microsoft Operations Management Suite.  
  
Você pode configurar o Microsoft Operations Management Suite (OMS) para fornecer telemetria básicas que irão ajudar você a gerenciar Skype (consulte [gerenciamento de v2 de sistemas de sala Skype planejar com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) e [gerenciamento de v2 implantar sistemas do Skype sala com OMS de dispositivos de sala de reunião ](../../deploy/deploy-clients/with-oms.md)para obter detalhes). Com o passar do tempo, você pode comprar funcionalidades adicionais de gerenciamento e dados para sua solução a fim de criar um modo de exibição mais detalhado do desempenho do dispositivo.
  
## <a name="understand-the-log-entries"></a>Entenda as entradas do log
<a name="Telemetry"> </a>

As descrições de eventos a seguir são inseridas no campo de descrição do log de eventos a cada cinco minutos, quando o aplicativo SRS registra as informações correspondente no log de eventos do Windows. O agente OMS passa esses relatórios para OMS, que analisa-los ao painel de controle que você criou no [gerenciamento de v2 implantar sistemas do Skype sala com OMS](../../deploy/deploy-clients/with-oms.md). No painel, você pode examinar as entradas individuais do log para estabelecer sequências de ações, se necessário. 
  
As IDs do Evento 2000 e 3000 indicam que o dispositivo em questão está funcionando conforme esperado. As IDs do Evento 2001 e 3001 indicam que ocorreu um problema. A ID do Evento 4000 pode exigir ações, caso seja observada com mais frequência que o esperado em comparação com uma linha de base que você define ou com outros dispositivos implantados em sua organização.
  
Se você entender essas descrições de eventos, será alertado rapidamente sobre problemas e terá um ponto inicial para a solução de problemas.
  
|Nível de ID do evento|Comportamento do evento|Descrição do evento|
|:----- |:---- |:---- |
|2000  <br/> Informações  <br/> | Este é um evento de pulsação íntegra. A cada 5 minutos, SRS v2 verifica que ele é conectado ao Skype para negócios e possui conectividade do Exchange e rede. <br/> Se todos os 3 fatores forem verdadeiros, ele gravará a ID do Evento 2000 no log de eventos a cada 5 minutos, até que o dispositivo fique offline ou uma ou mais condições não sejam mais atendidas. <br/> | {"Descrição": "Heartbeat é íntegro.", <br/> "ResourceState": "Íntegro", "Nomedaoperação": "Pulsação" <br/> "OperationResult": "Passar", "OS": "Windows 10" <br/> "OSVersion": "10.0.14393.693", "Alias": "alias<span></span>@contoso.com", <br/> "DisplayName": "Nome de exibição,"<br/>  "AppVersion": "1.0.38.0", "IPv4Address": "10.10.10.10" <br/> "IPv6Address": "Endereço de IP v6"} <br/> <br/> Neste exemplo, todas as condições de pulsação foram atendidas e o dispositivo SRS v2 foi marcado como íntegro. Se tivessem ocorrido erros, o aplicativo teria registrado a ID do Evento 2001.<br/> |
|2001  <br/> Erro  <br/> |Este é um evento de erro do aplicativo. A cada 5 minutos, o SRS v2 verifica se está conectado ao Skype for Business, com conectividade de rede e com o Exchange. Se um ou mais fatores não forem verdadeiros, ele gravará a ID do Evento 2001 no log de eventos a cada 5 minutos, até que o dispositivo fique offline ou todas as condições possam ser atendidas novamente.  <br/> | {"Description":"Network status : Healthy. <br/> Exchange status : Connected. **Signin status: Unhealthy.** ",<br/> "ResourceState": "Não íntegros", "Nomedaoperação": "Pulsação"<br/> "OperationResult": "Fail", "OS": "Windows 10" <br/> "OSVersion": "10.0.14393.693", "Alias": "",<br/> "DisplayName": "Nome de exibição", "AppVersion": "1.0.38.0"<br/>  "IPv4Address": "10.10.10.10", "IPv6Address": "endereço de ip v6"} <br/><br/>  Neste exemplo, o SRSv2 determinou que a conexão de rede estava íntegra e que o aplicativo estava conectado ao Exchange, mas a parte em negrito indica que o aplicativo não estava conectado ao Skype for Business. Pode ser um problema de configuração no dispositivo ou no host.  <br/> <br/> Network status será Healthy ou Unhealthy. Se o status não for íntegro, talvez haja um problema com a rede ou o dispositivo pode ter sido desconectado (mas, nesse caso, é provável que também ocorram erros com o Exchange e o Skype for Business).<br/> <br/> O Status do Exchange mostrará como conectado ou um dos seguintes: desconectados, conectando-se, AutodiscoveryError (o erro mais comuns encontrado), GeneralError ou ServerVersionNotSupported. Se o status for Connecting, aguarde até que a próxima mensagem de integridade seja enviada; para outros erros, mencione o problema a um administrador com experiência em resolução de problemas do Exchange.  <br/><br/>  Signin status (que indica que o aplicativo está conectado ao Skype for Business) aparecerá como Healthy ou Unhealthy. Se o status for não íntegro, peça para um técnico investigar melhor.<br/> |
|3000  <br/> Informações  <br/> |Esse evento verifica se uma verificação de hardware foi executada e encontrada estar íntegro. Cada 5 minutos SRS v2 as verificações que configurados os componentes de hardware, como a parte frontal da exibição da sala, microfone, alto-falante e câmera são conectado e funcionando. Se todos os componentes estiverem íntegros, ele gravará a ID do Evento 3000 no log de eventos. Esse evento continuará sendo gravado a cada 5 minutos, a menos que haja algum problema com um dispositivo conectado.  <br/> |{"Descrição": "HardwareCheckEngine está íntegra.",<br/> "ResourceState": "Íntegro", "Nomedaoperação": "HardwareCheckEngine"<br/> "OperationResult": "Passar", "OS": "Windows 10"<br/> "OSVersion": "10.0.14393.693", "Alias": "alias<span></span>@contoso.com",<br/> "DisplayName": "Nome de exibição", "AppVersion": "1.0.38.0"<br/> "IPv4Address": "10.10.10.10", "IPv6Address": "endereço de ip v6"}  <br/> Neste exemplo, todas as verificações de hardware foram positivas. Se houver erros, <br/> em vez disso, o aplicativo seria registre 3001 de ID do evento.  <br/> |
|3001  <br/> Evento Error  <br/> |Este é um evento de erro de hardware. O aplicativo SRS tem um processo que verificará a integridade dos componentes de hardware conectados (tela frontal da sala, microfone, alto-falante, câmera) a cada 5 minutos. Se um ou mais componentes não estiverem íntegros, ele gravará a ID do Evento 3001 no log de eventos. Esse evento continuará sendo gravado a cada 5 minutos até que o problema com o dispositivo seja corrigido.  <br/> |{"Descrição": " **Front de sala Exibir status: não íntegros.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy. ","ResourceState":"Unhealthy","OperationName":"HardwareCheckEngine","OperationResult":"Fail","OS":"Windows 10","OSVersion":"10.0.14393.1198","Alias":"alias@contoso.com","DisplayName":"Yosemite conference room","AppVersion":"2.0.58.0","IPv4Address":"10.10.10.10","IPv6Address":"IPv6Address","IPv4Address2":"10.10.10.10"} <br/>  Os periféricos de hardware são mostrados como Healthy ou Unhealthy. <br/> Neste exemplo, há duas telas frontais da sala configuradas e, no momento, nenhuma delas está disponível. Conference Microphone status é Unhealthy, o que poderia ter diversas causas possíveis. Como pelo menos um recurso não passou na verificação, ResourceState é listado como Unhealthy. Peça para um técnico investigar melhor.  <br/> |
|4000  <br/> Informações  <br/> |Este é um evento de reinício do aplicativo. Sempre que o aplicativo é reiniciado, esse evento é registrado no log de eventos do Windows.  <br/> | {"Description":"App restarts.","ResourceState":"Healthy","OperationName":"Restart","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@domain.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"} <br/> O aplicativo Skype for Business pode ser reiniciado por diversos motivos. Compare a frequência de reinício dos dispositivos no mesmo prédio e em prédios diferentes, considerando problemas conhecidos, como flutuações e falhas de energia, pois eles podem indicar problemas de infraestrutura. <br/> |
   
## <a name="see-also"></a>Ver também
<a name="Telemetry"> </a>

#### 

[Planejar o gerenciamento de v2 Skype sala sistemas com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Implantar o gerenciamento de v2 Skype sala sistemas com OMS](../../deploy/deploy-clients/with-oms.md)

