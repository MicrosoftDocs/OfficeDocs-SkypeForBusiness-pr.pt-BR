---
title: Usando o relatório do Power BI do CQD para exibir o Auto Attendant & histórico da fila de chamada
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre como usar o relatório Power BI do Painel de Qualidade de Chamada para exibir os dados históricos do Atendimento Automático e da Fila de Chamada.
ms.openlocfilehash: 16f8682e8f1bc444e2694a0586ff21cf442288cd
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130422"
---
# <a name="what-are-the-requirements"></a>Quais são os requisitos? 
Você precisa ter o Power BI Desktop instalado. Você pode instalá-lo na [Microsoft Windows Store.](https://aka.ms/pbidesktopstore)

Você pode usar a versão gratuita do Power BI Desktop. A versão mínima compatível é 2.85.681.0 (setembro de 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline do CQD
A conta que você usa para exibir o relatório histórico do CQ Analytics do AA & precisa ter permissões para acessar o pipeline de dados CQD. Consulte a função [de acesso CQD para](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) obter mais informações.

## <a name="installation"></a>Instalação 
As etapas a seguir supõem que você já instalou o Power BI Desktop no computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute estas etapas:
- Baixe o [Recurso Automático do CQD Teams &](https://aka.ms/TAPAACQAnalytics) relatório histórico da fila de chamada e salve-o em um diretório no seu computador.

- Clique duas vezes no modelo e a área de trabalho do Power BI deve ser lançada.

- Você será solicitado a selecionar a região do pipeline de dados CQD. Selecione a região onde seu locatário está localizado.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams":::

 - Você pode ver a região usando o cmdlet PS do Skype for Business Online (Get-CsTenant). Saída ServiceInstance. 
 A região será exibida após /like neste exemplo: 
 
   microsoftcommunicationsonline/noam-4a-s7 onde a região é noam.
   
 - O relatório será lançado com dados de exemplo.
 
 - Para ver seus próprios  dados, clique em Atualizar na guia Página Home em Consultas no Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams":::

- Você será solicitado a entrar. Selecione **a conta da** Organização e, em **seguida, selecione Entrar.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams":::

- Selecione **Conectar** e assistir à atualização de dados.

## <a name="data-latency-any-aa--cq-analytics"></a>Latência de dados Qualquer análise AA & CQ
Os dados estarão disponíveis no pipeline de dados do CQD dentro de 30 minutos.

Você terá que atualizar os dados para ver os novos dados de análise. 

## <a name="customization"></a>Personalização 
Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico, etc.

Não é possível adicionar campos de dados adicionais que não os fornecidos no relatório.

### <a name="change-color-schema"></a>Alterar esquema de cores 
As etapas a seguir supõem que você já concluiu as etapas de instalação.

Execute estas etapas:
- Selecione **a guia Exibir** na faixa de opções.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams":::

- Selecione o esquema de cores na lista lista listada.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams":::


## <a name="cqd-fields-description"></a>Descrição dos campos CQD

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identidade do Auto Attendant                 |String                   |Nome da conta de recurso anexada à AA<br>Exemplo: aa_test@microsoft.com|
|Hora de Início da Cadeia de Atendimento Automático         |datetime                 |Hora de início da cadeia de AA                    |
|Método de Pesquisa de Diretório do Auto Attendant  |String                   |Método de pesquisa do Último Livro de Endereços        |
|Ação de Transferência do Auto Attendant          |String                   |Tipo de destino de transferência de chamada<br>Valores possíveis:<br>§ desconhecido - tipo de entidade não especificado<br>§ usuário - entidade do usuário<br>§ orgaa - Entidade De Atendimento Automático Organizacional<br>§ hunt_group - entidade Fila de Chamada<br>§ aplicativo - entidade do aplicativo de voz<br>§ external_pstn - entidade PSTN externa<br>§ shared_voicemail - entidade de caixa postal compartilhada|
|Resultado da Chamada do Auto Attendant              |String                   |Resultado da chamada:<br>§ desconhecido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Fluxo de Chamada do Auto Attendant                |String                   |Encapsula os diferentes estados da Chamada de Atendimento Automático<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ comunicado|
|O Auto Attendant está envolvido              |Boolean                  |Indicado se a AA está envolvida na chamada |
|Contagem de Ações do Chamador de Atendimento Automático      |int                      |Contagem da ação usada pelo chamador         |
|Auto Attendant Chain Duration Seconds   |int                      |Duração da chamada no AA                 |
|Resultado da chamada em fila de chamada                  |Cadeia de caracteres                   |Estado final da chamada da fila de chamada<br>valores possíveis:<br>erro §<br>§ recusado<br>§ excedente<br>§ falha<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Ação de estado final da fila de chamada           |Cadeia de caracteres                   |Ação final da fila de chamada<br>valores possíveis:<br>§ para frente<br>§ desconectar<br>§ caixa postal<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ outro|
|Identidade da Fila de Chamada                     |Cadeia de caracteres                   |Nome da conta de recurso anexada ao CQ<br>Exemplo: aa_test@microsoft.com|
|Fila de chamada é o modo de conferência           |Boolean                  |Definir como 1 se o modo de conferência estiver habilitado no CQ |
|Tipo de Destino da Fila de Chamada                  |Cadeia de caracteres                   |Tipo de destino de redirecionamento de chamada esperado     |
|Transferido da identidade da fila de chamada    |Boolean                  |Nome da conta de recurso anexada ao CQ a partir da qual essa chamada foi transferida<br>Exemplo: aa_test@microsoft.com|
|Agente de fila de chamada optar pela contagem           |int                      |Contagem de agentes disponíveis para essa fila no momento da chamada |
|Contagem de Agente da Fila de Chamada                  |int                      |Contagem de agentes atribuídos a essa fila no momento da chamada |
|A fila de chamada está envolvida                  |Boolean                  |Se a fila de chamada estiver envolvida nesta chamada igual a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensões do modelo de dados do PowerBI

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                   |String                   |ID do Auto Attendant (ID da conta de recurso) |
|AACallFlow                              |String                   |Encapsula os diferentes estados da Chamada de Atendimento Automático<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Anúncio |
|AACallResult                            |String                   |Resultado da Chamada do Atendimento Automático:<br>§ desconhecido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – erro de configuração AA<br>§ service_terminated – erros internos da AA<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |String                   |Duração da chamada do Auto Attendant em segundos  |
|AACount                                 |String                   |# do Atendimento Automático envolve na chamada         |
|AADirectorySearchMethod                 |String                   |Método de pesquisa usado na chamada:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |String                   |Hora da chamada no UTC                            |
|AATransferAction                        |String                   |Receptor de chamada:<br>§ desconhecido - tipo de entidade não especificado<br>§ usuário - entidade do usuário<br>§ AA - Entidade De Atendimento Automático Organizacional<br>§ CQ - Entidade fila de chamada<br>§ aplicativo - entidade do aplicativo de voz<br>§ external_pstn - entidade PSTN externa<br>§ shared_voicemail - entidade de caixa postal compartilhada      |
|PSTNMinutes                             |int                      |Uso total de minutos                          |
|Resultado da chamada em fila de chamada                  |String                   |Estado final da chamada da fila de chamada<br>valores possíveis:<br>erro §<br>§ recusado<br>§ excedente<br>§ falha<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identidade da Fila de Chamada                     |String                   |Nome da conta de recurso anexada ao CQ     |
|Tipo de Destino da Fila de Chamada                  |String                   |Tipo de destino de redirecionamento de chamada esperado:<br>§ Usuário<br>§ Ponto de Extremidade do Aplicativo<br>§ Outros     |
|Resultado da chamada em fila de chamada                  |String                   |Estado final da chamada da fila de chamada<br>valores possíveis:<br>erro §<br>§ recusado<br>§ excedente<br>§ falha<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Ação de estado final da fila de chamada           |String                   |Ação final da fila de chamada<br>valores possíveis:<br>§ para frente<br>§ desconectar<br>§ caixa postal<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ outro             |
|Nome do agente                              |String                   |UPN do usuário               |


### <a name="measures"></a>Medidas

|Nome                                      |Tipo                       |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACalleractionCount                     |int                        |# da ação selecionada pelo usuário no AA durante a chamada  |
|PSTNMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |# de chamadas                                          |
|Duração média da chamada(Segundos)         |int                      |Duração total das chamadas na fila de chamadas em segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Auto Attendant de descrição do gráfico do Power BI

|Nome                                      |Descrição                            |
|:---------------------------------------|:--------------------------------------|
|Fonte de chamada de entrada                    |Distribuição de chamada por fonte de chamada interna/externa      |
|Totais do método de pesquisa de diretório          |Distribuição de chamada por tipo de pesquisa                         |
|Ação de chamador                           |Distribuição de chamada por receptor de chamada                       |
|Resultado da chamada                             |Distribuição de chamada por estado de chamada final                    |
|Contagem de ações do chamador                     |Distribuição da ação de chamada por número usada durante a chamada  |


### <a name="call-queue"></a>Fila de Chamada

|Nome                                      |Descrição                            |
|:---------------------------------------|:--------------------------------------|
|Fonte de chamada de entrada                    |Distribuição de chamada por fonte de chamada interna/externa         |
|Volume da chamada                             |Distribuição de chamada por filas de chamada                            |
|Resultado do chamador                           |Distribuição de chamada por resultado de chamada                            |
|Timeout/Overflow call total action      |Distribuição de chamada NÃO encaminhada(abandonado) por resultado de chamada   |
|Totais de destino de transferência/encaminhamento          |Distribuição de chamada encaminhada por resultado de chamada                  |
|Taxa de chamadas abandonado                   |Ratio of successful to abandoned call count                    |
|Duração média da sessão (segundos)        |Duração da chamada em segundos agrupada por chamadas abandonados/bem-sucedidas   |



### <a name="agent-timeline"></a>Linha do tempo do agente

|Nome                                                      |Descrição                            |
|:-------------------------------------------------------|:--------------------------------------|
|# chamadas por agente                                        |Distribuição de chamada por fila de chamada e agente                 |
|Duração total da chamada (segundos) por agente e Fila de Chamada   |Duração total (segundos) da chamada por agente e fila de chamada     |
|Duração média da chamada (segundos) por nome do agente            |Duração média (segundos) da chamada por agente                  |



## <a name="known-issues"></a>Problemas conhecidos
- Atualmente, a Fila de Chamada e o atendimento automático mostram a ID de contas de recurso em vez de nomes de fila de chamada/atendimento automático.  Para mostrar todo o tráfego de um atendimento automático ou fila de chamada, você deve selecionar todas as contas de recurso atribuídas ao atendimento automático ou fila de chamada.

- Atualmente, apenas 28 dias do histórico estão disponíveis no painel, pois os dados da Fila de Chamada/do atendimento automático são considerados informações de identificação do usuário final e estão sujeitos a políticas de retenção de privacidade de dados.
