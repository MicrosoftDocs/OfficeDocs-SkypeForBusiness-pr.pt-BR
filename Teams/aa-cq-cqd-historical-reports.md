---
title: Relatório histórico de fila & atendedor automático
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
description: Saiba mais sobre como usar o relatório do Power BI do Painel de Qualidade de Chamada para exibir os dados históricos do Atendedor Automático e da Fila de Chamadas.
ms.openlocfilehash: 23ce3663492ae84175825af4acc3772850935d3b
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614204"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Relatório histórico de fila & atendedor automático

O Atendedor Automático do Teams & relatório histórico da fila de chamadas do Power BI fornece os três relatórios a seguir:

- [Atendedor](media/cqd-teams-aa-cq-historical-report-sample-aa.png) Automático – mostrando a análise para chamadas que vêm para seus Atendedores Automáticos.
- [Fila de](media/cqd-teams-aa-cq-historical-report-sample-cq.png) Chamadas – mostrando a análise para chamadas que vêm para suas Filas de Chamadas.
- [Linha do tempo do](media/cqd-teams-aa-cq-historical-report-sample-at.png) agente – mostrando uma exibição de linha do tempo dos agentes que estão ativos em chamadas da Fila de Chamadas.

Esses relatórios usam dados do armazenamento [de dados do Painel de Qualidade de](CQD-Power-BI-query-templates.md) Chamada. Os relatórios permitem que as organizações relatem o número de chamadas que estão sendo processadas por atendedores automáticos e filas de chamadas.  Os relatórios também fornecem informações sobre o desempenho do agente nas filas de chamadas.

### <a name="v163-published-on-august-24-2022"></a>V1.63 publicada em 24 de agosto de 2022

## <a name="prerequisites"></a>Pré-requisitos

