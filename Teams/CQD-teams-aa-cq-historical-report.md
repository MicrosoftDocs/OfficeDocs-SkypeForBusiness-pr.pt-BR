---
title: Usando o relatório do CQD Power BI para ver o atendedor automático & relatório histórico histórico da fila de chamadas
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
description: Saiba como usar o relatório do Power BI do painel de qualidade de chamada para exibir os dados de atendedor automático e a fila de chamadas de dados históricos.
ms.openlocfilehash: 874bb87a32895bdec29aab1b0aaee20bdecb0fc2
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908764"
---
# <a name="what-are-the-requirements"></a>Quais são os requisitos? 
Você precisa ter o Power BI desktop instalado. Você pode instalá-lo na [Windows Store da Microsoft](https://aka.ms/pbidesktopstore).

Você pode usar a versão gratuita do Power BI desktop. A versão mínima compatível é 2.85.681.0 (setembro de 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline CQD
A conta que você usa para exibir o relatório histórico de análise de CQ de AA & precisa ter permissões para acessar o pipeline de dados CQD. Para obter mais informações, consulte a [função de acesso CQD](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) .

## <a name="installation"></a>Instalação 
As etapas a seguir pressupõem que você já tenha instalado o Power BI desktop no computador e que sua conta tenha as permissões necessárias para acessar o pipeline de dados CQD.

Siga estas etapas:
- Baixe o [CQD Teams auto Attendant & modelo de relatório histórico da fila de chamadas](https://aka.ms/TAPAACQAnalytics) e salve-o em um diretório em seu computador.
- Clique duas vezes no modelo e o Power BI desktop deve ser iniciado.
- Você será solicitado a selecionar a região de pipeline de dados CQD. Selecione a região onde seu locatário está localizado.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::

 - Você pode ver a região usando o cmdlet do PS do Skype for Business online (Get-CsTenant). Saída de serviceInstance. 
 A região será exibida após a/curtida neste exemplo: microsoftcommunicationsonline/Noam-4a-S7 em que a região é Noam.
 - O relatório será iniciado com dados de exemplo.
 - Para ver seus próprios dados, clique em **Atualizar** na guia página inicial em consultas na área de trabalho do Power bi.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::

- Em seguida, você será solicitado a entrar. Selecione a **conta da organização** e, em seguida, selecione **entrar**.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::

- Selecione **conectar** e assista à atualização de dados.

## <a name="data-latency-any-aa--cq-analytics"></a>Latência de dados qualquer & análise de CQ
Os dados estarão disponíveis no pipeline de dados do CQD em 30 minutos.

Você terá que atualizar os dados para ver os novos dados de análise. 

## <a name="customization"></a>Personalizada 
Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico etc.

Você não pode adicionar outros campos de dados além daqueles fornecidos no relatório.

### <a name="change-color-schema"></a>Alterar esquema de cores 
As etapas a seguir pressupõem que você já concluiu as etapas de instalação.

Siga estas etapas:
- Selecione a **guia Exibir** na faixa de opções.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::

- Selecione o esquema de cores na lista suspensa.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::


## <a name="cqd-fields-description"></a>Descrição dos campos CQD

|Nome                                    |Tipo de dados                |Descrição                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|Identidade do atendedor automático                 |String                   |Nome da conta do recurso anexada ao AA<br>Exemplo: aa_test@microsoft.com|
|Hora de início da cadeia de atendedor automático         |datetime                 |Hora de início da cadeia AA                    |
|Método de pesquisa do diretório de atendedor automático  |String                   |Último método de pesquisa do catálogo de endereços        |
|Ação de transferência do atendedor automático          |String                   |Tipo de destino da transferência de chamadas<br>Valores possíveis:<br>§ desconhecido-tipo de entidade não foi especificado<br>§ usuário – entidade de usuário<br>§ orgaa-entidade de atendedor automático organizacional<br>§ hunt_group-entidade da fila de chamadas<br>§ aplicativo-entidade do aplicativo de voz<br>§ external_pstn-entidade PSTN externa<br>§ shared_voicemail-entidade de correio de voz compartilhada|
|Resultado da chamada de atendedor automático              |String                   |Resultado da chamada:<br>§ desconhecido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Fluxo de chamadas do atendedor automático                |String                   |Encapsula os diferentes Estados de chamada de atendedor automático<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ lançamento|
|O atendedor automático está envolvido              |Boolean                  |Indicado se o AA estiver envolvido na chamada |
|Contagem de ações de chamadas de atendedor automático      |int                      |Contagem de ações usadas pelo chamador         |
|Segundos da duração da cadeia de atendedor automático   |int                      |Duração da chamada em AA                 |
|Resultado da chamada em fila de chamada                  |Cadeia de caracteres                   |Estado final da chamada na fila de chamadas<br>valores possíveis:<br>§ erro<br>§ recusada<br>§ estourado<br>§ falhou<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Ação de estado final da fila de chamadas           |Cadeia de caracteres                   |Ação final da fila de chamadas<br>valores possíveis:<br>§ frente<br>§ desconectar<br>§ correio de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ outros|
|Identidade da fila de chamadas                     |Cadeia de caracteres                   |Nome da conta de recurso anexada ao CQ<br>Exemplo: aa_test@microsoft.com|
|Fila de chamadas é o modo de conferência           |Boolean                  |Defina como 1 se o modo de conferência estiver habilitado no CQ |
|Tipo de destino da fila de chamadas                  |Cadeia de caracteres                   |Tipo de destino de redirecionamento de chamadas esperado     |
|Transferido da identidade da fila de chamadas    |Boolean                  |Nome da conta do recurso anexada ao CQ a partir do qual essa chamada foi transferida<br>Exemplo: aa_test@microsoft.com|
|Contagem de consentimento de agente de fila de chamadas           |int                      |Contagem de agentes disponíveis para esta fila no momento da chamada |
|Contagem de agente da fila de chamadas                  |int                      |Contagem de agentes atribuídos a esta fila no momento da chamada |
|A fila de chamadas está envolvida                  |Boolean                  |Se a fila de chamadas estiver envolvida para esta chamada igual a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensões do modelo de dados do PowerBI

|Nome                                    |Tipo de dados                |Descrição                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|Nome do AA                                   |String                   |ID do atendedor automático (ID da conta do recurso) |
|AACallFlow                              |String                   |Encapsula os diferentes Estados de chamada de atendedor automático<br> abs_search<br> call_termination<br> call_transfer<br> main_menu<br> user_selection<br> speech_input_confirmation<br> first_level_menu<br> automatic_menu<br>comunicado |
|AACallResult                            |String                   |Resultado da chamada de atendedor automático:<br> desconhecido<br> transferred_to_user<br> transferred_to_operator<br> failover_to_operator<br> user_terminated<br> service_declined – erro de configuração de AA<br> service_terminated – erros internos AA<br> failed_to_establish_media<br> terminated_no_operator<br> terminated_transfer_failed<br> terminated_automatic_selection<br> transferred_to_shared_voicemail<br> oaa_chain_too_long<br> oaa_session_too_long          |
|AAChainDuration                         |String                   |Duração da chamada de atendedor automático em segundos  |
|AACount                                 |String                   |# do atendedor automático envolve chamada         |
|AADirectorySearchMethod                 |String                   |Método de pesquisa usado na chamada:<br> abs_search_dtmf<br> abs_search_extension<br> abs_search_name<br>Tempo de chamada de cadeia de caracteres AAStartTime em UTC      |
|AATransferAction                        |String                   |Receptor de chamada:<br> desconhecido – o tipo de entidade não foi especificado<br>usuário -entidade de usuário<br> AA-entidade de atendedor automático da organização<br> CQ-entidade da fila de chamadas<br>aplicativo -entidade do aplicativo de voz<br>external_pstn -entidade PSTN externa<br>shared_voicemail-entidade de correio de voz compartilhada      |
|PSTNMinutes                             |int                      |Uso total de minutos                          |
|Resultado da chamada em fila de chamada                  |String                   |Estado final da chamada na fila de chamadas<br>valores possíveis:<br>erro de <br> recusada<br>estouro de <br> falhou<br> timed_out<br> transferred_to_agent<br>agent_joined_conference    |
|Identidade da fila de chamadas                     |String                   |Nome da conta de recurso anexada ao CQ     |
|Tipo de destino da fila de chamadas                  |String                   |Tipo de destino de redirecionamento de chamadas esperado:<br>usuário do <br>Ponto de extremidade do aplicativo <br>     |
|Resultado da chamada em fila de chamada                  |String                   |Estado final da chamada na fila de chamadas<br>valores possíveis:<br>erro de <br> recusada<br>estouro de <br> falhou<br> timed_out<br> transferred_to_agent<br>agent_joined_conference           |
|Ação de estado final da fila de chamadas           |String                   |Ação final da fila de chamadas<br>valores possíveis:<br>encaminhar <br>desconexão do <br>correio de voz <br> disconnect_with_busy<br> shared_voicemail<br> failed_to_accept_call<br>demais             |
|Nome do agente                              |String                   |UPN do usuário               |


### <a name="measures"></a>Mensura

|Nome                                      |Tipo                       |Descrição                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|AACallerActionCount                     |int                        |número de ações selecionadas pelo usuário em AA durante a chamada  |
|PSTNMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |n ° de chamadas                                          |
|Duração média da chamada (segundos)         |int                      |Duração total de chamadas na fila de chamadas em segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Atendedor automático da descrição do gráfico do Power BI

|Nome                                      |Descrição                            |
|---------------------------------------:|:-------------------------------------:|
|Fonte de chamadas de entrada                    |Distribuição de chamada por fonte interna/externa da chamada      |
|Totais do método de pesquisa de diretório          |Distribuição de chamada por tipo de pesquisa                         |
|Ação do chamador                           |Distribuição de chamada por receptor de chamadas                       |
|Resultado da chamada                             |Distribuição de chamada por estado final da chamada                    |
|Contagem de ação do chamador                     |Distribuição da ação de chamada por número usada durante a chamada  |


### <a name="call-queue"></a>Fila de chamadas

|Nome                                      |Descrição                            |
|---------------------------------------:|:-------------------------------------:|
|Fonte de chamadas de entrada                    |Distribuição de chamada por fonte interna/externa da chamada         |
|Volume da chamada                             |Distribuição de chamadas por filas de chamadas                            |
|Resultado do chamador                           |Distribuição de chamada por resultado da chamada                            |
|Ação de tempo limite/estouro total de chamadas      |Distribuição de chamada não encaminhada (abandonado) por resultado da chamada   |
|Transferir/redirecionar totais de destino          |Distribuição da chamada redirecionada por resultado da chamada                  |
|Taxa de chamadas abandonadas                   |Taxa de contagem de chamadas com êxito para abandonou                    |
|Tempo médio da sessão (segundos)        |Duração da chamada em segundos agrupadas por chamadas abandonadas/bem-sucedidas   |



### <a name="agent-timeline"></a>Linha do tempo do agente

|Nome                                                      |Descrição                            |
|-------------------------------------------------------:|:-------------------------------------:|
|# chamadas por agente                                        |Distribuição de chamada por fila de chamadas e agente                 |
|Duração total da chamada (segundos) por agente e fila de chamadas   |Duração total (segundos) de chamada por agente e fila de chamadas     |
|Duração média da chamada (segundos) pelo nome do agente            |Duração média (segundos) de chamada por agente                  |



## <a name="known-issues"></a>Problemas conhecidos
- Atualmente, a fila de chamadas e o atendedor automático mostram a ID das contas dos recursos em vez dos nomes da fila de chamadas/atendedor automático.  Para mostrar todo o tráfego de um atendedor automático ou de uma fila de chamadas, você deve selecionar todas as contas de recursos atribuídas ao atendedor automático ou à fila de chamadas.
- Atualmente, apenas 28 dias de histórico está disponível no painel, pois os dados da fila de chamadas/atendedor automático são considerados informações identificáveis pelo usuário final e estão sujeitos a políticas de retenção de privacidade de dados.
