---
title: Relatório de uso PSTN do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Saiba como usar o relatório de uso de PSTN do teams no centro de administração do Microsoft Teams para obter uma visão geral do uso de chamadas e videoconferências em sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c35699093168f5bb0443277f65da9a8060f27b69
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778247"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Relatório de uso PSTN do Microsoft Teams

O relatório de uso de PSTN do teams no centro de administração do Microsoft Teams oferece uma visão geral de atividades de chamadas e conferência de áudio em sua organização. Você pode exibir atividades de chamada detalhadas para planos de chamada se usar a Microsoft como sua operadora de telefonia e para roteamento direto se você usar sua própria operadora de telefonia.

A guia **planos de chamada** mostra informações, incluindo o número de minutos gastos pelos usuários em chamadas PSTN de entrada e saída e o custo dessas chamadas. A guia **encaminhamento direto** mostra informações incluindo o endereço SIP e os horários de início e término da chamada. Use as informações neste relatório para obter informações sobre o uso da PSTN em sua organização e ajudá-lo a investigar, planejar e tomar decisões de negócios.

## <a name="view-the-report"></a>Exibir o relatório

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** > relatórios de**uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **relatório de uso de PSTN**.
2. Em **intervalo de datas**, selecione um intervalo predefinido de 7 ou 28 dias, ou defina um intervalo personalizado e selecione **executar relatório**.

## <a name="interpret-the-report"></a>Interpretar relatório

### <a name="calling-plans"></a>Planos de Chamadas

![Captura de tela do relatório de relatório de uso PSTN dos planos de chamada no centro de administração](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Captura de tela do relatório de uso de PSTN no centro de administração do Microsoft Teams com textos explicativos numerados")

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser exibido para obter tendências nos últimos sete dias, 28 dias ou um intervalo de datas personalizado que você definiu |
|**2**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período de tempo selecionado. <br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela oferece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora de início da chamada.</li><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams.</li><li>**Nome** de usuário é o nome do usuário.</li><li>**Número de telefone** é o número que recebeu a chamada para chamadas recebidas ou o número discado para chamadas feitas.</li><li>**Tipo de chamada** é se a chamada foi uma chamada PSTN de saída ou de entrada e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que podem ser exibidas incluem:<br><br>**Tipos de chamada de usuário do teams**<ul><li>**user_in** -o usuário recebeu uma chamada PSTN de entrada.</li><li>**user_out** -o usuário fez uma chamada PSTN de saída</li><li>**user_out_conf** -o usuário adicionou dois ou mais participantes PSTN à chamada, como uma chamada em conferência tripla</li><li>**user_out_transfer** -o usuário transferiu a chamada para um número PSTN</li><li>**user_out_forwarding** -o usuário encaminhou a chamada para um número PSTN</li><li>**conf_in** -uma chamada de entrada para a ponte de audioconferência</li><li>**conf_out** -uma chamada de saída da ponte de videoconferência geralmente para adicionar um número PSTN à conferência</li></ul><br>**Tipos de chamada de bots do teams**<ul><li>**ucap_in** -uma chamada PSTN de entrada para bot de equipe, como atendedor automático ou fila de chamadas</li><li>**ucap_out** -uma chamada PSTN de saída de um bot de equipe, como atendedor automático ou fila de chamadas</li></ul><br><li>**Chamado para** é o número discado.</li><li>**Para país ou região** , a discagem do país ou região.</li><li>**Chamado de** é o número que fez a chamada.</li><li>**Do país ou região** é o país ou região de onde a chamada foi feita.</li><li>**Encargo** é a quantia de dinheiro ou o custo da chamada cobrada na sua conta. </li><li>**Moeda** é o tipo de moeda usado para calcular o custo da chamada. </li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Doméstica/internacional** informa se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário.</li><li>A **ID da chamada** é a ID da chamada para uma chamada. Trata-se de um identificador para a chamada que você pode usar ao ligar para o suporte da Microsoft.</li><li>**Tipo de número** é o tipo de número de telefone do usuário, como um serviço de número de chamada gratuita. </li><li>**País ou região** é o local de uso. </li> <li>**ID de conferência** é a ID de conferência da conferência de áudio. </li><li>**Recurso** é a licença usada para a chamada. Os tipos de licença que podem ser exibidos incluem:<ul><li>**MCOPSTNPP** -créditos de comunicações</li><li>**MCOPSTN1** -plano de chamadas domésticas (3000 min-US/1200 min) planos da UE)</li><li>**MCOPSTN2** -plano de chamadas internacionais</li><li>**MCOPSTN5** -plano de chamadas domésticas (120 min – plano de chamadas)</li><li>**MCOPSTN6** -plano de chamadas domésticas (240 min – plano de chamadas)</li><li>**MCOMEETADD** -audioconferência</li><li>**MCOMEETACPEA** -conferência de áudio de pagamento por minuto</li></ul></li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **Filtrar** para filtrar o relatório por nome de usuário ou tipo de chamada |
|**7**   |Selecione **tela inteira** para exibir o relatório em modo de tela inteira. |
|**8**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.|

