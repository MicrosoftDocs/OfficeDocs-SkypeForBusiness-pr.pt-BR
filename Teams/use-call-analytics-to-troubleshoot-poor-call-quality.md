---
title: Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Use os detalhes de chamada análise sobre dispositivos, redes e conectividade para solucionar problemas de usuário com o Skype para reuniões e chamadas comerciais.
ms.openlocfilehash: db1f0ed4ce79936a5355fe087220fe2802f61ce6
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23783146"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas

Análise de chamada ajuda você a solucionar problemas de chamada ou conexão com o Microsoft Teams e Skype para negócios. Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade para as chamadas e reuniões de cada usuário na sua conta do Office 365. Se criando, site e de inquilinos informações foram adicionadas para análise de chamada, ele também será mostrado para cada chamada e a sessão. Informações disponíveis por meio da análise de chamada podem ajudá-lo a descobrir por que um usuário teve uma chamada de baixa ou experiência da reunião. 
  
**Análise de chamada agora está disponível no Microsoft Teams e Skype para Business Admin Center.** Para ver todas as informações de chamada e os dados de um usuário, use a guia de **Histórico de chamadas** . Você pode fazer isso por procurando na página de perfil do usuário, qualquer procurando por usuário do painel ou localizar o usuário dos **usuários** no painel de navegação à esquerda.

> [!IMPORTANT]
> Permissões de operador de assistência técnica e carregamento de topologia de rede estará disponíveis no portal de administração do novo nos próximos meses. Enquanto isso, você pode continuar a usar https://adminportal.services.skypeforbusiness.com para acesso de assistência técnica de camada 1 e a camada 2.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar problemas de qualidade de chamada usando a análise de chamada

O nível de permissões atribuído a você determina qual tipo de informação que você tem acesso na análise de chamada:
  
- **Skype para Business admin**: você tem acesso a todas as informações na análise de chamadas e no Skype para Business Admin center.
    
- **Agente de assistência técnica com permissões de nível 1**: você ver um conjunto limitado de dados na análise de chamada. Você pode solucionar problemas de chamadas, mas você entregar problemas com reuniões para um agente de nível 2. Você não tem acesso ao restante do Skype para Business Admin center.
    
- **Agente de assistência técnica com permissões de nível 2**: ver todos os dados disponíveis na análise de chamada e pode ajudar a solucionar problemas com chamadas e reuniões. Você não tem acesso ao restante do Skype para Business Admin center.
    
Se você precisa de ajuda com permissões, consulte sua Skype para administração de negócios.
  
 **Abra o Analytics chamada como um agente de assistência técnica da camada 1 ou camada 2**
  
1. Vá para o Centro de administração do Office 365 e entrar usando sua conta do trabalho ou da escola. Em seguida, no seu navegador da web, vá para *https://adminportal.services.skypeforbusiness.com*.
    
2. Em **Pesquisa de usuário**, comece a digitar um endereço sip ou o nome do usuário cujas chamadas que você deseja resolver e, em seguida, selecione o usuário na lista.
    
    ![Captura de tela da caixa de pesquisa de usuário do Analytics chamada no Skype para Business Admin Center.](media/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. No **histórico de chamadas**, selecione a chamada ou reunião que você deseja resolver.
    
    ![Captura de tela mostra a página do histórico de chamada para um usuário com informações como detalhes de contato do usuário, um resumo da qualidade de 7 dias e atividade para reuniões e chamadas e uma visão geral das datas e horas, destinatários e qualidade de áudio](media/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Selecione a guia **Avançado** e, em seguida, procure por itens amarelos e vermelhos que indicam problemas de chamada de baixa qualidade ou conexão.
    
    Nos detalhes da sessão para cada chamada ou reunião, pequenos problemas serão exibidas em amarelo. (Por exemplo, a seguinte captura de tela, os valores são em amarelo para variação média, tremulação máxima e taxa de perda de pacote média.) Se algo é amarelo, ele estiver fora do intervalo normal e ele pode estar contribuindo para o problema, mas é improvável de ser a causa principal do problema. Se algo é vermelho, é um problema significativo e provavelmente é o principal motivo da qualidade da chamada ruim para esta sessão. 
    
    ![Captura de tela mostra a guia Avançado da chamada histórico de um usuário com a seção de rede de entrada expandida para revelar que os dados de variação média, máxima tremulação e taxa de perda de pacote média são mostrados com uma cor amarela, que significa que eles são pequenos problemas.](media/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
Em casos raros, dados qualidade da experiência não for recebida para sessões de áudio. Geralmente, isso é causado pela chamada eliminando e conexão com o cliente abortar. Quando isso acontecer, a classificação de sessão é "não disponível".
  
Para sessões de áudio que tenham dados qualidade da experiência (QoE), a tabela a seguir descreve os principais problemas que qualificar uma sessão como "ruim".
  
|**Problema**|**Área**|**Descrição**|
|:-----|:-----|:-----|
|Configuração da chamada  <br/> |Sessão  <br/> |O código de erro 20-29 Ms-diagnóstico indica que a instalação chamada falhou. O usuário não pôde ingressar na chamada ou a reunião.  <br/> |
|Rede de áudio classificadas chamadas ruins  <br/> |Sessão  <br/> |Problemas de qualidade de rede foram encontrados em áreas como perda de pacotes, tremulação, degradação NMOS, tempo de resposta, ou oculta a proporção. Para obter mais informações sobre as condições usado para classificar as chamadas de baixa, consulte esta [postagem de blog da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo não funcionando  <br/> |Dispositivo  <br/> | Um dispositivo não está funcionando corretamente. Dispositivo não funcionando taxas é: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados
[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Análise de chamada e o painel de controle de qualidade de chamada](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
