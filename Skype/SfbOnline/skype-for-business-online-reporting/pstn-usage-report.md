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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: A nova Skype for Business de Relatórios do Centro de Administração mostra a atividade de chamada e audioconferência em sua organização. Ele permite que você faça uma análise de relatórios para dar uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de detalhes do uso de PSTN do Skype for Business para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir detalhes de uso de PSTN de Audioconferência, incluindo o custo da chamada para que você possa entender seus detalhes de cobrança de chamada e uso para determinar o uso em sua organização.
ms.openlocfilehash: ad2ac65300e0cb1f1d1b3e879199f04506ceeb6c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731620"
---
# <a name="pstn-usage-report"></a>Relatório de uso da PSTN

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

A nova Skype for Business de  Relatórios do Centro de Administração mostra a atividade de chamada e audioconferência em sua organização. Ele permite que você faça uma análise de relatórios para dar uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de **detalhes do uso de PSTN do Skype for Business** para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir detalhes de uso de PSTN de Audioconferência, incluindo o custo da chamada para que você possa entender seus detalhes de cobrança de chamada e uso para determinar o uso em sua organização.
  
Confira a visão geral [relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obter mais relatórios disponíveis.
  
Este relatório, juntamente com os outros relatórios Skype for Business, fornece detalhes sobre a atividade, incluindo o uso de chamada em toda a sua organização. Esses detalhes são muito úteis ao investigar, planejar e tomar outras decisões de negócios para sua organização e para configurar [créditos de comunicação.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios Skype for Business quando fizer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Como acessar o relatório de detalhes do uso de PSTN do Skype for Business

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**

- Vá para o centro de administração > **centros de administração** Skype for Business de administração Relatórios detalhes de uso  >    >    >  **PSTN**.
    
    > [!NOTE]
    > Dependendo da assinatura Microsoft 365 ou Office 365 você tem, talvez você não veja todos os produtos e relatórios mostrados aqui.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar o relatório de uso de PSTN do Skype for Business

Você pode obter uma visão do uso de PSTN do Skype for Business feito pelo seu usuário em cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
[![Skype for Business relatório de uso PSTN. ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Número 1.](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão do uso de PSTN por usuário. Isso mostra todos os usuários que Skype for Business atribuídos a eles e seu uso PSTN. Você pode adicionar/remover colunas na tabela.
*    **A ID da** chamada é a ID de chamada de uma chamada. É um identificador para a chamada que é usada ao chamar o suporte de serviço da Microsoft.
*    **ID de usuário** é o nome que o usuário utiliza para entrar.
*    **Telefone número** é o Skype for Business telefone que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída.
*    **A localização** do usuário é o país/região onde o usuário está localizado.
*    A **ID** do chamador é o número de telefone do chamador (ID do chamador) para chamadas de entrada, o número do qual a chamada se originou ou o número Skype for Business do qual a chamada se originou para chamadas de saída.
*    **O tipo de** chamada é se a chamada foi uma chamada de saída ou de entrada PSTN e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamada que você pode ver são: 

     **Tipos de chamada do Plano de Chamada** 
     *    **user_in** (o usuário recebeu uma chamada PSTN de entrada) 
     *    **user_out** (o usuário fez uma chamada PSTN de saída) 
     *    **user_out_conf** (o usuário adicionou 2 ou mais participantes PSTN à chamada, como uma chamada de conferência 3 vias) 
     *    **user_out_transfer** (o usuário transferiu a chamada para um número PSTN) 
     *    **user_out_forwarding** (o usuário encaminhou a chamada para um número PSTN)

     **Tipos de chamada de audioconferência**
     *    **conf_in** (uma chamada de entrada para a ponte de Audioconferência). Para registros desse tipo de chamada, o usuário especificado na coluna **ID do** Usuário corresponde ao organizador da reunião.
     *    **conf_out** (uma chamada de saída da ponte de Audioconferência, geralmente para adicionar um número PSTN à conferência). Para registros desse tipo de chamada, o usuário especificado na coluna **ID do** Usuário corresponde ao organizador da reunião.

     **UCAP (Unified Communication Applications)** 
     *    **ucap_in** (uma chamada PSTN de entrada para o aplicativo UC, como atendimento automático ou fila de chamada) 
     *    **ucap_out** (uma chamada PSTN de saída do aplicativo UC, como atendimento automático ou fila de chamada)
         > [!NOTE]
         > As chamadas transferidas para um usuário do aplicativo UC, como um atendimento automático ou fila de chamadas, não serão exibidas no relatório de uso PSTN, pois essas chamadas são chamadas de áudio ponto a ponto (P2P). Você pode acessar as chamadas P2P no Centro de Administração do Skype for Business em "Ferramentas > Skype for Business Análise de Chamadas" e pesquisar pelo Nome de Usuário ou endereço SIP correlacionando a chamada por data/hora e/ou CLID de origem (ID da linha de chamada). 

     **Doméstico/Internacional** informa se a chamada feita foi considerada doméstica (dentro de um país/região) ou internacional (fora de um país/região) com base na localização do usuário. 
*    **Destino discado** é o nome do destino do país/região discado como França, Alemanha ou Estados Unidos (EUA). 
*    **Tipo de** número é o tipo de número de telefone que é do número de telefone de um usuário, um serviço ou número de chamada gratuita.  
*    **Hora de Início (UTC)** é a hora que a chamada foi iniciada ou feita. 
*    **Duração** é o tempo em que a chamada esteve conectada.  
*    **ConfID** é a ID da conferência de áudio. 
*    **A** cobrança é a quantidade de dinheiro ou custo da chamada que está sendo cobrada em sua conta. 
*    **Conversor de Moedas** é o tipo de moeda usado para calcular o custo da chamada. 
*    **A funcionalidade** é a licença usada para a chamada. Os tipos de licença que você pode ver são: 
     *    **MCOPSTNPP** - Créditos de Comunicações <br/> **MCOPSTN1** - Plano de Chamada Doméstica (3.000 min us / 1200 min planos da UE) 
     *    **MCOPSTN2** - Plano de Chamada Internacional 
     *    **MCOPSTN5** - Plano de Chamada Doméstica (plano de chamada de 120 minutos) 
     *    **MCOPSTN6** - Plano de Chamada Doméstica (plano de chamada de 240 minutos) Observação: Disponibilidade Limitada
     *    **MCOMEETADD -** Audioconferência
     *    **MCOMEETACPEA** - Audioconferência de pagamento por minuto
     
> [!NOTE]
> Se você quiser executar um relatório para incluir apenas chamadas pagas por minuto que não estão incluídas em sua assinatura de chamada ou conferência, filtre o relatório com a funcionalidade "MCOPSTNPP". Isso fornecerá uma itemização de todas as chamadas de pagamento por minuto.  Para audioconferência de pagamento por minuto, filtre por "MCOMEETACPEA" em vez de "MCOPSTNPP".  

> [!NOTE]
> Você também pode ver "sem dados" em alguns campos. "Nenhum dado" significa que o campo não é aplicável ao tipo ou recurso de chamada. 

> [!NOTE]
> Se você tiver um plano de chamada Telstra ou Softbank, não verá nenhum registro de detalhes de chamada no relatório de uso do PSTN. Entre em contato com Telstra ou Softbank para saber mais sobre suas necessidades de relatórios. 
***
![Número 2.](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas.
 ***

## <a name="exporting-pstn-usage-report"></a>Relatório de uso de PSTN de exportação

Clicar ou tocar no botão **Exportar para Excel** permite baixar o relatório de uso PSTN. Você pode exportar dados de até um ano a partir da data atual, a menos que os regulamentos específicos do país proíbam a retenção dos dados por 12 meses.

Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores.

O processo de exportação pode levar de alguns segundos a vários minutos para ser concluído, dependendo da quantidade dos dados. Quando o servidor concluir a exportação, você receberá um arquivo zip chamado "**Calls.Export.[ `identifier` ] .zip**", com o identificador sendo uma ID exclusiva para a exportação, que pode ser usada para solução de problemas.

Se você tiver planos de chamadas e roteamento direto, o arquivo exportado poderá conter dados para ambos os produtos. O arquivo de relatório de uso do PSTN terá nome de arquivo "**PSTN.calls.[ `UTC date` ] .csv**". Além dos arquivos PSTN e Roteamento Direto, o arquivo contém o arquivo "**parameters.json**", com o intervalo de tempo de exportação selecionado e Recursos (se for o caso).

Arquivo exportado é um arquivo CSV (Valores Separados por Vírgula), em conformidade com [o padrão RFC 4180.](https://tools.ietf.org/html/rfc4180) O arquivo pode ser aberto em Excel ou em qualquer outro editor compatível com padrões sem exigir transformações.

A primeira linha do CSV contém nomes de coluna.

### <a name="fields-in-the-export"></a>Campos na exportação

O arquivo exportado contém campos adicionais que não estão disponíveis no relatório online. Eles podem ser usados para solucionar problemas e fluxos de trabalho automatizados.

> [!div class="has-no-wrap"]  
> | #  | Nome | [Tipo de dados (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrição |
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
> | 13 | Hora de Início | `datetimeoffset` | Hora de início da chamada (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 14 | Hora de Término | `datetimeoffset` | Hora de término da chamada (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 15 | Segundos de Duração | `int` | Por quanto tempo a chamada foi conectada |
> | 16 | Taxa de Conexão | `numeric(16, 2)` | Preço da taxa de conexão |
> | 17 | Charge | `numeric(16, 2)` | Quantidade de dinheiro ou custo da chamada que é cobrada em sua conta |
> | 18 | Moeda | `nvarchar(3)` | Tipo de moeda usada para calcular o custo da chamada ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Recursos | `nvarchar(32)` | A licença usada para a chamada |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype for Business relatório de atividades](activity-report.md) Você pode ver o quanto seus usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Skype for Business de uso do dispositivo](device-usage-report.md) Você pode ver os dispositivos, incluindo Windows operacionais baseados em Windows dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para IM e reuniões.
    
- [Skype for Business relatório de atividades do organizador da conferência](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam IM, áudio/vídeo, compartilhamento de aplicativos, Web, /dial out - terceiros e /dial-out - Microsoft.
    
- [Skype for Business relatório de atividade do participante da conferência](conference-participant-activity-report.md) Você pode ver quantos IM, áudio/vídeo, compartilhamento de aplicativos, Web e conferências de áudio discada estão sendo participadas.
    
- [Skype for Business relatório de atividades ponto a ponto](peer-to-peer-activity-report.md) Você pode ver o quanto seus usuários estão usando IM, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype for Business relatório bloqueado de usuários](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Skype for Business pools de minutos PSTN](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual em sua organização.

- [Skype for Business de detalhes da sessão](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada de cada usuário.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
