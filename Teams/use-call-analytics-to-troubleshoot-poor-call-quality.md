---
title: Usar a análise de chamadas para solucionar problemas de qualidade de chamadas ruins
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use detalhes da análise de chamadas por usuário sobre dispositivos, redes e conectividade para solucionar problemas do usuário com chamadas e reuniões do Microsoft Teams.
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085317"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar a análise de chamadas para solucionar problemas de qualidade de chamadas ruins

Este artigo explica como usar a análise de chamadas para solucionar problemas de chamada e qualidade de reunião do Microsoft Teams para usuários individuais se você for um administrador do teams ou um especialista ou engenheiro de suporte a comunicações em equipe.


  
## <a name="call-analytics-permissions"></a>Permissões de análise de chamadas

Este artigo pressupõe que você já configurou a análise de chamadas. Se você ainda não fez isso, leia [Configurar análise de chamadas para o Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Introdução à análise de chamadas

A análise de chamadas mostra informações detalhadas sobre chamadas e reuniões do teams para cada usuário na sua conta do Office 365. Ele inclui informações sobre dispositivos, redes, conectividade e qualidade da chamada (qualquer um deles pode ser um fator em chamadas ruins ou qualidade de reunião). Se você carregar informações de construção, site e locatário, essas informações também serão mostradas para cada chamada e reunião. Use a análise de chamadas para ajudá-lo a descobrir o motivo pelo qual o usuário tinha uma experiência de chamada ou de reunião ruim.

O recurso de análise de chamadas mostra cada trecho de uma chamada ou reunião-por exemplo, de um participante para um segundo participante. Ao analisar esses detalhes, um administrador de equipe pode isolar áreas problemáticas e identificar a causa básica para uma qualidade ruim.
   
Como administrador do Teams, você obtém acesso completo a todos os dados da análise de chamadas para cada usuário. Além disso, você pode atribuir funções do Azure Active Directory a equipe de suporte. Para saber mais sobre essas funções, leia [conceder permissão para a equipe de suporte e suporte técnico](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). Não perca [o que as funções de suporte de cada equipe fazem?](#what-does-each-teams-support-role-do) abaixo.

## <a name="where-to-find-per-user-call-analytics"></a>Onde encontrar a análise de chamadas por usuário

Para ver todas as informações de chamada e dados de um usuário, vá para o [centro de administração do teams](https://admin.teams.microsoft.com). Em **usuários**, selecione um usuário e, em seguida, abra a guia **histórico de chamadas** na página de perfil do usuário. Aqui você encontrará todas as chamadas e reuniões desse usuário pelos últimos 30 dias.

![Captura de tela de todos os dados do usuário analítico](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obter informações adicionais sobre uma determinada sessão, incluindo estatísticas detalhadas de mídia e de rede, clique em uma sessão para ver os detalhes.

![Captura de tela dos dados da sessão do usuário do Analytics Analytics](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>Qual é a função de cada função do suporte do teams?

O **especialista de suporte do teams Communications** (suporte à camada 1) lida com problemas básicos de qualidade de chamada. Eles não investigam problemas com reuniões. Em vez disso, eles coletam informações relacionadas e encaminham para um engenheiro de suporte de comunicações. 

O **engenheiro de suporte do teams Communications** (suporte à camada 2) vê informações em logs de chamadas detalhados que estão ocultos no especialista de suporte de comunicações do teams. A tabela a seguir lista as informações disponíveis para cada função de suporte à comunicação da equipe.

A tabela a seguir informa quais informações por usuário estão disponíveis para cada função de suporte de comunicações.

|**Atividade**|**Às**|O que o **especialista** de suporte de comunicações vê|O que o **engenheiro** de suporte a comunicações vê|
|:-----|:-----|:-----|:-----|
|**Chamadas** <br/> |Nome do chamador  <br/> |Somente o nome do usuário para o qual o agente procurou.  <br/> |Nome de usuário.  <br/> |
||Nome do destinatário  <br/> |Mostra como usuário interno ou externo.  <br/> |Nome do destinatário.  <br/> |
||Número de telefone do chamador  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||Número de telefone do destinatário  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||**Detalhes**  >  da chamada Guia **avançado** <br/> |As informações não são mostradas.  <br/> |Todos os detalhes mostrados, como nomes de dispositivos, endereços IP, mapeamento de sub-rede e muito mais.  <br/> |
||**Detalhes**  >  da chamada **Avançado**  >  Guia **depurar** <br/> |As informações não são mostradas.  <br/> |Todos os detalhes exibidos, como sufixo DNS e SSID.  <br/> |
|**Reuniões** <br/> |Nomes dos participantes  <br/> |Somente o nome do usuário para o qual o agente procurou. Outros participantes identificados como usuário interno ou usuário externo.  <br/> |Todos os nomes mostrados.  <br/> |
||Contagem de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalhes da sessão  <br/> |Detalhes da sessão mostrados com exceções. Somente o nome do usuário para o qual o agente procurou é mostrado. Outros participantes identificados como usuário interno ou usuário externo. Os últimos três dígitos do número de telefone ofuscados com símbolos de asterisco.  <br/> |Detalhes da sessão mostrados. Nomes de usuário e detalhes da sessão mostrados. Os últimos três dígitos do número de telefone ofuscados com símbolos de asterisco.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de qualidade das chamadas do usuário 

1. Abra o centro de administração do Teams ( https://admin.teams.microsoft.com) e entre com suas credenciais de administrador do teams support ou Teams.

2. No **painel**, na **pesquisa do usuário**, comece a digitar o nome ou o endereço SIP do usuário cujas chamadas você deseja solucionar ou selecione **exibir usuários** para ver uma lista de usuários.

3. Selecione o usuário na lista.

4. Selecione **histórico de chamadas**e, em seguida, selecione a chamada ou a reunião para a qual você deseja solucionar o problema.
    
5. Selecione a guia **avançado** e, em seguida, procure por itens amarelos e vermelhos que indicam problemas com a baixa qualidade da chamada ou problemas de conexão.
    
    Nos detalhes da sessão de cada chamada ou reunião, os problemas secundários aparecem em amarelo. Se algo for amarelo, ele estará fora do intervalo normal e poderá estar contribuindo para o problema, mas é improvável que seja a principal causa do problema. Se algo estiver vermelho, é um problema significativo, e provavelmente é a principal causa da baixa qualidade da chamada para esta sessão. 
      
Em casos raros, os dados de qualidade da experiência não são recebidos para sessões de áudio. Geralmente, isso é causado por uma chamada descartada ou quando a conexão com o cliente é encerrada. Quando isso ocorre, a classificação da sessão não está **disponível**.
  
Para sessões de áudio que têm dados de qualidade da experiência (QoE), a tabela a seguir descreve problemas importantes que qualificam uma sessão como **ruim**.
  
|**Problema**|**Área**|**Descrição**|
|:-----|:-----|:-----|
|Configuração da chamada  <br/> |Session  <br/> |O código de erro MS-diag 20-29 indica falha na configuração da chamada. O usuário não pôde ingressar na chamada ou na reunião.  <br/> |
|Chamada deficiente da rede de áudio classificada  <br/> |Session  <br/> |Problemas de qualidade de rede (como perda de pacotes, tremulação, degradação do NMOS, RTT ou proporção oculta) foram encontrados.  <br/> |
|O dispositivo não está funcionando  <br/> |Dispositivo  <br/> | Um dispositivo não está funcionando corretamente. As proporções do dispositivo não estão funcionando: <br/>  DeviceRenderNotFunctioningEventRatio >= 0, 5 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0, 5 <br/> |
   

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a análise de chamadas por usuário](set-up-call-analytics.md)



  
 
