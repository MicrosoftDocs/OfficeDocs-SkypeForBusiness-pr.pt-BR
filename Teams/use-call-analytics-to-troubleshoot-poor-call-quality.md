---
title: Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use os detalhes do Call Analytics por usuário sobre dispositivos, redes e conectividade para solucionar problemas do usuário com Microsoft Teams chamadas e reuniões.
ms.openlocfilehash: 9f61796d83977c9d0782957fe3bafe787f60403b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731930"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada

Este artigo explica como usar o Call Analytics para solucionar problemas Microsoft Teams qualidade de chamada ou reunião para usuários individuais se você tiver o administrador do Teams, o especialista de suporte Teams comunicações ou Teams função de engenheiro de suporte de comunicações.

## <a name="call-analytics-permissions"></a>Permissões de Análise de Chamada

Este artigo supõe que você já tenha definido o Call Analytics. Se você não tiver, leia [Configurar análise de chamada para](set-up-call-analytics.md)Teams .

## <a name="introduction-to-call-analytics"></a>Introdução ao Call Analytics

O Call Analytics mostra informações detalhadas sobre Teams chamadas e reuniões para cada usuário em sua Office 365 conta. Ele inclui informações sobre dispositivos, redes, conectividade e qualidade de chamada (qualquer um deles pode ser um fator de má qualidade de chamada ou reunião). Se você carregar informações de construção, site e locatário, essas informações também serão mostradas para cada chamada e reunião. Use a Análise de Chamada para ajudá-lo a descobrir por que um usuário teve uma experiência ruim de chamada ou reunião.

A Análise de Chamada mostra cada etapa de uma chamada ou reunião - por exemplo, de um participante para um segundo participante. Analisando esses detalhes, um administrador de Teams pode isolar áreas problemáticas e identificar a causa raiz da má qualidade.

