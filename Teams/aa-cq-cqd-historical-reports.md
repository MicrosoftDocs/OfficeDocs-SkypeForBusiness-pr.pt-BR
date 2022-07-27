---
title: Relatório histórico de fila & atendedor automático
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: b9bb3cf0990058cd16ed35d52d07f63be6cd90fb
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024004"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Relatório histórico de fila & atendedor automático

O Atendedor Automático do Teams & relatório histórico da fila de chamadas do Power BI fornece os três relatórios a seguir:

- [Atendedor](media/cqd-teams-aa-cq-historical-report-sample-aa.png) Automático – mostrando a análise para chamadas que vêm para seus Atendedores Automáticos.
- [Fila de](media/cqd-teams-aa-cq-historical-report-sample-cq.png) Chamadas – mostrando a análise para chamadas que vêm para suas Filas de Chamadas.
- [Linha do tempo do](media/cqd-teams-aa-cq-historical-report-sample-at.png) agente – mostrando uma exibição de linha do tempo dos agentes que estão ativos em chamadas da Fila de Chamadas.

Esses relatórios usam dados do armazenamento [de dados do Painel de Qualidade de](CQD-Power-BI-query-templates.md) Chamada. Os relatórios permitem que as organizações relatem o número de chamadas que estão sendo processadas por atendedores automáticos e filas de chamadas.  Os relatórios também fornecem informações sobre o desempenho do agente nas filas de chamadas.

### <a name="v160-published-on-july-22-2022"></a>V1.60 publicada em 22 de julho de 2022

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
|Fonte de chamada<sup>de entrada 1</sup>        |Distribuição de chamadas por fonte de chamada interna/externa             |
|Totais do método de pesquisa de diretório          |Distribuição de chamadas por tipo de pesquisa                               |
|Ação do chamador                           |Distribuição de chamadas por receptor de chamada                             |
|Resultado da chamada                             |Distribuição de chamadas por estado de chamada final                          |
|Contagem de ações do chamador                     |Distribuição de chamadas por ação de número usada durante a chamada        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório     |Filtro Global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Atendedor Automático        |fAutoAttendant        |AAStartTime está dentro dos últimos 28 dias |


|Nome da tabela de relatório            |Nome da Tabela de Origem            |Processamento       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Linhas Filtradas" = Table.SelectRows(Source, each true), <br>#"Atendedor Automático" = Table.AddColumn(#"Filtered Rows", "AA Name", each List.First(Text.Split([AAIdentity], "@"))), <br>#"Changed Type" = Table.TransformColumnTypes(#"Auto Attendant",{{"AAStartTime", type datetime}}), <br>#"Colunas Removidas" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|Seção Relatório                                  |Campos usados                              |Filtros Aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Seletor de data                                   |AAStartTime                                |Nenhum                |
|Atendedor Automático                                  |Nome do AA                                    |Nenhum                |
|Fonte de chamada<sup>de entrada 1</sup>                |Tipo de Chamada<br>TotalCallCount                |Chamadas externas: o tipo de chamada é externo<br>Chamadas internas: o tipo de chamada é interno |
|Totais do método de pesquisa de diretório                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod é abs_search_dtmf ou abs_search_name    |
|Ações do chamador                                  |AATransferAction<br>TotalCallCount         |Nenhum                                                             |
|Média de segundos no AA<br>Média de ações do chamador |AAChainDuration<br>AACallerActionCount     |Nenhum                                                             |
|Resultados da chamada                                    |AACallResult<br>TotalCallCount             |Nenhum                                                             |
|Contagem de ações do chamador                            |AACallerActionCount<br>TotalCallCount      |Nenhum                                                             |
|Seção inferior do relatório                         |Nome do AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de Chamada<br>TotalCallCount |Nenhum                |

