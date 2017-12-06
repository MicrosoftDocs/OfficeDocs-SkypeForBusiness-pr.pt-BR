---
title: "Qual é a diferença entre a análise de chamadas e o painel de qualidade de chamada?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
description: "Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business."
---

# Qual é a diferença entre a análise de chamadas e o painel de qualidade de chamada?

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](4cd5fe35-8463-4996-a252-086cd3ca2d9a.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/4cd5fe35-8463-4996-a252-086cd3ca2d9a). 
  
Skype for Business fornece duas maneiras para monitorar e solucionar problemas de qualidade de chamada: análise de chamadas e painel de qualidade de chamada. Este artigo descreve os dois e explica quando usar cada um deles.
  
> [!NOTE]
> Análise de chamada está sendo preview. Texto e imagens descritas aqui podem não corresponder sua experiência. 
  
## Qual é a análise de chamadas, e quando devo usá-lo?

Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados à específico chamadas e reuniões para cada usuário em uma conta de Skype for Business. Se você for um administrador de Skype for Business, você pode usar a análise de chamada para solucionar problemas de qualidade e conexão de chamada de Skype for Business.
  
Se quiser que os não-administradores, como agentes de suporte técnico de um fornecedor externo, para usar a análise de chamadas, você pode atribuir permissões para que eles podem usar a análise de chamadas, mas eles não podem acessar o resto do Centro de administração do Skype for Business:
  
- **Agentes de suporte técnico com permissões de nível 1**: agentes de vejam um conjunto limitado de dados e informações de identificação pessoal (IIP) em análise de chamadas. Pode solucionar problemas de chamadas, mas eles serão entregar problemas com reuniões para um agente de nível 2.
    
- **Agentes de suporte técnico com permissões de nível 2**: agentes ver todos os dados disponíveis em análise de chamadas e solucionar problemas de chamadas e reuniões. Eles têm acesso completo a informações de cliente e logs de chamadas.
    
Para obter detalhes sobre como configurar a análise de chamadas, consulte [Configurar o Skype para a análise de chamadas de negócios](set-up-skype-for-business-call-analytics.md). Para obter mais informações sobre como os agentes de suporte técnico podem trabalhar com a análise de chamadas, consulte [Usar a análise de chamada solucionar má Skype para empresas a qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md).
  
## O que é o painel de qualidade de chamada e quando devo usá-lo?

Análise de chamada fornece informações detalhadas específicas sobre a qualidade das chamadas experimentada pelos usuários. Por que o usuário Tony Smith tinha uma chamada má hoje à tarde? Usando a análise de chamadas, um administrador de Skype for Business ou um agente de assistência técnica treinamento possa investigar o dispositivo, rede, conectividade e outros fatores relacionados a chamada de Tony.
  
Onde CA foi projetado para ajudar os administradores e agentes de suporte técnico solucionar problemas de qualidade de chamada com chamadas de específico, o painel de qualidade de chamada (CQD) foi projetado para ajudar os administradores de Skype for Business e engenheiros de rede otimizam uma rede. CQD desloca o foco de usuários específicos e, em vez disso examina agregadas informações para uma organização inteira Skype for Business.
  
Talvez a qualidade da chamada má de Tony é devido a um problema de rede que também está afetando a muitos outros usuários. Experiência de chamada individuais de Tony não estiver visível no CQD, mas a qualidade geral das chamadas feitas usando Skype for Business é capturada. Com o CQD, geral padrões podem se tornar evidentes, permitindo que os engenheiros de rede tornar informadas avaliações de qualidade da chamada. CQD fornece relatórios de métricas de qualidade de chamada que lhe dão ideias para chamam geral qualidade, fluxos de servidor-cliente e cliente e qualidade de voz [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Para obter mais detalhes, consulte [Recursos do painel de qualidade de chamada do Skype for Business Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_FeaturesOfTheCQD).
  
Análise de chamada e CQD executem em paralelo e podem ser usado independentemente ou em conjunto. Por exemplo, digamos que um agente de nível 1 determina que precisam de mais ajuda para solucionar um problema de chamada. O agente de nível 1 passa a chamada para um agente de nível 2, quem tem acesso a mais informações em análise de chamada que o agente de nível 1. Por sua vez, o agente de nível 2 pode alertar uma engenharia de rede para um problema. A engenharia de rede pode verificar CQD para ver se um problema de sites relacionados geral pode ser uma Colaborador causa de problemas de chamada.
  
Para saber mais sobre CQD, consulte [Como ativar e usar o painel de qualidade de chamada para Teams Microsoft e Skype for Business Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md) e[Dimensões e medidas disponíveis no chamar painel de controle de qualidade para Teams da Microsoft e o Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

