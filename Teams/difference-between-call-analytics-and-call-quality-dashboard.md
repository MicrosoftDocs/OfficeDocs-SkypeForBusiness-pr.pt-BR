---
title: Análise de Chamada e Painel de Qualidade de Chamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
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
ms.openlocfilehash: c85bcecd31c978616e5394740efac6bb5c28c07c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199787"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Análise de Chamada e Painel de Qualidade de Chamadas

Skype para negócios e o Teams da Microsoft oferecem duas maneiras para monitorar e solucionar problemas de qualidade da chamada: análise de chamada e o painel de controle de qualidade de chamada (CQD). Este artigo descreve os dois e informa quando usar cada uma delas.

Análise de chamada e CQD executem em paralelo e podem ser usado independentemente ou em conjunto. Por exemplo, diga uma especialista em suporte determina que precisa de mais ajuda solucionar um problema de chamada de comunicações. Especialista de suporte a comunicações passa a chamada para um engenheiro de suporte de comunicações, quem tem acesso mais informações na análise de chamada do que as comunicações especialista de suporte. Por sua vez, o engenheiro de suporte de comunicações alertando engenheiro de rede para um problema. O engenheiro de rede poderia verificar CQD para ver se um problema geral de sites relacionados poderia ser uma Colaborador causa de problemas de chamada.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>O que é chamada de análise e quando devo usá-lo?

