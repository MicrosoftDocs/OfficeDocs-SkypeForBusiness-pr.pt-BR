---
title: Relatório de uso de PSTN do Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como usar o relatório de uso de PSTN do Teams no centro de administração do Microsoft Teams para obter uma visão geral do uso de chamada e audioconferência em sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc2b1ae0b6df29e29a55152dbafb9b76ae31e973
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809291"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Relatório de uso de PSTN do Microsoft Teams

O relatório de uso de PSTN do Teams no centro de administração do Microsoft Teams oferece uma visão geral da atividade de chamada e audioconferência em sua organização. Você poderá exibir a atividade de chamadas detalhada para Planos de Chamadas se usar a Microsoft como operadora de telefonia e para Roteamento Direto se usar sua própria operadora de telefonia.

A **guia Planos de** Chamadas mostra informações, incluindo o número de minutos gastos pelos usuários em chamadas PSTN de entrada e saída e o custo dessas chamadas. A **guia Roteamento Direto** mostra informações, incluindo o endereço SIP e os horários de início e término da chamada. Use as informações neste relatório para obter informações sobre o uso de PSTN em sua organização e ajudá-lo a investigar, planejar e tomar decisões de negócios.

> [!NOTE]
> Se você tiver um plano de chamada Telstra ou Softbank, não verá nenhum registro de detalhes de chamada no relatório de uso da PSTN. Entre em contato com Telstra ou Softbank para suas necessidades de relatório. 

## <a name="view-the-pstn-usage-report"></a>Exibir o relatório de uso de PSTN

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **Relatório de uso de PSTN**.
2. Em **Intervalo de datas,** selecione um intervalo predefinido de 7 ou 28 dias ou de definir um intervalo personalizado e selecione **Executar relatório**.

## <a name="interpret-the-report"></a>Interpretar relatório

### <a name="calling-plans"></a>Planos de Chamadas

