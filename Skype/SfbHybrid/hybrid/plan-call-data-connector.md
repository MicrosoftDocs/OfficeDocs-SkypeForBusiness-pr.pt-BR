---
title: Plano do Call data Connector | Análise híbrida de monitoramento de painel de qualidade de chamada
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso das ferramentas de telemetria do Skype for Business online para monitorar uma implementação local em um cenário híbrido.
ms.openlocfilehash: dc129ed99e1ed69e3faf5d2a7b6923f818c482eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160391"
---
# <a name="plan-call-data-connector"></a>Planejar o Call data Connector

## <a name="overview"></a>Visão geral

Este tópico descreve os benefícios, as considerações de planejamento e os requisitos para implementar o conector de dados de chamadas do Skype for Business Server. Para obter mais informações sobre a configuração do conector de dados de chamadas, consulte [Configure Call data Connector](configure-call-data-connector.md).

> [!NOTE]
> Na versão prévia pública, somente o painel de análise de chamada está disponível.

O Call data Connector simplifica bastante o monitoramento de chamadas em um ambiente híbrido, porque você não precisa mais usar conjuntos diferentes de ferramentas locais e online para monitorar toda a qualidade de chamada de seus usuários. Se seus usuários estão hospedados no local ou online, você pode optar por exibir a qualidade da chamada para toda a organização online.

Com o Call data Connector, você pode executar as seguintes tarefas usando um único conjunto de ferramentas:

- Monitore a experiência do usuário no Microsoft Teams, no Skype for Business Online e no Skype for Business Server.

- Exibir e solucionar problemas em sua rede.

- Atribuir funções de assistência técnica e de administrador para a análise de chamadas, para que você possa permitir que os profissionais de assistência técnica vejam e solucionem problemas de suas áreas de responsabilidade.

Com o Call data Connector, o Skype for Business Server envia dados de chamada para o serviço de nuvem, de modo que você possa aproveitar as ferramentas do Skype for Business online Call Analytics (CA) e do CQD (painel de qualidade da chamada), conforme mostrado no diagrama a seguir:

![Caixa postal em nuvem do SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

O servidor envia os dados de QoE (qualidade da experiência) e de registro de detalhes da chamada (CDR) para o serviço online.

As ferramentas de análise de chamada e CQD permitem monitorar a qualidade das chamadas e solucionar problemas de conexão com o Microsoft Teams e o Skype for Business Services da seguinte maneira:

- O Microsoft Call Analytics se concentra em problemas de qualidade com chamadas específicas. Ele mostra informações detalhadas sobre chamadas e reuniões para cada usuário em uma conta do Skype for Business.  Com o Call Analytics, você pode atribuir permissões a um operador de helpdesk, que poderá monitorar as chamadas sem ter acesso ao restante do centro de administração do Skype for Business.

- O painel de qualidade da chamada concentra-se no desempenho da rede e nos problemas de uma organização. Administradores e engenheiros de rede do Skype for Business Use essa ferramenta para solucionar problemas e otimizar o desempenho da rede.

Para obter mais informações, consulte [Call Analytics and call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Obviamente, você pode querer manter alguns dados de qualidade de chamada no local. Esse pode ser o caso, por exemplo, se você estiver usando uma solução de terceiros com relatórios e fluxos de trabalho personalizados.  O Call data Connector permite que você configure o envio de dados para o serviço online enquanto também mantém uma cópia dos dados no servidor local, conforme mostrado no diagrama a seguir:

![Caixa postal em nuvem do SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressupõem que você já tenha o Skype for Business Server implantado em uma topologia com suporte.  Para obter mais informações sobre a implantação do Skype for Business Server e topologias com suporte, consulte [Basics Topology](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Para configurar o Call data Connector, você deve:

- Habilitar a conectividade híbrida. Se você já tem o Skype for Business Server implantado e deseja habilitar o Call data Connector, você deve garantir que a conectividade híbrida seja configurada entre seus ambientes locais e online. Isso às vezes é chamado de configuração de domínio dividido.

   Para saber mais, confira [planejar conectividade híbrida entre o Skype for Business Server e o office 365](plan-hybrid-connectivity.md) e [Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365](configure-hybrid-connectivity.md).

- Autentique o seu locatário do Office 365 e assegure-se de ter as seguintes funções habilitadas:

  - Administrador do Skype for Business Server
  - Administrador global do Office 365

- Se você ainda não tiver feito isso, ative o painel de qualidade de chamada conforme descrito em [ativando e usando o painel de qualidade de chamada para o Microsoft Teams e o Skype for Business online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Habilite o pool de front-ends para monitoramento, com os bancos de dados do LCSCdr e QoEMetrics local. Sem isso, o Call data Connector não terá dados de métricas para trabalhar.

> [!IMPORTANT]
> Call data Connector não funcionará se o monitoramento não estiver habilitado no pool de front-ends.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparação de relatórios do painel de qualidade de chamada online e local (CQD)

| Relatórios de recursos | Skype for Business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de compartilhamento de aplicativos |Sim | Limite |
| Informações de construção do cliente| Sim | Sim |
| Análise de busca detalhada | Sim | Não |
| Métricas de confiabilidade de mídia | Sim | Limite |
| Relatórios prontos para uso | Sim | Sim |
| Relatórios de visão geral | Sim | Não |
| Relatórios por usuário | Sim | Sim |
| Personalização de conjunto de relatórios <br> (adicionar, excluir, modificar relatórios) | Sim | Sim |
| Métricas de compartilhamento de tela baseado em vídeo | Sim | Não |
| APIs de dados para acesso programático <br> para CQD | Não | Sim |
||||
