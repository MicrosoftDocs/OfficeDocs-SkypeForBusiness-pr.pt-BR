---
title: Planejar o conector de dados de chamada | Análise híbrida do Monitoramento do Painel de Qualidade de Chamada
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso das ferramentas de telemetria do Skype for Business Online para monitorar uma implementação local em um cenário híbrido.
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221311"
---
# <a name="plan-call-data-connector"></a>Conector de Dados do Plano de Chamada

## <a name="overview"></a>Visão geral

Este tópico descreve os benefícios, considerações de planejamento e requisitos para implementar o Conector de Dados de Chamada do Skype for Business Server. Para obter mais informações sobre como configurar o Conector de Dados de Chamada, consulte [Configurar o Conector de Dados de Chamada.](configure-call-data-connector.md)


O Conector de Dados de Chamada simplifica bastante o monitoramento de chamada em um ambiente híbrido porque você não precisa mais usar conjuntos diferentes de ferramentas locais e online para monitorar a qualidade de chamada de todos os usuários. Se seus usuários estão locais ou online, você pode optar por exibir a qualidade da chamada para toda a sua organização online.

Com o Conector de Dados de Chamada, você pode executar as seguintes tarefas usando um único toolset:

- Monitore sua experiência do usuário no Microsoft Teams, Skype for Business Online e Skype for Business Server.

- Exibir e solucionar problemas em sua rede.

- Atribua funções de administrador e de helpdesk para a Análise de Chamada, para que você possa capacitar os funcionários de helpdesk a exibir e solucionar problemas em suas áreas de responsabilidade.

Com o Conector de Dados de Chamada, o Skype for Business Server faz push de dados de chamadas para o serviço de nuvem para que você possa aproveitar as ferramentas de Análise de Chamadas (CA) e Painel de Qualidade de Chamadas (CQD), conforme mostrado no diagrama a seguir:

![Caixa postal na nuvem do SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

O servidor pushs both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.

As ferramentas Análise de Chamadas e CQD permitem monitorar a qualidade das chamadas e solucionar problemas de conexão com o Microsoft Teams e os serviços do Skype for Business da seguinte forma:

- A Análise de Chamadas concentra-se em problemas de qualidade com chamadas específicas. Ele mostra informações detalhadas sobre chamadas e reuniões para cada usuário em uma conta do Skype for Business.  Com a Análise de Chamadas, você pode atribuir permissões a um operador de helpdesk que pode monitorar chamadas sem ter acesso ao restante do Centro de administração do Skype for Business.

- O Painel de Qualidade da Chamada se concentra no desempenho da rede e nos problemas em uma organização. Os administradores do Skype for Business e os engenheiros de rede usam essa ferramenta para solucionar problemas e otimizar o desempenho da rede.

Para obter mais informações, consulte [Análise de Chamada e Painel de Qualidade de Chamada.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

Obviamente, você pode querer manter alguns dados de qualidade de chamada no local. Esse pode ser o caso, por exemplo, se você estiver usando uma solução de terceiros com fluxos de trabalho e relatórios personalizados.  O Conector de Dados de Chamada permite configurar o envio de dados para o serviço online, mantendo também uma cópia dos dados em seu servidor local, conforme mostrado no diagrama a seguir:

![Caixa postal na nuvem do SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir presumem que você já tenha implantado o Skype for Business Server em uma topologia com suporte.  Para obter mais informações sobre como implantar o Skype for Business Server e topologias com suporte, consulte [Noções básicas de topologia.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics) Para configurar o Conector de Dados de Chamada, você deve:

- Habilitar conectividade híbrida. Se você já implantou o Skype for Business Server e deseja habilitar o Conector de Dados de Chamada, você deve garantir a configuração da conectividade híbrida entre seus ambientes locais e online. Isso algumas vezes é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) e configurar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)

- Autenti-se em sua organização do Microsoft 365 ou Office 365 e verifique se você tem as seguintes funções habilitadas:

  - Administrador do Skype for Business Server
  - Administrador Global do Microsoft 365 ou Office 365

- Se você ainda não tiver feito isso, a ligue o Painel de Qualidade da Chamada conforme descrito em Ativar e usar o Painel de Qualidade da Chamada para o Microsoft Teams e [o Skype for Business Online.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Habilita o pool de front-end para Monitoramento, com bancos de dados LCSCdr e QoEMetrics locais. Sem isso, o Conector de Dados de Chamada não terá dados de métricas com os qual trabalhar.

> [!IMPORTANT]
> O Conector de Dados de Chamada não funcionará se o Monitoramento não estiver habilitado no pool de front-end.

- Autenticação [de servidor para servidor configurada corretamente.](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparação de relatórios do Painel de Qualidade de Chamada (CQD) local e online

| Relatórios de recursos | Skype for Business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de compartilhamento de aplicativos |Sim | Limitado |
| Informações de criação do cliente| Sim | Sim |
| Análise de análise de análise | Sim | Não |
| Métricas de confiabilidade de mídia | Sim | Limitado |
| Relatórios of-the-box | Sim | Sim |
| Relatórios de visão geral | Sim | Não |
| Relatórios por usuário | Sim | Sim |
| Personalização do conjunto de relatórios <br> (adicionar, excluir, modificar relatórios) | Sim | Sim |
| Métricas de compartilhamento de tela baseado em vídeo | Sim | Não |
| APIs de dados para acesso programático <br> para CQD | Não | Sim |
||||
