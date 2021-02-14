---
title: Usar a análise de chamada para solucionar problemas de baixa qualidade da chamada
ms.author: serdars
author: SerdarSoysal
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
description: Use detalhes de análise de chamadas por usuário sobre dispositivos, redes e conectividade para solucionar problemas do usuário com chamadas e reuniões do Microsoft Teams.
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583620"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar a análise de chamada para solucionar problemas de baixa qualidade da chamada

Este artigo explica como usar a análise de chamada para solucionar problemas de baixa qualidade de chamada ou reunião do Microsoft Teams para usuários individuais se você for um administrador do Teams ou um engenheiro de suporte de comunicações do Teams.


  
## <a name="call-analytics-permissions"></a>Permissões de Análise de Chamada

Este artigo supõe que você já tenha definido a análise de chamada. Caso não tenha, leia [Configurar a análise de chamada para o Teams.](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>Introdução à análise de chamada

A análise de chamadas mostra informações detalhadas sobre chamadas e reuniões do Teams para cada usuário em sua conta do Office 365. Ele inclui informações sobre dispositivos, redes, conectividade e qualidade de chamada (qualquer um deles pode ser um fator de baixa qualidade de chamada ou reunião). Se você carregar informações de edifício, site e locatário, essas informações também serão mostradas para cada chamada e reunião. Use a análise de chamada para ajudá-lo a descobrir por que um usuário teve uma experiência ruim de chamada ou reunião.

A análise de chamada mostra cada etapa de uma chamada ou reunião, por exemplo, de um participante para um segundo participante. Ao analisar esses detalhes, um administrador do Teams pode isolar áreas do problema e identificar a causa raiz da baixa qualidade.
   
Como administrador do Teams, você tem acesso total a todos os dados de análise de chamada para cada usuário. Além disso, você pode atribuir funções do Azure Active Directory para dar suporte à equipe. Para saber mais sobre essas funções, leia Dar permissão para a equipe de suporte [e suporte.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) Não perca o que [cada função de suporte do Teams faz?](#what-does-each-teams-support-role-do) Abaixo.

## <a name="where-to-find-per-user-call-analytics"></a>Onde encontrar a análise de chamada por usuário

Para ver todas as informações e dados de chamada de um usuário, vá para o Centro de [administração do Teams.](https://admin.teams.microsoft.com) Em **Usuários,** selecione um usuário e abra a **guia** Histórico de Chamada na página de perfil do usuário. Aqui você encontrará todas as chamadas e reuniões para esse usuário nos últimos 30 dias.

![Captura de tela de todos os dados do usuário de análise](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obter informações adicionais sobre uma determinada sessão, incluindo estatísticas de rede e mídia detalhadas, clique em uma sessão para ver os detalhes.

![Captura de tela dos dados de sessão do usuário de análise de chamada](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>O que cada função de suporte do Teams faz?

O **especialista de suporte de comunicações do Teams** (suporte de nível 1) lida com problemas básicos de qualidade de chamada. Eles não investigam problemas com reuniões. Em vez disso, coletam informações relacionadas e, em seguida, encaminham para um engenheiro de suporte de comunicações. 

O **engenheiro de suporte de** comunicações do Teams (suporte de Nível 2) vê informações em logs de chamada detalhados que estão ocultos do especialista de suporte de comunicações do Teams. A tabela a seguir lista as informações disponíveis para cada função de suporte de comunicação do Teams.

A tabela a seguir informa quais informações por usuário estão disponíveis para cada função de suporte de comunicação.

|**Atividade**|**Informações**|O que o especialista **de suporte de** comunicações vê|O que o engenheiro de suporte **de** comunicações vê|
|:-----|:-----|:-----|:-----|
|**Chamadas** <br/> |Nome do chamador  <br/> |Somente o nome do usuário para o qual o agente pesquisou.  <br/> |Nome de usuário.  <br/> |
||Nome do destinatário  <br/> |Mostra como Usuário Interno ou Usuário Externo.  <br/> |Nome do destinatário.  <br/> |
||Número de telefone do chamador  <br/> |O número de telefone inteiro, exceto os últimos três dígitos, são ofuscados com símbolos de asterisco. Por exemplo, 15552823***.  <br/> |O número de telefone inteiro, exceto os últimos três dígitos, são ofuscados com símbolos de asterisco. Por exemplo, 15552823***.  <br/> |
||Número de telefone do destinatário  <br/> |O número de telefone inteiro, exceto os últimos três dígitos, são ofuscados com símbolos de asterisco. Por exemplo, 15552823***.  <br/> |O número de telefone inteiro, exceto os últimos três dígitos, são ofuscados com símbolos de asterisco. Por exemplo, 15552823***.  <br/> |
||**Detalhes da Chamada**  >  **Guia** Avançado <br/> |Informações não exibidas.  <br/> |Todos os detalhes mostrados, como nomes de dispositivos, endereço IP, mapeamento de sub-rede e muito mais.  <br/> |
||**Detalhes da Chamada**  >  **Avançado**  >  **Guia Depurar** <br/> |Informações não exibidas.  <br/> |Todos os detalhes mostrados, como sufixo DNS e SSID.  <br/> |
|**Reuniões** <br/> |Nomes dos participantes  <br/> |Somente o nome do usuário para o qual o agente pesquisou. Outros participantes identificados como Usuário Interno ou Usuário Externo.  <br/> |Todos os nomes mostrados.  <br/> |
||Contagem de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalhes da sessão  <br/> |Detalhes da sessão mostrados com exceções. Somente o nome do usuário para o qual o agente pesquisou é mostrado. Outros participantes identificados como Usuário Interno ou Usuário Externo. Últimos três dígitos de número de telefone ofuscados com símbolos de asterisco.  <br/> |Detalhes da sessão mostrados. Nomes de usuário e detalhes da sessão mostrados. Últimos três dígitos de número de telefone ofuscados com símbolos de asterisco.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de qualidade de chamada do usuário 

1. Abra o Centro de administração do Teams ( e entre com seu suporte de https://admin.teams.microsoft.com) comunicações do Teams ou credenciais de administrador do Teams.

2. No **Painel,** na Pesquisa de **Usuário,** comece a digitar o nome ou o endereço  SIP do usuário cujas chamadas você deseja solucionar ou selecione Exibir usuários para ver uma lista de usuários.

3. Selecione o usuário na lista.

4. Selecione **Histórico de** chamada e, em seguida, selecione a chamada ou reunião que você deseja solucionar.
    
5. Selecione a **guia Avançado** e procure itens amarelos e vermelhos que indicam baixa qualidade da chamada ou problemas de conexão.
    
    Nos detalhes da sessão de cada chamada ou reunião, problemas secundários aparecem em amarelo. Se algo for amarelo, ele está fora do intervalo normal e pode estar colaborando para o problema, mas é improvável que seja a principal causa do problema. Se algo estiver vermelho, é um problema significativo e provavelmente é a principal causa da baixa qualidade da chamada para esta sessão. 
      
Em casos raros, os dados de Qualidade da Experiência não são recebidos para sessões de áudio. Muitas vezes, isso é causado por uma chamada descarada ou quando a conexão com o cliente termina. Quando isso ocorre, a classificação da sessão fica **indisponível.**
  
Para sessões de áudio que têm dados de QoE (Qualidade da Experiência), a tabela a seguir descreve os principais problemas que qualificam uma sessão como **ruim.**
  
|**Problema**|**Área**|**Descrição**|
|:-----|:-----|:-----|
|Configuração de chamada  <br/> |Sessão  <br/> |O código de erro Ms-diag 20-29 indica que a configuração da chamada falhou. O usuário não pôde ingressar na chamada ou na reunião.  <br/> |
|Chamada ruim classificada de rede de áudio  <br/> |Sessão  <br/> |Problemas de qualidade de rede (como perda de pacote, tremidação, degradação de NMOS, RTT ou taxa oculta) foram encontrados.  <br/> |
|O dispositivo não está funcionando  <br/> |Dispositivo  <br/> | Um dispositivo não está funcionando corretamente. As taxas de funcionamento do dispositivo são: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a análise de chamada por usuário](set-up-call-analytics.md)



  
 