**Análise de chamada agora está disponível no [Centro de administração de equipes da Microsoft](https://admin.teams.microsoft.com).** Para ver todas as informações de chamada e os dados de um usuário, use a guia de **Histórico de chamadas** . Você pode fazer isso por procurando na página de perfil do usuário, qualquer procurando por usuário do painel ou localizar o usuário dos **usuários** no painel de navegação à esquerda.

Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados à chamadas específicas e reuniões para cada usuário em um Microsoft Teams ou Skype para a conta de negócios. Por que esse usuário tinha uma chamada de baixa tarde? Usando a análise de chamada, um administrador do Office 365 ou a assistência técnica treinados agente possa investigar o dispositivo, rede, conectividade e outros fatores relacionados a sua chamada para solucionar problemas de qualidade e conexão de chamada no Microsoft Teams e Skype para negócios.

Para ver essas informações para um usuário no Centro de administração do Microsoft Teams, clique na guia **Histórico de chamadas** para esse usuário na página de detalhes do usuário, mostrando todas as chamadas e reuniões que o usuário tem participou nos últimos 30 dias.

![Chame a análise de dados do usuário.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obter informações adicionais sobre uma determinada sessão, incluindo mídia detalhadas e estatísticas de rede, clique em uma sessão para ver os detalhes.

![Chame a análise de dados da sessão de usuário.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Se desejar que não-administradores, como operadores de assistência técnica de um fornecedor externo, para usar a análise de chamada, você pode atribuir permissões para que eles podem usar a análise de chamada, mas não podem acessar o resto do Centro de administração do Microsoft Teams: 
  
- **Operadores de assistência técnica com a comunicação oferece suporte a permissões de specialist**: agentes vejam um conjunto limitado de dados e informações de identificação pessoal (PII) na análise de chamada. Solucionam chamadas, mas eles serão entregar problemas com reuniões com um engenheiro de suporte de comunicações.
    
- **Operadores de assistência técnica com a comunicação oferece suporte a permissões de engenharia**: agentes ver todos os dados disponíveis na análise de chamada e solucionar problemas de chamadas e reuniões. Eles têm acesso completo ao chamar os logs e informações do cliente.

> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente à função de suporte da camada 1, a partir do portal de visualização e a função de engenheiro de suporte de comunicações é equivalente à função de suporte da camada 2 a partir do portal de visualização.

Para obter mais informações sobre as comunicações especialista de suporte e comunicações funções engenheiro de suporte, consulte o [equipes da Microsoft que usar funções de administrador para gerenciar equipes](using-admin-roles.md).

> [!IMPORTANT]
> Permissões de operador de assistência técnica e carregamento de topologia de rede estão disponíveis no Centro de administração do Microsoft Teams. Especialistas de suporte de comunicações e comunicações engenheiros de suporte podem usar este portal para acessar a análise de chamada e o painel de controle de qualidade de chamada.
    
Para obter detalhes sobre como configurar a análise de chamada, consulte [Configurar Skype para análise de chamada de negócios](set-up-call-analytics.md). Para obter mais informações sobre como os operadores de assistência técnica podem trabalhar com a análise de chamada, consulte [Análise de uso chamada solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Qual é o painel de controle de qualidade de chamada, e quando devo usá-lo?
  
Enquanto a chamada Analytics foi projetado para ajudar os administradores e operadores de assistência técnica solucionem problemas de qualidade de chamada com chamadas específicos, o painel de qualidade de chamada (CQD) foi projetado para ajudar os administradores de equipes, Skype para os administradores corporativos, e uma rede de otimizar a engenheiros de rede. CQD alterna o foco de usuários específicos e em vez disso, analisa agregam informações de todo um equipes ou Skype para organização de negócios. Para obter mais detalhes, consulte [recursos do painel de qualidade de chamada para equipes e Skype para negócios Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Talvez a qualidade de chamadas ruins do usuário é devido a um problema de rede que também está afetando a muitos outros usuários. A experiência de chamada individual não está visível no CQD, mas a qualidade geral de chamadas realizadas usando o Microsoft Teams ou Skype para negócios é capturada. Com o CQD, geral padrões podem ficar aparentes, permitindo que os engenheiros de rede tornar informadas avaliações de qualidade de chamada. CQD fornece relatórios de métricas de qualidade de chamada que lhe dão ideias sobre chamam geral qualidade, fluxos de servidor-cliente, fluxos de cliente e a qualidade de voz [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Captura de tela do painel de controle de qualidade de chamada. Guias mostradas são qualidade geral da chamada, o servidor - cliente, cliente - cliente e SLA de qualidade de voz.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Com a Ajuda do CQD Location-Enhanced relatórios, a qualidade da chamada agregação e a confiabilidade dentro de construção do usuário podem ser avaliadas para determinar se o problema é isolado a um único usuário ou que afeta um segmento maior de usuários.

![Captura de tela de relatórios de localização avançada do painel de qualidade de chamada. Guias mostradas são Overview, prédios - com fio, prédios - WiFi e Mobile (LTE). Um filtro está sendo aplicado para exibir os fluxos de um edifício específico.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> Para habilitar exibições edifício ou ponto de extremidade específicos no CQD, um administrador deve [carregar as informações de construção ou ponto de extremidade](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) na página de carregamento de dados de Inquilino do CQD. 

Se desejar que não-administradores, como agentes de assistência técnica, para usar o painel de qualidade de chamada, você pode atribuir esses usuários a função **Engenheiro de suporte de comunicação de equipes**, **Especialista equipes de suporte de comunicações**ou **Leitor de relatórios** . Usuários com as seguintes funções podem acessar o painel de controle de qualidade de chamada:

- Administrador global
- Skype para o administrador de negócios
- Administrador de Serviço de Equipes
- Administrador de Comunicações de Equipes
- Engenheiro de Suporte de Comunicações de Equipes
- Especialista de suporte de comunicação de equipes
- Leitor de relatórios

> [!NOTE]
> As funções de equipes engenheiro de suporte de comunicações, especialista equipes de suporte de comunicações e leitor de relatórios não podem modificar arquivos na página de carregamento de dados de Inquilino do CQD nem ativar CQD para um inquilino.

Para obter mais informações sobre essas funções, consulte [funções de administrador do Office 365](/office365/admin/add-users/about-admin-roles).

Para obter mais informações sobre CQD, consulte [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para Business Online](turning-on-and-using-call-quality-dashboard.md) e [dimensões e medidas disponíveis no painel de qualidade de chamada para equipes da Microsoft e Skype para negócios Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Vídeo: Visão geral de qualidade de chamada](https://aka.ms/teams-quality)

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Ativando e usando o painel de controle de qualidade de chamada para Teams da Microsoft e Skype para Business Online](turning-on-and-using-call-quality-dashboard.md)
