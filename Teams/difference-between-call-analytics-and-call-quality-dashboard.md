---
title: Análise de Chamada e Painel de Qualidade de Chamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Saiba mais sobre a análise de chamadas e o painel de qualidade de chamada e quando usá-los para monitorar e solucionar problemas de qualidade da chamada.
ms.openlocfilehash: be63c4e227e74e242169ec5c3b5e0b01a43a0730
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824900"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Análise de Chamada e Painel de Qualidade de Chamadas

O Microsoft Teams e o Skype for Business dão a você duas maneiras de monitorar e solucionar problemas de qualidade de chamada: painel de análise de chamadas e de qualidade de chamada (CQD). Este artigo descreve ambos e informa quando usar cada um deles.

A análise de chamadas e o CQD são executados em paralelo e podem ser usados de forma independente ou em conjunto. Por exemplo, digamos que um especialista de suporte de comunicações determine que precisa de mais ajuda para solucionar um problema com a chamada. O especialista de suporte de comunicações passa a chamada para um engenheiro de suporte a comunicações, que tem acesso a mais informações em análises de chamadas do que o especialista de suporte de comunicações. Por sua vez, o engenheiro de suporte de comunicações pode alertar um engenheiro de rede a um problema. O engenheiro de rede pode verificar o CQD para ver se um problema geral relacionado ao site pode ser uma causa contribuinte de problemas com chamadas.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>O que é a análise de chamadas e quando devo usá-la?

**O recurso de análise de chamadas agora está disponível no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com).** Para ver todas as informações de chamada e dados de um usuário, use a guia **histórico de chamadas** na página de perfil de um usuário. Para ver a guia, procure pelo usuário no painel ou encontre o usuário na guia **usuários** na barra de navegação à esquerda.

A análise de chamadas mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados às chamadas e reuniões para cada usuário em uma conta do Microsoft Teams ou do locatário do Skype for Business. Por que este usuário fez uma chamada ruim para esta tarde? Com o recurso de análise de chamadas, um administrador do Office 365 ou um agente de helpdesk treinado pode investigar o dispositivo, a rede, a conectividade e outros fatores relacionados a uma chamada para solucionar problemas de qualidade de chamada e conexão no Microsoft Teams e no Skype for Business.

Para ver essas informações para um usuário no centro de administração do Microsoft Teams, clique na guia **histórico de chamadas** desse usuário na página de detalhes do usuário para ver todas as chamadas e reuniões desse usuário nos últimos 30 dias.

