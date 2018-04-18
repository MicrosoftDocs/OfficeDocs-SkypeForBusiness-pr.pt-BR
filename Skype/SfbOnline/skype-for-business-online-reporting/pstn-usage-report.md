---
title: Relatório de uso do PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: O novo Skype para a área de relatórios do Centro de administração de negócios mostra você chamada e de áudio conferência atividade em sua organização. Ele permite extrair relatórios para proporcionar mais granular insight sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de detalhes do uso de PSTN do Skype for Business para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir os detalhes de uso de PSTN de conferência de áudio, incluindo o custo da chamada para que você possa entender o seu uso e chamada faturamento detalhes para determinar o uso em sua organização.
ms.openlocfilehash: 6ee6606ae37e02d07e3c3e57ca9fee529b150626
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="pstn-usage-report"></a>Relatório de uso do PSTN

O novo Skype para a área do Centro de administração de negócios **relatórios** mostra você chamada e de áudio conferência atividade em sua organização. Ele permite extrair relatórios para proporcionar mais granular insight sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de **detalhes do uso de PSTN do Skype for Business** para ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas. Você pode exibir os detalhes de uso de PSTN de conferência de áudio, incluindo o custo da chamada para que você possa entender o seu uso e chamada faturamento detalhes para determinar o uso em sua organização.
  
Confira a [Visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) mais de relatórios estão disponíveis.
  
