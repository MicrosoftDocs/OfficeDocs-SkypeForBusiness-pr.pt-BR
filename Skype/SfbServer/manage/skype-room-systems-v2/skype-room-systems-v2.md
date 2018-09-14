---
title: Visão geral do gerenciamento de sistemas de sala Skype v2
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
description: Visão geral do gerenciamento de sistemas de sala Skype v2.
ms.openlocfilehash: d79c04c69e320f404c8ce245120e9b01bd8de1ca
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965653"
---
# <a name="management-overview"></a>Visão geral do gerenciamento 

É essencial que você desenvolver e executar manutenção contínua e a experiência de operações para garantir que seus sistemas de v2 Skype sala sistemas estão disponíveis para os usuários e oferecem um ótimo usuário. 

## <a name="monitoring"></a>Monitoramento 

Sistemas de sala Skype v2 sistemas de monitoramento consistem em duas atividades principais:

-  Dispositivo, aplicativo e monitoramento de dispositivos periféricos

-  Qualidade e confiabilidade monitoring (CQD)

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a>Dispositivo de v2 Skype sala sistemas, aplicativos e o monitoramento de dispositivos periféricos

Para garantir que os usuários sejam capazes de usar as unidades do Skype sala sistemas v2, as unidades devem estar na, conectado à rede com o aplicativo de v2 de sistemas de sala Skype configurado corretamente e estar conectadas ao funcionamento dispositivos periféricos. 


Informações sobre o estado do aplicativo de v2 Skype sala sistemas e dispositivos periféricos conectados são gravadas pelo aplicativo Skype sala sistemas v2 para o log de eventos do Windows e documentadas [neste artigo](oms.md#understand-the-log-entries). 

|**Configuração**|**Permite**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Permite que os sistemas de sala Skype v2 inicialize  <br/> |
|Gerenciamento - de energia\> nas AC, desative tela após 10 minutos  <br/> Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão  <br/> |Permite que os sistemas de sala Skype v2 desativar exibe anexado e automaticamente de ativação  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou um modo equivalente de desabilitar a expiração da senha na conta local. A impossibilidade de fazer isso pode causar uma falha no logon com a conta do Skype com uma mensagem de senha expirada. Observe que isso afeta todas as contas locais do computador. Portanto, se isso não for definido, com o tempo, a conta de administrador também vai expirar.   <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>


Recomendamos que você use o pacote do Microsoft Operations Manager para monitorar os sistemas de v2 Skype sistemas de sala. Para obter orientação sobre como configurar o monitoramento e alerta básica, consulte [gerenciamento de v2 de implantar sistemas do Skype sala com OMS](../../deploy/deploy-clients/with-oms.md). 

Usando este guia, você pode criar um painel simples de usar para identificar problemas com suas unidades v2 de sistemas de sala Skype entre sua implantação. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme que você usará o pacote de gerenciamento de operações para monitorar sua implantação do Skype sala sistemas v2.</li><li>Decida a lista de distribuição de destino que você usará para alertas de email.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Defina sua qualidade e a confiabilidade abordagem de monitoramento.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualidade e confiabilidade monitoring (CQD)

É recomendável que você implemente qualidade operacional em andamento e a confiabilidade monitoring procedimentos como parte da sua implantação para monitorar as tendências de chamada e qualidade de reunião e confiabilidade, identificando quaisquer áreas de interesse e trabalhando com uma resolução. 

Quando você carregar suas informações de construção para CQD, você pode investigar tendências de qualidade e confiabilidade de chamada em um nível por construção, que torna mais fácil comparar os prédios e focalizar problemas específicos. Para obter mais informações, baixe o [Monitor-CQD para Skype para entrega Business Online e um guia de operações](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Recomendamos que você revise e siga o [Guia Quality of Experience revisar](https://aka.ms/qerguide) para identificar as tendências de qualidade e a confiabilidade e cria um plano de ação para resolvê-los. 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a>Atualizar o aplicativo de sistemas de sala Skype v2 SO e sistemas de sala do Skype 

Recomendamos que você atualize o Skype sala sistemas v2 SO e sistemas de sala Skype v2 aplicativo para se beneficiar de atualizações de produto e os aperfeiçoamentos. Para obter orientações detalhadas, consulte [gerenciar sistemas de sala Skype v2](room-systems-v2-operations.md#software-updates). 

## <a name="troubleshooting"></a>Solução de problemas

Recomendamos que você configure conforme descrito na seção acima para que sua equipe de operações e a assistência técnica serão alertados sobre qualquer problema de sistemas de sala Skype v2 alerta do pacote de gerenciamento de operações. As opções que disponíveis para gerenciamento remoto do PowerShell são descritas no [gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). Se um dispositivo periférico estiver desconectado, você talvez seja necessário contam com suporte de TI para investigar e reconectar os dispositivos ou de locais "ponteiros inteligentes". 

Para obter mais informações sobre o modo de administração e solução de problemas, consulte [gerenciar sistemas de sala Skype v2](room-systems-v2-operations.md#admin-mode-and-device-management). 

## <a name="see-also"></a>Consulte também

[Ajuda da versão 2 de sistemas de sala do Skype](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Planejar o Skype Room Systems versão 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Implantar o Skype Room Systems versão 2](../../deploy/deploy-clients/room-systems-v2.md)

[Configurar o console do Skype Room Systems versão 2](../../deploy/deploy-clients/console.md)

[Gerenciar as configurações de um console do Skype Room Systems v2 remotamente usando um arquivo de configuração XML](xml-config-file.md)
