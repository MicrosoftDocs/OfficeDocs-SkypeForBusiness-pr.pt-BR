---
title: Relatórios históricos atualizados de atendimento automático e fila de chamadas
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: Saiba mais sobre como usar o relatório histórico do Power BI do Relatório Histórico de Fila de Chamadas & Do Teams atualizado para exibir dados históricos do Assistente Automático e da Fila de Chamadas.
ms.openlocfilehash: 780d6057960c96713ac67be3e189d7982fd2fa46
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176688"
---
# <a name="updated-auto-attendant-and-call-queue-historical-reports"></a>Relatórios históricos atualizados de atendimento automático e fila de chamadas

>[!NOTE]
> Os clientes GCC HIgh e DOD devem continuar a usar a V1.63 do [Auto Attendant & Relatórios Históricos da Fila de Chamadas (CQD)](aa-cq-cqd-historical-reports-v163.md).

Este modelo do Power BI fornece três relatórios que permitem que as organizações informem sobre o número de chamadas que estão sendo processadas por atendentes automáticos e filas de chamadas.  Ele também fornece insights de desempenho do agente.

## <a name="v304-published-on-november-18-2022"></a>V3.0.4 publicado em 18 de novembro de 2022

O modelo do Power BI do Relatório Histórico da Fila de Chamadas & Do Teams fornece os seguintes três relatórios:

- O relatório do [Atendente Automático](media/aa-cq-historical-report-sample-aa-v304.png) mostra a análise de chamadas que chegam aos seus atendentes automáticos.
- O relatório [Fila de Chamadas](media/aa-cq-historical-report-sample-cq-v304.png) mostra a análise de chamadas que entram em suas filas de chamada.
- O relatório [Linha do Tempo do Agente](media/aa-cq-historical-report-sample-at-v304.png) mostra uma exibição de linha do tempo de agentes ativos em chamadas de fila de chamadas.

Esses relatórios usam dados do serviço VAAC (Voice Applications Analytics Collector).

## <a name="v3xx-prerequisites"></a>Pré-requisitos V3.x.x

### <a name="power-bi-desktop"></a>Power BI Desktop

