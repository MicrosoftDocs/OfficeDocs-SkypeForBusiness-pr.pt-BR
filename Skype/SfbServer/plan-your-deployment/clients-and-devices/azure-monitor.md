---
title: Planejar o gerenciamento de v2 Skype sala sistemas com Monitor do Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: Este artigo discute considerações de planejamento para usando o Monitor do Azure para administrar dispositivos de v2 de sistemas de sala do Skype no seu Skype para negócios ou equipes de implementação.
ms.openlocfilehash: 53f77f1353668e4887a6ff41efd040dc8f418c7e
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448426"
---
# <a name="plan-skype-room-systems-v2-management-with-azure-monitor"></a>Planejar o gerenciamento de v2 Skype sala sistemas com Monitor do Azure
 
 Este artigo discute considerações de planejamento para usando o Monitor do Azure para administrar dispositivos de v2 de sistemas de sala Skype no seu Skype para implementação da Business Server.
  
[Monitor do Windows Azure](https://docs.microsoft.com/azure/azure-monitor/overview) é um conjunto de serviços de gerenciamento que foram criados na nuvem desde o início. Em vez de implantação e gerenciamento de recursos no local, os componentes do Windows Azure Monitor inteiramente são hospedados no Windows Azure. Configuração é mínima, e você pode ser atualizado e sendo executado literalmente em questão de minutos. Com algum trabalho de personalização, ele também pode ajudar no gerenciamento de sistemas de conferência do Skype sala sistemas v2, fornecendo notificações em tempo real de integridade do sistema ou falhas para sistemas de sala individuais e potencialmente pode dimensione ao gerenciamento de milhares de sistemas de sala do Skype salas de conferência v2.
  
Este artigo oferece uma discussão sobre os requisitos, arquitetura do projeto e práticas recomendadas de implementação necessárias para implementar o gerenciamento de Monitor Azure com base de dispositivos de conferência do Skype sala sistemas v2 e fornece links para artigos detalhados sobre Implementando o Monitor do Windows Azure para sistemas de sala Skype v2 e informações de referência críticas para o monitoramento contínuo de salas de v2 Skype sistemas de sala. 
  
## <a name="functional-overview"></a>Visão geral funcional

![diagrama de gerenciamento SRS usando o Monitor do Azure](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
O aplicativo de v2 de sistemas de sala Skype no dispositivo console grava eventos seu registro de eventos do Windows. Um agente Microsoft Monitoring, uma vez instalado, passa as informações ao serviço de Monitor do Azure. 
  
Uma vez configurado corretamente, analisa de análise de Log a carga JSON incorporada no evento descrições para descrever como cada sistema v2 de sistemas de sala Skype está funcionando e quais falhas são detectadas. 
  
Um administrador usando o Monitor do Azure pode obter notificações dos sistemas de v2 Skype sala sistemas que estiverem offline ou está ocorrendo app, falhas de hardware ou conectividade bem como saber se um sistema precisa ser reiniciado. Cada status do sistema é atualizada com frequência, portanto essas notificações estiverem próximos atualizações em tempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Monitor Azure

Você deve ter uma assinatura válida de Azure para Monitor do Windows Azure usar o recurso de análise de Log. Veja Introdução a um espaço de trabalho de Log Analytics para criar uma assinatura para sua organização.
  
Você deve se familiarizar conforme o necessário sobre como usar o Designer de modo de exibição de análise de Log. Consulte [modos de exibição na análise de Log](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para obter os detalhes.
  
### <a name="related-tasks"></a>Tarefas relacionadas

1. Depois de inscritos na análise de Log do Windows Azure Monitor, crie personalizado campos (conforme descrito em [Mapear campos personalizados](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) necessário para analisar as informações que serão enviadas de consoles de v2 Skype sistemas de sala. Isso inclui Noções básicas sobre o esquema JSON documentado nos [entender as entradas de log](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).
    
2. Desenvolva um modo de exibição de gerenciamento do Skype sala sistemas v2 na análise de Log. Você pode a [criar um painel de v2 Skype sala sistemas usando o método de importação](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) ou [Crie um painel do Skype sala sistemas v2 manualmente](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Requisitos de Console do v2 Skype sala sistemas individuais

Cada console v2 de sistemas de sala Skype é um aplicativo de execução em um dispositivo Surface Pro no modo de quiosque (normalmente, ele é configurado para ser o único aplicativo que pode ser executado no dispositivo). Assim como acontece com qualquer aplicativo do Windows, o aplicativo do Skype sala sistemas v2 grava eventos, como falhas de hardware e de inicialização para o Log de eventos do Windows. A adição de um agente de Monitor da Microsoft no seu dispositivo de v2 Skype sala sistemas permite esses eventos a serem coletados. (Consulte Conectar computadores Windows ao serviço Log Analytics do Azure para obter mais detalhes.)
  
## <a name="ongoing-management"></a>Gerenciamento contínuo

Durante a utilização do Monitor do Windows Azure para gerenciar seus dispositivos de sistemas de sala Skype v2, você precisará compreender as informações contidas nos logs de eventos usados pelo Monitor do Azure. Consulte a [entender as entradas de log](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) para obter detalhes sobre essas mensagens de integridade.
  
### <a name="related-tasks"></a>Tarefas relacionadas

- Entender os alertas gerados pelo sistemas de sala Skype v2 e como resolvê-los a (consulte a seção intitulada [entender as entradas de log](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))
    
## <a name="see-also"></a>Consulte também

[Implantar o gerenciamento de v2 Skype sala sistemas com Monitor do Azure](../../deploy/deploy-clients/azure-monitor.md)
  
[Gerencia dispositivos de v2 de sistemas de sala Skype com Monitor do Azure](../../manage/skype-room-systems-v2/azure-monitor.md)