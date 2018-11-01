---
title: Planejar o gerenciamento do Skype Room Systems versão 2 com o OMS
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: Este artigo discute considerações de planejamento para usando o pacote de gerenciamento de operações para administrar dispositivos de v2 de sistemas de sala Skype no seu Skype para implementação da Business Server.
ms.openlocfilehash: 26cfe0fa000a92548c81b8bab80d1bdde5ee78b4
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839354"
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>Planejar o gerenciamento do Skype Room Systems versão 2 com o OMS
 
 Este artigo discute considerações de planejamento para usando o pacote de gerenciamento de operações para administrar dispositivos de v2 de sistemas de sala Skype no seu Skype para implementação da Business Server.
  
[Pacote de gerenciamento de operações](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) (OMS) é uma coleção de serviços de gerenciamento que foram criados na nuvem desde o início. Em vez de implantação e gerenciamento de recursos no local, os componentes OMS inteiramente são hospedados no Windows Azure. Configuração é mínima, e você pode ser atualizado e sendo executado literalmente em questão de minutos. Com algum trabalho de personalização, ele também pode ajudar no gerenciamento de sistemas de conferência do Skype sala sistemas v2, fornecendo notificações em tempo real de integridade do sistema ou falhas para sistemas de sala individuais e potencialmente pode dimensione ao gerenciamento de milhares de sistemas de sala do Skype salas de conferência v2.
  
Este artigo oferece uma discussão sobre os requisitos, arquitetura do projeto e práticas recomendadas de implementação necessárias para implementar o gerenciamento de OMS dos dispositivos de conferência do Skype sala sistemas v2 e fornece links para artigos detalhados sobre a implementação OMS gerenciamento para sistemas de sala Skype v2 e informações de referência críticas para o gerenciamento contínuo de OMS de salas de v2 Skype sistemas de sala. 
  
## <a name="functional-overview"></a>Visão geral funcional

![Diagrama do gerenciamento SRS usando OMS](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
O aplicativo de v2 de sistemas de sala Skype no dispositivo console grava eventos seu registro de eventos do Windows. Um agente OMS, depois de instalado, envia as informações para o OMS. 
  
Uma vez configurado corretamente, analisa OMS a carga JSON incorporada no evento descrições para descrever como cada sistema v2 de sistemas de sala Skype está funcionando e quais falhas são detectadas. 
  
Um administrador usando OMS pode obter notificações dos sistemas de v2 Skype sala sistemas que estiverem offline ou está ocorrendo falhas de hardware, conectividade ou aplicativo bem como saber se um sistema precisa ser reiniciado. Cada status do sistema é atualizado a cada cinco minutos; portanto, essas notificações têm atualizações quase em tempo real.
  
## <a name="oms-requirements"></a>Requisitos do OMS

Você deve ter uma assinatura válida do OMS para usar esse recurso. Veja [Introdução a um espaço de trabalho de Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) para criar uma assinatura para sua organização.
  
Você deve se familiarizar, conforme o necessário, com o uso do Designer de Exibição do OMS. Veja [Modos de exibição nas soluções de gerenciamento do OMS (Operations Management Suite)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-solutions-resources-views) para obter esses detalhes.
  
### <a name="related-tasks"></a>Tarefas relacionadas

1. Depois de inscritos OMS, crie personalizado campos (conforme descrito em [Mapear campos personalizados](../../deploy/deploy-clients/with-oms.md#Custom_fields)) necessário para analisar as informações que serão enviadas de consoles de v2 Skype sistemas de sala. Isso inclui Noções básicas sobre o esquema JSON documentado nos [entender as entradas de log](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries).
    
2. Desenvolva um modo de exibição de gerenciamento do Skype sala sistemas v2 no OMS. Você pode a [criar um painel de v2 Skype sala sistemas usando o método de importação](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) ou [Crie um painel do Skype sala sistemas v2 manualmente](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Requisitos de Console do v2 Skype sala sistemas individuais

Cada console v2 de sistemas de sala Skype é um aplicativo de execução em um dispositivo de 4 de superfície no modo de quiosque (normalmente, ele é configurado para ser o único aplicativo que pode ser executado no dispositivo). Assim como acontece com qualquer aplicativo do Windows, o aplicativo do Skype sala sistemas v2 grava eventos, como falhas de hardware e de inicialização para o Log de eventos do Windows. Adicionar um operador OMS no seu dispositivo v2 de sistemas de sala Skype permite esses eventos serão coletadas pelo OMS. (Consulte [Conectar computadores Windows ao serviço Log Analytics do Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents) para obter mais detalhes.)
  
## <a name="ongoing-management"></a>Gerenciamento contínuo

Durante a utilização do OMS para gerenciar seus dispositivos de conferência do Skype sala sistemas v2, você precisará compreender as informações contidas nos logs de eventos usados pelo OMS. Consulte a [entender as entradas de log](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries) para obter detalhes sobre essas mensagens de integridade.
  
### <a name="related-tasks"></a>Tarefas relacionadas

- Entender os alertas gerados pelo sistemas de sala Skype v2 e como resolvê-los a (consulte a seção intitulada [entender as entradas de log](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries))
    
## <a name="see-also"></a>Consulte também

[Implantar o gerenciamento do Skype Room Systems v2 com OMS](../../deploy/deploy-clients/with-oms.md)
  
[Gerenciar dispositivos do Skype Room Systems v2 com o OMS](../../manage/skype-room-systems-v2/oms.md)