Você precisa ter Power BI Desktop instalado. Você pode instalar e usar a versão gratuita do [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

A versão mínima compatível é 2.85.681.0 (setembro de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline do CQD

Embora essa versão dos relatórios não use o pipeline de dados CQD (Painel de Qualidade de Chamada), a conta usada para exibir os dados históricos ainda requer acesso ao Painel de Qualidade de Chamada. Para obter mais informações, confira [Função de acesso do CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

- Esse requisito será removido em uma versão futura.

## <a name="v3xx-installation"></a>Instalação do V3.x.x 

As etapas a seguir pressupõem que você já instalou Power BI Desktop em seu computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute as seguintes etapas:

1. Baixe e salve o arquivo [V3.0.4.zipHistórico de Fila de Chamadas & Do Teams ](https://www.microsoft.com/download/details.aspx?id=104623) no computador.

2. Abra o arquivo zip.

3. Abra o arquivo de `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` modelo. Power BI Desktop deve ser iniciado.

4. Você será solicitado a selecionar a **Fonte de Dados**.  Selecione a `api.interfaces.records.teams.microsoft.com` entrada.

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="Captura de tela selecionando o api.interfaces.records.teams.microsoft.com Data Soure":::

5. Você será solicitado a entrar com uma conta. Selecione **Conta organizacional** e selecione **Entrar**.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="Captura de tela mostrando o logon do V3.0.0.":::

6. Selecione **Conectar** e os dados serão atualizados.

> [!NOTE]
> Se você estiver usando v1.63 ou anterior, poderá encontrar um erro quando v3.x.x tentar recuperar os dados do VAAC.  Para resolver esse erro, é necessário limpar todas as credenciais anteriores do Power BI.
> 
> 1. Abra o modelo v3.x.x para limpar o erro. 
> 1. Selecione Opções **de Arquivo** > **& Configurações Configurações** > **De origem de dados**.
> 1. Selecione a lista suspensa para **Limpar Permissões** e selecione **Limpar Todas as Permissões**.
> 1. Feche o modelo depois que eles forem desmarcados e reinicie o Power BI. Você será solicitado a autorizar novamente. 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>Latência de dados para o atendimento automático e análise de fila de chamadas

Normalmente, os dados estão disponíveis dentro de 30 minutos após a conclusão da chamada; no entanto, há ocasiões em que pode levar várias horas para que os dados apareçam. 

Você precisará atualizar os dados para ver novos dados.

## <a name="customization"></a>Personalização 

Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico e muito mais.

O relatório contém todas as métricas de dados disponíveis no momento.

### <a name="change-color-schema"></a>Alterar esquema de cores 

As etapas a seguir pressupõem que você já concluiu as etapas de instalação.

Execute as seguintes etapas:

1. Selecione **Exibir guia** na faixa de opções.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Captura de tela selecionando a guia exibir para alterar o esquema de cores.":::

2. Selecione o esquema de cores na lista suspensa.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Captura de tela mostrando vários esquemas de cores.":::
  
## <a name="dimensions-and-measurements"></a>Dimensões e medidas

### <a name="common-dimensions"></a>Dimensões comuns

Essas dimensões são comuns a atendentes automáticos e filas de chamadas:

|Nome (Tipo)                                            |Valores possíveis                |Descrição                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|ConferenceId<br>(Texto)                                 |GUID                           |Identificador de chamada                                                   |
|Data<br>(DateTime)                                     |                               |Data de chamada (UTC)                                                |
|DialogId<br>(Texto)                                     |GUID                           |Identificador de chamada                                                   |
|Documentid<br>(Texto)                                   |GUID                           |Identificador de chamada                                                   |
|Duração<br>(Número inteiro)                             |                               |Duração da chamada, em segundos                                      |
|EndTime<br>(DateTime)                                  |                               |Chamada temporal encerrada (UTC)                                             |
|FirstIsCaller<br>(Booliano)                             |                               |                                                                  |
|FirstUPN<br>(Texto)                                     |                               |                                                                  |
|Hora<br>(Texto)                                         |                               |Chamada de hora iniciada (UTC)                                           |
|Minuto<br>(Texto)                                       |                               |Chamada minuciosa iniciada (UTC)                                         |
|PSTNCallDuration<br>(Número inteiro)                     |                               |                                                                  |
|PSTNCallType<br>(Texto)                                 |                               |                                                                  |
|                                                       |Externo                       |                                                                  |
|                                                       |Interno                       |                                                                  |
|PSTNConnectivityType<sup>1</sup><br>(Texto)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|Segundo<br>(Texto)                                       |                               |Segunda chamada iniciada (UTC)                                         |
|SecondUPN<br>(Texto)                                    |                               |                                                                  |
|TenantId<br>(Texto)                                     |                               |ID do locatário                                                         |
|Timestamp<br>(DateTime)                                |                               |O registro de tempo foi gravado (UTC)                                     |
|UserStartTimeUTC<br>(DateTime)                         |                               |Chamada temporal iniciada (UTC)                                           |

- <sup>1</sup> **PSTNConnectivityType** mostrará a fonte final da etapa de chamada em vez da fonte inicial da etapa de chamada. Por exemplo, se um atendente automático receber uma chamada externa e transferir a chamada para outro atendente automático ou fila de chamadas, a **fonte de chamada de entrada** será relatada como **Interna**.


### <a name="auto-attendant-dimensions"></a>Dimensões do atendente automático

|Nome (Tipo)                                            |Valores possíveis                |Descrição                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br>(Texto)                        |                               |Encapsula os diferentes estados da chamada do Atendente Automático          |
|                                                       |abs_search                     |                                                                  |
|                                                       |Anúncio                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br>(Texto)                      |                               |Resultado da chamada final                                                 |
|                                                       |failed_to_establish_media      |A parte da mídia da chamada não pôde ser estabelecida             |
|                                                       |failover_to_operator           |Chamada transferida para o operador normalmente devido a um erro do sistema      |
|                                                       |oaa_chain_too_long             |Muitas pernas no AA                                           |
|                                                       |oaa_session_too_long           |A sessão AA durou muito tempo                                    |
|                                                       |service_declined               |O AA não aceitou a chamada                                         |
|                                                       |service_terminated             |A configuração AA desconecta a chamada ou chamada desligada             |
|                                                       |terminated_automatic_selection |A configuração AA desconecta as chamadas                           |
|                                                       |terminated_no_operator         |Todos encerrados devido ao erro que nenhum operador definiu                   |
|                                                       |terminated_transfer_failed     |Chamada encerrada como falha na transferência - normalmente para número externo |
|                                                       |transfer_in_progress           |Transferência AA->AA                                                   |
|                                                       |transferred_to_operator        |A chamada foi transferida para o operador                                  |
|                                                       |transferred_to_cq              |A chamada foi transferida para a fila de chamadas                                |
|                                                       |transferred_to_receptionist    |O mesmo que transferred_to_operator                                   |
|                                                       |transferred_to_self            |A chamada foi retornada para o início do AA                          |
|                                                       |transferred_to_shared_voicemail |A chamada foi transferida para a caixa postal compartilhada                         |
|                                                       |transferred_to_user            |A chamada foi transferida para um usuário                                    |
|                                                       |Desconhecido                        |Ocorreu uma condição desconhecida                                 |
|                                                       |user_terminated                |O chamador desligou                                                    |
|AutoAttendantCallerActionCounts<br>(Número inteiro)      |                               |                                                                  |
|AutoAttendantChairDurationInSecs<br>(Número Real)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(Número inteiro)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(Número inteiro)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(Texto)           |                               |Método de pesquisa de diretório                                           |
|                                                       |abs_search_dtmf                |Tom de toque                                                        |
|                                                       |abs_search_voice               |Voz                                                             |
|Entidade AutoAttendantId<br>(Texto)                        |                               |A chamada de URI da conta de recurso chegou                              |
|AutoAttendantTransferAction<br>(Texto)                  |                               |Tipo de destino de transferência de chamada                                         |
|                                                       |Aa                             |Transferido para um AA                                              |
|                                                       |Cq                             |Transferido para um CQ                                               |
|                                                       |external_pstn                  |Transferido para um número externo                                 |
|                                                       |caixa postal compartilhada               |Transferido para a caixa postal compartilhada                                   |
|                                                       |Desconhecido                        |Ação desconhecida                                                    |
|HasAA<br>(Booliano)                                     |                               |O AA está envolvido na chamada                                            |


### <a name="call-queue-dimensions"></a>Dimensões da fila de chamadas

|Nome (Tipo)                                            |Valores possíveis                |Descrição                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br>(Número inteiro)                  |                               |Número de agentes na fila de chamadas                                    |
|CallQueueAgentOptInCount<br>(Número inteiro)             |                               |Número de agentes que optaram por entrar na fila de chamadas                           |
|CallQueueCallResult<br>(Texto)                          |                               |Estado final da chamada da fila de chamadas                                       |
|                                                       |agent_joined_conference        |Chamada respondida – CQ do modo de conferência                                |
|                                                       |Recusou                       |                                                                  |
|                                                       |Desconectado                   |                                                                  |
|                                                       |erro                          |                                                                  |
|                                                       |Falhou                         |                                                                  |
|                                                       |Inválido                        |                                                                  |
|                                                       |estouro                      |Condição de estouro atendida                                            |
|                                                       |timed_out                      |Condição de tempo limite atendida                                             |
|                                                       |transferred_to_agent           |Chamada atendida – CQ do modo de transferência                                  |
|CallQueueDurationSeconds<br>(Número Real)              |                               |                                                                  |
|CallQueueFinaleStateAction<br>(Texto)                   |                               |Ação final da fila de chamadas                                           |
|                                                       |Desconectar                     |time_out chamadas                                                    |
|                                                       |disconnect_with_busy           |chamadas estouro                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |Frente                        |                                                                  |
|                                                       |shared_voicemail               |                                                                  |
|                                                       |Outros                          |                                                                  |
|                                                       |Voicemail                      |                                                                  |
|Entidade CallQueueId<br>(Texto)                            |                               |A chamada de URI da conta de recurso chegou                              |
|CallQueueTargetType<br>(Texto)                          |                               |Destino de redirecionamento de chamada                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |Caixa de Correio                        |                                                                  |
|                                                       |Outros                          |                                                                  |
|                                                       |Telefone                          |                                                                  |
|                                                       |Usuário                           |                                                                  |
|HasCQ<br>(Booliano)                                     |                               |O CQ está envolvido na chamada                                            |
|Entidade TransferedFromCallQueueId<br>(Texto)             |                               |                                                                  |

### <a name="measurements"></a>Medidas

|Nome (Tipo)                                            |Valores possíveis                |Descrição                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br>(Número Real)  |                               |                                                                  |
|AvgCallDuration<br>(Número Real)                       |                               |                                                                  |
|AvgCallQueueDurationSeconds<br>(Número Real)           |                               |                                                                  |
|PSTNTotalMinutes<br>(Número Real)                      |                               |                                                                  |
|TotalAudioStreamDuration<br>(Número Real)              |                               |                                                                  |
|TotalCallCount<br>(Número inteiro)                       |                               |                                                                  |

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definições de relatórios históricos de atendimento automático e fila de chamadas

### <a name="cloud-auto-attendant-analytics-report"></a>Relatório do Cloud Auto Attendant Analytics

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Fonte de chamada de entrada                    |Distribuição de chamadas por fonte de chamada interna/externa            |
|Método de Pesquisa de Diretório                 |Distribuição de chamadas por tipo de pesquisa                              |
|Contagem de ações do chamador                     |Distribuição de chamadas por ação numérica usada durante a chamada       |
|Segundos médios no AA                   |Número médio de segundos que os chamadores gastam no AA                 |
|Ações médias de chamador                  |Número médio de ações que os chamadores executam no AA               |
|Chamar resultados                            |Distribuição de chamadas por estado de chamada final                         |
|Seção inferior do relatório                 |Divisão de fluxo de chamada                                               |

#### <a name="report-visual-and-field-mapping"></a>Relatar mapeamento visual e de campo

|Guia Relatório            |Nome da tabela de relatório     |Filtro Global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Atendente Automático        |fAutoAttendant        |Nenhum                                   |

|Seção Relatório                               |Campo(s) Usado                                                                                    |Filtros aplicados |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|Seletor de datas                                |AAStartTime                                                                                      |Nenhum       |
|Seletor de Intervalo de Tempo                          |AAStartHour                                                                                      |Nenhum       |
|Contas de recursos do Atendente Automático             |Nome AA                                                                                          |Nenhum       |
|Fonte de chamada de entrada                         |Tipo de Chamada<br>Soma de TotalCallCount         |Chamadas externas: Tipo de chamada é externo<br>Chamadas internas: Tipo de chamada é interno |
|Método de Pesquisa de Diretório                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod é abs_search_dtmf ou abs_search_name    |
|Contagem de ações do chamador                          |AACallerActionCount<br>TotalCallCount                                                            |Nenhum       |
|Segundos médios no AA                        |AAChainDuration                                                                                  |Nenhum       |
|Ações médias de chamador                       |AACallerActionCount                                                                              |Nenhum       |
|Chamar resultados                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |Nenhum       |
|Seção inferior do relatório                      |MM-DD<br>Nome AA<br>AACallFlow<br>Tipo de Chamada<br>AACallResult<br>TotalCallCount<br>AAChainDuration |Nenhum       |

#### <a name="fautoattendant-field-description"></a>descrição do campo fAutoAttendant

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                 |Texto                     |Nome da conta de recurso anexada ao Atendente Automático<br><br>Se o nome completo da Conta de Recurso for **aa_test@microsoft.com**, esse valor será: **aa_test** |
|AACallerActionCount                     |Número inteiro             |Resumindo: Soma<br>Contagem de ações selecionadas pelo chamador no Atendente Automático durante a chamada  |
|AACallerActionCount (Medida)           |Número inteiro             |O mesmo que acima, exceto, será 0 se nenhuma chamada em vez de em branco                              |
|AACallFlow                              |Texto                     |Confira Dimensões do Atendente Automático -> AutoAttendantCallFlow                                   |
|AACallResult                            |Texto                     |Consulte Dimensões do Atendente Automático -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |Texto                     |Configura itens de legenda com base em AACallResult                                               |
|AAChainDuration                         |Número decimal           |Resumindo: Soma<br>Duração da chamada no Atendente Automático                                     |
|AAChainDuration (Medida)               |Número decimal           |O mesmo que acima, exceto, será 0 se nenhuma chamada em vez de em branco                              |
|AAChainIndex                            |Texto                     |                                                                                         |
|AAConnectivityType                      |Texto                     |                                                                                         |
|AACount                                 |Texto                     |Número de atendentes automáticos envolvidos na chamada                                               |
|AADirectorySearchMethod                 |Texto                     |Consulte Dimensões do Atendente Automático -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |Texto                     |Configura itens de legenda com base em AADirectorySearchMethod                                    |
|AAStartHour                             |Número decimal           |Hora de início da chamada do Atendente Automático                                                           |
|AAStartTime                             |Data/hora                |Hora de início da chamada do Atendente Automático                                                           |
|AATransferAction                        |Texto                     |Consulte Dimensões do Atendente Automático -> AutoAttendantTransferAction                             |
|Tipo<sup>de chamada 1</sup>                   |Texto                     |Consulte Dimensões Comuns -> PSTNCallType                                                    |
|MM-DD                                   |Texto                     |Atendimento Automático chamada mês-dia                                                            |
|PSTNMinutes                             |Número inteiro             |Resumindo: Soma<br>Uso total de minutos                                                     |
|TotalCallCount                          |Número inteiro             |Resumindo: Soma<br>Always 1 – usado para fornecer a soma de todas as chamadas                            |
|Soma de TotalCallCount (Medida)         |Número inteiro             |O mesmo que acima, exceto, será 0 se nenhuma chamada em vez de em branco                              |


### <a name="cloud-call-queue-analytics-report"></a>Relatório do Cloud Call Queue Analytics

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Fonte de chamada de entrada                    |Distribuição de chamadas por fonte de chamada interna/externa             |
|Tempo médio de espera (segundos)             |Tempo de espera para chamadas atendidas e abandonadas                          |
|Contagem de opt-in de volume e agente de chamada      |Distribuição de chamadas por filas de chamada / Contagem máxima de opt-in do agente  |
|Chamar resultados                            |Distribuição de chamadas por resultado de chamada                               |
|Chamadas abandonadas                         |Distribuição de chamadas abandonadas por filas de chamada                     |
|Comprimento médio da sessão (segundos)        |Comprimento da chamada em segundos agrupados por resultado de chamada                      |
|Destinos de estouro/tempo limite de chamada      |Distribuição de chamadas com tempo limite ou estouro                 |


#### <a name="report-visual-and-field-mapping"></a>Relatar mapeamento visual e de campo

|Guia Relatório            |Nome da tabela de relatório                                   |Filtro Global       |
|:---------------------|:---------------------------------------------------|:-------------------|
|Fila de chamadas            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |Nenhum                |

|Seção Relatório                      |Campos de tabela -> usados                |Filtros aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Seletor de datas                       |fCallQueueAnalytics -> Date           |Nenhum                  |
|Seletor de Intervalo de Tempo                 |fCallQueueAnalytics -> CQHour         |Nenhum                  |
|Conta de recurso de fila de chamadas         |fCallQueueAnalytics -> Nome do CQ        |Nenhum                  |
|Fonte de chamada de entrada                |fCallQueueAnalytics -> Soma da Contagem de Chamadas (Medida)  |Chamadas externas: Tipo de chamada é externo<br>Chamadas internas: Tipo de chamada é interno |
|Tempo de espera do Avg (segundos)-Antes de responder |fCallQueueFinalStateAction -> Avg de Duração média do CQ (Medida) |O resultado da chamada de chamada de chamada é agent_joined_conference ou transferred_to_agent|
|Tempo de espera do Avg (segundos)-Antes de Abandonado |fCallQueueFinalStateAction -> Avg de duração média da chamada (medida) |O resultado da chamada de chamada não é agent_joined_conference, transferred_to_agent, estouro, timed_out |
|Contagem de Opt-In de volume e agente   |contagem de chamadas fCallQueueAnalytics -><br>fCallQueueAnalytics -> Agente de Fila de Chamadas Optar em Contagem<br>fCallQueueAnalytics -> Nome do CQ<br>fCallQueueAnalytics -> Date |Nenhum |
|Chamadas abandonadas                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | Legenda do resultado da chamada de fila de chamadas é abandonada |
|Comprimento médio da sessão (segundos)    |fCallQueueFinalStateAction -> Duração média da fila de chamadas (súm)<br>Legenda do resultado da chamada da fila de chamadas |Duração média da fila de chamadas (ss) > 0 |
|Destinos de estouro/tempo limite de chamada  |contagem de chamadas fCallQueueAnalytics -><br>fCallQueueAnalytics -> Tipo de destino da fila de chamadas<br>Legenda do tipo de destino fCallQueue |Legenda do tipo de destino da fila de chamadas não contém Abandonado e Agente Atendido |


#### <a name="fcallqueueanalytics-field-description"></a>descrição do campo fCallQueueAnalytics

|Nome                                    |Tipo de dados                |Descrição                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Contagem de Chamadas                              |Número inteiro             |Resumindo: Soma<br>Número de chamadas                                          |
|Contagem de agentes de fila de chamadas                  |Número inteiro             |Resumindo: Soma<br>Número de agentes configurados na fila de chamadas            |
|Agente de fila de chamadas opte pela contagem           |Número inteiro             |Resumindo: Soma<br>Número de agentes que optaram pela fila de chamadas              |
|Resultado da chamada de chamada de fila                  |Texto                     |Consulte Dimensões da Fila de Chamadas -> CallQueueCallResult                           |
|Legenda do resultado da chamada da fila de chamadas           |Texto                     |Configura itens de legenda com base no Resultado da Fila de Chamadas                            |
|Tipo de destino de fila de chamadas                  |Texto                     |Consulte Dimensões da Fila de Chamadas -> CallQueueTargetType                           |
|Legenda do tipo de destino da fila de chamadas           |Texto                     |Configura itens de legenda com base no Tipo de Destino da Fila de Chamadas                       |
|Tipo de Chamada                               |Texto                     |Consulte Dimensões Comuns -> PSTNCallType                              |
|Nome do CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso estiver **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Hora do CQ                                 |Número Inteiro             |Hora de início da chamada da fila de chamadas                                                 |
|Data                                    |Data/hora                |Data e hora de início da chamada da fila de chamadas (hora)                                 | 
|DateTimeCQName                          |Texto                     |Chave exclusiva para filtragem em fCallQueueFinalStateAction                     |
|Tipo de conectividade PSTN                  |Texto                     |Consulte Dimensões Comuns -> PSTNConnectivityType                              |
|Minutos Totais PSTN                      |Número inteiro             |Resumindo: Soma<br>Uso total de minutos para chamadas PSTN                       |
|Soma da contagem de chamadas (medida)             |Número inteiro             |O mesmo que Contagem de Chamadas, no entanto, será 0 quando nenhuma chamada                          |
|TotalCallCount (Medida)                |Número Inteiro             |Resumindo: Soma<br>Contagem de Chamadas                                               |


#### <a name="fcallqueuefinalstateaction-field-description"></a>descrição do campo fCallQueueFinalStateAction

|Nome                                    |Tipo de dados                |Descrição                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Duração média da chamada (segundos)         |Número decimal           |Resumindo: Soma<br>Duração média da chamada em segundos para chamadas abandonadas     |
|Duração média da fila de chamadas (ss)       |Número decimal           |Resumindo: Soma<br>Tempo médio de espera em segundos para chamadas atendidas       |
|Avg de duração média da chamada (medida)  |Número inteiro             |O mesmo que a duração média da chamada (segundos), no entanto, será 0 quando nenhuma chamada    |
|Avg de duração média do CQ (Medida)    |Número inteiro             |O mesmo que a duração média da fila de chamada (seg) no entanto será 0 quando nenhuma chamada  |
|Contagem de Chamadas                              |Número inteiro             |Resumindo: Soma<br>Número de chamadas                                          |
|Resultado da chamada de chamada de fila                  |Texto                     |Consulte Dimensões da Fila de Chamadas -> CallQueueCallResult                           |
|Legenda do resultado da chamada da fila de chamadas           |Texto                     |Configura itens de legenda com base no Resultado da Chamada de Chamada de Chamada                       |
|Ação de estado final da fila de chamadas           |Texto                     |Consulte Dimensões da Fila de Chamadas -> CallQueueFinaleStateAction                    |
|Nome do CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso estiver **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Hora do CQ                                 |Número                   |Hora em que a chamada ocorreu
|Data                                    |Data/hora                |Data e hora de início da chamada da fila de chamadas (hora)                                 |
|DateTimeCQName                          |Texto                     |Chave exclusiva para filtragem em fCallQueueFinalStateAction                     |
|Isabandoned                             |True/false               |True se a chamada não for atendida por um agente                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>Relatório da Linha do Tempo do Agente de Fila de Chamadas na Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                                          |Descrição                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|Número de chamadas por agente                                |Distribuição de chamadas por fila de chamadas e agente                       |
|Distribuição por agente e todas as filas                     |Distribuição de chamadas por agente e fila de chamadas                       |
|Tabela (inferior esquerdo)                                     |Distribuição de chamadas por agente com duração média e total da chamada |
|Duração média da chamada (segundos) pelo agente (inferior direito) |Duração média (segundos) de chamada por agente                         |

#### <a name="report-visual-field-mapping"></a>Mapear o campo visual de relatório

|Guia Relatório            |Nome da tabela de relatório           |Filtro Global       |
|:---------------------|:---------------------------|:-------------------|
|Linha do Tempo do Agente        |fAgentTimelineAnalytics     |Nenhum                |


|Seção Relatório                                |Campo(s) Usado                         |Filtros aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Seletor de datas                                 |Datetime                              |Nenhum                  |
|Seletor de nome de usuário do agente                       |Nome do agente                            |Nenhum                  |
|Seletor de Contas de Recurso de Fila de Chamadas         |Nome do CQ                               |Nenhum                  |
|Número de chamadas por agente                      |Contagem de Chamadas<br>Nome do agente<br>Data<br>Hora      |Nenhum                  |
|Distribuição por agente e fila de chamadas          |Nome do agente<br>Duração média de chamadas (segundos)<br>Contagem de Chamadas<br>Nome do CQ |Nenhum                      |
|Canto inferior esquerdo                                   |Nome do agente<br>Duração média da chamada (segundos)<br>Contagem de Chamadas<br>Duração da chamada (minuto)<br>Nome do CQ<br>Hora<br>MM-DD | Nenhum |
|Duração média da chamada (segundos) por agente      |Nome do agente<br>Duração média da chamada (segundos) | Nenhum |

#### <a name="fagenttimelineanalytics-field-description"></a>descrição do campo fAgentTimelineAnalytics

|Nome                                    |Tipo de dados                |Descrição                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome do agente                              |Texto                     |UPN do usuário<br>Se o nome de usuário completo estiver **user@microsoft.com**, esse valor será: **usuário** |
|Duração média da chamada (segundos)         |Número decimal           |Resumindo: Soma<br>A duração média das chamadas de fila de chamadas atendidas em segundos |
|Contagem de Chamadas                              |Número inteiro             |Resumindo: Soma<br>Número de chamadas atendidas pelo agente     |
|Duração da chamada (minutos)                 |Número inteiro             |Resumindo: Soma<br>Duração total da chamada de chamadas atendidas em minutos (arredondada para o minuto mais próximo)  |
|Nome do CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso estiver **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Data                                    |Data                     |Data da chamada                                             |
|Datetime                                |Datetime                 |Data da chamada                                             |
|Hora                                    |Número inteiro             |Hora da chamada                                             |
|MM-DD                                   |Texto                     |Mês e dia de chamada                                    |


> [!NOTE]
> Quando uma chamada chega à primeira fila de chamadas, se o número de chamadas já aguardando nessa fila tiver atingido o limite de **tratamento de estouro** de chamada e se a opção de redirecionamento enviar novas chamadas para uma segunda fila de chamadas, os agentes na segunda fila de chamadas serão mostrados como estando na primeira fila de chamadas neste relatório. 

## <a name="known-issues"></a>Problemas conhecidos

- Filas de chamadas e atendentes automáticos são mostrados pela ID da conta de recurso em vez de nomes de fila de chamadas/atendedores automáticos.  Para mostrar todo o tráfego de um atendente automático ou fila de chamadas, você deve selecionar todas as contas de recurso atribuídas ao atendente automático ou à fila de chamadas.

- Apenas 28 dias de histórico estão disponíveis no painel, pois os dados de fila de chamadas/atendimento automático são considerados dados pessoais e estão sujeitos a políticas de retenção de privacidade de dados.

- Em alguns cenários, a contagem de chamadas atendidas pelo agente no relatório **Linha do Tempo do Agente de Fila de Chamadas na Nuvem** pode ser diferente do número de chamadas mostradas no histórico de chamadas do cliente do Teams. O histórico de chamadas do cliente do Teams está correto. O suporte está investigando, mas não há tempo estimado para reparos disponíveis no momento.

## <a name="version-3xx-history"></a>Histórico da versão 3.x.x

Consulte: Assistente Automático do Teams & Relatórios Históricos da Fila de Chamadas – Alterar Log.docx no arquivo zip baixado para obter uma lista detalhada de alterações 

|Versão  |Data Publicada     |Filename                                                           |Descrição                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |18 de novembro de 2022  |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.4        |Erro corrigido, classificação de chamada aprimorada, legenda adicionada |
|3.0.3    |8 de novembro de 2022   |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.3        |Erro corrigido, link de documentação adicionado, consultas otimizadas |
|3.0.1    |26 de outubro de 2022   |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.1        |Entrada de fonte de dados de teste removida                   |
|3.0.0    |25 de outubro de 2022   |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.0        |Nova fonte de dados de back-end                             |
