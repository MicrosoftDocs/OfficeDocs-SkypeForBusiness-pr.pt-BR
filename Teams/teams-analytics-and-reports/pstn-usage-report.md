---
title: Microsoft Teams Relatório de uso de PSTN
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Saiba como usar o relatório de uso Teams PSTN no centro de administração Microsoft Teams para obter uma visão geral do uso de chamada e audioconferência em sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c6dccd9012b9756679bc09534d68f24a58052665
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861938"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams Relatório de uso de PSTN

O Teams de uso do PSTN (Rede Telefônica Pública Comutado) no centro de administração Microsoft Teams oferece uma visão geral da atividade de chamada e audioconferência em sua organização. Você pode exibir atividades de chamadas detalhadas para Planos de Chamadas se você usar a Microsoft como sua operadora de telefonia e para Roteamento Direto se você usar sua própria operadora de telefonia.

A **guia Planos de** Chamadas mostra informações, incluindo o número de minutos gastos pelos usuários em chamadas PSTN de entrada e saída e o custo dessas chamadas. A **guia Roteamento** Direto mostra informações, incluindo o endereço SIP e os horários de início e término da chamada. Use as informações deste relatório para obter informações sobre o uso de PSTN em sua organização e ajudá-lo a investigar, planejar e tomar decisões comerciais.

> [!NOTE]
> Se você tiver um plano de chamada Telstra ou Softbank, não verá nenhum registro de detalhes de chamada no relatório de uso do PSTN. Entre em contato com Telstra ou Softbank para saber mais sobre suas necessidades de relatórios. 

## <a name="view-the-pstn-usage-report"></a>Exibir o relatório de uso PSTN

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório**, selecione Relatório de uso **PSTN**.
2. Em **Intervalo de datas,** selecione um intervalo predefinido de 7 ou 28 dias ou de definir um intervalo personalizado e selecione **Executar relatório**.

## <a name="interpret-the-report"></a>Interpretar relatório

