---
title: Visão geral do gerenciamento de salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Visão geral do gerenciamento de salas de equipes da Microsoft.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32208243"
---
# <a name="management-overview"></a>Visão geral do gerenciamento 

É essencial que você desenvolver e executar manutenção contínua e a experiência de operações para garantir que seus sistemas de salas de equipes da Microsoft estão disponíveis para seus usuários e oferecem um ótimo usuário. 

## <a name="monitoring"></a>Monitoramento 

Monitorando sistemas de salas de equipes da Microsoft consiste em duas atividades principais:

-  Dispositivo, aplicativo e monitoramento de dispositivos periféricos

-  Qualidade e confiabilidade monitoring (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Dispositivo de salas de equipes da Microsoft, aplicativo e monitoramento de dispositivos periféricos

Para garantir que os usuários sejam capazes de usar as unidades de salas de equipes da Microsoft, as unidades devem estar na, conectado à rede com o aplicativo Microsoft equipes salas configurado corretamente e estar conectadas ao funcionamento dispositivos periféricos. 


Informações sobre o estado do aplicativo Microsoft equipes salas e dispositivos periféricos conectados é gravadas pelo aplicativo salas de equipes da Microsoft para o log de eventos do Windows e documentadas no [entender as entradas de log](azure-monitor.md#understand-the-log-entries). 

|**Configuração**|**Permite**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Permite que o Microsoft salas de equipes inicialize  <br/> |
|Gerenciamento - de energia\> nas AC, desative tela após 10 minutos  <br/> Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão  <br/> |Habilita a salas de equipes da Microsoft desativar exibe anexado e automaticamente de ativação  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou equivalentes meios de desativação de expiração de senha da conta local. Falha ao fazer isso, eventualmente, fará com que a conta do Skype falha de logon reclamando uma senha expirada. Observe que isso afeta todas as contas locais na máquina, e assim falha configurar isso também fará com que a conta administrativa na caixa eventualmente expire também.  <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Recomendamos que você use o pacote do Microsoft Operations Manager para monitorar os sistemas de salas de equipes da Microsoft. Para obter orientação sobre como configurar o monitoramento e alerta básica, consulte [gerenciamento de implantar o Microsoft equipes salas com Monitor do Azure](../../deploy/deploy-clients/azure-monitor.md). 

Usando este guia, você pode criar um painel simples de usar para identificar problemas com suas unidades de salas de equipes da Microsoft em sua implantação. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme que você usará o pacote de gerenciamento de operações para monitorar sua implantação de salas de equipes da Microsoft.</li><li>Decida a lista de distribuição de destino que você usará para alertas de email.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua qualidade e a confiabilidade abordagem de monitoramento.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualidade e confiabilidade monitoring (CQD)

É recomendável que você implemente qualidade operacional em andamento e a confiabilidade monitoring procedimentos como parte da sua implantação para monitorar as tendências de chamada e qualidade de reunião e confiabilidade, identificando quaisquer áreas de interesse e trabalhando com uma resolução. 

Quando você carregar suas informações de construção para CQD, você pode investigar tendências de qualidade e confiabilidade de chamada em um nível por construção, que torna mais fácil comparar os prédios e focalizar problemas específicos. Para obter mais informações, baixe o [Monitor-CQD para Skype para entrega Business Online e um guia de operações](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Recomendamos que você revise e siga o [Guia Quality of Experience revisar](https://aka.ms/qerguide) para identificar as tendências de qualidade e a confiabilidade e cria um plano de ação para resolvê-los. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Atualizar o aplicativo Microsoft equipes salas SO e salas de equipes da Microsoft

Recomendamos que você atualize o aplicativo Microsoft equipes salas SO e salas de equipes da Microsoft para se beneficiar de atualizações de produto e os aperfeiçoamentos. Para obter orientações detalhadas, consulte [Manage Rooms de equipes da Microsoft](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Atualizações do Windows

Salas de equipes da Microsoft é executado no Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas compilações de atualizações do Windows e o sistema operacional como uma área de trabalho padrão. Consulte [Gerenciar atualizações do Windows](updates.md) para obter detalhes.


## <a name="troubleshooting"></a>Solução de problemas

Recomendamos que você configurar o pacote de gerenciamento de operações de alerta conforme descrito na seção acima para que sua equipe de operações e a assistência técnica serão alertados sobre qualquer problema de salas de equipes da Microsoft. As opções que disponíveis para gerenciamento remoto do PowerShell são descritas no [gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). Se um dispositivo periférico estiver desconectado, você talvez seja necessário contam com suporte de TI para investigar e reconectar os dispositivos ou de locais "ponteiros inteligentes". 

Para obter mais informações sobre o modo de administração e solução de problemas, consulte [Manage Rooms de equipes da Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Planejar para salas de equipes da Microsoft](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Implantar salas de equipes da Microsoft](../../deploy/deploy-clients/room-systems-v2.md)

[Configurar um console de salas de equipes da Microsoft](../../deploy/deploy-clients/console.md)

[Gerenciar configurações do console um Microsoft equipes salas remotamente com um arquivo de configuração XML](xml-config-file.md)
