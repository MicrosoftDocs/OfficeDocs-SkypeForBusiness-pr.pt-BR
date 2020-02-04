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
ms.openlocfilehash: b76bd2f752b03e59143162261b37f311f1b38b64
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706046"
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
*    A **ID da chamada** é a ID da chamada para uma chamada. É um identificador exclusivo para a chamada usada ao chamar o suporte ao serviço da Microsoft.
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
     *    **conf_in** (uma chamada de entrada para a ponte de audioconferência) 
     *    **conf_out** (uma chamada de saída da ponte de videoconferência geralmente para adicionar um número PSTN à conferência)

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
***
> [!NOTE]
> Você também pode ver "nenhum dado" em alguns campos. "Nenhum dado" significa que o campo não é aplicável ao tipo ou funcionalidade de chamada. 
***
> [!NOTE]
> Se você tiver um plano de chamadas Telstra, não verá os registros de detalhes da chamada no relatório de uso de PSTN. Entre em contato com a Telstra para atender às suas necessidades de relatório. 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas.
 ***
![Número 3](../images/sfbcallout3.png)<br/>Você também pode exportar os dados do relatório para um arquivo do Excel delimitado por VÍRGULAs, clicando ou tocando no botão **exportar para o Excel** . Você pode exportar dados até um ano a partir da data atual, a menos que a regulamentação específica do país proíba a retenção dos dados por 12 meses.<br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. 
    
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
  
  
 