Como administrador Teams, você tem acesso total a todos os dados do Call Analytics para cada usuário. Além disso, você pode atribuir Azure Active Directory funções para dar suporte à equipe. Para saber mais sobre essas funções, leia Dar permissão para dar suporte [e ajudar a equipe](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). Não perca o [que cada função Teams Suporte faz?](#what-does-each-teams-support-role-do) abaixo.

## <a name="where-to-find-per-user-call-analytics"></a>Onde encontrar análise de chamada por usuário

Para ver todas as informações de chamada e dados de um usuário, vá para o centro de administração [Teams.](https://admin.teams.microsoft.com) Em **Usuários,** selecione um usuário e abra a guia **Reuniões & Chamadas** na página de perfil do usuário. Aqui você encontrará todas as chamadas e reuniões para esse usuário nos últimos 30 dias.

![Captura de tela de todos os dados do usuário de análise.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obter informações adicionais sobre uma determinada sessão, incluindo estatísticas detalhadas de mídia e rede, clique em uma sessão para ver os detalhes.

![Captura de tela dos dados de sessão do usuário de análise de chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>O que cada função Teams suporte faz?

O **Teams de comunicações** (suporte à Camada 1) lida com problemas básicos de qualidade de chamada. Eles não investigam problemas com reuniões. Em vez disso, eles coletam informações relacionadas e, em seguida, escalam para um engenheiro de suporte Teams comunicações.

O **Teams** de suporte de comunicações (suporte à Camada 2) vê informações em logs de chamadas detalhados que estão ocultos do especialista em suporte Teams comunicações. A tabela a seguir lista as informações disponíveis para cada função Teams de suporte de comunicação.

A tabela a seguir informa quais informações por usuário estão disponíveis para cada função de suporte de comunicações.

|Atividade|Informações|Quais são as comunicações<br>especialista *em* suporte vê|Quais são as comunicações<br>o *engenheiro de* suporte vê|
|---|---|---|---|
|**Chamadas**|Nome do chamador|Somente o nome do usuário para o qual o agente pesquisou.|Nome de usuário.|
||Nome do destinatário|Mostra como Usuário Interno ou Usuário Externo.|Nome do destinatário.|
||Número de telefone do chamador|O número de telefone inteiro, exceto os últimos três dígitos, é ofuscado com símbolos de asterisco. Por exemplo, 15552823 \* \* \* .|O número de telefone inteiro, exceto os últimos três dígitos, é ofuscado com símbolos de asterisco. Por exemplo, 15552823 \* \* \* .|
||Número de telefone do destinatário|O número de telefone inteiro, exceto os últimos três dígitos, é ofuscado com símbolos de asterisco. Por exemplo, 15552823 \* \* \* .|O número de telefone inteiro, exceto os últimos três dígitos, é ofuscado com símbolos de asterisco. Por exemplo, 15552823 \* \* \* .|
||**Detalhes da chamada** \> **Guia** Avançado|Informações não mostradas.|Todos os detalhes mostrados, como nomes de dispositivo, endereço IP, mapeamento de sub-rede e muito mais.|
||**Detalhes da chamada** \> **Avançado** \> **Guia Depurar**|Informações não mostradas.|Todos os detalhes mostrados, como sufixo DNS e SSID.|
|**Reuniões**|Nomes de participantes|Somente o nome do usuário para o qual o agente pesquisou. Outros participantes identificados como Usuário Interno ou Usuário Externo.|Todos os nomes mostrados.|
||Contagem de participantes|Número de participantes.|Número de participantes.|
||Detalhes da sessão|Detalhes da sessão mostrados com exceções. Somente o nome do usuário para o qual o agente pesquisou é mostrado. Outros participantes identificados como Usuário Interno ou Usuário Externo. Últimos três dígitos de número de telefone ofuscados com símbolos asterisco.|Detalhes da sessão mostrados. Nomes de usuário e detalhes de sessão mostrados. Últimos três dígitos de número de telefone ofuscados com símbolos asterisco.|
||||

> [!NOTE]
> As informações contidas na guia Depuração contêm telemetria e dados de diagnóstico de serviço destinados a ajudar os engenheiros de suporte da Microsoft. Sem o contexto dos dados adicionais disponíveis para dar suporte a engenheiros, pode parecer redundante, impreciso ou confuso. Embora o disponibilizamos para usuários avançados que estão procurando outro nível de detalhes na solução de problemas de chamada, não recomendamos fazer julgamentos com base nos dados sem o suporte da Microsoft.

## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de qualidade de chamada do usuário

1. Abra o Teams de administração ( ) e entre com o suporte Teams comunicações ou <https://admin.teams.microsoft.com> Teams Administrador.

2. No **Painel**, **na** Pesquisa de Usuário, comece a digitar o nome ou o  endereço SIP do usuário cujas chamadas você deseja solucionar problemas ou selecione Exibir usuários para ver uma lista de usuários.

3. Selecione o usuário na lista.

4. Selecione **Histórico de** chamada e selecione a chamada ou a reunião que você deseja solucionar problemas.

5. Selecione a **guia Avançado** e procure itens amarelos e vermelhos que indicam baixa qualidade de chamada ou problemas de conexão.

   Nos detalhes da sessão para cada chamada ou reunião, pequenos problemas aparecem em amarelo. Se algo for amarelo, ele está fora do intervalo normal e pode estar contribuindo para o problema, mas é improvável que seja a principal causa do problema. Se algo estiver vermelho, será um problema significativo e provavelmente será a principal causa da baixa qualidade da chamada para esta sessão.

Em casos raros, os dados de Qualidade da Experiência não são recebidos para sessões de áudio. Muitas vezes, isso é causado por uma chamada descarada ou quando a conexão com o cliente é encerrada. Quando isso ocorre, a classificação de sessão fica **indisponível**.

Para sessões de áudio que têm dados de QoE (Qualidade da Experiência), a tabela a seguir descreve os principais problemas que qualificam uma sessão como **ruim**.

|Problema|Área|Descrição|
|---|---|---|
|Configuração de chamada|Sessão|O código de erro Ms-diag 20-29 indica que a configuração da chamada falhou. O usuário não pôde ingressar na chamada ou na reunião.|
|Chamada ruim classificada de rede de áudio|Sessão|Problemas de qualidade de rede (como perda de pacotes, tremedeira, degradação de NMOS, RTT ou taxa oculta) foram encontrados.|
|Dispositivo que não está funcionando|Dispositivo|Um dispositivo não está funcionando corretamente. As taxas de funcionamento do dispositivo são: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Tópicos relacionados

[Configurar análise de chamada por usuário](set-up-call-analytics.md)
