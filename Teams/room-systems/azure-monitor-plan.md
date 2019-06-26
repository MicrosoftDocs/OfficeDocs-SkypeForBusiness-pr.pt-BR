---
title: Planejar o gerenciamento de salas do Microsoft Teams com o Azure monitor
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: Este artigo discute considerações de planejamento para usar o Azure monitor para administrar dispositivos de salas do Microsoft Teams na implementação do Skype for Business ou do teams.
ms.openlocfilehash: 6536ee07ef64119d3529c7b9f279df3a7bbbdaed
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221383"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planejar o gerenciamento de salas do Microsoft Teams com o Azure monitor
 
 Este artigo aborda as considerações de planejamento para usar o monitor do Azure para administrar dispositivos de salas do Microsoft Teams em sua implementação do Microsoft Teams ou do Skype for Business.
  
O [Azure monitor](https://docs.microsoft.com/azure/azure-monitor/overview) é uma coleção de serviços de gerenciamento que foram projetados na nuvem desde o início. Em vez de implantar e gerenciar recursos no local, os componentes do monitor do Azure são totalmente hospedados no Azure. A configuração é mínima, e você pode estar em funcionamento literalmente em questão de minutos. Com algum trabalho de personalização, ele pode ajudar a gerenciar sistemas de conferência de salas do Microsoft Teams ao fornecer notificações em tempo real de integridade do sistema ou falhas para sistemas de sala individuais, e pode ser capaz de dimensionar para gerenciar milhares de Microsoft Teams Salas de conferência de salas.
  
Este artigo fornece uma discussão sobre os requisitos, o design/a arquitetura e as práticas recomendadas de implementação necessárias para implementar o gerenciamento do Azure monitor baseado em dispositivos de conferência de salas do Microsoft Teams e fornece links para artigos detalhados sobre implementação do Azure monitor para salas do Microsoft Teams e informações de referência críticas para o monitoramento contínuo de salas de salas do Microsoft Teams. 
  
## <a name="functional-overview"></a>Visão geral funcional

![diagrama do gerenciamento de salas do Microsoft Teams usando o Azure monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
O aplicativo salas do Microsoft Teams no dispositivo do console grava eventos em seu log de eventos do Windows. Um Microsoft Monitoring Agent, depois de instalado, passa as informações para o serviço do Azure monitor. 
  
Uma vez configurado corretamente, a análise de logs analisa a carga JSON inserida nas descrições do evento para descrever como cada sistema de salas do Microsoft Teams está funcionando e quais falhas foram detectadas. 
  
Um administrador que usa o Azure monitor pode obter notificações de sistemas de salas do Microsoft Teams que estão offline ou que estão experimentando aplicativos, conectividade ou falhas de hardware, além de saber se um sistema precisa ser reiniciado. Cada status do sistema é atualizado com frequência, portanto, essas notificações estão próximas às atualizações em tempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos do Azure monitor

Você deve ter uma assinatura válida do Azure para o Azure monitor para usar o recurso análise de logs. Consulte [introdução a um espaço de trabalho de análise de logs](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para criar uma assinatura para sua organização.
  
Você deve se familiarizar como necessário para usar o designer do modo de exibição de análise de logs. Veja os [modos de exibição na análise de logs](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) para esses detalhes.
  
### <a name="related-tasks"></a>Tarefas relacionadas

1. Depois de se inscrever na análise de log do Azure monitor, crie campos personalizados (conforme descrito nos [campos personalizados do mapa](azure-monitor-deploy.md#Custom_fields)) necessários para analisar as informações que serão enviadas dos consoles de salas do Microsoft Teams. Isso inclui noções básicas sobre o esquema JSON documentado em [entender as entradas do log](azure-monitor-manage.md#understand-the-log-entries).
    
2. Desenvolva um modo de exibição de gerenciamento de salas do Microsoft Teams em análises de logs. Você pode [criar um painel de salas do Microsoft Teams usando o método de importação](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) ou [criar um painel de salas do Microsoft Teams manualmente](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisitos do console de salas do Microsoft Teams individuais

Cada console de salas do Microsoft Teams é um aplicativo em execução em um dispositivo Surface pro no modo de quiosque (normalmente, ele é configurado para ser o único aplicativo que pode ser executado no dispositivo). Assim como em qualquer aplicativo do Windows, o aplicativo salas do Microsoft Teams grava eventos como inicialização e falhas de hardware no log de eventos do Windows. Adicionar um agente do Microsoft monitor ao dispositivo de salas do Microsoft Teams permite que esses eventos sejam coletados. (Consulte [conectar computadores Windows ao serviço analítico de logs no Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) para obter detalhes.)
  
## <a name="ongoing-management"></a>Gerenciamento contínuo

Ao usar o monitor do Azure para gerenciar seus dispositivos de salas do Microsoft Teams, você precisará compreender as informações contidas nos logs de eventos usados pelo Azure monitor. Consulte [compreender as entradas do log](azure-monitor-manage.md#understand-the-log-entries) para obter detalhes sobre essas mensagens de integridade.
  
### <a name="related-tasks"></a>Tarefas relacionadas

- Entender os alertas gerados pelos salas do Microsoft Teams e como resolvê-los (consulte a seção intitulada [entender as entradas do log](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Confira também

[Implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md)
  
[Gerenciar dispositivos de salas do Microsoft Teams com o Azure monitor](azure-monitor-manage.md)