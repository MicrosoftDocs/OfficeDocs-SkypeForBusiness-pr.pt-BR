---
title: Atendedor Automático & Histórico da Fila de Chamada
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
description: Saiba mais sobre como usar o relatório do Painel de Qualidade de Chamada Power BI para exibir Atendedor Automático dados históricos da Fila de Chamada.
ms.openlocfilehash: 4594a673225a167e762bcfee63067f70e7fe10b4
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249553"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Atendedor Automático & Histórico da Fila de Chamada

O Modelo de Relatório Histórico Teams Atendedor Automático & de Fila de Chamada Power BI do CQD fornece os três relatórios a seguir:

- [Atendedor Automático](media/cqd-teams-aa-cq-historical-report-sample-aa.png) – mostrando a análise das chamadas que vêm para seus Assistentes Automáticos.
- [Fila de](media/cqd-teams-aa-cq-historical-report-sample-cq.png) Chamadas – mostrando a análise das chamadas que vêm em suas Filas de Chamadas.
- [Linha do tempo](media/cqd-teams-aa-cq-historical-report-sample-at.png) do agente – mostrando uma exibição de linha do tempo dos agentes que estão ativos em chamadas de Fila de Chamadas.

Esses relatórios usam dados do armazenamento de dados [do Painel](CQD-Power-BI-query-templates.md) de Qualidade de Chamada. Elas permitem que as organizações informem o número de chamadas que estão sendo processadas pelos atendimentos automáticos e filas de chamadas.  Eles também fornecem informações sobre o desempenho do agente nas filas de chamada.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="power-bi-desktop"></a>Power BI Desktop
Você precisa ter Power BI Desktop instalado. Você pode instalá-lo no [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Você pode usar a versão gratuita do Power BI Desktop. A versão mínima compatível é 2.85.681.0 (setembro de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline do CQD

A conta que você usa para exibir o relatório histórico do AA & CQ Analytics precisa ter permissões para acessar o pipeline de dados CQD. Para obter mais informações, consulte [a função de acesso CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Instalação 

As etapas a seguir pressuem que você já instalou Power BI Desktop no computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute as seguintes etapas:

- Baixe o [CQD Power BI Modelos](https://www.microsoft.com/download/details.aspx?id=102291) de Consulta e salve o arquivo zip em um diretório em seu computador.

- Clique duas vezes no arquivo zip para abri-lo.

- Clique duas vezes no arquivo de modelo "CQ e AA combinado analytics 20201105.pbit" e Power BI Desktop deve iniciar.

- Você será solicitado a selecionar a região do pipeline de dados CQD. Selecione a região onde seu locatário está localizado.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de tela selecionando a região do pipeline de dados CQD.":::

- A região onde seu locatário está localizado pode ser obtida usando o cmdlet [Get-CsTenant.](/powershell/module/skype/get-cstenant)

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - A região será exibida depois do exemplo acima em **/** que há região: noam

 - O relatório será lançado com dados de exemplo.
 
 - Para ver seus próprios dados, selecione **Atualizar** na guia Home em Consultas Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de tela selecionando a opção de atualização.":::

- Em seguida, você será solicitado a entrar. Selecione **Conta da Organização** e, em seguida, selecione **Entrar**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de tela mostrando logon.":::

- Selecione **Conexão** e assista à atualização de dados.

## <a name="data-latency-and-aa--cq-analytics"></a>Latência de dados e análise do AA & CQ

Os dados estarão disponíveis no pipeline de dados CQD dentro de 30 minutos.

Você terá que atualizar os dados para ver os novos dados de análise. 

## <a name="customization"></a>Personalização 

Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico e assim por diante.

Não é possível adicionar campos de dados adicionais ao relatório.

### <a name="change-color-schema"></a>Alterar esquema de cores 

As etapas a seguir pressuem que você já concluiu as etapas de instalação.

Execute as seguintes etapas:
- Selecione **Exibir guia** na faixa de opções.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de tela selecionando a guia exibir para alterar o esquema de cores.":::

- Selecione o esquema de cores na listada.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de tela mostrando vários esquemas de cores.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Atendedor Automático e Definições de Relatórios Históricos da Fila de Chamada

### <a name="cloud-auto-attendant-analytics"></a>Cloud Atendedor Automático Analytics

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Fonte de chamada<sup>de entrada 1</sup>        |Distribuição de chamadas por fonte de chamada interna/externa             |
|Totais do método de pesquisa de diretório          |Distribuição de chamadas por tipo de pesquisa                               |
|Ação do chamador                           |Distribuição de chamadas por receptor de chamada                             |
|Resultado da chamada                             |Distribuição de chamadas por estado de chamada final                          |
|Contagem de ações do chamador                     |Distribuição de chamadas por ação de número usada durante a chamada        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para mapeamento de campo e tabela CQD

|Guia Relatório            |Nome da tabela de relatório     |Filtro Global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Atendedor Automático        |fAutoAttendant        |O AAStartTime está nos últimos 28 dias |


|Nome da tabela de relatório            |Nome da tabela de origem            |Processamento       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Filtered Rows" = Table.SelectRows(Source, each true), <br>#"Atendedor Automático" = Table.AddColumn(#"Filtered Rows", "AA Name", each List.First(Text.Split([AAIdentity], "@")) <br>#"Tipo alterado" = Table.TransformColumnTypes(#"Atendedor Automático",{{"AAStartTime", digite datetime}}), <br>#"Removed Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|Seção Relatório                                  |Field(s) Used                              |Filtros Aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Seletor de data                                   |AAStartTime                                |Nenhum                |
|Atendedor Automático                                  |Nome do AA                                    |Nenhum                |
|Fonte de chamada<sup>de entrada 1</sup>                |Tipo de Chamada<br>TotalCallCount                |Chamadas externas: Tipo de chamada é Externo<br>Chamadas internas: Tipo de chamada é Interno |
|Totais do método de pesquisa de diretório                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod é abs_search_dtmf ou abs_search_name    |
|Ações do chamador                                  |AATransferAction<br>TotalCallCount         |Nenhum                                                             |
|Média de segundos no AA<br>Ações médias do chamador |AAChainDuration<br>AACallerActionCount     |Nenhum                                                             |
|Resultados de chamada                                    |AACallResult<br>TotalCallCount             |Nenhum                                                             |
|Contagem de ações do chamador                            |AACallerActionCount<br>TotalCallCount      |Nenhum                                                             |
|Seção inferior do relatório                         |Nome do AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de Chamada<br>TotalCallCount |Nenhum                |

#### <a name="fautoattendant-cqd-fields-description"></a>Descrição dos campos CQD fAutoAttendant

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome do AA                                 |text                     |Nome da conta de recurso anexada ao Atendedor Automático<br><br>Se o nome completo da conta de recurso **aa_test@microsoft.com** esse valor será: **aa_test** |
|AACallerActionCount                     |número inteiro             |Resumir: Soma<br>Contagem de ações selecionadas pelo chamador Atendedor Automático durante a chamada  |
|AACallFlow                              |text                     |Encapsula os diferentes estados da chamada Atendedor Automático -- valores possíveis:<br><br>§ abs_search<br>§ comunicado<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |text                     |Resultado final da chamada - valores possíveis:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ desconhecido<br>§ user_terminated |
|AAChainDuration                         |número decimal           |Resumir: Soma<br>Duração da chamada em Atendedor Automático                     |
|AAChainIndex                            |text                     |                                                                         |
|AAConnectivityType                      |text                     |Tipo de chamada - valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |text                     |Número de Atendimentos Automáticos envolvidos na chamada                               |
|AADirectorySearchMethod                 |text                     |Método de pesquisa do último livro de endereços - valores possíveis:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |date/time                |Atendedor Automático hora de início da chamada                                           |
|AATransferAction                        |text                     |Tipo de destino de transferência de chamada - valores possíveis:<br><br>***§ application - entidade de aplicativo** de voz §_<br> external_pstn <br>_§ hunt_group -*_Entidade_* fila de chamada _<br>_ * _§ orgaa - Entidade de Atendedor Automático organizacional_**<br>§ shared_voicemail<br>§ desconhecido<br>§ user |
|Tipo de chamada<sup>1</sup>                   |text                     |Tipo de chamada - valores possíveis:<br><br>§ Externo<br>§ Interno         |
|IsAAInvolved                            |text                     |Sempre 1                                                                 |
|PSTNMinutes                             |número inteiro             |Resumir: Soma<br>Uso total de minutos                                     |
|TotalCallCount                          |número inteiro             |Resumir: Soma<br>Sempre 1 - usado para fornecer a soma de todas as chamadas            |


### <a name="cloud-call-queue-analytics"></a>Análise de fila de chamada na nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Fonte de chamada<sup>de entrada 1</sup>        |Distribuição de chamada por fonte de chamada interna/externa              |
|Volume da chamada                             |Distribuição de filas de chamada por chamada                                |
|Resultado do chamador                           |Distribuição do resultado da chamada por chamada                                |
|Ação total de chamada tempo-extra/estouro      |Distribuição de not forwarded(abandoned) call by call result       |
|Totais de destino de transferência/encaminhamento          |Distribuição de chamada encaminhada por resultado de chamada                      |
|Taxa de chamadas abandonadas                   |Taxa de sucesso para contagem de chamada abandonada                        |
|Comprimento médio da sessão (segundos)        |Comprimento da chamada em segundos agrupado por chamadas abandonadas/bem-sucedidas       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para mapeamento de campo e tabela CQD

|Guia Relatório         |Nomes de tabela de relatório                                                          |Filtro Global |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Fila de Chamada         |Datas<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Nenhum          |
 
|Nome da tabela de relatório            |Nome da tabela de origem            |Processamento       |
|:----------------------------|:----------------------------|:----------------|
|Datas                        |Datas                        |Nenhum             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Removed Columns") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Nenhum             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Nenhum             |

|Seção Relatório                      |Table -> Field(s) Used                |Filtros Aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Seletor de data                       |Date -> DateTime                     |Nenhum                  |
|Identidade da Fila de Chamada                 |dCQ-CQIdentity -> De Fila de Chamada |Nenhum                  |
|Fonte de chamada<sup>de entrada 1</sup>    |fCallQueueAnalytics -> Contagem de Chamadas<br>fCallQueueAnalytics -> Tipo de Chamada    |Chamadas externas: Tipo de chamada é Externo<br>Chamadas internas: Tipo de chamada é Interno |
|Tempo de espera avg                    |fCallQueueFinalStateAction -> duração média da chamada (segundos) |Antes da transferência: o resultado da chamada de fila de chamada agent_joined_conference ou transferred_to_agent<br>Antes de desligar: o resultado da chamada da fila de chamada não é agent_joined_conference ou transferred_to_agent |
|Resultado da chamada                         |fCallQueueAnalytics -> Contagem de Chamadas<br>fCallQueueAnalytics -> Call Queue Call Result | Nenhum |
|Ação total de chamadas de tempo de tempo/estouro |fCallQueueFinalStateAction -> Contagem de Chamadas<br>fCallQueueFinalStateAction -> ação de estado final da fila de chamada |Ação de Estado Final da Fila de Chamada não está encaminhada |
|Totais de destino Transfer/Forard       |fCallQueueAnalytics -> Contagem de Chamadas<br>fCallQueueAnalytics -> tipo de destino da fila de chamadas |Nenhum |
|Volumes de chamada                        |fCallQueueAnalytics -> Contagem de Chamadas<br>fCallQueueAnalytics -> Call Queue Identify<br>fCallQueueAnalytics -> Date |Nenhum |
|Chamadas abandonadas                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Contagem de Chamadas<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned é True |
|Comprimento médio da sessão (segundos)    |fCallQueueFinalStateAction -> média de chamada<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Nenhum |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>DCQ-CQIdenity CQD fields description

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identidade da Fila de Chamada                     |text                     |Nome da conta de recurso anexada à Fila de Chamada<br><br>Se o nome completo da conta de recurso **cq_test@microsoft.com** esse valor será: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descrição dos campos CQD fCallQueueAnalytics

|Nome                                    |Tipo de dados                |Descrição                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Contagem de chamada                              |número inteiro             |Resumir: Soma<br>Número de chamadas                                          |
|Resultado da chamada de fila de chamada                  |text                     |Estado final da chamada de fila de chamada : valores possíveis:<br><br>§ agent_joined_conference<br>§ recusado<br>§ desconectado<br>§ error<br>§ falhou<br>§ inválido<br>§ estouro<br>§ timed_out<br>§ transferred_to_agent |
|Identidade da Fila de Chamada                     |text                     |Nome da conta de recurso anexada à Fila de Chamada<br><br>Se o nome completo da conta de recurso **cq_test@microsoft.com** esse valor será: **cq_test** |
|Tipo de destino de fila de chamada                  |text                     |***Tipo de destino de redirecionamento de chamada - valores possíveis:***<br><br>§ ApplicationEndpoint<br>§ Mailbox<br>§ Outros<br>§ Usuário |
|Tipo de chamada<sup>1</sup>                   |text                     |Tipo de chamada - valores possíveis:<br><br>§ Externo<br>§ Interno           |
|Data                                    |date/time                |Data e hora de início da chamada da fila de chamada (hora) (UTC)                           | 
|IsAbandoned                             |true/false               |True se a chamada não for atendida por um agente                                   |
|Tipo de conectividade PSTN                  |text                     |Tipo de chamada - valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall   |
|Minutos totais do PSTN                      |número inteiro             |Resumir: Soma<br>Uso total de minutos para chamadas PSTN                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics mede a descrição

|Nome                                    |Tipo de dados                |Descrição                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% de chamadas abandonadas***                 |percentagem               |Medida: TotalCallCount / Total de chamadas<br>Taxa de sucesso para contagem de chamada abandonada    |
|Total de chamadas                             |número inteiro             |Medida: agente soma atendida chamadas        |
|TotalCallCount                          |número inteiro             |Medida: Soma(Contagem de Chamada)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Descrição dos campos CQD fCallQueueFinalStateAction

|Nome                                    |Tipo de dados                |Descrição                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duração média da chamada (segundos)         |número decimal           |Resumir: Soma<br>Duração média da chamada em segundos |
|Contagem de chamada                              |número inteiro             |Resumir: Soma<br>Número de chamadas                  |
|Resultado da chamada de fila de chamada                  |text                     |Estado final da chamada de fila de chamada : valores possíveis:<br><br>§ agent_joined_conference<br>§ recusado<br>§ desconectado<br>§ error<br>§ falhou<br>§ inválido<br>§ estouro<br>§ timed_out<br>§ transferred_to_agent |
|Ação de estado final da fila de chamada           |text                     |Ação final da fila de chamada - valores possíveis:<br><br>§ disconnect<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ outros<br>§ caixa postal |
|Identidade da Fila de Chamada                     |text                     |Nome da conta de recurso anexada à Fila de Chamada<br><br>Se o nome completo da conta de recurso **cq_test@microsoft.com** esse valor será: **cq_test** |
|Data                                    |date/time                |Data e hora de início da chamada da fila de chamada (hora) (UTC)   |
|IsAbandoned                             |true/false               |True se a chamada não for atendida por um agente           |


### <a name="cloud-call-queue-agent-timeline"></a>Linha do tempo do agente de fila de chamada na nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                                          |Descrição                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# chamadas por agente                                        |Distribuição de chamada por fila de chamada e agente                 |
|Duração total da chamada (segundos) por agente e Fila de Chamada   |Duração total (segundos) da chamada por agente e fila de chamada     |
|Duração média da chamada (segundos) pelo nome do agente           |Duração média (segundos) da chamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para mapeamento de campo e tabela CQD

|Guia Relatório         |Nomes de tabela de relatório        |Filtro Global |
|:------------------|:-------------------------|:-------------|
|Linha do tempo do agente     |fAgentTimelineAnalytics   |Nenhum          |
 
|Nome da tabela de relatório            |Nome da tabela de origem            |Processamento       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Tipo alterado" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Seção Relatório                                |Field(s) Used                         |Filtros Aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nome do Agente                                    |Nome do Agente                            |Nenhum                  |
|Nome da Fila de Chamada                               |Nome da Fila de Chamada                       |Nenhum                  |
|#Calls Por Agente                               |Nome do Agente<br>Contagem de chamada<br>Data      |Nenhum                  |
|Distribuição por Agente e Fila de Chamada          |Nome do Agente<br>Contagem de chamada<br>Duração da chamada (Minutos)<br>Nome da Fila de Chamada |Nenhum                      |
|Inferior Esquerdo                                   |Nome do Agente<br>Duração média da chamada (segundo)<br>Contagem de chamada<br>Duração da Chamada (Minuto)<br>Nome da Fila de Chamada | Nenhum |
|Duração média da chamada (segundos) pelo nome do agente |Nome do Agente<br>Duração média da chamada (segundo)<br>Contagem de chamada<br>Duração da Chamada (Minuto)<br>Nome da Fila de Chamada | Nenhum |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>FAgentTimelineAnalytics CQD fields description

|Nome                                    |Tipo de dados                |Descrição                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome do Agente                              |text                     |UPN do usuário<br>Se o nome de usuário completo **user@microsoft.com,** esse valor será: **user** |
|Duração média da chamada (segundo)          |número decimal           |Resumir: Soma<br>A duração média das chamadas de fila de chamadas em segundos |
|Contagem de chamada                              |número inteiro             |Resumir: Soma<br>Número de chamadas manipuladas pelo agente                    |
|Duração da Chamada (Minuto)                  |número inteiro             |Resumir: Soma<br>Duração total de chamadas de fila de chamadas em minutos  |
|Nome da Fila de Chamada                         |text                     |Nome da conta de recurso anexada à Fila de Chamada<br><br>Se o nome completo da conta de recurso **cq_test@microsoft.com** esse valor será: **cq_test** |
|Data                                    |date                     |                                                    |


> [!NOTE]
> 1) Este relatório mostra as contagens de chamadas da perspectiva dos agentes e, portanto, o total da contagem de chamadas neste relatório normalmente será maior do que o número total de chamadas no relatório análise de fila de chamadas **na** nuvem. Cada chamada na fila pode ser apresentada a um ou mais agentes pelo menos uma vez antes de ser atendida. Cada chamada de fila de chamada apresentada a um agente é contada neste relatório, mesmo que não tenha sido atendida pelo agente. A diferença nas contagens de chamada entre esses dois relatórios é mais pronunciada com a opção de roteamento **attendant** que toca todos os agentes para cada chamada. 
> 2) Quando uma chamada chega pela primeira vez à primeira fila de chamadas,  se o número de chamadas já aguardando nessa fila exceder o limite de tratamento de estouro de chamada e se a opção de redirecionamento enviar chamadas para uma segunda fila de chamadas, os agentes na segunda fila de chamadas serão mostrados como sendo na primeira fila de chamadas neste relatório. 

## <a name="known-issues"></a>Problemas Conhecidos

- A fila de chamada e os atendimentos automáticos são mostrados pela ID da conta de recurso em vez de nomes de fila de chamada/atendimento automático.  Para mostrar todo o tráfego de um atendimento automático ou fila de chamada, você deve selecionar todas as contas de recursos atribuídas ao atendimento automático ou fila de chamada.

- Somente 28 dias de histórico estão disponíveis no painel, pois os dados de fila de chamada/atendimento automático são considerados dados pessoais e estão sujeitos a políticas de retenção de privacidade de dados.

- <sup>1</sup> **A origem da** chamada de entrada nos gráficos de fila de chamadas e de atendimento automático mostra a origem da etapa de chamada final em vez da origem inicial do trecho de chamada. Por exemplo, se um atendimento automático receber uma chamada externa e transferir a  chamada para outro atendimento automático ou fila de chamadas, a fonte de chamada de entrada será relatada como Interna.
