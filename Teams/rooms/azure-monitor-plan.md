---
title: Planejar o gerenciamento de Salas do Microsoft Teams com o Monitor do Azure
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: Este artigo aborda considerações de planejamento para usar o Monitor do Azure para administrar dispositivos de Salas do Microsoft Teams na implementação do Skype for Business ou do Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137601"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planejar o gerenciamento de Salas do Microsoft Teams com o Monitor do Azure
 
 Este artigo aborda considerações de planejamento para usar o Monitor do Azure para administrar dispositivos de Salas do Microsoft Teams em sua implementação do Microsoft Teams ou skype for Business.
  
[O Monitor do Azure](https://docs.microsoft.com/azure/azure-monitor/overview) é um conjunto de serviços de gerenciamento que foram projetados na nuvem desde o início. Em vez de implantar e gerenciar recursos locais, os componentes do Monitor do Azure são totalmente hospedados no Azure. A configuração é mínima e você pode estar funcionando literalmente em questão de minutos. Com algum trabalho de personalização, ele pode ajudar no gerenciamento de sistemas de conferência de Salas do Microsoft Teams, fornecendo notificações em tempo real sobre a saúde do sistema ou falhas para sistemas de salas individuais, e pode potencialmente ampliar o gerenciamento de milhares de salas de conferência do Microsoft Teams Rooms.
  
Este artigo fornece uma discussão sobre os requisitos, o design/arquitetura e as práticas recomendadas de implementação necessárias para implementar o gerenciamento baseado no Monitor do Azure de dispositivos de conferência do Microsoft Teams Rooms e fornece links para artigos detalhados sobre como implementar o Monitor do Azure para Salas do Microsoft Teams e informações de referência crítica para monitoramento contínuo de salas do Microsoft Teams. 
  
## <a name="functional-overview"></a>Visão geral funcional

![diagrama de gerenciamento de Salas do Microsoft Teams usando o Monitor do Azure](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
O aplicativo Salas do Microsoft Teams no dispositivo de console grava eventos em seu Log de Eventos do Windows. Um agente de Monitoramento da Microsoft, uma vez instalado, passa as informações para o serviço do Monitor do Azure. 
  
Uma vez configurado corretamente, o Log Analytics analisará a carga JSON inserida nas descrições do evento para descrever como cada sistema de Salas do Microsoft Teams está funcionando e quais falhas são detectadas. 
  
Um administrador que usa o Monitor do Azure pode receber notificações de sistemas de Salas do Microsoft Teams que estão offline ou que estão enfrentando falhas de aplicativo, conectividade ou hardware, além de saber se um sistema precisa ser reiniciado. Cada status do sistema é atualizado com frequência, portanto, essas notificações estão próximas às atualizações em tempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos do Monitor do Azure

Você deve ter uma assinatura válida do Azure para o Monitor do Azure para usar o recurso Análise de Log. Consulte [Começar a usar um espaço de trabalho do Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para criar uma assinatura para sua organização.
  
Você deve se familiarizar conforme necessário sobre como usar o Designer de Exibição de Análise de Log. Veja [os exibições na Análise de Log](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para obter esses detalhes.
  
### <a name="related-tasks"></a>Tarefas relacionadas

1. Uma vez inscrito na Análise de Log do Monitor do Azure, crie campos personalizados (conforme descrito nos campos personalizados do [Mapa)](azure-monitor-deploy.md#Custom_fields)necessários para analisar as informações que serão enviadas dos consoles de Salas do Microsoft Teams. Isso inclui entender o esquema JSON documentado em [Entender as entradas de log.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Desenvolva uma exibição de gerenciamento de Salas do Microsoft Teams no Log Analytics. Você pode criar [um painel de](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) Salas do Microsoft Teams usando o método de importação ou criar um painel de Salas do Microsoft Teams [manualmente.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos individuais do Console de Salas do Microsoft Teams

Cada console do Microsoft Teams Rooms é um aplicativo em execução em um dispositivo Surface Pro no modo quiosque (normalmente, ele está configurado para ser o único aplicativo que pode ser executado no dispositivo). Como acontece com qualquer aplicativo do Windows, o aplicativo Salas do Microsoft Teams grava eventos como falhas de inicialização e hardware no Log de Eventos do Windows. Adicionar um agente do Microsoft Monitor em seu dispositivo Microsoft Teams Rooms permite que esses eventos sejam coletados. (Consulte [Conectar computadores Windows ao serviço Análise de Log no Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) para obter detalhes.)
  
## <a name="ongoing-management"></a>Gerenciamento contínuo

Ao usar o Monitor do Azure para gerenciar seus dispositivos de Salas do Microsoft Teams, você precisará entender as informações contidas nos logs de eventos usados pelo Monitor do Azure. Consulte [Entender as entradas de log para](azure-monitor-manage.md#understand-the-log-entries) obter detalhes sobre essas mensagens de saúde.
  
### <a name="related-tasks"></a>Tarefas relacionadas

- Entenda os Alertas gerados pelas Salas do Microsoft Teams e como resolvê-los (consulte a seção intitulada Compreender as entradas [de log)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Confira também

[Implantar o gerenciamento de Salas do Microsoft Teams com o Monitor do Azure](azure-monitor-deploy.md)
  
[Gerenciar dispositivos de Salas do Microsoft Teams com o Monitor do Azure](azure-monitor-manage.md)