### <a name="direct-routing"></a>Roteamento Direto

![Captura de tela do relatório de uso de uso de PSTN de roteamento direto no centro de administração](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Captura de tela do relatório de uso de PSTN Routing Direct no centro de administração do Microsoft Teams com textos explicativos numerados")

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser exibido para obter tendências nos últimos sete dias ou 28 dias. |
|**2**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período de tempo selecionado.<br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela oferece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora de início da chamada.</li><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configurações do usuário no centro de administração do Microsoft Teams. O nome também pode ser o nome de um bot, por exemplo, a fila de chamadas ou o atendedor automático na nuvem. </li><li>**Endereço SIP** é o endereço SIP do usuário ou um bot que recebeu ou fez a chamada.</li><li>**Número de chamada** é o número do usuário ou do bot que fez a chamada. </li><li>**Número do chamador** é o número do usuário ou do bot que recebeu a chamada. Em uma chamada de entrada para um usuário do teams será o usuário do Teams, em uma chamada de saída de um usuário do Teams, será o usuário PSTN. </li><li>**Tipo de chamada** é se a chamada foi uma chamada PSTN de saída ou de entrada e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que você pode ver incluem:<br><br>**Tipos de chamada de usuário do teams**<ul><li>**dr_in** -o usuário recebeu uma chamada PSTN de entrada</li><li>**dr_out** -o usuário fez uma chamada PSTN de saída</li><li>**dr_out_user_conf** -o usuário adicionou um participante PSTN à chamada</li><li>**user_out_transfer** -o usuário transferiu a chamada para um número PSTN</li><li>**dr_out_user_forwarding** -o usuário encaminhou a chamada para um número PSTN</li><li>**dr_out_user_transfer** -o usuário transferiu a chamada para um número PSTN</li><li>**dr_emergency_out** -o usuário fez uma chamada de emergência</li></ul><br>**Tipos de chamada de bots do teams**<ul><li>**dr_in_ucap** -uma chamada PSTN de entrada para um bot de equipe, como atendedor automático ou fila de chamadas</li><li>**dr_out_ucap** -uma chamada PSTN de saída de um bot de equipe, como atendedor automático ou fila de chamadas</li></ul><br><li>**Chamado para** é o número do usuário que recebeu a chamada.</li><li>**Hora de início (UTC)** é o momento em que o proxy SIP recebeu a resposta final (mensagem SIP "200 OK") do SBC em uma chamada de saída (Teams/bot para um usuário PSTN) ou depois que o proxy SIP envia o convite para o próximo salto no backend do teams em uma chamada de entrada (usuário PSTN para um Teams/bot). </li><li>O **tempo de convite (UTC)** é o tempo durante o qual o convite inicial foi enviado em uma chamada de entrada de um usuário do teams ou uma chamada de bot para o SBC, ou recebido em uma chamada de entrada para uma chamada de Teams ou bot pelo componente de proxy SIP do roteamento direto do SBC.</li><li>**Tempo de falha (UTC)** é a hora de falha na chamada. Somente para chamadas com falha. O código SIP final, o subcódigo final da Microsoft e a frase SIP final fornecem os motivos pelos quais a chamada falhou e pode ajudar na solução de problemas. </li><li>**Hora de término (UTC)** é a hora de término da chamada (apenas para chamadas com êxito).</li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Tipo de número** é o tipo de número de telefone do usuário, como um serviço de número de chamada gratuita. </li><li>**Bypass de mídia** indica se o tronco foi habilitado para bypass de mídia. </li> <li>O o **FQDN do SBC** é o nome de domínio totalmente qualificado (FQDN) do controlador de borda de sessão (SBC). </li><li>A **região do Azure para mídia** é o Data Center usado como caminho de mídia em uma chamada não ignorada. </li><li>A **região do Azure para sinalização** é o Data Center que foi usado para a sinalização para chamadas ignoradas e não ignoradas. </li><li>**Tipo de evento** é o tipo de evento da chamada. Você verá o êxito para fazer chamadas bem-sucedidas e tentar fazer chamadas com falha. </li><li>**Código SIP final** é o código com o qual a chamada foi encerrada.</li><li>**O subcódigo final da Microsoft** é um código que indica ações específicas ocorridas.</li><li>**Frase SIP final** é a descrição do código SIP e do subcódigo da Microsoft.</li><li>A **ID de correlação** é um identificador exclusivo para a chamada que você pode usar ao chamar o suporte da Microsoft.</li><li>A **ID de correlação compartilhada** só está visível no arquivo CSV para download e não existe no Portal. A ID de correlação compartilhada existe em pelo menos duas chamadas relacionadas. Veja a descrição detalhada abaixo.</li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **tela inteira** para exibir o relatório em modo de tela inteira. |
|**7**   |Selecione **exportar para o Excel** para baixar os dados em um arquivo separado por vírgula (CSV) para análise offline ou para usá-lo como entrada para o seu sistema de cobrança. |

#### <a name="callercallee-fields-considerations"></a>Considerações dos campos Caller/Callee

Dependendo da direção da chamada, os nomes do chamador ou do chamado podem conter números não e164.

Esses campos podem vir do (s) SBC (s) cliente. Há três formatos que o SBC pode enviar para roteamento direto: números e. 164, números non-E. 164 e cadeias de caracteres.

- Número de telefone e. 164 de um usuário que tem um número E. 164 para um usuário que também tem um número E. 164. 
- Chamada de um número que não seja E. 164. Um usuário de um PBX de terceiros interconectado com o roteamento direto faz uma chamada para um usuário do teams. Nesse caso, o número de chamadas pode ser qualquer número que não seja E. 164, por exemplo, + 1001. 
- Um remetente de spam se chama e não apresenta um número, apenas um nome, por exemplo, "serviço de receita interna". Esta cadeia de caracteres será mostrada nos relatórios.

#### <a name="about-shared-correlation-id"></a>Sobre a ID de correlação compartilhada

A ID de correlação compartilhada existe somente no arquivo do Excel exportado que você baixar e indica que duas ou mais chamadas estão relacionadas. A seguir explica os diferentes cenários e quando a ID de correlação compartilhada está presente.

1.  Usuário PSTN 1 em um ponto de extremidade PSTN chamado Teams user 1 no cliente do Teams, tipo de chamada Dr_In, ID de correlação 57f28917-42k5-4c0c-9433-79734873f2ac, nenhuma ID de correlação compartilhada.
2.  Usuário do teams 1 no cliente do teams chamado de usuário PSTN 1 em um ponto de extremidade PSTN, tipo de chamada Dr_Out 2c12b8ca-62eb-4c48-B68D-e451f518ff4, nenhuma ID de correlação compartilhada.
3.  Usuário PSTN 1 em um ponto de extremidade PSTN chamado de usuário do teams 2 no cliente do Teams, tipo de chamada Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de correlação compartilhada f45e9a25-9f94-46e7-a457-84f5940efde9.
4.  Chamada existente 3 com ID de correlação "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuário PSTN 1 em uma chamada com o usuário do teams 2. Usuário do teams 2 transferido (cego ou consultiva) uma chamada para equipes ou usuários de PSTN, tipo de chamada Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID de correlação compartilhada f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportando os relatórios
Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto. O processo de exportação pode levar de alguns segundos a vários minutos para ser concluído, dependendo da quantidade de dados.

Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores. Os arquivos exportados contêm campos adicionais que não estão disponíveis no relatório online. Elas podem ser usadas para solução de problemas e fluxos de trabalho automatizados.

 Você receberá um arquivo zip chamado "**calls. Export`[identifier]`.. zip**", com o identificador sendo uma ID exclusiva para a exportação que pode ser usada para solução de problemas.

Se você tiver planos de chamada e roteamento direto, o arquivo exportado poderá conter dados para ambos os produtos. O arquivo de relatório de uso de PSTN terá o nome de arquivo "**PSTN. calls`[UTC date]`.. CSV**"e roteamento direto"**DirectRouting. calls`[UTC date]`.. CSV**".

 Além dos arquivos PSTN e roteamento direto, o arquivo contém "**Parameters. JSON**", com o intervalo de tempo de exportação e os recursos selecionados.

Os arquivos exportados estão em formato CSV (valores separados por vírgulas) compatíveis com o padrão [RFC 4180](https://tools.ietf.org/html/rfc4180) . Os arquivos podem ser abertos no Excel ou qualquer outro editor compatível com padrões sem precisar de transformações.

A primeira linha do CSV contém nomes de coluna. Todas as datas são UTC e no formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Relatório de uso de PSTN exportado

 Você pode exportar dados até um ano a partir da data atual, a menos que as normas específicas do país proíbam a retenção dos dados por 12 meses.

| # | Nome | [Tipo de dados (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
| :-: | :-: | :-: |:------------------- |
| 0 | Usageid | `uniqueidentifier` | Identificador de chamada exclusivo |
| 1 | ID da chamada | `nvarchar(64)` | Identificador de chamadas. Não garantido como exclusivo |
| 2 | ID de conferência | `nvarchar(64)` | ID da conferência de áudio |
| 3 | Local do usuário | `nvarchar(2)` | Código do país do usuário, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | ObjectId do AAD | `uniqueidentifier` | Chamando a ID do usuário no Azure Active Directory.<br/> Esta e outras informações do usuário serão nulas/vazias para tipos de chamada do bot (ucap_in ucap_out) |
| 5 | UPNS | `nvarchar(128)` | UserPrincipalName (nome do usuário) no Azure Active Directory.<br/>Geralmente, é o mesmo que o endereço SIP do usuário e pode ser o mesmo que o endereço de email do usuário |
| 6 | Nome de exibição do usuário | `nvarchar(128)` | Exibir o nome do usuário |
| 7 | ID do chamador | `nvarchar(128)` | Número que recebeu a chamada para chamadas recebidas ou o número foi discado para chamadas feitas. Formato [E. 164](https://en.wikipedia.org/wiki/E.164) |
| 8 | Tipo de Chamada | `nvarchar(32)` | Se a chamada foi uma chamada PSTN de saída ou de entrada e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio |
| 9 | Tipo de número | `nvarchar(16)` | Tipo de número de telefone do usuário, como um serviço de número de chamada gratuita |
| 254 | Doméstica/internacional | `nvarchar(16)` | Se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário |
| 11:00 | Destino discado | `nvarchar(64)` | País ou região discada |
| 12 | Número do destino | `nvarchar(32)` | Número discado no formato [E. 164](https://en.wikipedia.org/wiki/E.164) |
| 0,13 | Hora de início | `datetimeoffset` | Hora de início da chamada |
| 14 | Hora de término | `datetimeoffset` | Hora de término da chamada |
| 15 | Segundos de duração | `int` | Tempo em que a chamada foi conectada |
| 16 | Taxa de conexão | `numeric(16, 2)` | Preço da taxa de conexão |
| 16 | Chargeback | `numeric(16, 2)` | Valor de dinheiro ou custo da chamada cobrada na sua conta |
| dezoito | Moeda | `nvarchar(3)` | Tipo de moeda usado para calcular o custo da chamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
| pol | Funcionalidade | `nvarchar(32)` | A licença usada para a chamada |

### <a name="exported-direct-routing-usage-report"></a>Relatório de uso de roteamento direto exportado

Você pode exportar dados de até cinco meses (150 dias) a partir da data atual, a menos que as normas específicas do país proíbam a retenção dos dados desse período.

| # | Nome | [Tipo de dados (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
| :-: | :-: | :-: |:------------------- |
| 0 | CorrelationId | `uniqueidentifier` | Identificador de chamada exclusivo |
| 1 | Endereço SIP | `nvarchar(128)` | O endereço do usuário ou do bot que fez ou recebeu a chamada.<br/>Observe que isso é realmente UserPrincipalName (UPN, nome do usuário) no Azure Active Directory, que geralmente é o mesmo que o endereço SIP |
| 2 | Nome para exibição | `nvarchar(128)` | O nome de um usuário ou um bot de chamada (por exemplo, fila de chamadas ou atendedor automático) conforme definido no centro de administração do Microsoft 365 |
| 3 | País do usuário | `nvarchar(2)` | Código do país do usuário, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | Hora do convite | `datetimeoffset` | Quando o convite inicial envia a saída do usuário do teams ou a chamada de bot para o SBC ou recebido em chamadas de entrada para equipes ou bot pelo componente de proxy SIP do direcionamento direto do SBC |
| 5 | Hora de início | `datetimeoffset` | Hora em que o proxy SIP recebeu a resposta final (mensagem SIP "200 OK") do SBC em saída (equipes/bot a um usuário PSTN) ou depois que o proxy SIP envia o convite para o próximo salto no backend do teams na chamada de entrada (usuário PSTN para um Teams/bot).<br/>Para chamadas com falha e não atendidas, isso pode ser igual ao tempo de convite ou falha |
| 6 | Tempo de falha | `datetimeoffset` | Existe apenas para chamadas com falha (não totalmente estabelecidas) |
| 7 | Hora de término | `datetimeoffset` | Existe apenas para chamadas bem-sucedidas (totalmente estabelecidas). Hora da chamada encerrada |
| 8 | Duração (segundos) | `int` | Duração da chamada |
| 9 | Sucesso | `nvarchar(3)` | Sim/não. Êxito ou tentativa |
| 254 | Número do chamador | `nvarchar(32)` | Número do usuário ou do bot que fez a chamada. Em entrada a uma chamada de usuário da equipe, ele será um usuário PSTN, na saída do teams User Call, e será o número de usuário da equipe |
| 12 | Número do chamador | `nvarchar(32)` | Número do usuário ou do bot que recebeu a chamada. Em entrada a uma chamada de usuário da equipe, ele será o usuário do Teams, na saída do teams User Call, e será o usuário da PSTN |
| 0,13 | Tipo de chamada | `nvarchar(32)` | Tipo de chamada e direção |
| 14 | Região do Azure para mídia | `nvarchar(8)` | O datacenter usado para o caminho de mídia em chamada sem bypass |
| 15 | Região do Azure para sinalização | `nvarchar(8)` | O datacenter usado para sinalizar para chamadas ignoradas e não ignoradas |
| 16 | Código SIP final | `int` | O código com o qual a chamada terminou, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
| 16 | Subcódigo final da Microsoft | `int` | Além dos códigos SIP, a Microsoft tem subcódigos que indicam o problema específico |
| dezoito | Frase SIP final | `nvarchar(256)` | Descrição do código SIP e do subcódigo da Microsoft |
| pol | O FQDN DO SBC | `nvarchar(64)` | Nome de domínio totalmente qualificado do controlador de borda de sessão |
| cedido | Bypass de mídia | `nvarchar(3)` | Sim/não. Indica se o tronco foi habilitado para bypass de mídia ou não |
| 21 | ID de correlação compartilhada | `uniqueidentifier` | Indica que duas ou mais chamadas estão relacionadas |


## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