Nesse relatório, juntamente com o outro Skype para relatórios de negócios, oferece detalhes sobre a atividade, incluindo a chamar o uso em sua organização. Esses detalhes são muito úteis quando você investigando, planejamento e tornando outros negócios decisões para sua organização e para configurar a [comunicação créditos](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> [!OBSERVAçãO] Você pode ver todos os relatórios do Skype for Business quando faz logon como administrador no Centro de administração do Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Como acessar o relatório de detalhes do uso de PSTN do Skype for Business

- Vá para **o Centro de administração do Office 365** > **Admin centrais** > **Skype para centro de administração de negócios** > **relatórios** > **detalhes de uso do PSTN**.
    
    > [!NOTE]
    > [!IMPORTANTE] Dependendo da sua assinatura do Office 365, talvez você não veja todos os produtos e relatórios mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretar o relatório de uso de PSTN do Skype for Business

Você pode obter uma visão do uso de PSTN do Skype for Business feito pelo seu usuário em cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
![Relatório de uso de PSTN do Skype for Business](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Número 1](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão do uso de PSTN por usuário. Todos os usuários que possuem Skype para negócios atribuídos a eles e seu uso PSTN é exibida. Você pode adicionar/remover colunas na tabela.
*    **ID de chamadas** é a ID de chamadas para uma chamada. É um identificador exclusivo para a chamada que é usada ao chamar o suporte de serviço da Microsoft.
*    **ID de usuário** é o nome que o usuário utiliza para entrar.
*    **Número de telefone** é o Skype para o número de telefone comercial que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída.
*    **Local do usuário** é o país/região onde o usuário está localizado.
*    **ID do chamador** é o número de telefone do chamador (ID de chamador) para chamadas de entrada, o número do qual a chamada foi originada ou o Skype para o número comercial do qual a chamada foi originada para chamadas de saída.
*    **Tipo de chamada** é se a chamada foi chamada de uma PSTN de entrada ou de saída e o tipo de chamada por exemplo, uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamada, talvez você veja são: 

     **Tipos de chamada de plano de chamada** 
     *    **user_in** (o usuário recebeu uma chamada de PSTN de entrada) 
     *    **user_out** (o usuário feita uma chamada de PSTN de saída) 
     *    **user_out_conf** (o usuário adicionado 2 ou mais participantes PSTN à chamada como uma chamada em conferência vias 3) 
     *    **user_out_transfer** (o usuário transferir a chamada para um número PSTN) 
     *    **user_out_forwarding** (o usuário encaminhadas a chamada para um número PSTN)

     **Tipos de chamadas de conferência de áudio**
     *    **conf_in** (uma chamada de entrada para a ponte de conferência de áudio) 
     *    **conf_out** (uma chamada de saída da ponte de conferência de áudio geralmente para adicionar um número PSTN à conferência)

     **Aplicativos de comunicação unificada (UCAP)** 
     *    **ucap_in** (uma chamada de entrada para o aplicativo de comunicação unificada como a fila de chamada e atendente automático) 
     *    **ucap_out** (uma chamada de saída do aplicativo de comunicação unificada, como a fila de chamada e atendente automático)
*     
     **Doméstico/internacional** informa se a chamada realizada era considerada internacionais (fora de um país/região) ou domésticas (dentro de um país/região) com base no local do usuário. 
*    **Destino discado** é o nome do destino do país/região que é discado como França, Alemanha ou dos Estados Unidos (EUA). 
*    **Tipo de número** é o tipo de número de telefone do número de telefone do usuário, um serviço ou número de chamada gratuito.  
*    **Hora de Início (UTC)** é a hora que a chamada foi iniciada ou feita. 
*    **Duração** é o tempo em que a chamada esteve conectada.  
*    **ConfID** é a ID de conferência da conferência de áudio. 
*    **Cobrança** é a quantidade de dinheiro ou o custo da chamada que está sendo carregada à sua conta. 
*    **Moeda** é o tipo de moeda que é usado para calcular o custo da chamada. 
*    **O recurso** é a licença usada para a chamada. Os tipos de licença, talvez você veja são: 
     *    **MCOPSTNPP** - créditos de comunicações <br/> **MCOPSTN1** - domésticas chamar planejar (min 3000 US / planos de 1200 min da UE) 
     *    **MCOPSTN2** - plano de chamadas internacionais 
     *    **MCOPSTN5** - domésticas chamar Plan (plano de chamada 120 min) 
     *    **MCOMEETADD** - serviços de audioconferência
     *    **MCOMEETACPEA** - pagamento por minuto serviços de audioconferência 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas.
 ***
![Número 3](../images/sfbcallout3.png)<br/>Você também pode exportar o relatório de dados em uma guia delimitados arquivo do Excel, clicando ou tocando no botão **Exportar para o Excel** . <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype para relatório de atividade de negócios](activity-report.md) Você pode ver quanto os usuários estão usando-a-ponto, organizada e participado em sessões de conferência.
    
- [Skype para o relatório de uso do dispositivo de negócios](device-usage-report.md) Você pode para ver os dispositivos, incluindo os sistemas operacionais baseados no Windows e dispositivos móveis que têm o Skype para o aplicativo de negócios instalados e usá-lo para mensagens Instantâneas e reuniões.
    
- [Skype para relatório de atividade do organizador de conferência de negócios](conference-organizer-activity-report.md) Você pode ver quanto os usuários são organizem conferências que utilizam a mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativo, Web, /dial check-out de terceiros - 3rd e /dial check-out - Microsoft.
    
- [Skype para relatório de atividade de participante de conferência de negócios](conference-participant-activity-report.md) Você pode ver quantos compartilhamento de aplicativos de mensagens Instantâneas, áudio/vídeo, webconferências e conferências de áudio de discagem estão sendo participou.
    
- [Skype para relatório de atividade ponto a ponto de negócios](peer-to-peer-activity-report.md) Você pode ver quanto os usuários estão usando mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype para usuários comerciais bloqueados relatório](users-blocked-report.md) Você pode ver os usuários em sua organização que foram bloqueados façam chamadas PSTN.

- [Skype para relatório de minuto pools corporativos PSTN](pstn-minute-pools-report.md) , que você pode ver o número de minutos gastos durante o mês atual dentro da sua organização.

- [Skype para relatório de detalhes de sessão de negócios](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada do usuário individual.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