#### <a name="fautoattendant-cqd-fields-description"></a>Descrição dos campos CQD fAutoAttendant

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome do AA                                 |Texto                     |Nome da conta de recurso anexada ao Atendedor Automático<br><br>Se o nome completo da Conta de Recurso **aa_test@microsoft.com**, esse valor será: **aa_test** |
|AACallerActionCount                     |Número inteiro             |Resumir: Soma<br>Contagem de ações selecionadas pelo chamador no Atendedor Automático durante a chamada  |
|AACallFlow                              |Texto                     |Encapsula os diferentes estados da Chamada de Atendedor Automático – valores possíveis:<br><br>§ abs_search<br>§ comunicado<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texto                     |Resultado final da chamada – valores possíveis:<br><br>§ failed_to_establish_media (não foi possível estabelecer a parte de mídia da chamada)<br>§ failover_to_operator (chamada transferida para o operador normalmente devido a um erro do sistema)<br>§ oaa_chain_too_long (muitas pernas no AA)<br>§ oaa_session_too_long (a sessão do AA durou muito tempo)<br>§ service_declined (AA não aceitou a chamada)<br>§ service_terminated (a configuração do AA desconecta a chamada)<br>§ terminated_automatic_selection (a configuração do AA desconecta as chamadas)<br>§ terminated_no_operator (chamada encerrada devido a erro nenhum operador definido) <br>§ terminated_transfer_failed (chamada encerrada como falha na transferência - normalmente para número expernal)<br>***§ transferred_to_operator*** (a chamada foi transferida para o operador - normalmente devido a um erro de entrada do usuário)<br>§ transferred_to_receptionist (o mesmo que transferred_to_operator)<br>§ transferred_to_self (a chamada foi retornada para o início do AA - normalmente de uma opção de anúncio de menu)<br>§ transferred_to_shared_voicemail (a chamada foi transferida para a caixa postal compartilhada)<br>§ transferred_to_user (a chamada foi transferida para um usuário – inclui filas de chamadas)<br>§ desconhecido (ocorreu um erro desconhecido)<br>§ user_terminated (chamador desligado) |
|AAChainDuration                         |Número decimal           |Resumir: Soma<br>Duração da chamada no Atendedor Automático                     |
|AAChainIndex                            |Texto                     |                                                                         |
|AAConnectivityType                      |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Texto                     |Número de Atendedores Automáticos envolvidos na chamada                               |
|AADirectorySearchMethod                 |Texto                     |Último método de pesquisa de catálogo de endereços – valores possíveis:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Data/hora                |Hora de início da chamada do Atendedor Automático                                           |
|AATransferAction                        |Texto                     |Tipo de destino de transferência de chamada – valores possíveis:<br><br>***§ aplicativo - entidade de aplicativo de** _<br>voz§ external_pstn<br>_*_§ hunt_group - Entidade fila_*_<br>_* de chamadas _§ orgaa - entidade Atendedor Automático Organizacional_**<br>§ shared_voicemail<br>§ desconhecido<br>§ usuário |
|Tipo de Chamada<sup>1</sup>                   |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ Externo<br>§ Interno         |
|IsAAInvolved                            |Texto                     |Sempre 1                                                                 |
|PSTNMinutes                             |Número inteiro             |Resumir: Soma<br>Uso total de minutos                                     |
|TotalCallCount                          |Número inteiro             |Resumir: Soma<br>Sempre 1 – usado para fornecer a soma de todas as chamadas            |


### <a name="cloud-call-queue-analytics"></a>Análise de Fila de Chamadas na Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Fonte de chamada<sup>de entrada 1</sup>        |Distribuição de chamada por fonte de chamada interna/externa              |
|Volume da chamada                             |Distribuição de chamadas por filas de chamadas                                |
|Resultado do chamador                           |Distribuição de chamada por resultado de chamada                                |
|Ação total de chamada de tempo limite/estouro      |Distribuição de chamada NÃO encaminhada (abandonada) por resultado da chamada       |
|Totais de destino de transferência/encaminhamento          |Distribuição da chamada encaminhada pelo resultado da chamada                      |
|Taxa de chamadas abandonadas                   |Proporção de contagem de chamadas abandonadas com êxito                        |
|Comprimento médio da sessão (segundos)        |Comprimento da chamada em segundos agrupado por chamadas abandonadas/bem-sucedidas       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório         |Nomes de tabela de relatório                                                          |Filtro Global |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Fila de Chamadas         |Datas<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Nenhum          |
 
