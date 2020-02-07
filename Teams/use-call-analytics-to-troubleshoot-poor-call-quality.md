---
title: Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use os detalhes da análise de chamadas sobre dispositivos, redes e conectividade para solucionar problemas do usuário com o Microsoft Teams e chamadas e reuniões do Skype for Business.
ms.openlocfilehash: a9ef3265fa86349ef92c6174c6f561b006af4d1a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836761"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada

O recurso de análise de chamadas ajuda você a solucionar problemas de chamada ou conexão com o Microsoft Teams e o Skype for Business. A análise de chamadas mostra informações detalhadas sobre os dispositivos, redes e conectividade para as chamadas e reuniões de cada usuário na sua conta do Office 365. Se as informações de construção, site e locatário tiverem sido adicionadas à análise de chamadas, ela também será mostrada para cada chamada e sessão. As informações disponíveis por meio de análises de chamadas podem ajudá-lo a descobrir o motivo pelo qual um usuário teve uma experiência de chamada ou de reunião ruim. 
  
## <a name="call-analytics-permissions"></a>Permissões de análise de chamadas

Como administrador, você tem acesso total a todos os recursos do recurso de análise de chamadas. Além disso, você pode atribuir funções do Azure Active Directory a equipe de suporte. Atribua a função de especialista de comunicações do teams a usuários que devem ter uma visão limitada da análise de chamadas. Atribua a função de engenheiro de suporte de comunicações ao Teams a usuários que precisam acessar a funcionalidade completa do recurso de análise de chamadas. Os dois níveis de permissão impedem o acesso ao restante do centro de administração do Microsoft Teams.

Especialistas de suporte de comunicações lidam com problemas básicos de qualidade de chamada. Eles não investigam problemas com reuniões. Em vez disso, eles coletam informações relacionadas e encaminham para um engenheiro de suporte de comunicações. Engenheiros de suporte a comunicações consulte informações em logs de chamadas detalhados que estão ocultos a especialistas de suporte de comunicações. A tabela a seguir fornece uma visão geral das informações disponíveis para especialistas de suporte de comunicações e engenheiros de suporte de comunicações quando eles usam a análise de chamadas.

O nível de permissões atribuído a você determina que tipo de informações você tem acesso na análise de chamadas:
  
- Administrador de **Serviços do teams ou administrador de comunicações do teams**: você tem acesso a todas as informações no Microsoft Analytics Analytics e no centro de administração do Microsoft Teams.
    
- **Especialista em suporte às comunicações do teams**: você vê um conjunto limitado de dados na análise de chamadas. Você pode solucionar problemas, mas vai desligar problemas com reuniões para um engenheiro de suporte de comunicações do teams. Você não tem acesso ao restante do centro de administração do Microsoft Teams.
    
- **Engenheiro de suporte de comunicações do teams**: você vê todos os dados disponíveis na análise de chamadas e pode ajudar a solucionar problemas com chamadas e reuniões. Você não tem acesso ao restante do centro de administração do Microsoft Teams.
    
> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente ao suporte de nível 1 e a função de engenheiro de suporte de comunicações equivale ao suporte de nível 2.

Para obter mais informações sobre as funções de administração do Teams, consulte [usar funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md). Para obter uma comparação detalhada das funções do especialista em suporte de comunicações do teams support e do engenheiro de suporte de comunicações do Teams, consulte [Configurar Analytics de chamadas](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Veja suas equipes e o administrador do Skype for Business se precisar de ajuda com permissões.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar problemas de qualidade de chamada usando a análise de chamadas

1. Entre com as credenciais de administrador do teams support ou Teams de comunicações de equipe.

2. No navegador da Web, vá *https://admin.teams.microsoft.com*para.
    
3. No **painel**, na **pesquisa do usuário**, comece a digitar o nome ou o endereço SIP do usuário cujas chamadas você deseja solucionar ou selecione **exibir usuários** para ver uma lista de usuários.
    
    ![Captura de tela da caixa de pesquisa de usuário da análise de chamadas](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Selecione o usuário na lista.

5. Selecione **histórico de chamadas**e, em seguida, selecione a chamada ou a reunião para a qual você deseja solucionar o problema.
    
    ![Captura de tela da página Histórico de chamadas de um usuário.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Selecione a guia **avançado** e, em seguida, procure por itens amarelos e vermelhos que indicam problemas com a baixa qualidade da chamada ou problemas de conexão.
    
    Nos detalhes da sessão de cada chamada ou reunião, os problemas secundários aparecem em amarelo. (Por exemplo, na captura de tela a seguir, os valores estão em amarelo para tremulação média, tremulação máx e taxa de perda de pacotes média.) Se algo for amarelo, ele estará fora do intervalo normal e poderá estar contribuindo para o problema, mas é improvável que seja a principal causa do problema. Se algo estiver vermelho, é um problema significativo, e provavelmente é a principal causa da baixa qualidade da chamada para esta sessão. 
    
    ![Captura de tela da guia Avançado do histórico de chamadas de um usuário ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
Em casos raros, os dados de qualidade da experiência não são recebidos para sessões de áudio. Geralmente, isso é causado pelo cancelamento de chamada e pela conexão com o cliente sendo encerrado. Quando isso ocorre, a classificação da sessão não está **disponível**.
  
Para sessões de áudio que têm dados de qualidade da experiência (QoE), a tabela a seguir descreve problemas importantes que qualificam uma sessão como **ruim**.
  
|**Problema**|**Área**|**Descrição**|
|:-----|:-----|:-----|
|Configuração da chamada  <br/> |Session  <br/> |O código de erro MS-diag 20-29 indica falha na configuração da chamada. O usuário não pôde ingressar na chamada ou na reunião.  <br/> |
|Chamada deficiente da rede de áudio classificada  <br/> |Session  <br/> |Problemas de qualidade de rede (como perda de pacotes, tremulação, degradação do NMOS, RTT ou proporção oculta) foram encontrados. Para obter mais informações sobre as condições usadas para classificar chamadas ruins, consulte esta [postagem de blog da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|O dispositivo não está funcionando  <br/> |Dispositivo  <br/> | Um dispositivo não está funcionando corretamente. As proporções do dispositivo não estão funcionando: <br/>  DeviceRenderNotFunctioningEventRatio >= 0, 5 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0, 5 <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados
[Configurar Análise de Chamada](set-up-call-analytics.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
