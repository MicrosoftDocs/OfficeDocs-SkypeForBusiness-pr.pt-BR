---
title: Relatório histórico da fila de chamadas do assistente automático &
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
description: Saiba mais sobre como usar o relatório histórico do Power BI do Assistente Automático do Teams & Relatório Histórico da Fila de Chamadas para exibir dados históricos do Assistente Automático e da Fila de Chamadas.
ms.openlocfilehash: 3db0705ea1321b3ef6d2efef5a01e3283f091cc9
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131190"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Relatório histórico da fila de chamadas do assistente automático &

Este modelo do Power BI fornece três relatórios que permitem que as organizações informem sobre o número de chamadas que estão sendo processadas por atendentes automáticos e filas de chamadas.  Ele também fornece insights de desempenho do agente.

## <a name="v304-published-on-november-18-2022"></a>V3.0.4 publicado em 18 de novembro de 2022

O modelo do Power BI do Relatório Histórico da Fila de Chamadas & Do Teams fornece os seguintes três relatórios:

- O relatório do [Atendente Automático](media/aa-cq-historical-report-sample-aa-v304.png) mostra a análise de chamadas que chegam aos seus atendentes automáticos.
- O relatório [Fila de Chamadas](media/aa-cq-historical-report-sample-cq-v304.png) mostra a análise de chamadas que entram em suas filas de chamada.
- O relatório [Linha do Tempo do Agente](media/aa-cq-historical-report-sample-at-v304.png) mostra uma exibição de linha do tempo de agentes ativos em chamadas de fila de chamadas.

Esses relatórios usam dados do serviço VAAC (Voice Applications Analytics Collector).

>[!NOTE]
> A coleta de dados históricos está em andamento em todas as regiões.  Trinta dias de dados históricos estarão disponíveis em horários diferentes, com todas as regiões tendo 30 dias completos de dados até 25 de novembro de 2022.
>
> Os clientes do GCCH/DOD devem continuar a usar a V1.63.

## <a name="v3xx-prerequisites"></a>Pré-requisitos V3.x.x

### <a name="power-bi-desktop"></a>Power BI Desktop
Você precisa ter Power BI Desktop instalado. Você pode instalar e usar a versão gratuita da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

