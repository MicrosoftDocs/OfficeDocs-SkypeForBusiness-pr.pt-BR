---
title: Planejar o gerenciamento de salas de equipes da Microsoft com o Monitor do Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: Este artigo discute considerações de planejamento para usando o Monitor do Azure para administrar dispositivos de salas de equipes da Microsoft no seu Skype para negócios ou equipes de implementação.
ms.openlocfilehash: dfa65435da63eb9783422e1e7ee10e66ba33b891
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214566"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planejar o gerenciamento de salas de equipes da Microsoft com o Monitor do Azure
 
 Este artigo discute considerações de planejamento para usando o Monitor de Windows Azure para administrar dispositivos de salas de equipes da Microsoft no seu Skype para a implementação do servidor de negócios.
  
[Monitor do Windows Azure](https://docs.microsoft.com/azure/azure-monitor/overview) é um conjunto de serviços de gerenciamento que foram criados na nuvem desde o início. Em vez de implantação e gerenciamento de recursos no local, os componentes do Windows Azure Monitor inteiramente são hospedados no Windows Azure. Configuração é mínima, e você pode ser atualizado e sendo executado literalmente em questão de minutos. Com algum trabalho de personalização, ele também pode ajudar no gerenciamento de sistemas de conferência de salas de equipes da Microsoft, fornecendo notificações em tempo real de integridade do sistema ou falhas para sistemas de sala individuais e potencialmente pode dimensione para gerenciamento de milhares de Teams da Microsoft Salas de conferência de salas.
  
Este artigo oferece uma discussão sobre os requisitos, arquitetura do projeto e práticas recomendadas de implementação necessárias para implementar o gerenciamento de Monitor Azure com base de dispositivos de conferência de salas de equipes da Microsoft e fornece links para artigos detalhados sobre Implementando o Monitor do Windows Azure para salas de equipes da Microsoft e informações de referência críticas para o monitoramento contínuo de salas de salas de equipes da Microsoft. 
  
## <a name="functional-overview"></a>Visão geral funcional

![diagrama de gerenciamento de salas de equipes da Microsoft usando o Monitor do Azure](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
O aplicativo Microsoft equipes salas no dispositivo console grava eventos seu registro de eventos do Windows. Um agente Microsoft Monitoring, uma vez instalado, passa as informações ao serviço de Monitor do Azure. 
  
Uma vez configurado corretamente, analisa de análise de Log a carga JSON incorporada no evento descrições para descrever como cada sistema salas de equipes da Microsoft está funcionando e quais falhas são detectadas. 
  
Um administrador usando o Monitor do Azure pode obter notificações de sistemas de salas de equipes da Microsoft que estão offline ou está ocorrendo app, conectividade ou falhas de hardware bem como saber se um sistema precisa ser reiniciado. Cada status do sistema é atualizada com frequência, portanto essas notificações estiverem próximos atualizações em tempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos de Monitor Azure

Você deve ter uma assinatura válida de Azure para Monitor do Windows Azure usar o recurso de análise de Log. Consulte a [Introdução com um espaço de trabalho de análise de Log](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para criar uma assinatura para sua organização.
  
Você deve se familiarizar conforme o necessário sobre como usar o Designer de modo de exibição de análise de Log. Consulte [modos de exibição na análise de Log](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para obter os detalhes.
  
### <a name="related-tasks"></a>Tarefas relacionadas

1. Depois de inscritos na análise de Log do Windows Azure Monitor, crie personalizado campos (conforme descrito em [Mapear campos personalizados](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) necessário para analisar as informações que serão enviadas de consoles de salas de equipes da Microsoft. Isso inclui Noções básicas sobre o esquema JSON documentado nos [entender as entradas de log](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).
    
2. Desenvolva um modo de exibição de gerenciamento de salas de equipes da Microsoft na análise de Log. Você pode [criar um painel de salas de equipes da Microsoft usando o método de importação](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) ou [criar um painel de salas de equipes da Microsoft manualmente](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos do Console de salas do Microsoft equipes individuais

Cada console de salas de equipes da Microsoft é um aplicativo de execução em um dispositivo Surface Pro no modo de quiosque (normalmente, ele é configurado para ser o único aplicativo que pode ser executado no dispositivo). Assim como acontece com qualquer aplicativo do Windows, o aplicativo Microsoft equipes salas grava eventos, como falhas de hardware e de inicialização para o Log de eventos do Windows. Adicionar um agente de Monitor da Microsoft no seu dispositivo de salas de equipes da Microsoft permite que esses eventos a serem coletados. (Consulte [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) para obter detalhes).
  
## <a name="ongoing-management"></a>Gerenciamento contínuo

Durante a utilização do Monitor do Windows Azure para gerenciar seus dispositivos de salas de equipes da Microsoft, você precisará compreender as informações contidas nos logs de eventos usados pelo Monitor do Azure. Consulte a [entender as entradas de log](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) para obter detalhes sobre essas mensagens de integridade.
  
### <a name="related-tasks"></a>Tarefas relacionadas

- Entender os alertas gerados pela Microsoft equipes salas e como resolvê-los a (consulte a seção intitulada [entender as entradas de log](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))
    
## <a name="see-also"></a>Confira também

[Implantar o gerenciamento de salas de equipes da Microsoft com o Monitor do Azure](../../deploy/deploy-clients/azure-monitor.md)
  
[Gerencia dispositivos de salas de equipes da Microsoft com Monitor do Azure](../../manage/skype-room-systems-v2/azure-monitor.md)