|Nome da tabela de relatório            |Nome da Tabela de Origem            |Processamento       |
|:----------------------------|:----------------------------|:----------------|
|Datas                        |Datas                        |Nenhum             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Colunas Removidas" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Removed Columns") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Nenhum             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Nenhum             |

|Seção Relatório                      |Tabela -> campos usados                |Filtros Aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Seletor de data                       |Dates -> DateTime                     |Nenhum                  |
|Chamar Identidade da Fila                 |dCQ-CQIdentity -> de Fila de Chamadas |Nenhum                  |
|Fonte de chamada<sup>de entrada 1</sup>    |fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> tipo de chamada    |Chamadas externas: o tipo de chamada é externo<br>Chamadas internas: o tipo de chamada é interno |
|Tempo médio de espera                    |fCallQueueFinalStateAction -> duração média da chamada (segundos) |Antes da transferência: o resultado da chamada da fila de chamadas agent_joined_conference ou transferred_to_agent<br>Antes de desligar: o resultado da chamada à fila de chamadas não agent_joined_conference ou transferred_to_agent |
|Resultado da chamada                         |fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> chamada da fila de chamada | Nenhum |
|Ação total de chamadas de tempo limite/estouro |fCallQueueFinalStateAction -> chamada<br>fCallQueueFinalStateAction -> estado final da fila de chamada |A Ação de Estado Final da Fila de Chamadas não está encaminhada |
|Totais de destino transfer/Forard       |fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> de Destino da Fila de Chamadas |Nenhum |
|Volumes de chamada                        |fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> de Chamada<br>fCallQueueAnalytics -> Data |Nenhum |
|Chamadas abandonadas                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> chamada<br>fCallQueueAnalytics -> Data<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned é True |
|Comprimento médio da sessão (segundos)    |fCallQueueFinalStateAction -> Duração Média da Chamada<br>fCallQueueFinalStateAction -> Data<br>fCallQueueFinalStateAction -> IsAbandoned |Nenhum |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>Descrição dos campos CQD dCQ-CQIdenity

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Chamar Identidade da Fila                     |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descrição dos campos CQD fCallQueueAnalytics

|Nome                                    |Tipo de dados                |Descrição                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Contagem de chamadas                              |Número inteiro             |Resumir: Soma<br>Número de chamadas                                          |
|Resultado da chamada da fila de chamadas                  |Texto                     |Estado final da chamada da fila de chamadas – valores possíveis:<br><br>§ agent_joined_conference (chamadas de modo de conferência atendidas)<br>§ recusado<br>§ desconectado<br>§ erro<br>§ falhou<br>§ inválido<br>§ estouro (condição de estouro atendida)<br>§ timed_out (condição de tempo limite atendida)<br>§ transferred_to_agent (chamadas de modo de tranfer respondidas {default}) |
|Chamar Identidade da Fila                     |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Tipo de destino da fila de chamadas                  |Texto                     |***Tipo de destino de redirecionamento de chamada – valores possíveis:***<br><br>§ ApplicationEndpoint<br>§ Caixa de correio<br>§ Outros<br>§ Usuário |
|Tipo de Chamada<sup>1</sup>                   |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ Externo<br>§ Interno           |
|Data                                    |Data/hora                |Data e hora de início da chamada da Fila de Chamadas (hora) (UTC)                           | 
|Isabandoned                             |True/false               |True se a chamada não for atendida por um agente                                   |
|Tipo de conectividade PSTN                  |Texto                     |Tipo de chamada – valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall   |
|Total de Minutos PSTN                      |Número inteiro             |Resumir: Soma<br>Uso total de minutos para chamadas PSTN                       |

