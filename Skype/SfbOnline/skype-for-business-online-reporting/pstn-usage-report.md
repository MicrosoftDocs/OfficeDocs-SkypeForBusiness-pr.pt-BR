---
title: Relatório de uso da PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: A nova área de relatórios do centro de administração do Skype for Business mostra a atividade de chamadas e conferência de áudio em sua organização. Ele permite que você faça uma busca detalhada nos relatórios para dar a você uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de detalhes do uso de PSTN do Skype for Business para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir os detalhes de uso de PSTN da videoconferência, incluindo o custo da chamada para que você possa entender seu uso e fazer chamadas para os detalhes de cobrança para determinar o uso dentro da sua organização.
ms.openlocfilehash: 7050334a390188f47f5d201b3fa541d337601400
ms.sourcegitcommit: a4fd238de09366d6ed33d72c908faff812da11a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637138"
---
# <a name="pstn-usage-report"></a>Relatório de uso da PSTN

A nova área de **relatórios** do centro de administração do Skype for Business mostra a atividade de chamadas e conferência de áudio em sua organização. Ele permite que você faça uma busca detalhada nos relatórios para dar a você uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de **detalhes do uso de PSTN do Skype for Business** para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir os detalhes de uso de PSTN da videoconferência, incluindo o custo da chamada para que você possa entender seu uso e fazer chamadas para os detalhes de cobrança para determinar o uso dentro da sua organização.
  
