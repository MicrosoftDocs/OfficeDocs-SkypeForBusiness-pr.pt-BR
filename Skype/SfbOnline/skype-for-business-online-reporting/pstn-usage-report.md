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
description: A nova área Relatórios do Centro de Administração do Skype for Business mostra a atividade de chamadas e audioconferências em sua organização. Ele permite detalhar relatórios para lhe dar informações mais granulares sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de detalhes do uso de PSTN do Skype for Business para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir detalhes de uso de PSTN de AudioConferência, incluindo o custo da chamada, para que você possa entender seus detalhes de uso e cobrança de chamada para determinar o uso em sua organização.
ms.openlocfilehash: 09d372f6526d14a65e878271a1b277fc19d7d3e4
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201165"
---
# <a name="pstn-usage-report"></a>Relatório de uso da PSTN

A nova área Relatórios do Centro de Administração **do** Skype for Business mostra a atividade de chamadas e audioconferências em sua organização. Ele permite detalhar relatórios para lhe dar informações mais granulares sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de **detalhes do uso de PSTN do Skype for Business** para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir detalhes de uso de PSTN de AudioConferência, incluindo o custo da chamada, para que você possa entender seus detalhes de uso e cobrança de chamada para determinar o uso em sua organização.
  
Confira a visão geral [de Relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obter mais relatórios disponíveis.
  
Este relatório, juntamente com os outros relatórios do Skype for Business, fornece detalhes sobre a atividade, incluindo o uso de chamadas em toda a organização. Esses detalhes são muito úteis ao investigar, planejar e tomar outras decisões de negócios para sua organização e para configurar [Créditos de Comunicação.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Como acessar o relatório de detalhes do uso de PSTN do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

- Vá para o centro de administração > **centro** de administração do Skype for Business  >  **reporta** detalhes de uso  >    >  **de PSTN.**
    
    > [!NOTE]
    > Dependendo da assinatura do Microsoft 365 ou do Office 365 que você tem, talvez você não veja todos os produtos e relatórios mostrados aqui.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar o relatório de uso de PSTN do Skype for Business

Você pode obter uma visão do uso de PSTN do Skype for Business feito pelo seu usuário em cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
[![Relatório de uso de PSTN ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png) do Skype for Business](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Número 1](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão do uso de PSTN por usuário. Isso mostra todos os usuários que têm o Skype for Business atribuído a eles e seu uso de PSTN. Você pode adicionar/remover colunas na tabela.
*    **A ID de chamada** é a ID de chamada de uma chamada. Ele é um identificador para a chamada que é usada ao ligar para o suporte ao serviço da Microsoft.
*    **ID de usuário** é o nome que o usuário utiliza para entrar.
*    **Número de** telefone é o número de telefone do Skype for Business que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída.
*    **A localização** do usuário é o país/região onde o usuário está localizado.
*    A **ID** de chamadas é o número de telefone do chamador (ID do chamador) para chamadas de entrada, o número de origem da chamada ou o número do Skype for Business do qual a chamada se originou para chamadas de saída.
*    **O tipo de** chamada é se a chamada foi de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma audioconferência. Os tipos de chamada que você pode ver são: 

     **Tipos de Chamada do Plano de Chamada** 
     *    **user_in** (o usuário recebeu uma chamada PSTN de entrada) 
     *    **user_out** (o usuário fez uma chamada PSTN de saída) 
     *    **user_out_conf** (o usuário adicionou 2 ou mais participantes PSTN à chamada, como uma chamada em conferência 3d) 
     *    **user_out_transfer** (o usuário transferiu a chamada para um número PSTN) 
     *    **user_out_forwarding** (o usuário encaminhou a chamada para um número PSTN)

     **Tipos de chamada de audioconferência**
     *    **conf_in** (uma chamada de entrada para a ponte de Audioconferência). Para registros desse tipo de chamada, o usuário especificado na coluna **ID** do Usuário corresponde ao organizador da reunião.
     *    **conf_out** (uma chamada de saída da ponte de Audioconferência, geralmente para adicionar um número PSTN à conferência). Para registros desse tipo de chamada, o usuário especificado na coluna **ID** do Usuário corresponde ao organizador da reunião.

     **UCAP (Unified Communication Applications)** 
     *    **ucap_in** (uma chamada PSTN de entrada para o aplicativo UC, como o atendimento automático ou fila de chamada) 
     *    **ucap_out** (uma chamada PSTN de saída do aplicativo UC, como o atendimento automático ou fila de chamada)
         > [!NOTE]
         > As chamadas que foram transferidas para um usuário do aplicativo UC, como um atender automático ou fila de chamadas, não aparecerão no relatório de uso de PSTN, pois essas chamadas são chamadas de áudio ponto a ponto (P2P). Você pode acessar as chamadas P2P no Centro de administração do Skype for Business em "Ferramentas > Análise de Chamadas do Skype for Business" e pesquisar por Nome de Usuário ou endereço SIP correlacionando a chamada por data/hora e/ou CLID (ID de linha de chamada). 

     **O doméstico/internacional** informa se a chamada feita foi considerada doméstica (dentro de um país/região) ou internacional (fora de um país/região) com base na localização do usuário. 
*    **Destino discado** é o nome do destino do país/região discado, como França, Alemanha ou Estados Unidos. 
*    **O tipo** de número é o tipo de número de telefone que vem do número de telefone de um usuário, de um serviço ou de chamada gratuita.  
*    **Hora de Início (UTC)** é a hora que a chamada foi iniciada ou feita. 
*    **Duração** é o tempo em que a chamada esteve conectada.  
*    **ConfID** é a ID de conferência da audioconferência. 
*    **A** cobrança é a quantia em dinheiro ou o custo da chamada que está sendo cobrada na sua conta. 
*    **Moeda** é o tipo de moeda usada para calcular o custo da chamada. 
*    **O recurso** é a licença usada para a chamada. Os tipos de licença que você pode ver são: 
     *    **MCOPSTNPP** - Créditos de Comunicação <br/> **MCOPSTN1** - Plano de Chamada Doméstica (3.000 min.US /1200 min planos da UE) 
     *    **MCOPSTN2** – Plano de Chamada Internacional 
     *    **MCOPSTN5** - Plano de Chamada Doméstica (plano de chamada de 120 minutos) 
     *    **MCOPSTN6** - Plano de Chamada Doméstica (plano de chamada de 240 minutos) Observação: Disponibilidade limitada
     *    **MCOMEETADD -** Audioconferência
     *    **MCOMEETACPEA** - Audioconferência paga por minuto
     
> [!NOTE]
> Se você quiser executar um relatório para incluir apenas chamadas pagas por minuto que não estão incluídas em sua assinatura de chamada ou conferência, filtre o relatório com capacidade "MCOPSTNPP". Isso fornecerá uma lista de todas as chamadas pagas por minuto.  Para audioconferência paga por minuto, filtre por "MCOMEETACPEA" em vez de "MCOPSTNPP".  

> [!NOTE]
> Você também pode ver "nenhum dado" em alguns campos. "Nenhum dado" significa que o campo não é aplicável ao tipo ou recurso de chamada. 

> [!NOTE]
> Se você tiver um plano de chamada Telstra ou Softbank, não verá nenhum registro de detalhes de chamada no relatório de uso de PSTN. Entre em contato com Telstra ou Softbank para ver suas necessidades de relatórios. 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportar relatório de uso de PSTN

Clicar ou tocar no **botão Exportar** para Excel permite baixar o relatório de uso de PSTN. Você pode exportar dados de até um ano a partir da data atual, a menos que os regulamentos específicos do país leiam a retenção dos dados por 12 meses.

Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores.

O processo de exportação pode levar alguns segundos a vários minutos para ser concluído, dependendo da quantidade de dados. Quando o servidor concluir a exportação, você receberá um arquivo zip chamado "**Calls.Export.[ `identifier` ]. zip**", com o identificador sendo uma ID exclusiva para a exportação, que pode ser usada para solução de problemas.

Se você tiver Planos de Chamada e Roteamento Direto, o arquivo exportado pode conter dados para ambos os produtos. O arquivo de relatório de uso de PSTN terá o nome de arquivo "**PSTN.calls.[ `UTC date` ]. csv**". Além dos arquivos PSTN e Roteamento Direto, o arquivo contém "**parameters.js** em ", com o intervalo de tempo de exportação selecionado e recursos (se for o caso).

Arquivo exportado é um arquivo CSV (Valores Separados por Vírgula), compatível com [o padrão RFC 4180.](https://tools.ietf.org/html/rfc4180) O arquivo pode ser aberto no Excel ou em qualquer outro editor compatível com padrões sem exigir transformações.

A primeira linha do CSV contém nomes de coluna.

### <a name="fields-in-the-export"></a>Campos na exportação

O arquivo exportado contém campos adicionais que não estão disponíveis no relatório online. Elas podem ser usadas para solução de problemas e fluxos de trabalho automatizados.

> [!div class="has-no-wrap"]  
> | #  | Nome | [Tipo de dados (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificador de chamada exclusivo |
> | 1 | ID da chamada | `nvarchar(64)` | Identificador de chamada. Não é garantido que seja exclusivo |
> | 2 | ID de conferência | `nvarchar(64)` | ID da audioconferência |
> | 3 | Localização do Usuário | `nvarchar(2)` | Código do país do usuário, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Chamando a ID do usuário no Azure Active Directory.<br/> Esta e outras informações do usuário serão nulas/vazias para tipos de chamada de bot (ucap_in, ucap_out) |
> | 5 | Upn | `nvarchar(128)` | UserPrincipalName (nome de login) no Azure Active Directory.<br/>Geralmente, isso é o mesmo que o Endereço SIP do usuário e pode ser igual ao endereço de email do usuário |
> | 6 | Nome de Exibição do Usuário | `nvarchar(128)` | Nome de exibição do usuário |
> | 7 | ID do chamador | `nvarchar(128)` | Número que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo de Chamada | `nvarchar(32)` | Se a chamada era uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma audioconferência |
> | 9 | Tipo de Número | `nvarchar(16)` | Tipo de número de telefone do usuário, como um serviço de número de chamada gratuita |
> | 10 | Domésticas/Internacionais | `nvarchar(16)` | Se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário |
> | 11 | Destino Discado | `nvarchar(64)` | País ou região discada |
> | 12 | Número de Destino | `nvarchar(32)` | Número discado no [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Hora de Início | `datetimeoffset` | Hora de início da chamada (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Hora de término | `datetimeoffset` | Hora de término da chamada (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Segundos de Duração | `int` | Por quanto tempo a chamada foi conectada |
> | 16 | Taxa de conexão | `numeric(16, 2)` | Preço da taxa de conexão |
> | 17 | Carga | `numeric(16, 2)` | Quantia em dinheiro ou custo da chamada que é cobrada em sua conta |
> | 18 | Moeda | `nvarchar(3)` | Tipo de moeda usado para calcular o custo da chamada ([ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Recursos | `nvarchar(32)` | A licença usada para a chamada |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividades do Skype for Business](activity-report.md) Você pode ver o quanto seus usuários estão usando ponto a ponto, organizaram e participaram de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados no Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens de mensagens e reuniões.
    
- Relatório de atividade do organizador de [conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam mensagens de iM, áudio/vídeo, compartilhamento de aplicativos, Web, /discagem – terceiros e /discagem – Microsoft.
    
- [Relatório de atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver em quantas conferências de áudio, áudio/ vídeo, mensagens de áudio, compartilhamento de aplicativos, Web e discagem estão participando.
    
- [Relatório de atividade ponto a ponto](peer-to-peer-activity-report.md) do Skype for Business Você pode ver o quanto seus usuários estão usando mensagens de texto, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório bloqueado de usuários do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Pools de minutos PSTN](pstn-minute-pools-report.md) do Skype for Business relatam o número de minutos consumidos durante o mês atual em sua organização.

- [Relatório de detalhes da sessão do Skype for Business](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada de um usuário individual.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
