---
title: Planejar Salas do Microsoft Teams monitoramento com o Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Este artigo aborda as considerações de planejamento para usar o Azure Monitor para monitorar Salas do Microsoft Teams em sua implementação Skype for Business ou teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5640fd63ac413403105be7d5f23e413b2f19ebdf
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606390"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planejar Salas do Microsoft Teams monitoramento com o Azure Monitor
 
 Este artigo aborda as considerações de planejamento para usar o Azure Monitor para administrar Salas do Microsoft Teams dispositivos em seu Microsoft Teams ou Skype for Business implementação.

> [!NOTE]
> Você também pode [configurar o monitoramento de integridade de Salas do Teams](../alerts/device-health-status.md) o Centro de administração do Teams.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

[O Azure Monitor](/azure/azure-monitor/overview) é uma coleção de serviços de monitoramento que foram projetados na nuvem desde o início. Em vez de implantar e gerenciar recursos locais, os componentes do Azure Monitor são totalmente hospedados no Azure. A configuração é mínima e você pode estar em funcionamento em questão de minutos. Com algum trabalho de personalização, ele pode ajudar no monitoramento do Salas do Microsoft Teams fornecendo notificações de integridade ou falhas do sistema para sistemas de sala individuais e pode escalar verticalmente para gerenciar milhares de Salas do Microsoft Teams.
  
Este artigo fornece uma discussão sobre os requisitos, o design/arquitetura e as práticas recomendadas de implementação necessárias para implementar o monitoramento baseado no Azure Monitor Salas do Microsoft Teams. Ele também fornece links para artigos detalhados sobre como implementar o Azure Monitor para Salas do Microsoft Teams e informações de referência críticas para o monitoramento contínuo de Salas do Microsoft Teams salas.
  
## <a name="functional-overview"></a>Visão geral funcional

![diagrama de Salas do Microsoft Teams gerenciamento usando o Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
O Salas do Microsoft Teams grava eventos no Log de Eventos do Windows. Um agente de Monitoramento da Microsoft, uma vez instalado, passa as informações para o serviço do Azure Monitor.
  
Depois de configurado corretamente, o Log Analytics analisa o conteúdo JSON inserido nas descrições do evento para descrever como o Salas do Microsoft Teams está funcionando e quais falhas são detectadas.
  
Um administrador que usa o Azure Monitor pode receber notificações de Salas do Microsoft Teams que estão offline ou estão enfrentando falhas de aplicativo, conectividade ou hardware, bem como saber se um sistema precisa ser reiniciado. Cada status do sistema é atualizado com frequência, portanto, essas notificações estão próximas das atualizações em tempo real.
  
## <a name="azure-monitor-requirements"></a>Requisitos do Azure Monitor

Você deve ter uma assinatura válida do Azure para o Azure Monitor para usar os recursos do Log Analytics. Consulte [Introdução a um workspace do Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) para criar uma assinatura para sua organização.
  
Você deve se familiarizar sobre como usar o Designer de Exibição do Log Analytics. Consulte [exibições no Log Analytics](/azure/azure-monitor/platform/view-designer) para obter esses detalhes.
  
### <a name="related-tasks"></a>Tarefas relacionadas

1. Depois de assinar o Log Analytics do Azure Monitor, crie campos personalizados (conforme descrito nos campos personalizados do [Mapa)](azure-monitor-deploy.md#Custom_fields) necessários para analisar as informações que serão enviadas do Salas do Microsoft Teams. Isso inclui entender o esquema JSON documentado em [Noções básicas sobre as entradas de log](azure-monitor-manage.md#understand-the-log-entries).
    
2. Desenvolva uma exibição Salas do Microsoft Teams de gerenciamento no Log Analytics. Você pode [criar um painel Salas do Microsoft Teams manualmente](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Requisitos Salas do Microsoft Teams individuais

Salas do Microsoft Teams é um aplicativo em execução em um dispositivo de computação no modo de quiosque. Assim como ocorre com qualquer aplicativo do Windows, o Salas do Microsoft Teams grava eventos como falhas de inicialização e hardware no Log de Eventos do Windows. Adicionar um agente do Microsoft Monitor Salas do Microsoft Teams permite que esses eventos sejam coletados. (Consulte [Conectar computadores Windows ao serviço Log Analytics no Azure](/azure/azure-monitor/platform/agent-windows) para obter detalhes.)
  
## <a name="ongoing-management"></a>Gerenciamento contínuo

Ao usar o Azure Monitor para monitorar seu Salas do Microsoft Teams, você precisará entender as informações contidas nos logs de eventos usados pelo Azure Monitor. Consulte [Entender as entradas de log para](azure-monitor-manage.md#understand-the-log-entries) obter detalhes sobre essas mensagens de integridade.
  
### <a name="related-tasks"></a>Tarefas relacionadas

- Entenda os Alertas gerados por Salas do Microsoft Teams e como resolvê-los (consulte a seção intitulitada [Entender as entradas de log](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Confira também

[Implantar Salas do Microsoft Teams gerenciamento com o Azure Monitor](azure-monitor-deploy.md)
  
[Gerenciar Salas do Microsoft Teams com o Azure Monitor](azure-monitor-manage.md)
