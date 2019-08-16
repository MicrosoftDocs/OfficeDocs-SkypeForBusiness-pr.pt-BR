---
title: Visão geral de gerenciamento para salas do Microsoft Teams
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Visão geral de gerenciamento para salas do Microsoft Teams.
ms.openlocfilehash: db1569f86ba0066691b6797517351087307cf38a
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427869"
---
# <a name="management-overview"></a>Visão geral do gerenciamento 

É essencial que você desenvolva e execute manutenção e operações contínuas para garantir que seus sistemas de salas do Microsoft Teams estejam disponíveis para seus usuários e proporcionar uma excelente experiência do usuário. 

## <a name="monitoring"></a>Monitoramento 

Monitorar as salas do Microsoft Teams Systems consiste em duas atividades importantes:

-  Monitoramento de dispositivos, aplicativos e periféricos

-  Monitoramento de qualidade e confiabilidade (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Monitoramento de dispositivos, aplicativos e dispositivos periféricos do Microsoft Teams

Para garantir que os usuários possam usar as unidades de sala do Microsoft Teams, as unidades devem estar conectadas à rede com o aplicativo salas do Microsoft Teams configurado corretamente e estar conectado a dispositivos periféricos em funcionamento. 


Informações sobre o estado do aplicativo salas do Microsoft Teams e dispositivos periféricos conectados são escritos pelo aplicativo salas do Microsoft Teams para o log de eventos do Windows e documentados em [entender as entradas do log](azure-monitor-manage.md#understand-the-log-entries). 

|**Configuração**|**Permite**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1  <br/> |Permite que salas do Microsoft Teams sejam inicializadas  <br/> |
|Gerenciamento de energia\> -em AC, desligar a tela após 10 minutos  <br/> Gerenciamento de energia\> -em AC, nunca coloque o sistema em suspensão  <br/> |Permite que as salas do Microsoft Teams desativem exibições anexadas e ativadas automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou uma maneira equivalente de desabilitar a expiração de senha na conta local. Deixar de fazer isso fará com que a conta do Skype falhe ao fazer logon com uma senha expirada. Observe que isso afeta todas as contas locais do computador e, portanto, não definir isso também fará com que a conta administrativa na caixa acabe de expirar também.  <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
A transferência de arquivos usando políticas de grupo é discutida em [configurar um item de arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Recomendamos que você use o pacote do Microsoft Operations Manager para monitorar seus sistemas de salas do Microsoft Teams. Para obter orientação sobre como configurar o monitoramento e o alerta básico, consulte [implantar gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md). 

Usando esta orientação, você pode criar um painel simples de usar para identificar os problemas com as unidades de sala do Microsoft Teams na sua implantação. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme que você usará o Operations Management Suite para monitorar a implantação de salas do Microsoft Teams.</li><li>Escolha a lista de distribuição de destino que você usará para alertas de email.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de qualidade e monitoramento de confiabilidade.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Monitoramento de qualidade e confiabilidade (CQD)

Recomendamos que você implemente a qualidade operacional contínua e os procedimentos de monitoramento de confiabilidade como parte da sua implantação para monitorar a tendência da chamada e a qualidade e a confiabilidade da reunião, identificando as áreas de interesse e trabalhando em direção a uma resolução. 

Ao carregar suas informações de construção para CQD, você pode investigar as tendências de qualidade de chamada e confiabilidade em um nível de construção, o que torna mais fácil comparar os prédios e concentrar sua atenção em problemas específicos.

Recomendamos que você examine e siga o [Guia de revisão da qualidade da experiência](https://aka.ms/qerguide) para identificar as tendências de qualidade e confiabilidade e crie um plano de ação para solucioná-los. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Atualizando o aplicativo salas do Microsoft Teams e salas do Microsoft Teams

Recomendamos que você atualize o sistema operacional de salas do Microsoft Teams e o aplicativo de salas do Microsoft Teams para se beneficiar de atualizações e melhorias de produtos. Para obter orientação detalhada, consulte [gerenciar salas do Microsoft Teams](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Atualizações do Windows

As salas do Microsoft Teams são executadas no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebe as mesmas versões do Windows e do sistema operacional do Windows como uma área de trabalho padrão. Consulte [gerenciar atualizações do Windows](updates.md) para obter detalhes.


## <a name="troubleshooting"></a>Solução de problemas

Recomendamos que você configure o alerta do Operations Management Suite conforme descrito na seção acima para que sua equipe de operações e helpdesks sejam alertados sobre problemas de sala do Microsoft Teams. As opções que você tem para gerenciamento remoto do PowerShell são descritas em [gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). Caso um dispositivo periférico seja desconectado, talvez seja necessário confiar em "práticas inteligentes" locais ou no suporte de ti para investigar e reconectar os dispositivos. 

Para obter mais informações sobre solução de problemas e modo de administração, consulte [gerenciar salas do Microsoft Teams](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)

[Implantar salas do Microsoft Teams](room-systems-v2.md)

[Configurar um console de salas do Microsoft Teams](console.md)

[Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md)
