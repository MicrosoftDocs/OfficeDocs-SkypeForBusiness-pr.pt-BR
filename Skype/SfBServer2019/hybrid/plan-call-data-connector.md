---
title: Planejar o conector de dados chamada | Chamar o painel de controle de qualidade Monitoring análise híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso Skype para as ferramentas de telemetria Business Online para monitorar uma implementação local em um cenário híbrido.
ms.openlocfilehash: 4e38f7d190cd30c1f0e39dc4cdfa5166ba6a929d
ms.sourcegitcommit: 183a2e40af762e6ab36f05ee8ed31a98e8b8be57
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2019
ms.locfileid: "29690442"
---
# <a name="plan-call-data-connector"></a>Planejar o conector de dados de chamada

## <a name="overview"></a>Visão geral

Este tópico descreve os benefícios, considerações sobre planejamento e requisitos para implementar o Skype para Business Server chamada dados Connector. Para obter mais informações sobre como configurar o conector de dados da chamada, consulte [Configurar o conector de dados da chamada](configure-call-data-connector.md).

> [!NOTE]
> Nesta versão de demonstração pública, painel de análise de chamadas somente está disponível.

Conector de dados chamada simplifica bastante chamada monitoramento em um ambiente híbrido porque não precisar mais usar diferentes conjuntos de locais e ferramentas online para monitorar a qualidade da chamada seus usuários. Se os usuários estão hospedados no local ou online, você pode optar por exibir a qualidade da chamada de toda sua organização online.

Com o conector de dados de chamada, você pode executar as seguintes tarefas usando um único conjunto de ferramentas:

- Monitore sua experiência do usuário em produtos Microsoft Teams, Skype para Business Online e Skype para Business Server.

- Visualizar e solucionar problemas em sua rede.

- Atribua funções de administrador e assistência técnica para a análise de chamada, para que você pode capacitar os trabalhadores de assistência técnica para visualizar e solucionar problemas de suas áreas de responsabilidade.

Com o conector de dados de chamadas, o Skype para Business Server envia dados de chamada ao serviço de nuvem para que você pode aproveitar o Skype para ferramentas de análise de chamada Online corporativos (CA) e o painel de controle de qualidade de chamada (CQD), conforme mostrado no diagrama a seguir:

![Caixa postal de nuvem SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

O servidor encaminha o Quality of Experience (QoE) e a gravação de detalhes das chamadas (CDR) de dados para o serviço online.

As ferramentas CQD e uma análise de chamada permitem que você monitorar a qualidade das chamadas e solucionar problemas de conexão com o Microsoft Teams e Skype para serviços corporativos da seguinte maneira:

- Chama enfatiza a análise em problemas de qualidade com chamadas específicos. Ela mostra informações detalhadas sobre chamadas e reuniões para cada usuário em um Skype para a conta de negócios.  Com a análise de chamada, você pode atribuir permissões para um operador de assistência técnica, que pode monitorar chamadas sem ter acesso ao restante do Skype para Business Admin center.

- Painel de controle de qualidade de chamada se concentra no desempenho da rede e questões em toda a organização. Skype para administradores de negócios e os engenheiros de rede usar essa ferramenta para solucionar problemas e otimizar o desempenho da rede.

Para obter mais informações, consulte [análise de chamada e o painel de controle de qualidade de chamada](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Obviamente, você talvez queira manter alguns dados de qualidade de chamada no local. Isso pode ser o caso, por exemplo, se você estiver usando uma solução de terceiros com fluxos de trabalho e relatórios personalizados.  Conector de dados de chamada permite que você configure o envio de dados para o serviço online enquanto mantém também uma cópia dos dados no servidor local, conforme mostrado no diagrama a seguir:

![Caixa postal de nuvem SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressupõem que você já tem Skype para Business Server implantado em uma topologia com suporte.  Para obter mais informações sobre como implantar o Skype para Business Server e topologias com suporte, consulte [Noções básicas de topologia](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Para configurar o conector de dados da chamada, você deve:

- Habilite conectividade híbrida. Se você já tiver Skype para Business Server implantado e você deseja habilitar o conector de dados de chamadas, certifique-se de que você tem conectividade híbrida configurada entre seu local e ambientes on-line. Às vezes, isso é chamado uma configuração de domínio dividido.

   Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](plan-hybrid-connectivity.md) e a [Configurar a conectividade de híbrido entre Skype para Business Server e Office 365](configure-hybrid-connectivity.md).

- Autenticar seu locatário do Office 365 e verifique se você tem as seguintes funções habilitadas:

  - Skype para o administrador de servidor de negócios
  - Administrador Global do Office 365

- Se ainda não tiver feito isso, ative o painel de controle de qualidade de chamada conforme descrito em [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para negócios Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Habilite o pool de front-end para monitoramento, com bancos de dados LcsCDR e QoEMetrics locais. Sem isso, chame o conector de dados não terá dados de métricas para trabalhar.

> [!IMPORTANT]
> Conector de dados de chamada não funcionará se monitoramento não estiver habilitado no pool de front-end.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Relatórios de comparação dos locais e online painel de controle de qualidade de chamada (CQD)

| Relatórios de recurso | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de compartilhamento de aplicativo |Sim | Limitado |
| Informações de construção do cliente| Sim  | Sim  |
| Análise de detalhamento | Sim | Não |
| Métricas de confiabilidade de mídia | Sim | Limitado |
| Relatórios de caixa | Sim  | Sim  |
| Visão geral de relatórios | Sim | Não |
| Por relatórios do usuário | Sim  | Sim  |
| Personalização de conjunto de relatórios <br> (Adicionar, excluir, modificar relatórios) | Sim  | Sim  |
| Métricas de compartilhamento de tela com base em vídeo | Sim | Não |
| APIs de dados para acesso programático <br> para CQD | Não | Sim |
||||
