---
title: Usando o relatório de Power BI CQD para exibir Atendedor Automático & Relatório Histórico da Fila de Chamada
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre como usar o relatório do Painel de Qualidade de Chamada Power BI para exibir Atendedor Automático dados históricos da Fila de Chamada.
ms.openlocfilehash: 73ffd8e993a3dacd0412123d49e19c704df0cb8c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731380"
---
# <a name="what-are-the-requirements"></a>Quais são os requisitos? 
Você precisa ter Power BI Desktop instalado. Você pode instalá-lo no [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Você pode usar a versão gratuita do Power BI Desktop. A versão mínima compatível é 2.85.681.0 (setembro de 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permissões para acessar o pipeline do CQD
A conta que você usa para exibir o relatório histórico do AA & CQ Analytics precisa ter permissões para acessar o pipeline de dados CQD. Consulte a função de acesso [CQD para](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) obter mais informações.

## <a name="installation"></a>Instalação 
As etapas a seguir pressuem que você já instalou Power BI Desktop no computador e que sua conta tem as permissões necessárias para acessar o pipeline de dados CQD.

Execute estas etapas:
- Baixe o Modelo de Relatório Histórico Teams Atendedor Automático & fila de chamada do [CQD](./aa-cq-cqd-historical-reports.md) e salve-o em um diretório em seu computador.

- Clique duas vezes no modelo e Power BI Desktop deve ser acionado.

- Você será solicitado a selecionar a região do pipeline de dados CQD. Selecione a região onde seu locatário está localizado.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração.":::

 - Você pode ver a região usando o cmdlet Skype for Business PS Online (Get-CsTenant). Saída serviceInstance. 
 A região será exibida após o /like neste exemplo: 
 
   microsoftcommunicationsonline/noam-4a-s7 onde a região é noam.
   
 - O relatório será lançado com dados de exemplo.
 
 - Para ver seus próprios dados, clique em **Atualizar** na guia Home em Consultas Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração.":::

- Em seguida, você será solicitado a entrar. Selecione **Conta da Organização** e, em seguida, selecione **Entrar**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração.":::

- Selecione **Conexão** e assista à atualização de dados.

## <a name="data-latency-any-aa--cq-analytics"></a>Latência de dados Qualquer análise do AA & CQ
Os dados estarão disponíveis no pipeline de dados CQD dentro de 30 minutos.

Você terá que atualizar os dados para ver os novos dados de análise. 

## <a name="customization"></a>Personalização 
Você pode personalizar determinados aspectos de visualização dos relatórios, como adicionar ou remover campos a serem mostrados nas várias visualizações, alterar o tipo de gráfico, etc.

Não é possível adicionar campos de dados adicionais que não os fornecidos no relatório.

### <a name="change-color-schema"></a>Alterar esquema de cores 
As etapas a seguir pressuem que você já concluiu as etapas de instalação.

Execute estas etapas:
- Selecione **Exibir guia** na faixa de opções.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração.":::

- Selecione o esquema de cores na listada.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração.":::


## <a name="cqd-fields-description"></a>Descrição dos campos CQD

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Atendedor Automático Identidade                 |string                   |Nome da conta de recurso anexada ao AA<br>Exemplo: aa_test@microsoft.com|
|Atendedor Automático hora de início da cadeia         |datetime                 |Hora de início da cadeia de AA                    |
|Atendedor Automático De pesquisa de diretório  |string                   |Método de pesquisa do Livro de Endereços Últimos        |
|Atendedor Automático Ação de Transferência          |string                   |Tipo de destino de transferência de chamada<br>Valores possíveis:<br>§ desconhecido - tipo de entidade não foi especificado<br>§ user - entidade do usuário<br>§ orgaa - Entidade Atendedor Automático organizacional<br>§ hunt_group - Entidade fila de chamada<br>§ application - entidade de aplicativo de voz<br>§ external_pstn - entidade PSTN externa<br>§ shared_voicemail - entidade de caixa postal compartilhada|
|Atendedor Automático Resultado da Chamada              |string                   |Resultado da chamada:<br>§ desconhecido - Falha na configuração ou transferência de chamada e o serviço não recebeu nenhum motivo significativo de falha <br>§ transferred_to_user - Chamada transferida para um usuário por meio de Dial By Name/Extension ou Opção de Menu configurada <br>§ transferred_to_operator - A chamada foi transferida para um operador configurado, por exemplo, se o AA estiver configurado com um operador para o pós-horário <br>§ failover_to_operator - Fallback para operador quando a transferência falhar ou o reconhecimento de nome não funcionar após três tentativas<br>§ user_terminated - O chamador terminou a chamada <br>§ service_declined - Chamada recusada pelo serviço, isso pode acontecer se o serviço não conseguir buscar Atendedor Automático configuração <br>§ service_terminated - o serviço back-end terminou a chamada, possivelmente se uma transferência para o destino falhar e nenhum operador for configurado como um fallback <br>§ failed_to_establish_media - Falha no estabelecimento de mídia entre o chamador e o serviço <br>§ terminated_no_operator - Falha no reconhecimento de nome após três tentativas e nenhum operador está configurado <br>§ terminated_transfer_failed - Falha na transferência para destino e nenhum operador está configurado <br>§ terminated_automatic_selection - Se nenhuma ação for configurada durante ou após o horário, a chamada será encerrada por padrão <br>§ transferred_to_shared_voicemail - Chamada transferida para caixa postal compartilhada se configurada como destino <br>§ oaa_chain_too_long - Quando uma cadeia de Atendedor Automático exceder cinco Atendimentos Automáticos em sucessão, a chamada será encerrada para evitar possíveis loops de chamada <br>§ oaa_session_too_long - A chamada excedeu o comprimento máximo de sessão permitida e o tempo limite foi ultrapassado |
|Atendedor Automático chamada Flow                |string                   |Encapsula os diferentes estados de Atendedor Automático Call<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ comunicado|
|Está Atendedor Automático envolvido              |Boolean                  |Indicado se a AA está envolvida na chamada |
|Atendedor Automático contagem de ações do chamador      |int                      |Contagem da ação usada pelo chamador         |
|Atendedor Automático de duração da cadeia   |int                      |Duração da chamada no AA                 |
|Resultado da chamada de fila de chamada                  |Cadeia de caracteres                   |Estado final da chamada de fila de chamada<br>valores possíveis:<br>§ error<br>§ recusado<br>§ estouro<br>§ falhou<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Ação de estado final da fila de chamada           |Cadeia de caracteres                   |Ação final da fila de chamada<br>valores possíveis:<br>§ forward<br>§ disconnect<br>§ caixa postal<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ outros|
|Identidade da Fila de Chamada                     |Cadeia de caracteres                   |Nome da conta de recurso anexada ao CQ<br>Exemplo: aa_test@microsoft.com|
|Fila de Chamada é modo de conferência           |Boolean                  |Definir como 1 se o modo de conferência estiver habilitado no CQ |
|Tipo de destino de fila de chamada                  |Cadeia de caracteres                   |Tipo de destino de redirecionamento de chamada esperado     |
|Transferido da identidade da fila de chamada    |Boolean                  |Nome da conta de recurso anexada ao CQ da qual essa chamada foi transferida<br>Exemplo: aa_test@microsoft.com|
|Opção do Agente de Fila de Chamada na Contagem           |int                      |Contagem de agentes disponíveis para essa fila no momento da chamada |
|Contagem do Agente de Fila de Chamada                  |int                      |Contagem de agentes atribuídos a essa fila no momento da chamada |
|É a fila de chamada envolvida                  |Boolean                  |Se a fila de chamada estiver envolvida nessa chamada igual a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensões do modelo de dados do PowerBI

|Nome                                    |Tipo de dados                |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome do AA                                   |string                   |Atendedor Automático ID (ID da conta de recurso) |
|AACallFlow                              |string                   |Encapsula os diferentes estados de Atendedor Automático Call<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>announcement |
|AACallResult                            |string                   |Resultado de Atendedor Automático Chamada:<br>§ desconhecido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – erro de configuração do AA<br>§ service_terminated – erros internos do AA<br>§ failed_to_establish_media<br>terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |string                   |Duração Atendedor Automático chamada em segundos  |
|AACount                                 |string                   |# de Atendedor Automático envolver na chamada         |
|AADirectorySearchMethod                 |string                   |Método de pesquisa usado na chamada:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |string                   |Hora da chamada em UTC                            |
|AATransferAction                        |string                   |Receptor de chamada:<br>§ desconhecido - tipo de entidade não foi especificado<br>§ user - entidade do usuário<br>§ AA - Entidade de Atendedor Automático organizacional<br>§ CQ - Entidade fila de chamada<br>§ application - entidade de aplicativo de voz<br>§ external_pstn - entidade PSTN externa<br>§ shared_voicemail - entidade de caixa postal compartilhada      |
|PSTNMinutes                             |int                      |Uso total de minutos                          |
|Resultado da chamada de fila de chamada                  |string                   |Estado final da chamada de fila de chamada<br>valores possíveis:<br>§ error<br>§ recusado<br>§ estouro<br>§ falhou<br>timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identidade da Fila de Chamada                     |string                   |Nome da conta de recurso anexada ao CQ     |
|Tipo de destino de fila de chamada                  |string                   |Tipo de destino de redirecionamento de chamada esperado:<br>§ Usuário<br>§ Ponto de extremidade do aplicativo<br>§ Outros     |
|Resultado da chamada de fila de chamada                  |string                   |Estado final da chamada de fila de chamada<br>valores possíveis:<br>§ error<br>§ recusado<br>§ estouro<br>§ falhou<br>timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Ação de estado final da fila de chamada           |string                   |Ação final da fila de chamada<br>valores possíveis:<br>§ forward<br>§ disconnect<br>§ caixa postal<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ outros             |
|Nome do Agente                              |string                   |UPN do usuário               |


### <a name="measures"></a>Medidas

|Nome                                      |Tipo                       |Descrição                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# da ação selecionada pelo usuário no AA durante a chamada  |
|PSTNMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |# de chamadas                                          |
|Duração média da chamada( Segundos)         |int                      |Duração total das chamadas de fila de chamadas em segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI descrição do gráfico Atendedor Automático

|Nome                                      |Descrição                            |
|:---------------------------------------|:--------------------------------------|
|Fonte de chamada de entrada                    |Distribuição de chamada por fonte de chamada interna/externa      |
|Totais do método de pesquisa de diretório          |Distribuição de chamada por tipo de pesquisa                         |
|Ação do chamador                           |Distribuição de chamada por receptor de chamada                       |
|Resultado da chamada                             |Distribuição da chamada por estado de chamada final                    |
|Contagem de ações do chamador                     |Distribuição da ação de chamada por número usada durante a chamada  |


### <a name="call-queue"></a>Fila de Chamada

|Nome                                      |Descrição                            |
|:---------------------------------------|:--------------------------------------|
|Fonte de chamada de entrada                    |Distribuição de chamada por fonte de chamada interna/externa         |
|Volume da chamada                             |Distribuição de filas de chamada por chamada                            |
|Resultado do chamador                           |Distribuição do resultado da chamada por chamada                            |
|Ação total de chamada tempo-extra/estouro      |Distribuição de not forwarded(abandoned) call by call result   |
|Totais de destino de transferência/encaminhamento          |Distribuição de chamada encaminhada por resultado de chamada                  |
|Taxa de chamadas abandonadas                   |Taxa de sucesso para contagem de chamada abandonada                    |
|Comprimento médio da sessão (segundos)        |Comprimento da chamada em segundos agrupado por chamadas abandonadas/bem-sucedidas   |



### <a name="agent-timeline"></a>Linha do tempo do agente

|Nome                                                      |Descrição                            |
|:-------------------------------------------------------|:--------------------------------------|
|# chamadas por agente                                        |Distribuição de chamada por fila de chamada e agente                 |
|Duração total da chamada (segundos) por agente e Fila de Chamada   |Duração total (segundos) da chamada por agente e fila de chamada     |
|Duração média da chamada (segundos) pelo nome do agente            |Duração média (segundos) da chamada por agente                  |



## <a name="known-issues"></a>Problemas Conhecidos
- Atualmente, Fila de Chamada e atendimento automático mostram a ID de contas de recurso em vez de nomes de fila de chamada/atendimento automático.  Para mostrar todo o tráfego de um atendimento automático ou fila de chamada, selecione todas as contas de recurso atribuídas ao atendimento automático ou fila de chamada.

- Atualmente, apenas 28 dias de histórico estão disponíveis no painel, pois os dados de fila de chamada/atendimento automático são considerados informações de identificação do usuário final e estão sujeitos a políticas de retenção de privacidade de dados.
