---
title: Análise de chamada e o painel de controle de qualidade de chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Saiba mais sobre a análise de chamada e painel de controle de qualidade de chamada e quando usá-los para monitorar e solucionar problemas de qualidade da chamada.
ms.openlocfilehash: b4c009d356453b11ecf4af70380491f69f843188
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754631"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Análise de chamada e o painel de controle de qualidade de chamada

Skype para negócios e o Teams da Microsoft oferecem duas maneiras para monitorar e solucionar problemas de qualidade da chamada: análise de chamada e o painel de controle de qualidade de chamada. Este artigo descreve os dois e informa quando usar cada uma delas.
  
**Análise de chamada está disponível no Centro de administração do Microsoft Teams.** Para ver todas as informações de chamada e os dados de um usuário, use a guia de **Histórico de chamadas** . Você pode fazer isso por procurando na página de perfil do usuário, qualquer procurando por usuário do painel ou localizar o usuário dos **usuários** no painel de navegação à esquerda.

> [!IMPORTANT]
> Permissões de operador de assistência técnica e carregamento de topologia de rede estará disponíveis no portal de administração do novo nos próximos meses. Enquanto isso, você pode continuar a usar https://adminportal.services.skypeforbusiness.com para acesso de assistência técnica de camada 1 e a camada 2.
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>O que é chamada de análise e quando devo usá-lo?

Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados à chamadas específicas e reuniões para cada usuário em um Microsoft Teams ou Skype para a conta de negócios. Se você for um administrador do Office 365, você pode usar a chamada análise para solucionar problemas de qualidade e conexão de chamada no Microsoft Teams e Skype para negócios.

Para ver essas informações para um usuário no Centro de administração do Microsoft Teams, clique na guia **Histórico de chamadas** para esse usuário na página de detalhes do usuário, mostrando todas as chamadas e reuniões que o usuário tem participou nos últimos 30 dias.

![Chame a análise de dados do usuário.](media/call-analytics-user-data.png)

Para obter informações adicionais sobre uma determinada sessão, incluindo mídia detalhadas e estatísticas de rede, clique em uma sessão para ver os detalhes.

![Chame a análise de dados da sessão de usuário.](media/call-analytics-user-data-session.png)

Se desejar que não-administradores, como operadores de assistência técnica de um fornecedor externo, para usar a análise de chamada, você pode atribuir permissões para que eles podem usar a análise de chamada, mas não podem acessar o resto do Centro de administração do Microsoft Teams: 
  
- **Operadores de assistência técnica com a comunicação oferece suporte a permissões de specialist**: agentes vejam um conjunto limitado de dados e informações de identificação pessoal (PII) na análise de chamada. Solucionam chamadas, mas eles serão entregar problemas com reuniões com um engenheiro de suporte de comunicações.
    
- **Operadores de assistência técnica com a comunicação oferece suporte a permissões de engenharia**: agentes ver todos os dados disponíveis na análise de chamada e solucionar problemas de chamadas e reuniões. Eles têm acesso completo ao chamar os logs e informações do cliente.

> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente ao suporte da camada 1 e a função de engenheiro de suporte de comunicações é equivalente ao suporte da camada 2.

Para obter mais informações sobre as comunicações especialista de suporte e comunicações funções engenheiro de suporte, consulte o [equipes da Microsoft que usar funções de administrador para gerenciar equipes](using-admin-roles.md).

> [!IMPORTANT]
> Permissões de operador de assistência técnica e carregamento de topologia de rede estão disponíveis no Centro de administração do Microsoft Teams. Especialistas de suporte de comunicações e comunicações engenheiros de suporte podem usar este portal para acessar a análise de chamada e o painel de controle de qualidade de chamada.
    
Para obter detalhes sobre como configurar a análise de chamada, consulte [Configurar Skype para análise de chamada de negócios](set-up-call-analytics.md). Para obter mais informações sobre como os operadores de assistência técnica podem trabalhar com a análise de chamada, consulte [Análise de uso chamada solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Qual é o painel de controle de qualidade de chamada, e quando devo usá-lo?

Análise de chamada oferece informações detalhadas específicas sobre a qualidade da chamada experimentada pelos usuários. Por que o usuário Tony Smith tinha uma chamada de baixa tarde? Usando a análise de chamada, um Microsoft Teams ou Skype para administração de negócios ou do agente de assistência técnica treinados possa investigar o dispositivo, rede, conectividade e outros fatores relacionados a chamada de Tony.
  
Onde a autoridade de certificação foi projetada para ajudar os administradores e operadores de assistência técnica a solucionar problemas de qualidade de chamada com chamadas específicos, o painel de qualidade de chamada (CQD) foi projetado para ajudar Skype para os administradores de negócios e otimizam a uma rede engenheiros de rede. CQD alterna o foco de usuários específicos e em vez disso, analisa agregam informações para um inteiro Skype para organização de negócios. 
  
Talvez a qualidade de chamadas ruins de Tony é devido a um problema de rede que também está afetando a muitos outros usuários. Experiência de chamada individual de Tony não está visível no CQD, mas a qualidade geral de chamadas realizadas usando Skype para negócios é capturada. Com o CQD, geral padrões podem ficar aparentes, permitindo que os engenheiros de rede tornar informadas avaliações de qualidade de chamada. CQD fornece relatórios de métricas de qualidade de chamada que lhe dão ideias sobre chamam geral qualidade, fluxos de cliente e servidor-cliente e [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualidade de voz. 
  
![Captura de tela do painel de qualidade de chamada no Skype para Business Admin Center. Guias mostradas são qualidade geral da chamada, o servidor - cliente, cliente - cliente e SLA de qualidade de modo de exibição.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Para obter mais detalhes, consulte [recursos do painel de qualidade de chamada do Skype para negócios Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Análise de chamada e CQD executem em paralelo e podem ser usado independentemente ou em conjunto. Por exemplo, diga uma especialista em suporte determina que precisa de mais ajuda solucionar um problema de chamada de comunicações. Especialista de suporte a comunicações passa a chamada para um engenheiro de suporte de comunicações, quem tem acesso mais informações na análise de chamada do que as comunicações especialista de suporte. Por sua vez, o engenheiro de suporte de comunicações alertando engenheiro de rede para um problema. O engenheiro de rede poderia verificar CQD para ver se um problema geral de sites relacionados poderia ser uma Colaborador causa de problemas de chamada.
  
Para obter mais informações sobre CQD, consulte [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para Business Online](turning-on-and-using-call-quality-dashboard.md) e [dimensões e medidas disponíveis no painel de qualidade de chamada para equipes da Microsoft e Skype para negócios Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Vídeo: Visão geral de qualidade de chamada](https://aka.ms/teams-quality)

[Configurar a análise de chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Ativando e usando o painel de controle de qualidade de chamada para Teams da Microsoft e Skype para Business Online](turning-on-and-using-call-quality-dashboard.md)