Confira a [visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver mais relatórios disponíveis.
  
Esse relatório, juntamente com os outros relatórios do Skype for Business, fornece detalhes sobre atividades, incluindo o uso de chamadas em toda a sua organização. Esses detalhes são muito úteis quando você está investigando, planejando e fazendo outras decisões empresariais para a sua organização e para configurar [créditos de comunicações](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logon como administrador no centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Como acessar o relatório de detalhes do uso de PSTN do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

- Vá para o centro de administração > **centros** > de administração o**Centro** > de administração do Skype for Business**relata** > **detalhes de uso de PSTN**.
    
    > [!NOTE]
    > [!IMPORTANTE] Dependendo da sua assinatura do Office 365, talvez você não veja todos os produtos e relatórios mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar o relatório de uso de PSTN do Skype for Business

Você pode obter uma visão do uso de PSTN do Skype for Business feito pelo seu usuário em cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
![Relatório de uso de PSTN do Skype for Business](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Número 1](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão do uso de PSTN por usuário. Isso mostra todos os usuários que têm o Skype for Business atribuído a eles e seu uso de PSTN. Você pode adicionar/remover colunas na tabela.
*    A **ID da chamada** é a ID da chamada para uma chamada. Trata-se de um identificador para a chamada usada ao chamar o suporte ao serviço Microsoft.
*    **ID de usuário** é o nome que o usuário utiliza para entrar.
*    **Número de telefone** é o número de telefone do Skype for Business que recebeu a chamada para as chamadas recebidas ou o número discado para chamadas de saída.
*    **Local do usuário** é o país/região onde o usuário está localizado.
*    O recurso de **identificação** de chamadas é o número de telefone da pessoa (identificação de chamadas) para chamadas recebidas, o número do qual a chamada originou ou o número Skype for Business do qual a chamada originou as chamadas feitas.
*    **Tipo de chamada** é se a chamada foi uma chamada PSTN ou uma chamada de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que você pode ver são: 

     **Tipos de chamadas de plano de chamada** 
     *    **user_in** (o usuário recebeu uma chamada PSTN de entrada) 
     *    **user_out** (o usuário fez uma chamada PSTN de saída) 
     *    **user_out_conf** (o usuário adicionou dois ou mais participantes PSTN à chamada, como uma chamada em conferência de 3 vias) 
     *    **user_out_transfer** (o usuário transferiu a chamada para um número PSTN) 
     *    **user_out_forwarding** (o usuário encaminhou a chamada para um número PSTN)

     **Tipos de chamada de audioconferência**
     *    **conf_in** (uma chamada de entrada para a ponte de audioconferência). Para registros desse tipo de chamada, o usuário especificado na coluna **ID do usuário** corresponde ao organizador da reunião.
     *    **conf_out** (uma chamada de saída da ponte de audioconferência, geralmente para adicionar um número PSTN à conferência). Para registros desse tipo de chamada, o usuário especificado na coluna **ID do usuário** corresponde ao organizador da reunião.

     **Aplicativos de comunicação unificada (UCAP)** 
     *    **ucap_in** (uma chamada PSTN de entrada para o aplicativo de comunicação unificada, como atendedor automático ou fila de chamadas) 
     *    **ucap_out** (uma chamada PSTN de saída do aplicativo UC, como atendedor automático ou fila de chamadas)
     *    **Observação:** As chamadas que foram transferidas para um usuário do aplicativo UC, como um atendedor automático ou fila de chamadas, não aparecerão no relatório de uso de PSTN, pois esses trechos de chamadas são chamadas de áudio ponto a ponto (P2P). Você pode acessar as chamadas ponto a ponto no centro de administração do Skype for Business em "ferramentas > Skype for Business Call Analytics" e Pesquisar por nome de usuário ou endereço SIP que correlaciona a chamada por data/hora e/ou CLID (ID da linha de chamada) de origem. 
*     
     **Doméstica/internacional** informa se a chamada que foi feita foi considerada doméstica (dentro de um país/região) ou internacional (fora de um país/região) com base na localização do usuário. 
*    **Destino discado** é o nome do destino de país/região que é discado, como França, Alemanha ou Estados Unidos (EUA). 
*    **Tipo de número** é o tipo de número de telefone do número de telefone de um usuário, um serviço ou número de chamada gratuita.  
*    **Hora de Início (UTC)** é a hora que a chamada foi iniciada ou feita. 
*    **Duração** é o tempo em que a chamada esteve conectada.  
*    **Confid** é a ID de conferência da conferência de áudio. 
*    **Encargo** é a quantia de dinheiro ou o custo da chamada que está sendo cobrada na sua conta. 
*    **Moeda** é o tipo de moeda que é usado para calcular o custo da chamada. 
*    **Recurso** é a licença usada para a chamada. Os tipos de licença que você pode ver são: 
     *    **MCOPSTNPP** -créditos de comunicações <br/> **MCOPSTN1** -plano de chamadas domésticas (3000 min-US/1200 min) planos da UE) 
     *    **MCOPSTN2** -plano de chamadas internacionais 
     *    **MCOPSTN5** -plano de chamadas domésticas (120 min – plano de chamadas) 
     *    **MCOPSTN6** -plano de chamadas domésticas (240 min-plano de chamadas) Nota: disponibilidade limitada
     *    **MCOMEETADD** -audioconferência
     *    **MCOMEETACPEA** -conferência de áudio de pagamento por minuto
     
> [!NOTE]
> Se você quiser executar um relatório para incluir somente chamadas pagas por minuto que não estão incluídas na sua assinatura de chamadas ou conferência, filtre o relatório com a funcionalidade "MCOPSTNPP". Isso fornecerá uma discriminação de todas as chamadas pagas por minuto.  Para conferências de áudio de pagamento por minuto, filtre por "MCOMEETACPEA" em vez de "MCOPSTNPP".  

> [!NOTE]
> Você também pode ver "nenhum dado" em alguns campos. "Nenhum dado" significa que o campo não é aplicável ao tipo ou funcionalidade de chamada. 

> [!NOTE]
> Se você tiver um plano de chamadas Telstra, não verá os registros de detalhes da chamada no relatório de uso de PSTN. Entre em contato com a Telstra para atender às suas necessidades de relatório. 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportando o relatório de uso de PSTN

Clicar ou tocar no botão **exportar para o Excel** permite baixar o relatório de uso de PSTN. Você pode exportar dados até um ano a partir da data atual, a menos que as normas específicas do país proíbam a retenção dos dados por 12 meses.

Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores.

O processo de exportação pode levar de alguns segundos a vários minutos para ser concluído, dependendo da quantidade de dados. Quando o servidor concluir a exportação, você receberá um arquivo zip chamado "**calls. Export. [ ] `identifier`. zip**", com o identificador sendo uma ID exclusiva para a exportação, que pode ser usada para solução de problemas.

Se você tiver planos de chamada e roteamento direto, o arquivo exportado poderá conter dados para ambos os produtos. O arquivo de relatório de uso de PSTN terá o nome de arquivo "**PSTN. calls. [ ] `UTC date`. csv**". Além dos arquivos PSTN e roteamento direto, o arquivo contém "**Parameters. JSON**", com o intervalo de exportação selecionado e os recursos (se houver).

Arquivo exportado é um arquivo CSV (valores separados por vírgula) compatível com o padrão [RFC 4180](https://tools.ietf.org/html/rfc4180) . O arquivo pode ser aberto no Excel ou em qualquer outro editor compatível com padrões sem precisar de transformações.

A primeira linha do CSV contém nomes de coluna.

### <a name="fields-in-the-export"></a>Campos na exportação

Arquivo exportado contém campos adicionais que não estão disponíveis no relatório online. Elas podem ser usadas para solução de problemas e fluxos de trabalho automatizados.

| #  | Nome | [Tipo de dados (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
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
| 0,13 | Hora de início | `datetimeoffset` | Hora de início da chamada (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
| 14 | Hora de término | `datetimeoffset` | Hora de término da chamada (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
| 15 | Segundos de duração | `int` | Tempo em que a chamada foi conectada |
| 16 | Taxa de conexão | `numeric(16, 2)` | Preço da taxa de conexão |
| 16 | Chargeback | `numeric(16, 2)` | Valor de dinheiro ou custo da chamada cobrada na sua conta |
| dezoito | Moeda | `nvarchar(3)` | Tipo de moeda usado para calcular o custo da chamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
| pol | Potencial | `nvarchar(32)` | A licença usada para a chamada |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividade do Skype for Business](activity-report.md) Você pode ver o quanto os usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados em Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens instantâneas e reuniões.
    
- [Relatório de atividade do organizador de conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver quanto seus usuários estão organizando conferências que usam mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, Web,/dial out-terceiro e/dial-Microsoft.
    
- [Relatório atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver quantas mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, conferências de áudio da Web e de discagem estão sendo participadas.
    
- [Relatório de atividade ponto a ponto do Skype for Business](peer-to-peer-activity-report.md) Você pode ver o quanto os usuários estão usando mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório de usuários bloqueados do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Relatório de grupos de minutos PSTN do Skype for Business](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual dentro de sua organização.

- [Relatório de detalhes da sessão do Skype for Business](session-details-report.md) Você pode ver detalhes sobre as experiências de chamadas de um usuário individual.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