#### <a name="fcallqueueanalytics-measures-description"></a>Descrição das medidas fCallQueueAnalytics

|Nome                                    |Tipo de dados                |Descrição                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% de chamadas abandonadas***                 |Porcentagem               |Medida: Número de chamadas abandonadas/Total de Chamadas    |
|Total de Chamadas                             |Número inteiro             |Medida: Soma de chamadas atendidas pelo agente        |
|TotalCallCount                          |Número inteiro             |Medida: Soma(Contagem de Chamadas)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Descrição dos campos CQD fCallQueueFinalStateAction

|Nome                                    |Tipo de dados                |Descrição                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duração média da chamada (segundos)         |Número decimal           |Resumir: Soma<br>Duração média da chamada em segundos |
|Contagem de chamadas                              |Número inteiro             |Resumir: Soma<br>Número de chamadas                  |
|Resultado da chamada da fila de chamadas                  |Texto                     |Estado final da chamada da fila de chamadas – valores possíveis:<br><br>§ agent_joined_conference (chamadas de modo de conferência atendidas)<br>§ recusado<br>§ desconectado<br>§ erro<br>§ falhou<br>§ inválido<br>§ estouro (condição de estouro atendida)<br>§ timed_out (condição de tempo limite atendida)<br>§ transferred_to_agent (chamadas de modo de transferência atendidas {default} |
|Ação de Estado Final da Fila de Chamadas           |Texto                     |Ação final da fila de chamadas – valores possíveis:<br><br>§ desconectar (timed_out chamadas)<br>§ disconnect_with_busy (chamadas estouro)<br>§ failed_to_accept_call<br>§ para frente<br>§ shared_voicemail<br>§ outros<br>§ caixa postal |
|Chamar Identidade da Fila                     |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Data                                    |Data/hora                |Data e hora de início da chamada da Fila de Chamadas (hora) (UTC)   |
|Isabandoned                             |True/false               |True se a chamada não for atendida por um agente           |


### <a name="cloud-call-queue-agent-timeline"></a>Linha do tempo do Agente de Fila de Chamadas na Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                                          |Descrição                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Nº de chamadas por agente                                        |Distribuição de chamada por fila de chamadas e agente                 |
|Duração total da chamada (segundos) por agente e Fila de Chamadas   |Duração total (segundos) da chamada por agente e fila de chamadas     |
|Duração média da chamada (segundos) pelo nome do agente           |Duração média (segundos) da chamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório         |Nomes de tabela de relatório        |Filtro Global |
|:------------------|:-------------------------|:-------------|
|Linha do tempo do agente     |fAgentTimelineAnalytics   |Nenhum          |
 
|Nome da tabela de relatório            |Nome da Tabela de Origem            |Processamento       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Tipo Alterado" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Seção Relatório                                |Campos usados                         |Filtros Aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nome do Agente                                    |Nome do Agente                            |Nenhum                  |
|Nome da Fila de Chamadas                               |Nome da Fila de Chamadas                       |Nenhum                  |
|#Calls por agente                               |Nome do Agente<br>Contagem de chamadas<br>Data      |Nenhum                  |
|Distribuição por Agente e Fila de Chamadas          |Nome do Agente<br>Contagem de chamadas<br>Duração da chamada (minutos)<br>Nome da Fila de Chamadas |Nenhum                      |
|Inferior Esquerdo                                   |Nome do Agente<br>Duração Média da Chamada (Segundo)<br>Contagem de chamadas<br>Duração da chamada (minuto)<br>Nome da Fila de Chamadas | Nenhum |
|Duração média da chamada (segundos) pelo nome do agente |Nome do Agente<br>Duração Média da Chamada (Segundo)<br>Contagem de chamadas<br>Duração da chamada (minuto)<br>Nome da Fila de Chamadas | Nenhum |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descrição dos campos CQD fAgentTimelineAnalytics

|Nome                                    |Tipo de dados                |Descrição                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome do Agente                              |Texto                     |UPN do usuário<br>Se o nome de usuário completo **user@microsoft.com**, esse valor será: **usuário** |
|Duração Média da Chamada (Segundo)          |Número decimal           |Resumir: Soma<br>A duração média das chamadas da fila de chamadas atendidas em segundos |
|Contagem de chamadas                              |Número inteiro             |Resumir: Soma<br>Número de chamadas apresentadas ao agente     |
|Duração da chamada (minuto)                  |Número inteiro             |Resumir: Soma<br>Duração total da chamada de chamadas atendidas em minutos (arredondado para baixo até o minuto mais próximo)  |
|Nome da Fila de Chamadas                         |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Data                                    |Data                     |                                                    |


> [!NOTE]
> 1) Este relatório mostra as contagens de chamadas da perspectiva dos agentes e, portanto, o total da contagem de chamadas nesse relatório normalmente será maior do que o número total de chamadas no relatório do **Cloud Call Queue Analytics** . Cada chamada na fila pode ser apresentada a um ou mais agentes pelo menos uma vez antes de ser atendida. Cada chamada da fila de chamadas apresentada a um agente é contada nesse relatório, mesmo que ela não tenha sido atendida pelo agente. A diferença nas contagens de chamadas entre esses dois relatórios é mais pronunciada com a opção **de** roteamento de Atendedor que toca cada agente para cada chamada. 
> 2) Quando uma chamada chega pela primeira vez à primeira fila de chamadas, se o número de chamadas já aguardando nessa fila exceder o limite  de tratamento de estouro de chamada e se a opção de redirecionamento enviar chamadas para uma segunda fila de chamadas, os agentes na segunda fila de chamadas serão mostrados como estando na primeira fila de chamadas neste relatório. 

