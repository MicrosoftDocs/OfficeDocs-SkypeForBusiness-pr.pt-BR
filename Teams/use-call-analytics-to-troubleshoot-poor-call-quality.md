---
title: Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
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
description: Use os detalhes de chamada análise sobre dispositivos, redes e conectividade para solucionar problemas de usuário com o Microsoft Teams e Skype para reuniões e chamadas comerciais.
ms.openlocfilehash: d5409e1f37aaec6853362edc8caf74ea2a468cd7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464400"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada

Análise de chamada ajuda a solucionar problemas de chamada ou conexão com o Microsoft Teams e Skype para negócios. Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade para as chamadas e reuniões de cada usuário na sua conta do Office 365. Se criando, site e de inquilinos informações foram adicionadas para análise de chamada, ele também será mostrado para cada chamada e a sessão. Informações disponíveis por meio da análise de chamada podem ajudá-lo a descobrir por que um usuário teve uma chamada de baixa ou experiência da reunião. 
  
## <a name="call-analytics-permissions"></a>Permissões de análise de chamada

Como o administrador, você deve obter acesso total a todos os recursos de análise de chamada. Além disso, você pode atribuir funções do Azure Active Directory para a equipe de suporte. Atribua a função de especialista de suporte de comunicação de equipes a usuários que devem ter uma exibição limitada da análise de chamada. Atribua a função de engenheiro de suporte de comunicações equipes aos usuários que precisam acessar a funcionalidade completa do Analytics chamada. Ambos os níveis de permissão impedem o acesso ao restante do Centro de administração do Microsoft Teams.

Especialistas de suporte de comunicações lidar com problemas de qualidade de chamada básicos. Eles não investigar problemas com reuniões. Em vez disso, eles coletam informações relacionadas e, em seguida, escalonar para um engenheiro de suporte de comunicações. Engenheiros de suporte de comunicações consulte informações nos logs de chamada detalhadas ocultas de comunicações de especialistas de suporte. A tabela a seguir oferece uma visão geral das informações disponíveis aos engenheiros de suporte a comunicações suporte communications e especialistas quando utilizarem a análise de chamada.

O nível de permissões atribuído a você determina qual tipo de informação que você tem acesso na análise de chamada:
  
- **Equipes de equipes communications administrador ou serviço**: você tem acesso a todas as informações na análise de chamada e no Centro de administração do Microsoft Teams.
    
- **Especialista em comunicações de equipes de suportam**: você ver um conjunto limitado de dados na análise de chamada. Você pode solucionar problemas de chamadas, mas você entregar problemas com reuniões com um engenheiro de suporte de comunicações de equipes. Você não tem acesso ao restante do Centro de administração do Microsoft Teams.
    
- **Engenheiro de suporte a comunicações de equipes**: ver todos os dados disponíveis na análise de chamada e pode ajudar a solucionar problemas com chamadas e reuniões. Você não tem acesso ao restante do Centro de administração do Microsoft Teams.
    
> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente ao suporte da camada 1 e a função de engenheiro de suporte de comunicações é equivalente ao suporte da camada 2.

Para obter mais informações sobre as funções de administrador de equipes, consulte [equipes da Microsoft que usar funções de administrador para gerenciar equipes](using-admin-roles.md). Para obter uma comparação detalhada do suporte a comunicações equipes especializados e comunicações de equipes têm suporte para funções de engenharia, consulte [Configurar a análise de chamada](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Consulte suas equipes e Skype for Business admin se você precisa de ajuda com permissões.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar problemas de qualidade de chamada usando a análise de chamada

1. Entrar com seu suporte a comunicações equipes ou credenciais de administrador de equipes.

2. No navegador da web, vá para *https://admin.teams.microsoft.com*.
    
3. No **Painel de controle**, em **Pesquisa de usuário**, comece a digitar o nome ou endereço sip do usuário cujas chamadas que você deseja resolver ou selecione **Exibir usuários** para ver uma lista de usuários.
    
    ![Captura de tela da caixa de pesquisa de usuário do Analytics chamada no Centro de administração do Microsoft Teams.](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Selecione o usuário na lista.

5. Selecione o **histórico de chamadas**e selecione a chamada ou reunião que você deseja resolver.
    
    ![Captura de tela mostra a página do histórico de chamada para um usuário.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Selecione a guia **Avançado** e, em seguida, procure por itens amarelos e vermelhos que indicam problemas de chamada de baixa qualidade ou conexão.
    
    Nos detalhes da sessão para cada chamada ou reunião, pequenos problemas serão exibidas em amarelo. (Por exemplo, a seguinte captura de tela, os valores são em amarelo para variação média, tremulação máxima e taxa de perda de pacote média.) Se algo é amarelo, ele estiver fora do intervalo normal e ele pode estar contribuindo para o problema, mas é improvável de ser a causa principal do problema. Se algo é vermelho, é um problema significativo e provavelmente é o principal motivo da qualidade da chamada ruim para esta sessão. 
    
    ![Captura de tela mostra a guia Avançado da chamada histórico de um usuário ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
Em casos raros, dados qualidade da experiência não for recebida para sessões de áudio. Geralmente, isso é causado pela chamada eliminando e conexão com o cliente abortar. Quando isso acontecer, a classificação de sessão não está **disponível**.
  
Para sessões de áudio que tenham dados qualidade da experiência (QoE), a tabela a seguir descreve problemas principais que qualificar uma sessão como **ruim**.
  
|**Problema**|**Área**|**Descrição**|
|:-----|:-----|:-----|
|Configuração da chamada  <br/> |Sessão  <br/> |O código de erro 20-29 Ms-diagnóstico indica que a instalação chamada falhou. O usuário não pôde ingressar na chamada ou a reunião.  <br/> |
|Rede de áudio classificadas chamadas ruins  <br/> |Sessão  <br/> |Problemas de qualidade de rede (por exemplo, tremulação, perda de pacotes, degradação NMOS, tempo de resposta ou proporção escondida) foram encontrados. Para obter mais informações sobre as condições usado para classificar as chamadas de baixa, consulte esta [postagem de blog da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo não funcionando  <br/> |Dispositivo  <br/> | Um dispositivo não está funcionando corretamente. Dispositivo não funcionando taxas é: <br/>  Gt _ de DeviceRenderNotFunctioningEventRatio = 0,005 <br/>  Gt _ de DeviceCaptureNotFunctioningEventRatio = 0,005 <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados
[Configurar Análise de Chamada](set-up-call-analytics.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
