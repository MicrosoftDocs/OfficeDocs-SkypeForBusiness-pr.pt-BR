---
title: Planejar o conector de dados de chamada | Análise Híbrida de Monitoramento de Painel de Qualidade de Chamada
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Visão geral do uso Skype for Business de telemetria online para monitorar uma implementação local em um cenário híbrido.
ms.openlocfilehash: 2584453ca120c3dce9b4b0ce432e244cd15ec53b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013325"
---
# <a name="plan-call-data-connector"></a>Conector de Dados do Plano de Chamada

## <a name="overview"></a>Visão Geral

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este tópico descreve benefícios, considerações de planejamento e requisitos para implementar Skype for Business Server Conector de Dados de Chamada. Para obter mais informações sobre como configurar o Conector de Dados de Chamada, consulte [Configure Call Data Connector](configure-call-data-connector.md).


O Conector de Dados de Chamada simplifica muito o monitoramento de chamada em um ambiente híbrido porque você não precisa mais usar conjuntos diferentes de ferramentas locais e online para monitorar a qualidade de chamada de todos os usuários. Se seus usuários estão no local ou online, você pode optar por exibir a qualidade da chamada para toda a organização online.

Com o Conector de Dados de Chamada, você pode executar as seguintes tarefas usando um único toolset:

- Monitore sua experiência do usuário Microsoft Teams, Skype for Business Online e Skype for Business Server.

- Exibir e solucionar problemas em toda a sua rede.

- Atribua funções de assistente e administrador para Análise de Chamada, para que você possa capacitar os funcionários do helpdesk a exibir e solucionar problemas de suas áreas de responsabilidade.

Com o Conector de Dados de Chamada, o Skype for Business Server pressiona dados de chamada para o serviço de nuvem para que você possa aproveitar as ferramentas Skype for Business de Análise de Chamada Online (CA) e CQD (Call Quality Dashboard), conforme mostrado no diagrama a seguir:

![Diagrama de Caixa postal na Nuvem SfB.](../../sfbserver2019/media/call-data-connector-plan-1.png)

O servidor empurra dados de Qualidade de Experiência (QoE) e CdR (Registro de Detalhes de Chamada) para o serviço online.

As ferramentas de Análise de Chamadas e CQD permitem monitorar a qualidade das chamadas e solucionar problemas de conexão com Microsoft Teams e Skype for Business serviços da seguinte forma:

- A Análise de Chamadas se concentra em problemas de qualidade com chamadas específicas. Ele mostra informações detalhadas sobre chamadas e reuniões para cada usuário em uma Skype for Business de usuário.  Com o Call Analytics, você pode atribuir permissões a um operador auxiliar que pode monitorar chamadas sem ter acesso ao restante do centro de administração Skype for Business.

- O Painel de Qualidade de Chamada se concentra no desempenho da rede e em problemas em uma organização. Skype for Business administradores e engenheiros de rede usam essa ferramenta para solucionar problemas e otimizar o desempenho da rede.

Para obter mais informações, [consulte Microsoft Teams: Monitorar e melhorar a qualidade da chamada.](/monitor-call-quality-qos)

É claro que você pode querer manter alguns dados de qualidade de chamada no local. Esse pode ser o caso, por exemplo, se você estiver usando uma solução de terceiros com relatórios e fluxos de trabalho personalizados.  O Conector de Dados de Chamada permite configurar o envio de dados para o serviço online e também manter uma cópia dos dados em seu servidor local, conforme mostrado no diagrama a seguir:

![SfB Caixa postal na Nuvem.](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressuem que você já Skype for Business Server implantado em uma topologia com suporte.  Para obter mais informações sobre como implantar Skype for Business Server topologias com suporte, consulte [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md). Para configurar o Conector de Dados de Chamada, você deve:

- Habilitar conectividade híbrida. Se você já tiver Skype for Business Server e quiser habilitar o Conector de Dados de Chamada, certifique-se de ter a conectividade híbrida configurada entre seus ambientes locais e online. Às vezes, isso é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and Configure hybrid [connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Autenticar sua organização Microsoft 365 ou Office 365 e garantir que você tenha as seguintes funções habilitadas:

  - Skype for Business Server Administrador
  - Microsoft 365 ou Office 365 Administrador Global

- Se você ainda não tiver feito isso, a turn on Call Quality Dashboard conforme descrito em Ativar e usar o Painel de Qualidade de Chamada para Microsoft Teams e [Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Habilita o pool front-end para Monitoramento, com bancos de dados LCSCdr e QoEMetrics locais. Sem isso, o Conector de Dados de Chamada não terá dados de métricas para trabalhar.

> [!IMPORTANT]
> O Conector de Dados de Chamada não funcionará se o Monitoramento não estiver habilitado no pool front-end.

- Autenticação [de servidor para servidor configurada corretamente.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparação de relatórios do CQD (Painel de Qualidade de Chamada) local e online

| Relatórios de recursos | Skype for Business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de compartilhamento de aplicativos |Sim | Limited |
| Informações de criação do cliente| Sim | Sim |
| Análise de detalhamento | Sim | Não |
| Métricas de confiabilidade de mídia | Sim | Limited |
| Relatórios in-locar | Sim | Sim |
| Relatórios de visão geral | Sim | Não |
| Relatórios por usuário | Sim | Sim |
| Personalização do conjunto de relatórios <br> (adicionar, excluir, modificar relatórios) | Sim | Sim |
| Métricas de compartilhamento de tela baseada em vídeo | Sim | Não |
| APIs de dados para acesso programático <br> para CQD | Não | Sim |
||||