A versão mínima compatível é 2.85.681.0 (setembro de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline do CQD

Embora essa versão dos relatórios não use o pipeline de dados CQD (Painel de Qualidade de Chamada), a conta usada para exibir os dados históricos ainda requer acesso ao Painel de Qualidade de Chamada. Para obter mais informações, confira [Função de acesso do CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).
- Esse requisito será removido em uma versão futura.

## <a name="v3xx-installation"></a>Instalação V3.x.x 

As etapas a seguir pressupõem que você já instalou Power BI Desktop em seu computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute as seguintes etapas:

1. Baixe e salve o arquivo [V3.0.4.zipHistórico de Fila de Chamadas & Do Teams ](https://www.microsoft.com/download/details.aspx?id=104623) no computador.

1. Abra o arquivo zip.

1. Abra o arquivo de `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` modelo. Power BI Desktop deve ser iniciado.

1. Você será solicitado a selecionar a **Fonte de Dados**.  Selecione a `api.interfaces.records.teams.microsoft.com` entrada.

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="Captura de tela selecionando o api.interfaces.records.teams.microsoft.com Data Soure":::

1. Você será solicitado a entrar com uma conta. Selecione **Conta organizacional** e selecione **Entrar**.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="Captura de tela mostrando o logon do V3.0.0.":::

1. Selecione **Conectar** e os dados serão atualizados.

> [!NOTE]
> Se você estiver usando v1.63 ou anterior, poderá encontrar um erro quando v3.x.x tentar recuperar os dados do VAAC.  Para resolver esse erro, é necessário limpar todas as credenciais anteriores do Power BI.
> 
> 1. Abra o modelo v3.x.x para limpar o erro. 
> 1. Selecione Opções **de Arquivo** > **& Configurações Configurações** > **De origem de dados**.
> 1. Selecione a lista suspensa para **Limpar Permissões** e selecione **Limpar Todas as Permissões**.
> 1. Feche o modelo depois que eles forem desmarcados e reinicie o Power BI. Você será solicitado a autorizar novamente. 

## <a name="v163-published-on-august-24-2022"></a>V1.63 publicado em 24 de agosto de 2022

> [!IMPORTANT]
> O suporte à nuvem pública para o modelo V1.63 terminará em 25 de novembro de 2022.
> 
> Os clientes do GCCH/DOD devem continuar a usar a V1.63.

O **Modelo histórico do Power BI do Relatório Histórico da Fila de Chamadas & do Teams do Teams** fornece os seguintes três relatórios:

- O relatório do [Atendente Automático](media/aa-cq-historical-report-sample-aa-v163.png) mostra a análise de chamadas que chegam aos seus atendentes automáticos.
- O relatório [Fila de Chamadas](media/aa-cq-historical-report-sample-cq-v163.png) mostra a análise de chamadas que entram em suas filas de chamada.
- O relatório [Linha do Tempo do Agente](media/aa-cq-historical-report-sample-at-v163.png) mostra uma exibição de linha do tempo de agentes ativos em chamadas de fila de chamadas.

Esses relatórios usam dados do repositório de dados [CQD (Painel de Qualidade de Chamada).](CQD-Power-BI-query-templates.md) 

## <a name="v163-prerequisites"></a>Pré-requisitos do V1.63

### <a name="power-bi-desktop"></a>Power BI Desktop
Você precisa ter Power BI Desktop instalado. Você pode instalar e usar a versão gratuita da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

A versão mínima compatível é 2.85.681.0 (setembro de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline do CQD

A conta que você usa para exibir o relatório histórico precisa ter permissões para acessar o pipeline de dados do CQD. Para obter mais informações, confira [Função de acesso do CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="v163-installation"></a>Instalação do V1.63 

As etapas a seguir pressupõem que você já instalou Power BI Desktop em seu computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute as seguintes etapas:

1. Baixe e salve o arquivo zip [modelos de consulta do CQD Power BI](https://www.microsoft.com/download/details.aspx?id=102291) em seu computador.

1. Abra o arquivo zip.

1. Abra o arquivo de `CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit` modelo. Power BI Desktop deve ser iniciado.

1. Você será solicitado a selecionar a região do pipeline de dados CQD. Selecione a região em que seu locatário está localizado.

  :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="Captura de tela selecionando a região do pipeline de dados CQD.":::

1. A região em que seu locatário está localizado pode ser obtida usando o cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```powershell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    1. A região será exibida após o **/** como no exemplo acima em que a região é `noam`.

 1. O relatório será iniciado com dados de exemplo.
 
 1. Para ver seus próprios dados, selecione **Atualizar** na guia **Página Inicial** em **Consultas** em Power BI Desktop.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="Captura de tela selecionando a opção de atualização.":::

1. Você será solicitado a entrar. Selecione **Conta organizacional** e selecione **Entrar**.

  :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="Captura de tela mostrando o logon da V1.63.":::

1. Selecione **Conectar** e os dados serão atualizados.

## <a name="data-latency-and-aa--cq-analytics"></a>Latência de dados e análise de CQ & AA

Normalmente, os dados estão disponíveis dentro de 30 minutos após a conclusão da chamada; no entanto, há ocasiões em que pode levar várias horas para que os dados apareçam. 

Você precisará atualizar os dados para ver novos dados.

## <a name="customization"></a>Personalização 

Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico e assim por diante.

O relatório contém todas as métricas de dados disponíveis no momento.

### <a name="change-color-schema"></a>Alterar esquema de cores 

As etapas a seguir pressupõem que você já concluiu as etapas de instalação.

Execute as seguintes etapas:

- Selecione **Exibir guia** na faixa de opções.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Captura de tela selecionando a guia exibir para alterar o esquema de cores.":::

- Selecione o esquema de cores na lista suspensa.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Captura de tela mostrando vários esquemas de cores.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definições de relatórios históricos de atendimento automático e fila de chamadas

### <a name="cloud-auto-attendant-analytics-report"></a>Relatório do Cloud Auto Attendant Analytics

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Fonte<sup>de chamada de entrada 1</sup>        |Distribuição de chamadas por fonte de chamada interna/externa            |
|Método de Pesquisa de Diretório                 |Distribuição de chamadas por tipo de pesquisa                              |
|Contagem de ações do chamador                     |Distribuição de chamadas por ação numérica usada durante a chamada       |
|Segundos médios no AA                   |Número médio de segundos que os chamadores gastam no AA                 |
|Ações médias de chamador                  |Número médio de ações que os chamadores executam no AA               |
|Chamar resultados                            |Distribuição de chamadas por estado de chamada final                         |
|Seção inferior do relatório                 |Divisão de fluxo de chamada                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório     |Nome da tabela de origem            |Filtro Global                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Atendente Automático        |fAutoAttendant        |AutoAttendant                |Nenhum                                   |

|Seção Relatório                                  |Campo(s) Usado                              |Filtros aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Seletor de datas                                   |AAStartTime                                |Nenhum                |
|Seletor de Intervalo de Tempo                             |AAStartHour                                |Nenhum                |
|Atendente Automático                                  |Nome AA                                    |Nenhum                |
|Fonte<sup>de chamada de entrada 1</sup>                |Tipo de Chamada<br>Soma de TotalCallCount (Medida) |Chamadas externas: Tipo de chamada é externo<br>Chamadas internas: Tipo de chamada é interno |
|Método de Pesquisa de Diretório                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod é abs_search_dtmf ou abs_search_name    |
|Contagem de ações do chamador                             |AACallerActionCount<br>TotalCallCount      |Nenhum                                                             |
|Segundos médios no AA                           |AAChainDuration (Medida)                  |Nenhum                                                             |
|Ações médias de chamador                          |AACallerActionCount (Medida)              |Nenhum                                                             |
|Chamar resultados                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Nenhum                                       |
|Seção inferior do relatório                         |Nome AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de Chamada<br>MM-DD<br>TotalCallCount |Nenhum       |

#### <a name="fautoattendant-cqd-fields-description"></a>descrição dos campos CQD fAutoAttendant

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                 |Texto                     |Nome da conta de recurso anexada ao Atendente Automático<br><br>Se o nome completo da Conta de Recurso for **aa_test@microsoft.com**, esse valor será: **aa_test** |
|AACallerActionCount                     |Número inteiro             |Resumindo: Soma<br>Contagem de ações selecionadas pelo chamador no Atendente Automático durante a chamada  |
|AACallerActionCount (Medida)          |Número inteiro             |O mesmo que acima, exceto, será 0 se nenhuma chamada em vez de em branco                              |
|AACallFlow                              |Texto                     |Encapsula os diferentes estados de Chamada de Atendimento Automático – valores possíveis:<br><br>§ abs_search<br>§ comunicado<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texto                     |Resultado da chamada final -- valores possíveis:<br><br>§ failed_to_establish_media (a parte de mídia da chamada não pôde ser estabelecida)<br>§ failover_to_operator (chamada transferida para o operador normalmente devido a um erro do sistema)<br>§ oaa_chain_too_long (muitas pernas no AA)<br>§ oaa_session_too_long (a sessão do AA durou muito tempo)<br>§ service_declined (a AA não aceitou a chamada)<br>§ service_terminated (a configuração do AA desconecta a chamada ou a chamada desligada)<br>§ terminated_automatic_selection (a configuração do AA desconecta as chamadas)<br>§ terminated_no_operator (chamada encerrada devido ao erro que nenhum operador definiu) <br>§ terminated_transfer_failed (chamada encerrada como falha de transferência - normalmente para número externo)<br>§ transfer_in_progress (transferência AA->AA)<br>§ transferred_to_operator (a chamada foi transferida para o operador - normalmente devido a um erro de usuário)<br>§ transferred_to_receptionist (igual a transferred_to_operator)<br>§ transferred_to_self (a chamada foi retornada para o início do AA - normalmente de uma opção de anúncio de menu)<br>§ transferred_to_shared_voicemail (a chamada foi transferida para a caixa postal compartilhada)<br>§ transferred_to_user (a chamada foi transferida para um usuário - inclui filas de chamadas)<br>§ desconhecido (ocorreu uma condição desconhecida)<br>§ user_terminated (chamador desligado) |
|AA Call Legend                          |Texto                     |Configura itens de legenda com base em AACallResult                               |
|AAChainDuration                         |Número decimal           |Resumindo: Soma<br>Duração da chamada no Atendente Automático                     |
|AAChainDuration (Medida)               |Número decimal           |O mesmo que acima, exceto, será 0 se nenhuma chamada em vez de em branco              |
|AAChainIndex                            |Texto                     |                                                                         |
|AAConnectivityType                      |Texto                     |Tipo de chamada- valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Texto                     |Número de atendentes automáticos envolvidos na chamada                               |
|AADirectorySearchMethod                 |Texto                     |Método de pesquisa do último catálogo de endereços— valores possíveis:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Número decimal           |Hora de início da chamada do Atendente Automático                                           |
|AAStartTime                             |Data/hora                |Hora de início da chamada do Atendente Automático                                           |
|AATransferAction                        |Texto                     |Tipo de destino de transferência de chamada— valores possíveis:<br><br>§ aplicativo – entidade de aplicativo de voz<br>§ external_pstn<br>§ hunt_group – Entidade de fila de chamadas<br>§ orgaa – Entidade de Atendimento Automático<br>§ shared_voicemail<br>§ desconhecido<br>§ usuário |
|Tipo<sup>de chamada 1</sup>                   |Texto                     |Tipo de chamada- valores possíveis:<br><br>§ Externo<br>§ Interno           |
|IsAAInvolved                            |Texto                     |Sempre 1                                                                 |
|MM-DD                                   |Texto                     |Atendimento Automático chamada mês-dia                                            |
|PSTNMinutes                             |Número inteiro             |Resumindo: Soma<br>Uso total de minutos                                     |
|TotalCallCount                          |Número inteiro             |Resumindo: Soma<br>Always 1 – usado para fornecer a soma de todas as chamadas            |
|Soma de TotalCallCount (Medida)         |Número inteiro             |O mesmo que acima, exceto, será 0 se nenhuma chamada em vez de em branco              |


### <a name="cloud-call-queue-analytics-report"></a>Relatório do Cloud Call Queue Analytics

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                          |Descrição                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Fonte<sup>de chamada de entrada 1</sup>        |Distribuição de chamadas por fonte de chamada interna/externa             |
|Tempo médio de espera (segundos)             |Tempo de espera para chamadas atendidas e abandonadas                          |
|Contagem de opt-in de volume e agente de chamada      |Distribuição de chamadas por filas de chamada / Contagem máxima de opt-in do agente  |
|Chamar resultados                            |Distribuição de chamadas por resultado de chamada                               |
|Chamadas abandonadas                         |Distribuição de chamadas abandonadas por filas de chamada                     |
|Comprimento médio da sessão (segundos)        |Comprimento da chamada em segundos agrupados por resultado de chamada                      |
|Destinos de estouro/tempo limite de chamada      |Distribuição de chamadas com tempo limite ou estouro                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório                                   |Nome da tabela de origem                               |Filtro Global       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Fila de chamadas            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Nenhum                |

|Seção Relatório                      |Campos de tabela -> usados                |Filtros aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Seletor de datas                       |fCallQueueAnalytics -> Date           |Nenhum                  |
|Seletor de Intervalo de Tempo                 |fCallQueueAnalytics -> CQHour         |Nenhum                  |
|Conta de recurso de fila de chamadas         |fCallQueueAnalytics -> Nome do CQ        |Nenhum                  |
|Fonte de chamada<sup>de entrada 1</sup>    |fCallQueueAnalytics -> Soma da Contagem de Chamadas (Medida)<br>fCallQueueAnalytics -> Tipo de Chamada    |Chamadas externas: Tipo de chamada é externo<br>Chamadas internas: Tipo de chamada é interno |
|Tempo de espera do Avg (segundos)-Antes de responder |fCallQueueFinalStateAction -> Avg de Duração média do CQ (Medida) |O resultado da chamada de chamada de chamada é agent_joined_conference ou transferred_to_agent|
|Tempo de espera do Avg (segundos)-Antes de Abandonado |fCallQueueFinalStateAction -> Avg de duração média da chamada (medida) |O resultado da chamada de chamada não é agent_joined_conference, transferred_to_agent, estouro, timed_out |
|Contagem de Opt-In de volume e agente   |contagem de chamadas fCallQueueAnalytics -><br>fCallQueueAnalytics -> Agente de Fila de Chamadas Optar em Contagem<br>fCallQueueAnalytics -> Nome do CQ<br>fCallQueueAnalytics -> Date |Nenhum |
|Chamadas abandonadas                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | Legenda do resultado da chamada de fila de chamadas é abandonada |
|Comprimento médio da sessão (segundos)    |fCallQueueFinalStateAction -> Duração média da fila de chamadas (súm)<br>Legenda do resultado da chamada da fila de chamadas |Duração média da fila de chamadas (ss) > 0 |
|Destinos de estouro/tempo limite de chamada  |contagem de chamadas fCallQueueAnalytics -><br>fCallQueueAnalytics -> Tipo de destino da fila de chamadas<br>Legenda do tipo de destino fCallQueue |Legenda do tipo de destino da fila de chamadas não contém Abandonado e Agente Atendido |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descrição dos campos CQD fCallQueueAnalytics

|Nome                                    |Tipo de dados                |Descrição                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Contagem de Chamadas                              |Número inteiro             |Resumindo: Soma<br>Número de chamadas                                          |
|Contagem de agentes de fila de chamadas                  |Número inteiro             |Resumindo: Soma<br>Número de agentes configurados na fila de chamadas            |
|Agente de fila de chamadas opte pela contagem           |Número inteiro             |Resumindo: Soma<br>Número de agentes que optaram pela fila de chamadas              |
|Resultado da chamada de chamada de fila                  |Texto                     |Estado final da chamada da fila de chamadas -- valores possíveis:<br><br>§ agent_joined_conference (chamadas de modo de conferência atendidas)<br>§ recusado<br>§ desconectado<br>Erro do §<br>§ falhou<br>§ inválido<br>§ estouro (condição de estouro atendida)<br>§ timed_out (condição de tempo limite atendida)<br>§ transferred_to_agent (chamadas do modo de transferência atendida {default}) |
|Legenda do resultado da chamada da fila de chamadas           |Texto                     |Configura itens de legenda com base no Resultado da Fila de Chamadas                             |
|Tipo de destino de fila de chamadas                  |Texto                     |***Tipo de destino de redirecionamento de chamada — valores possíveis:***<br><br>§ ApplicationEndpoint<br>§ Caixa de correio<br>§ Outros<br>§ Usuário |
|Legenda do tipo de destino da fila de chamadas           |Texto                     |Configura itens de legenda com base no Tipo de Destino da Fila de Chamadas                        |
|Tipo<sup>de chamada 1</sup>                   |Texto                     |Tipo de chamada- valores possíveis:<br><br>§ Externo<br>§ Interno             |
|Nome do CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso estiver **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Hora do CQ                                 |Número Inteiro             |Hora de início da chamada da fila de chamadas                                                 |
|Data                                    |Data/hora                |Data e hora de início da chamada da fila de chamadas (hora)                                 | 
|DateTimeCQName                          |Texto                     |Chave exclusiva para filtragem em fCallQueueFinalStateAction                     |
|Tipo de conectividade PSTN                  |Texto                     |Tipo de chamada- valores possíveis:<br><br>§ ExternalCall<br>§ InternalCall     |
|Minutos Totais PSTN                      |Número inteiro             |Resumindo: Soma<br>Uso total de minutos para chamadas PSTN                       |
|Soma da contagem de chamadas (medida)             |Número inteiro             |O mesmo que Contagem de Chamadas, no entanto, será 0 quando nenhuma chamada                          |
|TotalCallCount (Medida)                |Número Inteiro             |Resumindo: Soma<br>Contagem de Chamadas                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>descrição dos campos do CQD fCallQueueFinalStateAction

|Nome                                    |Tipo de dados                |Descrição                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duração média da chamada (segundos)         |Número decimal           |Resumindo: Soma<br>Duração média da chamada em segundos para chamadas abandonadas    |
|Duração média da fila de chamadas (ss)       |Número decimal           |Resumindo: Soma<br>Espera média em segundos para chamadas atendidas           |
|Avg de duração média da chamada (medida)  |Número inteiro             |O mesmo que a duração média da chamada (segundos), no entanto, será 0 quando nenhuma chamada   |
|Avg de duração média do CQ (Medida)    |Número inteiro             |O mesmo que a duração média da fila de chamada (seg) no entanto será 0 quando nenhuma chamada |
|Contagem de Chamadas                              |Número inteiro             |Resumindo: Soma<br>Número de chamadas                                         |
|Resultado da chamada de chamada de fila                  |Texto                     |Estado final da chamada da fila de chamadas -- valores possíveis:<br><br>§ agent_joined_conference (chamadas de modo de conferência atendidas)<br>§ recusado<br>§ desconectado<br>Erro do §<br>§ falhou<br>§ inválido<br>§ estouro (condição de estouro atendida)<br>§ timed_out (condição de tempo limite atendida)<br>§ transferred_to_agent (chamadas de modo de transferência atendidas {default} |
|Legenda do resultado da chamada da fila de chamadas           |Texto                     |Configura itens de legenda com base no Resultado da Chamada de Chamada de Chamada                      |
|Ação de estado final da fila de chamadas           |Texto                     |Ação final da fila de chamadas - valores possíveis:<br><br>§ desconectar (timed_out chamadas)<br>§ disconnect_with_busy (chamadas transbordadas)<br>§ failed_to_accept_call<br>§ encaminhar<br>§ shared_voicemail<br>§ outro<br>§ caixa postal                |
|Nome do CQ                                 |Texto                     |Nome da conta de recurso anexada à Fila de Chamadas<br><br>Se o nome completo da Conta de Recurso estiver **cq_test@microsoft.com**, esse valor será: **cq_test** |
|Data                                    |Data/hora                |Data e hora de início da chamada da fila de chamadas (hora)                                 |
|DateTimeCQName                          |Texto                     |Chave exclusiva para filtragem em fCallQueueFinalStateAction                     |
|Isabandoned                             |True/false               |True se a chamada não for atendida por um agente                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>Relatório da Linha do Tempo do Agente de Fila de Chamadas na Nuvem

#### <a name="report-description"></a>Descrição do relatório

|Seção Relatório                                          |Descrição                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Número de chamadas por agente                                |Distribuição de chamadas por fila de chamadas e agente                |
|Distribuição por agente e todas as filas                     |Distribuição de chamadas por agente e fila de chamadas                |
|Tabela (inferior direito)                                    |Distribuição de chamadas por agente com duração média e total da chamada |
|Duração média da chamada (segundos) por Agente                |Duração média (segundos) de chamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Relatório para tabela CQD e mapeamento de campo

|Guia Relatório            |Nome da tabela de relatório           |Nome da tabela de origem         |Filtro Global       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Linha do Tempo do Agente        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Nenhum                |


|Seção Relatório                                |Campo(s) Usado                         |Filtros aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Seletor de datas                                 |Datetime                              |Nenhum                  |
|Seletor de nome de usuário do agente                       |Nome do agente                            |Nenhum                  |
|Seletor de Contas de Recurso de Fila de Chamadas          |Nome do CQ                               |Nenhum                  |
|Número de chamadas por agente                      |Nome do agente<br>Contagem de Chamadas<br>Hora      |Nenhum                  |
|Distribuição por agente e fila de chamadas          |Nome do agente<br>Duração média de chamadas (segundos)<br>Contagem de Chamadas<br>Nome do CQ |Nenhum                      |
|Canto inferior esquerdo                                   |Nome do agente<br>Duração média da chamada (segundos)<br>Contagem de Chamadas<br>Duração da chamada (minuto)<br>Nome do CQ<br>Hora<br>MM-DD | Nenhum |
|Duração média da chamada (segundos) por agente      |Nome do agente<br>Duração média da chamada (segundos) | Nenhum |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descrição dos campos CQD fAgentTimelineAnalytics

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

- A fila de chamadas e os atendentes automáticos são mostrados pela ID da conta de recurso em vez de nomes de fila de chamadas/atendente automático.  Para mostrar todo o tráfego de um atendente automático ou fila de chamadas, você deve selecionar todas as contas de recurso atribuídas ao atendente automático ou à fila de chamadas.

- Apenas 28 dias de histórico estão disponíveis no painel, pois os dados de fila de chamadas/atendimento automático são considerados dados pessoais e estão sujeitos a políticas de retenção de privacidade de dados.

- Em alguns cenários, a contagem de chamadas atendidas pelo agente no relatório **Linha do Tempo do Agente de Fila de Chamadas na Nuvem** pode ser diferente do número de chamadas mostradas no histórico de chamadas do cliente do Teams. O histórico de chamadas do cliente do Teams está correto. O suporte está investigando, mas não há tempo estimado para reparos disponíveis no momento.

- <sup>1 Fonte de</sup> **chamada de entrada** nos grafos de fila de atendimento automático e de chamada mostram a fonte final da etapa de chamada em vez da fonte inicial da etapa de chamada. Por exemplo, se um atendente automático receber uma chamada externa e transferir a chamada para outro atendente automático ou fila de chamadas, a **fonte de chamada de entrada** será relatada como Interna.

## <a name="version-3xx-history"></a>Histórico da versão 3.x.x

Consulte: Assistente Automático do Teams & Relatórios Históricos da Fila de Chamadas – Alterar Log.docx no arquivo zip baixado para obter uma lista detalhada de alterações 

|Versão  |Data Publicada     |Filename                                                           |Descrição                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |18 de novembro de 2022  |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.4        |Erro corrigido, classificação de chamada aprimorada, legenda adicionada |
|3.0.3    |8 de novembro de 2022   |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.3        |Erro corrigido, link de documentação adicionado, consultas otimizadas |
|3.0.1    |26 de outubro de 2022   |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.1        |Entrada de fonte de dados de teste removida                   |
|3.0.0    |25 de outubro de 2022   |Assistente Automático do Teams & relatórios históricos da fila de chamadas V3.0.0        |Nova fonte de dados de back-end                             |


## <a name="version-1xx-history"></a>Histórico da versão 1.xx

Consulte: Assistente Automático do CQD Teams & Relatórios Históricos da Fila de Chamadas – Alterar Log.docx no arquivo zip baixado para obter uma lista detalhada de alterações                         

|Versão  |Data Publicada     |Filename                                                           |Descrição                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |24 de agosto de 2022    |CQD Teams Auto Attendant & Relatório Histórico da Fila de Chamadas V1.63.pbit |                                                    |
|1.60     |22 de julho de 2022      |CQD Teams Auto Attendant & Relatório Histórico da Fila de Chamadas V1.60.pbit |                                                    |
|1.00     |5 de novembro de 2020   |CQ e AA combined Analytics 20201105.pbit                         |Versão inicial                                     |