![Captura de tela de todos os dados do usuário da análise.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obter informações adicionais sobre uma determinada sessão, incluindo estatísticas detalhadas de mídia e de rede, clique em uma sessão para ver os detalhes.

![Captura de tela dos dados da sessão do usuário da análise de chamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Se você quiser que não administradores (como agentes da assistência técnica de um fornecedor externo) usem a análise de chamadas, poderá atribuir permissões para que eles possam usar a análise de chamadas, mas não poderão acessar o restante do centro de administração do Microsoft Teams:
  
- **Agentes da assistência técnica com permissões de suporte de suporte a comunicações**: os agentes vêem um conjunto limitado de dados e informações de identificação pessoal (PII) na análise de chamadas. Elas podem solucionar problemas, mas aumentam os problemas com reuniões para um engenheiro de suporte de comunicações.
- **Agentes da assistência técnica com permissões de engenheiro de suporte a comunicações**: os agentes vêem todos os dados disponíveis no Analytics e solucionam problemas em chamadas e reuniões. Eles têm acesso completo a logs de chamadas e informações do cliente.

> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente à função de suporte de nível 1 do portal de visualização e a função de engenheiro de suporte de comunicações é equivalente à função de suporte de camada 2 do portal de visualização.

Para obter mais informações sobre as funções do especialista de suporte de comunicações e do engenheiro de suporte de comunicações, consulte [usar funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md).

> [!IMPORTANT]
> Permissões de agente de helpdesk e carregamento de topologia de rede estão disponíveis no centro de administração do Microsoft Teams. Especialistas de suporte de comunicações e engenheiros de suporte de comunicação podem usar esse portal para acessar o recurso de análise de chamadas e o painel de qualidade da chamada.

Para obter detalhes sobre a análise de chamadas, consulte [Configurar o Skype for Business Call Analytics](set-up-call-analytics.md). Para obter mais informações sobre como os agentes da assistência técnica podem trabalhar com a análise de chamadas, consulte [usar a análise de chamadas para solucionar problemas de qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>O que é o painel de qualidade da chamada e quando devo usá-lo?
  
O recurso de análise de chamadas foi projetado para ajudar os agentes administradores e helpdesks a solucionar problemas de qualidade de chamada com *chamadas específicas*. O painel de qualidade de chamada (CQD) foi projetado para ajudar administradores de equipe, administradores do Skype for Business e engenheiros de rede *a otimizar uma rede*. CQD muda o foco de usuários específicos e, em vez disso, examina as informações de agregação de uma ou mais organizações do Skype for Business. Para obter mais informações, consulte [recursos do painel de qualidade de chamada para o Teams e o Skype for Business online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Suponha que a qualidade de chamadas deficientes de um usuário seja devida a um problema de rede que também afete muitos outros usuários. A experiência de chamada individual não está visível no CQD, mas a qualidade geral das chamadas feitas usando o Microsoft Teams ou o Skype for Business é capturada. Com o CQD, os padrões gerais podem se tornar aparentes, para que os engenheiros de rede possam fazer avaliações informadas de qualidade das chamadas. O CQD fornece relatórios de métricas de qualidade de chamada que proporcionam a você uma visão geral da qualidade da chamada, do servidor-fluxo de cliente, do cliente-fluxo de cliente e do [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualidade de voz.
  
![Captura de tela do painel de qualidade da chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

A localização da CQD-relatórios avançados agregam qualidade de chamada e confiabilidade no prédio de um usuário. Os dados podem ser avaliados para determinar se o problema está isolado a um único usuário ou afeta um segmento maior de usuários.

![Captura de tela dos relatórios de localização avançada do painel de qualidade da chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> Para habilitar os modos de exibição específicos de construção ou ponto de extremidade no CQD, um administrador deve [carregar informações de construção ou de ponto de extremidade](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) na página de carregamento de dados de locatário do CQD.

Se você quiser que os usuários que não são administradores (como agentes da assistência técnica) usem o painel de qualidade da chamada, você pode atribuir a esses usuários uma das funções a seguir, que também têm permissões necessárias para acessar o painel de qualidade da chamada:

- Administrador global
- Leitor global
- Administrador do Skype for Business
- Administrador de Serviço de Equipes
- Administrador de Comunicações de Equipes
- Engenheiro de Suporte de Comunicações de Equipes
- Especialista em suporte do teams Communications
- Leitor de relatórios

> [!NOTE]
> O engenheiro de suporte de comunicações do Teams, o especialista em regras do teams support e as funções de leitor de relatórios não podem modificar arquivos na página de carregamento de dados de locatários do CQD, nem ativar o CQD para

Para obter mais informações sobre essas funções, consulte [sobre as funções de administrador do Office 365](/office365/admin/add-users/about-admin-roles).

Para obter mais informações sobre o CQD, consulte [ativando e usando o painel de qualidade de chamada para Microsoft Teams e Skype for Business online](turning-on-and-using-call-quality-dashboard.md) e [dimensões e medidas disponíveis no painel de qualidade de chamada do Microsoft Teams e do Skype for Business online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Vídeo: visão geral da qualidade da chamada](https://aka.ms/teams-quality)

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Ativar e usar o painel de qualidade da chamada para Microsoft Teams e Skype for Business Online](turning-on-and-using-call-quality-dashboard.md)