### <a name="calling-plans"></a>Planos de Chamadas

   ![Captura de tela do relatório de uso do PSTN planos de chamada no centro de administração](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Captura de tela do relatório de uso do PSTN no centro de administração Microsoft Teams com callouts numerados](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser exibido para tendências nos últimos 7, 28 dias ou um intervalo de datas personalizado que você definiu |
|**2**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período de tempo selecionado. <br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela fornece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora em que a chamada foi iniciada.</li><li>**Nome para** exibição é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Microsoft Teams de administração.</li><li>**Nome** de usuário é o nome de login do usuário.</li><li>**Telefone número** é o número que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída.</li><li>**O tipo de** chamada é se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que você pode ver incluem:<br><br>**Teams tipos de chamada de usuário**<ul><li>**user_in** - o usuário recebeu uma chamada PSTN de entrada.</li><li>**user_out** - o usuário fez uma chamada PSTN de saída</li><li>**user_out_conf** - o usuário adicionou dois ou mais participantes PSTN à chamada, como uma chamada de conferência de três vias</li><li>**user_out_transfer** - o usuário transferiu a chamada para um número PSTN</li><li>**user_out_forwarding** - o usuário encaminhou a chamada para um número PSTN</li><li>**conf_in** - uma chamada de entrada para a ponte de Audioconferência</li><li>**conf_out** - uma chamada de saída da ponte de Audioconferência geralmente para adicionar um número PSTN à conferência</li><li>**unassigned_in** - uma chamada PSTN de entrada via Plano de Chamada para um número não atribuído</li></ul><br>**Teams tipos de chamada de bots**<ul><li>**ucap_in** - uma chamada PSTN de entrada para Teams bot, como atendimento automático ou fila de chamada</li><li>**ucap_out** - uma chamada PSTN de saída de um bot Teams como atendimento automático ou fila de chamada</li></ul><br><li>**Chamado para** é o número discado.</li><li>**Para país ou região** é o país ou região discado.</li><li>**Chamado de** é o número que fez a chamada.</li><li>**De país ou região** é o país ou região de onde a chamada foi colocada.</li><li>**A** cobrança é a quantidade de dinheiro ou custo da chamada que é cobrada em sua conta. </li><li>**Conversor de Moedas** é o tipo de moeda usada para calcular o custo da chamada. </li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Doméstico/internacional** informa se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário.</li><li>**A ID da** chamada é a ID de chamada de uma chamada. É um identificador para a chamada que você pode usar ao chamar o Suporte da Microsoft.</li><li>**Tipo de** número é o tipo de número de telefone do usuário, como um serviço de número de chamada gratuita. </li><li>**País ou região é** o local de uso. </li> <li>**A ID da** conferência é a ID da conferência de áudio. </li><li>**A funcionalidade** é a licença usada para a chamada. Os tipos de licença que você pode ver incluem:<ul><li>**MCOEV ou MCOEV_VIRTUALUSER ou MCOEV_VIRTUALUSER_GOV** - Aplicativos de voz, como Atendimento Automático ou Filas de Chamadas</li><li>**FREECALL** - Em caso de um problema técnico que nos impeça de precificação de uma chamada, a chamada é fornecida gratuitamente e aparecerá com esse recurso</li><li>**MCOPSTN1** - Plano de Chamada Doméstica (3.000 min us / 1200 min planos da UE)</li><li>**MCOPSTN2** - Plano de Chamada Internacional</li><li>**MCOPSTN5** - Plano de Chamada Doméstica (plano de chamada de 120 minutos)</li><li>**MCOPSTN6** - Plano de Chamada Doméstica (plano de chamada de 240 minutos)</li><li>**MCOPSTN8** - Plano de Chamada Doméstica 120 min por usuário (não está em pool entre usuários, como os outros planos de chamada)</li><li>**MCOPSTN9** - Plano de Chamada Internacional</li><li>**MCOPSTNCAP** - Área comum Telefone</li><li>**MCOPSTNPP** - Créditos de Comunicações</li><li>**MCOMEETADD -** Audioconferência</li><li>**MCOMEETADD_DIALOUT_US** - Plano de discagem de Audioconferência dos EUA e do Canadá</li><li>**MCOMEETADD_CN_GLOBAL** - Audioconferência para usuários que não são da China</li><li>**MCOMEETADD_TATA** - Conexões de Comunicações de Tata</li><li>**MCOMEETACPEA** - Audioconferência Pay-per-Minute </li><li>**MCOMEETACPEA_GOV** - Audioconferência Paga por Minuto para o Governo</li></ul></li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **Filtrar** para filtrar o relatório por nome de usuário ou tipo de chamada |
|**7**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira. |
|**8**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando estiver pronto.|

### <a name="direct-routing"></a>Roteamento Direto

   ![Captura de tela do relatório de uso de PSTN de Roteamento Direto no centro de administração](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Captura de tela do relatório de uso de PSTN de Roteamento Direto no centro de administração Microsoft Teams com callouts numerados](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser exibido para tendências nos últimos 7 ou 28 dias. |
|**2**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período de tempo selecionado.<br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela fornece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora em que a chamada foi iniciada.</li><li>**Nome para** exibição é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir até a página de configurações do usuário no Microsoft Teams de administração. O nome também pode ser o nome de um bot, por exemplo, a Fila de Chamada ou a nuvem Atendedor Automático. </li><li>**O endereço SIP** é o endereço SIP do usuário ou um bot que recebeu ou fez a chamada.</li><li>**O número do** chamador é o número do usuário ou do bot que fez a chamada. </li><li>**O número do chamador** é o número do usuário ou do bot que recebeu a chamada. Em uma chamada de entrada para um usuário Teams será o usuário Teams, em uma chamada de saída de um usuário Teams será o Usuário PSTN. </li><li>**O tipo de** chamada é se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamada que você pode ver incluem:<br><br>**Teams tipos de chamada de usuário**<ul><li>**dr_in** - o usuário recebeu uma chamada PSTN de entrada</li><li>**dr_out** - o usuário fez uma chamada PSTN de saída</li><li>**dr_out_user_conf** - o usuário adicionou um participante PSTN à chamada</li><li>**user_out_transfer** - o usuário transferiu a chamada para um número PSTN</li><li>**dr_out_user_forwarding** - o usuário encaminhou a chamada para um número PSTN</li><li>**dr_out_user_transfer** - o usuário transferiu a chamada para um número PSTN</li><li>**dr_emergency_out** - o usuário fez uma chamada de emergência</li><li>**dr_unassigned_in** - uma chamada PSTN de entrada via Roteamento Direto para um número não atribuído</li></ul><br>**Teams tipos de chamada de bots**<ul><li>**dr_in_ucap** - uma chamada PSTN de entrada para um bot Teams como atendimento automático ou fila de chamada</li><li>**dr_out_ucap** - uma chamada PSTN de saída de um bot Teams como atendimento automático ou fila de chamada</li></ul><br><li>**Chamado para** é o número do usuário que recebeu a chamada.</li><li>A hora de início **(UTC)** é a hora em que o proxy SIP recebeu a resposta final (Mensagem SIP "200 OK") do SBC em uma chamada de saída (Teams/Bot para um usuário PSTN) ou depois que o Proxy SIP enviar o Convite para o próximo salto dentro do back-end do Teams em uma chamada de entrada (Usuário PSTN para um Teams/Bot). </li><li>Hora do convite **(UTC)** é a hora em que o Convite inicial foi enviado em uma chamada de saída de uma chamada de usuário ou bot do Teams para o SBC ou recebido em uma chamada de entrada para uma chamada de Teams ou bot pelo componente proxy SIP do Roteamento Direto do SBC.</li><li>**Tempo de falha (UTC)** é a hora em que a chamada falhou. Somente para chamadas com falha. O Código SIP Final, o Subcódigo Final da Microsoft e a Frase FINAL SIP fornecem os motivos pelos quais a chamada falhou e pode ajudar na solução de problemas. </li><li>**Hora de término (UTC)** é a hora em que a chamada terminou (somente para chamadas bem-sucedidas).</li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Tipo de** número é o tipo de número de telefone do usuário, como um serviço de número de chamada gratuita. </li><li>**O bypass de** mídia indica se o tronco foi habilitado para bypass de mídia. </li> <li>**FQDN SBC** é o FQDN (nome de domínio totalmente qualificado) do Controlador de Borda de Sessão (SBC). </li><li>**A região do Azure para Mídia** é o data center que foi usado como caminho de mídia em uma chamada que não seja ignorada. </li><li>**A região do Azure para Sinalização** é o data center usado para sinalização para chamadas de bypass e não bypass. </li><li>**Tipo de** evento é o tipo de evento da chamada. Você verá Êxito para chamadas bem-sucedidas e Tentativa de chamadas com falha. </li><li>**Código SIP final** é o código com o qual a chamada terminou.</li><li>**O subcódigo final** da Microsoft é um código que indica ações específicas que ocorreram.</li><li>**A frase SIP final** é a descrição do código SIP e do subcódigo da Microsoft.</li><li>**A ID de** correlação é um identificador exclusivo para a chamada que você pode usar ao chamar o Suporte da Microsoft.</li><li>**A ID de Correlação** Compartilhada só fica visível no arquivo CSV baixável e não existe no portal. A ID de correlação compartilhada existe em pelo menos duas chamadas relacionadas. Confira a descrição detalhada abaixo.</li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira. |
|**7**   |Selecione **Exportar para Excel** baixar os dados em um arquivo separado por vírgula (CSV) para análise offline ou para usá-los como entrada para seu sistema de cobrança. |

#### <a name="callercallee-fields-considerations"></a>Considerações sobre campos de chamador/chamador

Dependendo da direção da chamada, os nomes de chamador ou chamador podem conter números que não são E164.

Esses campos podem vir dos SBC(s) do cliente. Há três formatos que o SBC pode enviar para Roteamento Direto: números E.164, números não E.164 e cadeias de caracteres.

- Número de telefone E.164 de um usuário que tem um número E.164 para um usuário que também tem um número E.164. 
- Chamada de um número que não seja E.164. Um usuário de um PBX de terceiros interconectado com Roteamento Direto faz uma chamada para um Teams usuário. Nesse caso, o número do chamador pode ser qualquer número que não seja E.164, por exemplo +1001. 
- Um remetente de spam chama e não apresenta um número, apenas um nome, por exemplo "Serviço de Receita Interna". Essa cadeia de caracteres será mostrada nos relatórios.

#### <a name="about-shared-correlation-id"></a>Sobre a ID de Correlação Compartilhada

A ID de Correlação Compartilhada só existe no arquivo de Excel exportado que você baixa e indica que duas ou mais chamadas estão relacionadas. O seguinte explica os diferentes cenários e quando a ID de Correlação Compartilhada está presente.

1.    Usuário PSTN 1 em um ponto de extremidade PSTN chamado Teams Usuário 1 no cliente Teams, tipo de chamada Dr_In, ID de correlação 57f28917-42k5-4c0c-9433-79734873f2ac, sem ID de correlação compartilhada.
2.    Teams Usuário 1 em um cliente Teams chamado PSTN User 1 em um ponto de extremidade PSTN, tipo de chamada Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, sem ID de correlação compartilhada.
3.    Usuário PSTN 1 em um ponto de extremidade PSTN chamado Teams Usuário 2 no Teams cliente, tipo de chamada Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de correlação compartilhada f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Chamada existente 3 com ID de correlação "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuário PSTN 1 em uma chamada com Teams Usuário 2. Teams Usuário 2 transferido (cego ou consultivo) uma chamada para Teams ou Usuário PSTN, tipo de chamada Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID de correlação compartilhada f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportando os relatórios
Clique **em Exportar para Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando estiver pronto. O processo de exportação pode levar de alguns segundos a vários minutos para ser concluído, dependendo da quantidade dos dados.

Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores. Arquivos exportados contêm campos adicionais que não estão disponíveis no relatório online. Eles podem ser usados para solucionar problemas e fluxos de trabalho automatizados.

 Você receberá um arquivo zip chamado "**Calls.Export. `[identifier]`.zip**", com o identificador sendo uma ID exclusiva para a exportação que pode ser usada para solução de problemas.

Se você tiver planos de chamadas e roteamento direto, o arquivo exportado poderá conter dados para ambos os produtos. O arquivo de relatório de uso de PSTN terá nome de arquivo "**PSTN.calls. `[UTC date]`.csv**" e Roteamento Direto "**DirectRouting.calls. `[UTC date]`.csv**".

 Além dos arquivos PSTN e Roteamento Direto, o arquivo contém "**parameters.json**", com o intervalo de tempo de exportação selecionado e os recursos.

Os arquivos exportados estão no formato CSV (Valores Separados por Vírgula), em conformidade com [o padrão RFC 4180.](https://tools.ietf.org/html/rfc4180) Os arquivos podem ser abertos em Excel ou em qualquer outro editor compatível com padrões sem exigir transformações.

A primeira linha do CSV contém nomes de coluna. Todas as datas são UTC e [no formato ISO 8601.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Relatório de uso de PSTN exportado

 Você pode exportar dados de até um ano a partir da data atual, a menos que os regulamentos específicos do país proíbam a retenção dos dados por 12 meses.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo de dados (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador de chamada exclusivo |
> | 1 | ID da chamada | `nvarchar(64)` | Identificador de chamada. Não é garantido que seja exclusivo |
> | 2 | ID de conferência | `nvarchar(64)` | ID da conferência de áudio |
> | 3 | Localização do usuário | `nvarchar(2)` | Código de país do usuário, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Chamando a ID do usuário Azure Active Directory.<br/> Essa e outras informações de usuário serão nulas/vazias para tipos de chamada de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nome de login) no Azure Active Directory.<br/>Isso geralmente é o mesmo que o Endereço SIP do usuário e pode ser igual ao endereço de email do usuário |
> | 6 | Nome de exibição do usuário | `nvarchar(128)` | Nome de exibição do usuário |
> | 7 | ID do chamador | `nvarchar(128)` | Número que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de Chamada | `nvarchar(32)` | Se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de telefone do usuário, como um serviço de número de chamada gratuita |
> | 10 | Doméstico/Internacional | `nvarchar(16)` | Se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário |
> | 11 | Destino Discado | `nvarchar(64)` | País ou região discada |
> | 12 | Número de Destino | `nvarchar(32)` | Número discado no [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de Início | `datetimeoffset` | Hora de início da chamada |
> | 14 | Hora de Término | `datetimeoffset` | Hora de término da chamada |
> | 15 | Segundos de Duração | `int` | Por quanto tempo a chamada foi conectada |
> | 16 | Taxa de Conexão | `numeric(16, 2)` | Preço da taxa de conexão |
> | 17 | Charge | `numeric(16, 2)` | Quantidade de dinheiro ou custo da chamada que é cobrada em sua conta |
> | 18 | Moeda | `nvarchar(3)` | Tipo de moeda usada para calcular o custo da chamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Recursos | `nvarchar(32)` | A licença usada para a chamada |

### <a name="exported-direct-routing-usage-report"></a>Relatório de uso do Roteamento Direto Exportado

Você pode exportar dados de até cinco meses (150 dias) a partir da data atual, a menos que as regulamentações específicas do país proíbam a retenção dos dados para esse período.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo de dados (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificador de chamada exclusivo |
> | 1 | Endereço SIP | `nvarchar(128)` | O endereço do usuário ou bot que fez ou recebeu a chamada.<br/>Observe que este é realmente UserPrincipalName (UPN, nome de logon) no Azure Active Directory, que normalmente é o mesmo que Endereço SIP |
> | 2 | Nome para Exibição | `nvarchar(128)` | O nome de um usuário ou um bot de chamada (por exemplo, Fila de Chamada ou Atendedor Automático) como definido em Centro de administração do Microsoft 365 |
> | 3 | País do usuário | `nvarchar(2)` | Código de país do usuário, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Hora do convite | `datetimeoffset` | Quando o convite inicial enviar na saída de Teams chamada de usuário ou bot para o SBC ou recebido na entrada para Teams ou chamada de bot pelo componente proxy SIP do Roteamento Direto do SBC |
> | 5 | Hora de início | `datetimeoffset` | Hora em que o proxy SIP recebeu a resposta final (Mensagem SIP "200 OK") do SBC na saída (Teams/Bot para um usuário PSTN) ou depois que o Proxy SIP enviar o Convite para o próximo salto dentro de um Teams back-end na chamada de entrada (Usuário PSTN para um Teams/Bot).<br/>Para chamadas com falha e sem resposta, isso pode ser igual a tempo de convite ou falha |
> | 6 | Tempo de falha | `datetimeoffset` | Só existe para chamadas com falha (não totalmente estabelecidas) |
> | 7 | Hora de término | `datetimeoffset` | Só existe para chamadas bem-sucedidas (totalmente estabelecidas). Hora em que a chamada terminou |
> | 8 | Duração (segundos) | `int` | Duração da chamada |
> | 9 | Sucesso | `nvarchar(3)` | Sim/Não. Sucesso ou tentativa |
> | 10 | Número do chamador | `nvarchar(32)` | Número do usuário ou bot que fez a chamada. Ao entrar em uma chamada de usuário de equipe, ele será um Usuário PSTN, na saída de Teams chamada de usuário será o número de usuário Teams usuário |
> | 12 | Número do chamador | `nvarchar(32)` | Número do usuário ou bot que recebeu a chamada. Ao entrar em uma chamada de usuário de equipe, ele será o usuário Teams, ao sair de Teams chamada de usuário será o Usuário PSTN |
> | 13 | Tipo de chamada | `nvarchar(32)` | Tipo e direção de chamada |
> | 14 | Região do Azure para Mídia | `nvarchar(8)` | O datacenter usado para o caminho de mídia em chamada não ignorada |
> | 15 | Região do Azure para Sinalização | `nvarchar(8)` | O datacenter usado para sinalização para chamadas de bypass e não bypass |
> | 16 | Código SIP final | `int` | O código com o qual a chamada terminou, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Subcodigo final da Microsoft | `int` | Além dos códigos SIP, a Microsoft tem subcódigos próprios que indicam o problema específico |
> | 18 | Frase FINAL SIP | `nvarchar(256)` | Descrição do código SIP e subcódigo da Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nome de domínio totalmente qualificado do controlador de borda de sessão |
> | 20 | Bypass de mídia | `nvarchar(3)` | Sim/Não. Indica se o tronco foi habilitado para bypass de mídia ou não |
> | 21 | ID de correlação compartilhada | `uniqueidentifier` | Indica que duas ou mais chamadas estão relacionadas |


## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