### <a name="power-bi-desktop"></a>Power BI Desktop
Você precisa ter Power BI Desktop instalado. Você pode instalá-lo da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Você pode usar a versão gratuita do Power BI Desktop. A versão mínima compatível é 2.85.681.0 (setembro de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline CQD

A conta usada para exibir o relatório histórico precisa ter permissões para acessar o pipeline de dados CQD. Para obter mais informações, consulte [a função de acesso CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Instalação 

As etapas a seguir pressupõem que você já instalou o Power BI Desktop em seu computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute as seguintes etapas:

- Baixe os [Modelos de Consulta do Power BI CQD](https://www.microsoft.com/download/details.aspx?id=102291) e salve o arquivo zip em um diretório em seu computador.

- Clique duas vezes no arquivo zip para abri-lo.

- Clique duas vezes no arquivo de modelo "Atendedor Automático do CQD Teams & Relatório Histórico da Fila de Chamadas V1.60.pbit". O Power BI Desktop deve ser iniciado.

- Você será solicitado a selecionar a região do pipeline de dados CQD. Selecione a região em que seu locatário está localizado.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de tela selecionando a região do pipeline de dados CQD.":::

- A região em que seu locatário está localizado pode ser obtida usando o cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - A região será exibida após o **/** exemplo acima em que a região é: noam

 - O relatório será iniciado com dados de exemplo.
 
 - Para ver seus próprios dados, selecione **Atualizar** na guia Página Inicial em Consultas Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de tela selecionando a opção atualizar.":::

- Você será solicitado a entrar. Selecione **Conta organizacional** e, em seguida, **selecione Entrar**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de tela mostrando o logon.":::

- Selecione **Conectar** e assista à atualização de dados.

## <a name="data-latency-and-aa--cq-analytics"></a>Latência de dados e análise do AA & CQ

Os dados normalmente estão disponíveis dentro de 30 minutos após a conclusão da chamada; no entanto, há ocasiões em que pode levar várias horas para que os dados sejam exibidos. 

Você precisará atualizar os dados para ver novos dados.

## <a name="customization"></a>Personalização 

Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico e assim por diante.

O relatório contém todas as métricas de dados disponíveis no momento.

### <a name="change-color-schema"></a>Alterar esquema de cor 

As etapas a seguir pressupõem que você já concluiu as etapas de instalação.

Execute as seguintes etapas:
- Selecione **a guia Exibir** na faixa de opções.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de tela selecionando a guia Exibir para alterar o esquema de cores.":::

- Selecione o esquema de cores na lista suspensa.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de tela mostrando vários esquemas de cores.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definições de relatórios históricos do atendedor automático e da fila de chamadas

### <a name="cloud-auto-attendant-analytics"></a>Análise do Atendedor Automático de Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Fonte de Chamada<sup>de Entrada 1</sup>        |Distribuição de chamadas por fonte de chamada interna/externa            |
|Método de Pesquisa de Diretório                 |Distribuição de chamadas por tipo de pesquisa                              |
|Contagem de Ações do Chamador                     |Distribuição de chamadas por ação de número usada durante a chamada       |
|Média de segundos no AA                   |Número médio de segundos que os chamadores gastam no AA                 |
|Média de ações do chamador                  |Número médio de ações que os chamadores executam no AA               |
|Resultados da Chamada                            |Distribuição de chamadas por estado de chamada final                         |
|Seção inferior do relatório                 |Detalhamento do fluxo de chamadas                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório     |Nome da Tabela de Origem            |Filtro Global                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Atendedor Automático        |fAutoAttendant        |AutoAttendant                |Nenhum                                   |

|Seção Relatório                                  |Campos usados                              |Filtros Aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Seletor de data                                   |AAStartTime                                |Nenhum                |
|Seletor de Intervalo de Tempo                             |AAStartHour                                |Nenhum                |
|Atendedor Automático                                  |Nome do AA                                    |Nenhum                |
|Fonte de Chamada<sup>de Entrada 1</sup>                |Tipo de Chamada<br>Soma de TotalCallCount (Medida) |Chamadas externas: o tipo de chamada é externo<br>Chamadas internas: o tipo de chamada é interno |
|Método de Pesquisa de Diretório                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod é abs_search_dtmf ou abs_search_name    |
|Contagem de Ações do Chamador                             |AACallerActionCount<br>TotalCallCount      |Nenhum                                                             |
|Média de segundos no AA                           |AAChainDuration (Medida)                  |Nenhum                                                             |
|Média de ações do chamador                          |AACallerActionCount (Measure)              |Nenhum                                                             |
|Resultados da Chamada                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Nenhum                                       |
|Seção inferior do relatório                         |Nome do AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de Chamada<br>MM-DD<br>TotalCallCount |Nenhum       |

#### <a name="fautoattendant-cqd-fields-description"></a>Descrição dos campos CQD fAutoAttendant

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome do AA                                 |Texto                     |Nome da conta de recurso anexada ao Atendedor Automático<br><br>Se o nome completo da Conta de Recurso **aa_test@microsoft.com**, esse valor será: **aa_test** |
|AACallerActionCount                     |Número inteiro             |Resumir: Soma<br>Contagem de ações selecionadas pelo chamador no Atendedor Automático durante a chamada  |
|AACallerActionCount (Measure)          |Número inteiro             |O mesmo que acima, exceto será 0 se nenhuma chamada em vez de em branco                              |
|AACallFlow                              |Texto                     |Encapsula os diferentes estados da Chamada de Atendedor Automático – valores possíveis:<br><br>§ abs_search<br>§ comunicado<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texto                     |Resultado final da chamada – valores possíveis:<br><br>§ failed_to_establish_media (não foi possível estabelecer a parte de mídia da chamada)<br>§ failover_to_operator (chamada transferida para o operador normalmente devido a um erro do sistema)<br>§ oaa_chain_too_long (muitas pernas no AA)<br>§ oaa_session_too_long (a sessão do AA durou muito tempo)<br>§ service_declined (AA não aceitou a chamada)<br>§ service_terminated (a configuração do AA desconecta a chamada ou chamada suspensa)<br>§ terminated_automatic_selection (a configuração do AA desconecta as chamadas)<br>§ terminated_no_operator (chamada encerrada devido a erro nenhum operador definido) <br>§ terminated_transfer_failed (chamada encerrada como falha na transferência - normalmente para o número externo)<br>§ transfer_in_progress (transferência AA->AA)<br>§ transferred_to_operator (a chamada foi transferida para o operador - normalmente devido a um erro do usuário)<br>§ transferred_to_receptionist (o mesmo que transferred_to_operator)<br>§ transferred_to_self (a chamada foi retornada para o início do AA - normalmente de uma opção de anúncio de menu)<br>§ transferred_to_shared_voicemail (a chamada foi transferida para a caixa postal compartilhada)<br>§ transferred_to_user (a chamada foi transferida para um usuário – inclui filas de chamadas)<br>§ desconhecido (ocorreu uma condição desconhecida)<br>§ user_terminated (chamador desligado) |
|Legenda de chamada AA                          |Texto                     |Configura itens de legenda com base em AACallResult                               |
|AAChainDuration                         |Número decimal           |Resumir: Soma<br>Duração da chamada no Atendedor Automático                     |
|AAChainDuration (Medida)               |Número decimal           |O mesmo que acima, exceto será 0 se nenhuma chamada em vez de em branco              |
|AAChainIndex                            |Texto                     |                                                                         |
|AAConnectivityType                      |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Texto                     |Número de Atendedores Automáticos envolvidos na chamada                               |
|AADirectorySearchMethod                 |Texto                     |Último método de pesquisa de catálogo de endereços – valores possíveis:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Número decimal           |Hora de início da chamada do Atendedor Automático                                           |
|AAStartTime                             |Data/hora                |Hora de início da chamada do Atendedor Automático                                           |
|AATransferAction                        |Texto                     |Tipo de destino de transferência de chamada – valores possíveis:<br><br>§ aplicativo - entidade de aplicativo de voz<br>§ external_pstn<br>§ hunt_group - Entidade Fila de Chamadas<br>§ orgaa - Entidade atendedor automático<br>§ shared_voicemail<br>§ desconhecido<br>§ usuário |
|Tipo de Chamada<sup>1</sup>                   |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ Externo<br>§ Interno           |
|IsAAInvolved                            |Texto                     |Sempre 1                                                                 |
|MM-DD                                   |Texto                     |Chamada de Atendedor Automático mês-dia                                            |
|PSTNMinutes                             |Número inteiro             |Resumir: Soma<br>Uso total de minutos                                     |
|TotalCallCount                          |Número inteiro             |Resumir: Soma<br>Sempre 1 – usado para fornecer a soma de todas as chamadas            |
|Soma de TotalCallCount (Medida)         |Número inteiro             |O mesmo que acima, exceto será 0 se nenhuma chamada em vez de em branco              |


### <a name="cloud-call-queue-analytics"></a>Análise de Fila de Chamadas na Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Fonte de Chamada<sup>de Entrada 1</sup>        |Distribuição de chamadas por fonte de chamada interna/externa             |
|Tempo médio de espera (segundos)             |Tempo de espera para chamadas atendidas e abandonadas                          |
|Contagem de aceitação do volume de chamadas e do agente      |Distribuição de chamadas por filas de chamadas/Contagem máxima de aceitação do agente  |
|Resultados da Chamada                            |Distribuição de chamadas por resultado de chamada                               |
|Chamadas abandonadas                         |Distribuição de chamadas abandonadas por filas de chamadas                     |
|Comprimento médio da sessão (segundos)        |Comprimento da chamada em segundos agrupado por resultado da chamada                      |
|Chamar destinos de estouro/tempo limite      |Distribuição de chamadas que tempo limiteram ou estouraram                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório                                   |Nome da Tabela de Origem                               |Filtro Global       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Fila de Chamadas            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Nenhum                |

|Seção Relatório                      |Tabela -> campos usados                |Filtros Aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Seletor de data                       |fCallQueueAnalytics -> Data           |Nenhum                  |
|Seletor de Intervalo de Tempo                 |fCallQueueAnalytics -> CQHour         |Nenhum                  |
|Conta de Recurso da Fila de Chamadas         |fCallQueueAnalytics -> CQ Name        |Nenhum                  |
|Fonte de chamada<sup>de entrada 1</sup>    |fCallQueueAnalytics -> soma da contagem de chamadas (medida)<br>fCallQueueAnalytics -> tipo de chamada    |Chamadas externas: o tipo de chamada é externo<br>Chamadas internas: o tipo de chamada é interno |
|Tempo médio de espera (segundos) - Antes de Responder |fCallQueueFinalStateAction -> média de duração média de CQ (medida) |O resultado da chamada à fila de chamadas agent_joined_conference ou transferred_to_agent|
|Tempo médio de espera (segundos)-Antes de Abandonado |fCallQueueFinalStateAction -> média de duração média da chamada (medida) |O resultado da chamada à fila de chamadas não agent_joined_conference, transferred_to_agent, estouro, timed_out |
|Volume de chamadas e contagem de Opt-In agente   |fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> agente de fila de chamada aceitar contagem<br>fCallQueueAnalytics -> CQ Name<br>fCallQueueAnalytics -> Data |Nenhum |
|Chamadas abandonadas                     |fCallQueueAnalytics -> Data<br>fCallQueueAnalytics -> TotalCallCount | A legenda do resultado da chamada da fila de chamadas está abandonada |
|Comprimento médio da sessão (segundos)    |fCallQueueFinalStateAction -> duração média da fila de chamadas (s)<br>Legenda do resultado da chamada da fila de chamadas |Duração Média da Fila de Chamadas (s) > 0 |
|Chamar destinos de estouro/tempo limite  |fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> de Destino da Fila de Chamadas<br>Legenda do tipo de destino fCallQueue |A Legenda do Tipo de Destino da Fila de Chamadas não contém Abandonado e Agente Atendido |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descrição dos campos CQD fCallQueueAnalytics

|Nome                                    |Tipo de dados                |Descrição                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Contagem de chamadas                              |Número inteiro             |Resumir: Soma<br>Número de chamadas                                          |
|Contagem de Agentes de Fila de Chamadas                  |Número inteiro             |Resumir: Soma<br>Número de agentes configurados na fila de chamadas            |
|Contagem de Aceitação do Agente de Fila de Chamadas           |Número inteiro             |Resumir: Soma<br>Número de agentes aceitos na fila de chamadas              |
|Resultado da chamada da fila de chamadas                  |Texto                     |Estado final da chamada da fila de chamadas – valores possíveis:<br><br>§ agent_joined_conference (chamadas de modo de conferência atendidas)<br>§ recusado<br>§ desconectado<br>§ erro<br>§ falhou<br>§ inválido<br>§ estouro (condição de estouro atendida)<br>§ timed_out (condição de tempo limite atendida)<br>§ transferred_to_agent (chamadas de modo de transferência respondidas {default}) |
|Legenda do resultado da chamada da fila de chamadas           |Texto                     |Configura itens de legenda com base no resultado da fila de chamadas                             |
|Tipo de destino da fila de chamadas                  |Texto                     |***Tipo de destino de redirecionamento de chamada – valores possíveis:***<br><br>§ ApplicationEndpoint<br>§ Caixa de correio<br>§ Outros<br>§ Usuário |
|Legenda do tipo de destino da fila de chamada           |Texto                     |Configura itens de legenda com base no Tipo de Destino da Fila de Chamadas                        |
|Tipo de Chamada<sup>1</sup>                   |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ Externo<br>§ Interno             |
|Nome CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Hora do CQ                                 |Número Inteiro             |Hora de início da chamada da fila de chamadas                                                 |
|Data                                    |Data/hora                |Data e hora de início da chamada da fila de chamadas (hora)                                 | 
|DateTimeCQName                          |Texto                     |Chave exclusiva para filtragem em fCallQueueFinalStateAction                     |
|Tipo de conectividade PSTN                  |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall     |
|Total de Minutos PSTN                      |Número inteiro             |Resumir: Soma<br>Uso total de minutos para chamadas PSTN                       |
|Soma da Contagem de Chamadas (Medida)             |Número inteiro             |Mesmo que a Contagem de Chamadas, no entanto, será 0 quando nenhuma chamada                          |
|TotalCallCount (Medida)                |Número Inteiro             |Resumir: Soma<br>Contagem de chamadas                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Descrição dos campos CQD fCallQueueFinalStateAction

|Nome                                    |Tipo de dados                |Descrição                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duração média da chamada (segundos)         |Número decimal           |Resumir: Soma<br>Duração média da chamada em segundos para chamadas abandonadas    |
|Duração Média da Fila de Chamadas (s)       |Número decimal           |Resumir: Soma<br>Espera média em segundos para chamadas atendidas           |
|Média de Duração Média da Chamada (Medida)  |Número inteiro             |Mesmo que a Duração Média da Chamada (Segundos), no entanto, será 0 quando nenhuma chamada   |
|Média de Duração Média de CQ (Medida)    |Número inteiro             |Mesmo que a Duração Média da Fila de Chamadas (s), no entanto, será 0 quando nenhuma chamada |
|Contagem de chamadas                              |Número inteiro             |Resumir: Soma<br>Número de chamadas                                         |
|Resultado da chamada da fila de chamadas                  |Texto                     |Estado final da chamada da fila de chamadas – valores possíveis:<br><br>§ agent_joined_conference (chamadas de modo de conferência atendidas)<br>§ recusado<br>§ desconectado<br>§ erro<br>§ falhou<br>§ inválido<br>§ estouro (condição de estouro atendida)<br>§ timed_out (condição de tempo limite atendida)<br>§ transferred_to_agent (chamadas de modo de transferência atendidas {default} |
|Legenda do resultado da chamada da fila de chamadas           |Texto                     |Configura itens de legenda com base no resultado da chamada da fila de chamadas                      |
|Ação de Estado Final da Fila de Chamadas           |Texto                     |Ação final da fila de chamadas – valores possíveis:<br><br>§ desconectar (timed_out chamadas)<br>§ disconnect_with_busy (chamadas estouro)<br>§ failed_to_accept_call<br>§ para frente<br>§ shared_voicemail<br>§ outros<br>§ caixa postal                |
|Nome CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Data                                    |Data/hora                |Data e hora de início da chamada da Fila de Chamadas (hora)                                 |
|DateTimeCQName                          |Texto                     |Chave exclusiva para filtragem em fCallQueueFinalStateAction                     |
|Isabandoned                             |True/false               |True se a chamada não for atendida por um agente                                   |


### <a name="cloud-call-queue-agent-timeline"></a>Linha do tempo do Agente de Fila de Chamadas na Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                                          |Descrição                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Número de chamadas por agente                                |Distribuição de chamadas por fila de chamadas e agente                |
|Distribuição por agente e toda a fila                     |Distribuição de chamadas por agente e fila de chamadas                |
|Tabela (parte inferior direita)                                    |Distribuição de chamadas por agente com duração média e total de chamadas |
|Duração Média da Chamada (segundos) por Agente                |Duração média (segundos) da chamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório           |Nome da Tabela de Origem         |Filtro Global       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Linha do tempo do agente        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Nenhum                |


|Seção Relatório                                |Campos usados                         |Filtros Aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Seletor de data                                 |Datetime                              |Nenhum                  |
|Seletor de nome de usuário do agente                       |Nome do Agente                            |Nenhum                  |
|Seletor de Contas de Recursos da Fila de Chamadas          |Nome CQ                               |Nenhum                  |
|Número de chamadas por agente                      |Nome do Agente<br>Contagem de chamadas<br>Hora      |Nenhum                  |
|Distribuição por Agente e Fila de Chamadas          |Nome do Agente<br>Duração média de chamadas (segundos)<br>Contagem de chamadas<br>Nome CQ |Nenhum                      |
|Inferior Esquerdo                                   |Nome do Agente<br>Duração média da chamada (segundos)<br>Contagem de chamadas<br>Duração da chamada (minuto)<br>Nome CQ<br>Hora<br>MM-DD | Nenhum |
|Duração média da chamada (segundos) por agente      |Nome do Agente<br>Duração média da chamada (segundos) | Nenhum |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descrição dos campos CQD fAgentTimelineAnalytics

|Nome                                    |Tipo de dados                |Descrição                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome do Agente                              |Texto                     |UPN do usuário<br>Se o nome de usuário completo **user@microsoft.com**, esse valor será: **usuário** |
|Duração média da chamada (segundos)         |Número decimal           |Resumir: Soma<br>A duração média das chamadas da fila de chamadas atendidas em segundos |
|Contagem de chamadas                              |Número inteiro             |Resumir: Soma<br>Número de chamadas atendidas pelo agente     |
|Duração da chamada (minutos)                 |Número inteiro             |Resumir: Soma<br>Duração total da chamada de chamadas atendidas em minutos (arredondado para baixo até o minuto mais próximo)  |
|Nome CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Data                                    |Data                     |Data da chamada                                             |
|Datetime                                |Datetime                 |Data da chamada                                             |
|Hora                                    |Número inteiro             |Hora da chamada                                             |
|MM-DD                                   |Texto                     |Mês e dia da chamada                                    |


> [!NOTE]
> Quando uma chamada chega à primeira fila de chamadas, se o número de chamadas já aguardando nessa fila tiver atingido o limite de  tratamento de estouro de chamada e se a opção de redirecionamento enviar novas chamadas para uma segunda fila de chamadas, os agentes na segunda fila de chamadas serão mostrados como estando na primeira fila de chamadas neste relatório. 

## <a name="known-issues"></a>Problemas Conhecidos

- A fila de chamadas e os atendedores automáticos são mostrados pela ID da conta de recurso em vez de nomes de fila de chamadas/atendedores automáticos.  Para mostrar todo o tráfego de um atendedor automático ou fila de chamadas, você deve selecionar todas as contas de recursos atribuídas ao atendedor automático ou fila de chamadas.

- Apenas 28 dias de histórico estão disponíveis no painel, pois os dados da fila de chamadas/atendedor automático são considerados dados pessoais e estão sujeitos a políticas de retenção de privacidade de dados.

- Em alguns cenários, a contagem de chamadas atendidas pelo agente no relatório linha do tempo do agente da fila de chamadas na nuvem pode ser diferente do número de chamadas mostradas no histórico de chamadas do cliente do Teams. O histórico de chamadas do cliente do Teams está correto. O suporte está investigando, mas não há tempo estimado para reparo disponível no momento.

- <sup>1 A</sup> **origem da chamada de** entrada nos gráficos do atendedor automático e da fila de chamadas mostra a origem final do segmento de chamada em vez da origem inicial do segmento de chamada. Por exemplo, se um atendedor automático receber uma chamada externa e transferir a chamada para outro atendedor automático ou fila de chamadas,  a origem da chamada de entrada será relatada como Interna.

## <a name="version-history"></a>Histórico de versões
|Versão  |Data da Publicação     |Filename                                                           |Descrição                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.63     |24 de agosto de 2022    |Atendedor Automático do CQD Teams & Relatório Histórico da Fila de Chamadas V1.63.pbit |Consulte:<br>Atendedor Automático do CQD Teams & Relatórios Históricos da Fila de Chamadas – Alterar Log.docx no arquivo zip baixado para obter uma lista de alterações                                                                             |
|1.60     |22 de julho de 2022      |Atendedor Automático do CQD Teams & Relatório Histórico da Fila de Chamadas V1.60.pbit |Consulte:<br>Atendedor Automático do CQD Teams & Relatórios Históricos da Fila de Chamadas – Alterar Log.docx no arquivo zip baixado para obter uma lista de alterações                                                                             |
|1.00     |5 de novembro de 2020   |CQ e AA combinados Analytics 20201105.pbit                         |Versão inicial                                     |