## <a name="known-issues"></a>Problemas Conhecidos

- A fila de chamadas e os atendedores automáticos são mostrados pela ID da conta de recurso em vez de nomes de fila de chamadas/atendedores automáticos.  Para mostrar todo o tráfego de um atendedor automático ou fila de chamadas, você deve selecionar todas as contas de recursos atribuídas ao atendedor automático ou fila de chamadas.

- Apenas 28 dias de histórico estão disponíveis no painel, pois os dados da fila de chamadas/atendedor automático são considerados dados pessoais e estão sujeitos a políticas de retenção de privacidade de dados.

- Em alguns cenários, a contagem de chamadas atendidas pelo agente no relatório linha do tempo do agente da fila de chamadas na nuvem pode ser diferente do número de chamadas mostradas no histórico de chamadas do cliente do Teams. O histórico de chamadas do cliente do Teams está correto. O suporte está investigando, mas não há tempo estimado para reparo disponível no momento.

- <sup>1 A</sup> **origem da chamada de** entrada nos gráficos do atendedor automático e da fila de chamadas mostra a origem final do segmento de chamada em vez da origem inicial do segmento de chamada. Por exemplo, se um atendedor automático receber uma chamada externa e transferir a chamada para outro atendedor automático ou fila de chamadas,  a origem da chamada de entrada será relatada como Interna.

## <a name="version-history"></a>Histórico de versões
|Versão  |Data da Publicação     |Filename                                                           |Descrição                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.60     |22 de julho de 2022      |Atendedor Automático do CQD Teams & Relatório Histórico da Fila de Chamadas V1.60.pbit |Consulte:<br>Atendedor Automático do CQD Teams & Relatórios Históricos da Fila de Chamadas – Alterar Log.docx no arquivo zip baixado para obter uma lista de alterações                                                                             |
|1.00     |5 de novembro de 2020   |CQ e AA combinados Analytics 20201105.pbit                         |Versão inicial                                     |



