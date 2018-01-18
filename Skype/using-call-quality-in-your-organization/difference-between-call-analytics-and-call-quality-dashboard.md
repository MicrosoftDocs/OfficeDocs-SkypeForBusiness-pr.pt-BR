---
title: "O que é a diferença entre a análise de chamada e o painel de controle de qualidade de chamada?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Saiba mais sobre a análise de chamada e painel de controle de qualidade de chamada e quando usá-los para monitorar e solucionar problemas de qualidade de chamada no Skype para negócios."
ms.openlocfilehash: bc42c5a58520cbb96f523181ba350d46e3c64a3e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a>O que é a diferença entre a análise de chamada e o painel de controle de qualidade de chamada?

Skype para negócios oferece duas maneiras para monitorar e solucionar problemas de qualidade da chamada: análise de chamada e o painel de controle de qualidade de chamada. Este artigo descreve os dois e informa quando usar cada uma delas.
  
> [!NOTE]
> Análise de chamada está sendo preview. Texto e imagens descritas aqui podem não corresponder sua experiência. 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>O que é chamada de análise e quando devo usá-lo?

Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados à chamadas específicas e reuniões para cada usuário em um Skype para a conta de negócios. Se você for um Skype para administração de negócios, você pode usar a chamada análise solucionar Skype para problemas de qualidade e conexão de chamada de negócios.
  
Se desejar que não-administradores, como operadores de assistência técnica de um fornecedor externo, para usar a análise de chamada, você pode atribuir permissões para que eles podem usar a análise de chamada, mas não podem acessar o restante do Skype para Business Admin center: 
  
- **Operadores de assistência técnica com permissões de nível 1**: agentes vejam um conjunto limitado de dados e informações de identificação pessoal (PII) na análise de chamada. Solucionam chamadas, mas eles serão entregar problemas com reuniões para um agente de nível 2.
    
- **Operadores de assistência técnica com permissões de nível 2**: agentes ver todos os dados disponíveis na análise de chamada e solucionar problemas de chamadas e reuniões. Eles têm acesso completo ao chamar os logs e informações do cliente.
    
Para obter detalhes sobre como configurar a análise de chamada, consulte [Configurar Skype para análise de chamada de negócios](set-up-call-analytics.md). Para obter mais informações sobre como os operadores de assistência técnica podem trabalhar com a análise de chamada, consulte [Análise de uso chamada solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Qual é o painel de controle de qualidade de chamada, e quando devo usá-lo?

Análise de chamada oferece informações detalhadas específicas sobre a qualidade da chamada experimentada pelos usuários. Por que o usuário Tony Smith tinha uma chamada de baixa tarde? Usando a análise de chamada, um Skype para administração de negócios ou do agente de assistência técnica treinados possa investigar o dispositivo, rede, conectividade e outros fatores relacionados a chamada de Tony.
  
Onde a autoridade de certificação foi projetada para ajudar os administradores e operadores de assistência técnica a solucionar problemas de qualidade de chamada com chamadas específicos, o painel de qualidade de chamada (CQD) foi projetado para ajudar Skype para os administradores de negócios e otimizam a uma rede engenheiros de rede. CQD alterna o foco de usuários específicos e em vez disso, analisa agregam informações para um inteiro Skype para organização de negócios. 
  
Talvez a qualidade de chamadas ruins de Tony é devido a um problema de rede que também está afetando a muitos outros usuários. Experiência de chamada individual de Tony não está visível no CQD, mas a qualidade geral de chamadas realizadas usando Skype para negócios é capturada. Com o CQD, geral padrões podem ficar aparentes, permitindo que os engenheiros de rede tornar informadas avaliações de qualidade de chamada. CQD fornece relatórios de métricas de qualidade de chamada que lhe dão ideias sobre chamam geral qualidade, fluxos de cliente e servidor-cliente e [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualidade de voz. 
  
![Captura de tela do painel de qualidade de chamada no Skype para Business Admin Center. Guias mostradas são qualidade geral da chamada, o servidor - cliente, cliente - cliente e SLA de qualidade de modo de exibição.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Para obter mais detalhes, consulte [recursos do painel de qualidade de chamada do Skype para negócios Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Análise de chamada e CQD executem em paralelo e podem ser usado independentemente ou em conjunto. Por exemplo, digamos que um agente de nível 1 determina que precisa de mais ajuda solucionar um problema de chamada. O agente de camada 1 passa a chamada para um agente de nível 2, quem tem acesso às informações mais na análise de chamada que o agente de nível 1. Por sua vez, o agente de nível 2 alertando engenheiro de rede para um problema. O engenheiro de rede pode verificar CQD para ver se um problema geral de sites relacionados poderia ser uma Colaborador causa de problemas de chamada.
  
Para obter mais informações sobre CQD, consulte [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para Business Online](turning-on-and-using-call-quality-dashboard.md) e [dimensões e medidas disponíveis no painel de qualidade de chamada para equipes da Microsoft e Skype para negócios Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype para análise de chamada de negócios](set-up-call-analytics.md)

[Qualidade de chamada de análise de uso chamada solucionar ruim Skype para negócios](use-call-analytics-to-troubleshoot-poor-call-quality.md)