[![Captura de tela do relatório de uso de PSTN de](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot of the PSTN usage report in the Microsoft Teams admin center with numbered callouts") Planos de Chamada no centro de administração](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser consultado sobre tendências dos últimos 7, 28 dias ou um intervalo de datas personalizado definido por você |
|**2**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período selecionado. <br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela fornece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora em que a chamada foi iniciada.</li><li>**Nome para** exibição é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Centro de administração do Microsoft Teams.</li><li>**Nome** de usuário é o nome de login do usuário.</li><li>**Número de** telefone é o número que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída.</li><li>**O tipo de** chamada é se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que você pode ver incluem:<br><br>**Tipos de chamada de usuário do Teams**<ul><li>**user_in** - o usuário recebeu uma chamada PSTN de entrada.</li><li>**user_out** - o usuário fez uma chamada PSTN de saída</li><li>**user_out_conf** - o usuário adicionou dois ou mais participantes PSTN à chamada, como uma chamada de conferência de três vias</li><li>**user_out_transfer** - o usuário transferiu a chamada para um número PSTN</li><li>**user_out_forwarding** - o usuário encaminhou a chamada para um número PSTN</li><li>**conf_in** - uma chamada de entrada para a ponte de Audioconferência</li><li>**conf_out** - uma chamada de saída da ponte de Audioconferência geralmente para adicionar um número PSTN à conferência</li></ul><br>**Tipos de chamada de bots do Teams**<ul><li>**ucap_in** - uma chamada PSTN de entrada para o bot do Teams, como o atendimento automático ou fila de chamada</li><li>**ucap_out** - uma chamada PSTN de saída de um bot do Teams, como o atendimento automático ou fila de chamada</li></ul><br><li>**Chamado é** o número discado.</li><li>**Para o país ou região** é o país ou região discado.</li><li>**Chamado de** é o número que fez a chamada.</li><li>**Do país ou região é** o país ou região de onde a chamada foi feita.</li><li>**A** cobrança é a quantidade de dinheiro ou custo da chamada que é cobrada em sua conta. </li><li>**Moeda** é o tipo de moeda usado para calcular o custo da chamada. </li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**A doméstica/internacional** informa se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário.</li><li>**A ID da** chamada é a ID de chamada de uma chamada. É um identificador da chamada que você pode usar ao chamar o Suporte da Microsoft.</li><li>**Tipo de** número é o tipo de número de telefone do usuário, como um serviço de número gratuito. </li><li>**País ou região é** o local de uso. </li> <li>**A ID de** conferência é a ID de conferência da audioconferência. </li><li>**A funcionalidade** é a licença usada para a chamada. Os tipos de licença que você pode ver incluem:<ul><li>**MCOPSTNPP** - Créditos de Comunicação</li><li>**MCOEV ou MCOEV_VIRTUALUSER** - Aplicativos de voz, como o Atendimento Automático ou Filas de Chamadas</li><li>**FREECALL** - No caso de um problema técnico que nos impeça de fazer o preço de uma chamada, a chamada é fornecida gratuitamente e aparecerá com essa funcionalidade</li><li>**MCOPSTN1** - Plano de Chamada Doméstica (3000 min US /1200 min planos da UE)</li><li>**MCOPSTN2** - Plano de Chamada Internacional</li><li>**MCOPSTN5** - Plano de Chamada Doméstica (plano de chamada de 120 minutos)</li><li>**MCOPSTN6** - Plano de Chamada Doméstica (plano de chamada de 240 minutos)</li><li>**MCOMEETADD** - Audioconferência</li><li>**MCOMEETACPEA** - Audioconferência paga por minuto</li></ul></li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **Filtrar** para filtrar o relatório por nome de usuário ou tipo de chamada |
|**7**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira. |
|**8**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para o Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando ele estiver pronto.|

### <a name="direct-routing"></a>Roteamento Direto

[![Captura de tela do relatório de uso de PSTN de](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot of the Direct Routing PSTN usage report in the Microsoft Teams admin center with numbered callouts") Roteamento Direto no centro de administração](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser consultado sobre tendências dos últimos 7 ou 28 dias. |
|**2**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período selecionado.<br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela fornece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora em que a chamada foi iniciada.</li><li>**Nome para** exibição é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configurações do usuário no centro de administração do Microsoft Teams. O nome também pode ser o nome de um bot, por exemplo, a Fila de Chamada ou a Nuvem Atendedor Automático. </li><li>**Endereço SIP** é o endereço SIP do usuário ou um bot que recebeu ou fez a chamada.</li><li>**O número do** chamador é o número do usuário ou do bot que fez a chamada. </li><li>**O número do destinatário** da chamada é o número do usuário ou do bot que recebeu a chamada. Em uma chamada de entrada para um usuário do Teams, ele será o usuário do Teams, em uma chamada de saída de um usuário do Teams, ele será o Usuário PSTN. </li><li>**O tipo de** chamada é se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamada que você pode ver incluem:<br><br>**Tipos de chamada de usuário do Teams**<ul><li>**dr_in** - o usuário recebeu uma chamada PSTN de entrada</li><li>**dr_out** - o usuário fez uma chamada PSTN de saída</li><li>**dr_out_user_conf** - o usuário adicionou um participante PSTN à chamada</li><li>**user_out_transfer** - o usuário transferiu a chamada para um número PSTN</li><li>**dr_out_user_forwarding** - o usuário encaminhou a chamada para um número PSTN</li><li>**dr_out_user_transfer** - o usuário transferiu a chamada para um número PSTN</li><li>**dr_emergency_out** - o usuário fez uma chamada de emergência</li></ul><br>**Tipos de chamada de bots do Teams**<ul><li>**dr_in_ucap** - uma chamada PSTN de entrada para um bot do Teams, como o atendimento automático ou fila de chamada</li><li>**dr_out_ucap** - uma chamada PSTN de saída de um bot do Teams, como o atendimento automático ou fila de chamada</li></ul><br><li>**Chamado é** o número do usuário que recebeu a chamada.</li><li>A hora de início **(UTC)** é a hora em que o proxy SIP recebeu a resposta final (Mensagem SIP "200 OK") do SBC em uma chamada de saída (Teams/Bot para um usuário PSTN) ou depois que o Proxy SIP envia o Convite para o próximo salto dentro do back-end do Teams em uma chamada de entrada (Usuário PSTN para um Teams/Bot). </li><li>Hora do convite **(UTC)** é a hora em que o Convite inicial foi enviado em uma chamada de saída de um usuário ou bot do Teams para o SBC, ou recebido em uma chamada de entrada para um Teams ou chamada de bot pelo componente proxy SIP do Roteamento Direto do SBC.</li><li>**Tempo de falha (UTC)** é a hora em que a chamada falhou. Somente para chamadas com falha. O Código SIP final, o Subcódigo Final da Microsoft e a Frase SIP Final fornecem os motivos pelos quais a chamada falhou e podem ajudar na solução de problemas. </li><li>**Hora de término (UTC)** é a hora em que a chamada terminou (somente para chamadas bem-sucedidas).</li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Tipo de** número é o tipo de número de telefone do usuário, como um serviço de número gratuito. </li><li>**O bypass de** mídia indica se o tronco foi habilitado para bypass de mídia. </li> <li>**SBC FQDN** é o FQDN (nome de domínio totalmente qualificado) do Controlador de Borda de Sessão (SBC). </li><li>**A região do Azure para Mídia** é o data center que foi usado como caminho de mídia em uma chamada sem bypass. </li><li>**A região do Azure para Sinalização** é o data center que foi usado para sinalização para chamadas de bypass e não bypass. </li><li>**Tipo de** evento é o tipo de evento da chamada. Você verá Êxito para chamadas bem-sucedidas e Tentativa de chamadas com falha. </li><li>**Código SIP final** é o código com o qual a chamada terminou.</li><li>**O subcódigo final** da Microsoft é um código que indica ações específicas que ocorreram.</li><li>**A frase SIP final** é a descrição do código SIP e do subcódigo da Microsoft.</li><li>**A ID de** correlação é um identificador exclusivo para a chamada que você pode usar ao chamar o Suporte da Microsoft.</li><li>**A ID de Correlação Compartilhada** só é visível no arquivo CSV baixável e não existe no portal. A ID de correlação compartilhada existe em pelo menos duas chamadas relacionadas. Confira a descrição detalhada abaixo.</li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira. |
|**7**   |Selecione **Exportar para o Excel** para baixar os dados em um arquivo separado por vírgula (CSV) para análise offline ou para usá-los como entrada para seu sistema de cobrança. |

#### <a name="callercallee-fields-considerations"></a>Considerações sobre campos de chamador/chamador

Dependendo da direção da chamada, os nomes do chamador ou do chamador podem conter números que não são E164.

Esses campos podem vir do(s) SBC(s) cliente(s). Há três formatos que o SBC pode enviar para o Roteamento Direto: números E.164, números não E.164 e cadeias de caracteres.

- Número de telefone E.164 de um usuário que tem um número E.164 para um usuário que também tem um número E.164. 
- Chamada de um número que não seja E.164. Um usuário de um PBX de terceiros interconectado com o Roteamento Direto faz uma chamada para um usuário do Teams. Nesse caso, o número do chamador pode ser qualquer número que não seja E.164, por exemplo +1001. 
- Um remetente de spam chama e não apresenta um número, apenas um nome, por exemplo "Serviço de Receita Interna". Essa cadeia de caracteres será mostrada nos relatórios.

#### <a name="about-shared-correlation-id"></a>Sobre a ID de Correlação Compartilhada

A ID de Correlação Compartilhada existe apenas no arquivo do Excel exportado que você baixa e indica que duas ou mais chamadas estão relacionadas. A seguir, explica os diferentes cenários e quando a ID de Correlação Compartilhada está presente.

1.    Usuário PSTN 1 em um ponto de extremidade PSTN chamado Usuário 1 do Teams no cliente do Teams, tipo de chamada Dr_In, ID de correlação 57f28917-42k5-4c0c-9433-79734873f2ac, sem ID de correlação compartilhada.
2.    Teams User 1 on Teams client called PSTN User 1 on a PSTN endpoint, call type Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, no shared correlation ID.
3.    Usuário PSTN 1 em um ponto de extremidade PSTN chamado usuário 2 do Teams no cliente do Teams, tipo de chamada Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID de correlação compartilhada f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Chamada 3 existente com ID de correlação "f45e9a25-9f94-46e7-a457-84f5940efde9". Usuário PSTN 1 em uma chamada com o Usuário do Teams 2. Usuário do Teams 2 transferido (cego ou consultivo) uma chamada para o Teams ou Usuário PSTN, tipo de chamada Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID de correlação compartilhada f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportando os relatórios
Clique **em Exportar para o Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando ele estiver pronto. O processo de exportação pode levar de alguns segundos a vários minutos para ser concluído, dependendo da quantidade dos dados.

Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores. Os arquivos exportados contêm campos adicionais que não estão disponíveis no relatório online. Eles podem ser usados para solucionar problemas e fluxos de trabalho automatizados.

 Você receberá um arquivo zip chamado "**Calls.Export. `[identifier]` . zip**", com o identificador sendo uma ID exclusiva para a exportação que pode ser usada para solução de problemas.

Se você tiver Planos de Chamadas e Roteamento Direto, o arquivo exportado poderá conter dados para ambos os produtos. O arquivo de relatório de uso de PSTN terá o nome de arquivo "**PSTN.calls. `[UTC date]` . csv**" e Roteamento Direto "**DirectRouting.calls. `[UTC date]` . csv**".

 Além dos arquivos PSTN e Roteamento Direto, o arquivo contém o arquivo "**parameters.js** em ", com o intervalo de tempo de exportação selecionado e os recursos.

Os arquivos exportados estão no formato Valores Separados por Vírgula (CSV), em conformidade com o [padrão RFC 4180.](https://tools.ietf.org/html/rfc4180) Os arquivos podem ser abertos no Excel ou em qualquer outro editor compatível com padrões sem a necessidade de transformações.

A primeira linha do CSV contém nomes de coluna. Todas as datas são UTC e no [formato ISO 8601.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Relatório de uso de PSTN exportado

 Você pode exportar dados de até um ano a partir da data atual, a menos que as regulamentações específicas do país proibirem a retenção dos dados por 12 meses.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo de dados (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador exclusivo de chamada |
> | 1 | ID da chamada | `nvarchar(64)` | Identificador de chamada. Não é garantido que seja exclusivo |
> | 2 | ID de conferência | `nvarchar(64)` | ID da audioconferência |
> | 3 | Localização do usuário | `nvarchar(2)` | Código do país do usuário, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Chamando a ID do usuário no Azure Active Directory.<br/> Essa e outras informações do usuário serão nulas/vazias para tipos de chamada de bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nome de login) no Azure Active Directory.<br/>Isso geralmente é o mesmo endereço SIP do usuário e pode ser igual ao endereço de email do usuário |
> | 6 | Nome de Exibição do Usuário | `nvarchar(128)` | Nome de exibição do usuário |
> | 7 | ID do chamador | `nvarchar(128)` | Número que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de Chamada | `nvarchar(32)` | Se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio |
> | 9 | Tipo de número | `nvarchar(16)` | Tipo de número de telefone do usuário, como um serviço de número gratuito |
> | 10 | Doméstica/internacional | `nvarchar(16)` | Se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário |
> | 11 | Destination Dialed | `nvarchar(64)` | País ou região discada |
> | 12 | Número de Destino | `nvarchar(32)` | Número discado no [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de Início | `datetimeoffset` | Hora de início da chamada |
> | 14 | Hora de Término | `datetimeoffset` | Hora de término da chamada |
> | 15 | Segundos de Duração | `int` | Por quanto tempo a chamada foi conectada |
> | 16 | Taxa de Conexão | `numeric(16, 2)` | Preço da taxa de conexão |
> | 17 | Cobrança | `numeric(16, 2)` | Quantidade de dinheiro ou custo da chamada que é cobrada em sua conta |
> | 18 | Moeda | `nvarchar(3)` | Tipo de moeda usado para calcular o custo da chamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Recursos | `nvarchar(32)` | A licença usada para a chamada |

### <a name="exported-direct-routing-usage-report"></a>Relatório de uso do Roteamento Direto Exportado

Você pode exportar dados de até cinco meses (150 dias) a partir da data atual, a menos que as regulamentações específicas do país proibirem a retenção dos dados para esse período.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo de dados (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificador exclusivo de chamada |
> | 1 | Endereço SIP | `nvarchar(128)` | O endereço do usuário ou bot que fez ou recebeu a chamada.<br/>Observe que isso é realmente UserPrincipalName (UPN, nome de logon) no Azure Active Directory, que geralmente é o mesmo endereço SIP |
> | 2 | Nome para Exibição | `nvarchar(128)` | O nome de um usuário ou um bot de chamada (por exemplo, Fila de Chamada ou Atendedor Automático) conforme definido no Centro de administração do Microsoft 365 |
> | 3 | País do usuário | `nvarchar(2)` | Código do país do usuário, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Hora do convite | `datetimeoffset` | Quando o convite inicial enviar na saída do usuário ou da chamada de bot do Teams para o SBC ou recebido na entrada para o Teams ou chamada de bot pelo componente proxy SIP do Roteamento Direto do SBC |
> | 5 | Hora de início | `datetimeoffset` | Hora em que o proxy SIP recebeu a resposta final (Mensagem SIP "200 OK") do SBC na saída (Teams/Bot para um usuário PSTN) ou depois que o Proxy SIP envia o Convite para o próximo salto no back-end do Teams na chamada de entrada (Usuário PSTN para um Teams/Bot).<br/>Para chamadas com falha e não respondidas, isso pode ser igual ao tempo de convite ou falha |
> | 6 | Tempo de falha | `datetimeoffset` | Existe apenas para chamadas com falha (não totalmente estabelecidas) |
> | 7 | Hora de término | `datetimeoffset` | Existe apenas para chamadas bem-sucedidas (totalmente estabelecidas). Hora em que a chamada terminou |
> | 8 | Duração (segundos) | `int` | Duração da chamada |
> | 9 | Sucesso | `nvarchar(3)` | Sim/Não. Sucesso ou tentativa |
> | 10 | Número do chamador | `nvarchar(32)` | Número do usuário ou bot que fez a chamada. Ao entrar em uma chamada de usuário de equipe, ele será um Usuário PSTN, ao sair da chamada de usuário do Teams, será o número de usuário do Teams |
> | 12 | Número do destinatário da chamada | `nvarchar(32)` | Número do usuário ou bot que recebeu a chamada. Ao entrar em uma chamada de usuário de equipe, ele será o usuário do Teams, ao sair da chamada de usuário do Teams, ele será o Usuário PSTN |
> | 13 | Tipo de chamada | `nvarchar(32)` | Tipo e direção da chamada |
> | 14 | Região do Azure para Mídia | `nvarchar(8)` | O datacenter usado para o caminho de mídia em chamada não ignorada |
> | 15 | Região do Azure para Sinalização | `nvarchar(8)` | O datacenter usado para sinalização para chamadas de bypass e não ignorar |
> | 16 | Código SIP final | `int` | O código com o qual a chamada terminou, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Subcódigo final da Microsoft | `int` | Além dos códigos SIP, a Microsoft tem subcódigos próprios que indicam o problema específico |
> | 18 | Frase SIP final | `nvarchar(256)` | Descrição do código SIP e do subcódigo da Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nome de domínio totalmente qualificado do controlador de borda da sessão |
> | 20 | Bypass de mídia | `nvarchar(3)` | Sim/Não. Indica se o tronco foi habilitado para bypass de mídia ou não |
> | 21 | ID de correlação compartilhada | `uniqueidentifier` | Indica que duas ou mais chamadas estão relacionadas |


## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
