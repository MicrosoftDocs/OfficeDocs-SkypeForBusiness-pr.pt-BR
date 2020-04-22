---
title: Relatório de detalhes da sessão
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
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
description: O novo painel relatórios do Microsoft 365 mostra a visão geral da atividade em todos os produtos do Office 365 em sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto.
ms.openlocfilehash: b10e68e46b8865579692594ded33e89558f4fdc2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776276"
---
# <a name="session-details-report"></a>Relatório de detalhes da sessão

O novo painel **Relatórios** do Office 365 mostra a visão geral das atividades em todos os produtos do Office 365 da sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto. Por exemplo, você pode usar o relatório de **detalhes da sessão do Skype for Business** para ver detalhes sobre as experiências de chamadas de um usuário individual.
  
Consulte a [visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver mais relatórios disponíveis.
  
Esse relatório, juntamente com os outros relatórios do Skype for Business, fornece detalhes sobre atividades, incluindo detalhes da sessão em toda a organização. Esses detalhes são muito úteis quando você está investigando, planejando e fazendo outras decisões empresariais para a sua organização e para configurar [créditos de comunicações](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logon como administrador no centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Como acessar o relatório de detalhes da sessão do Skype for Business

1. Vá para o centro de administração > **relatórios**
    
2. Selecione **relatórios** no menu à esquerda e clique em **uso**.
    
3. Na lista em **selecionar um relatório**, clique em **detalhes da sessão do Skype for Business**.
    
    > [!TIP]
    > Se você não vir esse relatório listado, acesse o >  **centro de administração do Skype for Business****relata** > **detalhes da sessão**. 
  
    > [!IMPORTANT]
    > Dependendo da assinatura do Microsoft 365 ou do Office 365 que você tem, talvez você não veja todos os produtos e relatórios que são mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar o relatório de detalhes da sessão do Skype for Business

Você pode obter uma visão dos detalhes da sessão do Skype for Business do seu usuário examinando cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
![Painel de relatório de detalhes da sessão do Skype for Business.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Pesquisar usuário por alias** permite que você pesquise um único usuário e exiba todos os detalhes da sessão do usuário na tabela abaixo. 
***
![Número 2](../images/sfbcallout2.png)<br/>**Enter a partir de data e hora** permite que você coloque a data de início. Você pode usar o calendário para selecionar a data ou inserir a data manualmente. Este campo deve ser preenchido.
***
![Número 3](../images/sfbcallout3.png)<br/>**Inserir data e hora** permite que você coloque a data de término. Você pode usar o calendário para selecionar a data ou inserir a data manualmente. Se nenhuma data de término for definida, o padrão será 30 dias a partir da data de início.
***
![Número 4](../images/sfbcallout4.png)<br/>A tabela mostra um detalhamento de todos os detalhes da sessão por usuário. Isso mostra todos os usuários que têm o Skype for Business atribuído a eles e suas informações de sessão. Você pode adicionar/remover colunas na tabela. <br/><br/>A tabela tem as seguintes colunas para cada sessão:
*    A **ID da caixa de diálogo** é a ID do identificador exclusivo da sessão SIP.
*    **Descrição de tipos de mídia** descreve se a sessão é uma chamada em conferência ou uma sessão ponto a ponto e o tipo de mídia usado (compartilhamento de áudio/vídeo/aplicativos).
*    A **hora de início** é a hora de início da sessão.
*    A **hora de término** é a hora de término da sessão.
*    **From URI** é o URI do usuário ou serviço que iniciou a sessão. Pode estar em branco se o usuário iniciou a sessão a partir de um telefone PSTN.
*    **Para URI** é o URI do usuário ou serviço que era o destino do início da sessão. No caso da conferência, esse é o URI do organizador. Pode estar em branco se o destino da sessão for um número de telefone PSTN.
*    **Da versão do cliente** informa o agente de usuário e a versão do cliente usado pelo usuário ou serviço que iniciou a sessão.
*    **Para a versão do cliente** informa o agente de usuário e a versão do cliente usado pelo usuário ou serviço que era o destino do início da sessão.
*    **URL da conferência** é a URL do SIP para a conferência, se a sessão for uma chamada em conferência. Todos os usuários na mesma chamada em conferência terão a mesma URL de conferência. 
*    **Do número de telefone celular** é o número de telefone que era o alvo da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos por ' x ' para proteger a privacidade do usuário.
*    **Para telefone celular** é o número de telefone que era o alvo da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos por ' x ' para proteger a privacidade do usuário.
*    **De ID de ponto de extremidade** é um GUID exclusivo do ponto de extremidade usado pelo usuário de. Usado para identificar se o usuário está comunicando várias sessões do mesmo ponto de extremidade. Pode estar em branco se o usuário estiver usando um telefone PSTN ou se a sessão foi iniciada a partir de um serviço.
*    **Para ID de ponto de extremidade** é um GUID exclusivo do ponto de extremidade usado pelo usuário para. Usado para identificar se o usuário está comunicando várias sessões do mesmo ponto de extremidade. Pode estar em branco se o usuário estiver usando um telefone PSTN, se a sessão foi iniciada a partir de um serviço ou uma sessão não pôde estabelecer uma sessão.
*    **Conf instância** é um GUID exclusivo da instância da conferência que usa a URL da conferência. Reuniões recorrentes terão a mesma URL de conferência, mas cada instância da reunião terá uma ocorrência de conf de diferença.
*    **Em nome do URI** é o URI da delegação em nome do qual a sessão está sendo estabelecida. <br/> **Referenciado por URI** é o URI do usuário que se referiu ao estabelecimento de uma sessão.
*    **Código de resposta** é o código de resposta SIP para o estabelecimento da sessão que indica se a sessão foi estabelecida com êxito.

Para cada sessão, há uma subtabela com dados diferentes disponíveis, dependendo do cenário. Os itens a seguir listam as guias disponíveis na subtabela dos usuários ou serviços de e para.
*    A guia sessão mostra dados sobre máquinas e sistemas operacionais.
*    MEDIALINES guia mostrar informações de conectividade de rede e informações de dispositivo.
*    AUDIOSTREAMS guia mostrar dados de desempenho de rede sobre os fluxos de áudio envolvidos na sessão.
*    A guia AUDIOCLIENTEVENTS mostra dados sobre problemas detectados pelo cliente que afetam a experiência de áudio.
*    AUDIOSIGNALS guia mostrar dados sobre o processamento de sinal de áudio para a sessão.
*    APPSHARINGSTREAMS guia mostrar dados de desempenho de rede sobre compartilhamento de aplicativos ou fluxos de trabalho de compartilhamento de área de trabalho envolvidos na sessão.
*    VIDEOCLIENTEVENTS guia mostrar dados sobre problemas detectados pelo cliente que afetam a experiência com vídeo.
*    VIDEOSTREAMS guia mostrar dados de desempenho de rede sobre os fluxos de vídeo envolvidos na sessão.
*    Guia TRACEROUTEs mostra os saltos de rede coletados via traceroute durante a sessão. O caminho de mídia real usado para a sessão pode variar e esses dados estão disponíveis apenas quando há áudio na sessão.
*    A guia FEEDBACKREPORTS mostra qualquer fim dos dados da pesquisa de chamadas fornecidos pelos usuários na sessão.
***
![Número 5](../images/sfbcallout5.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 6](../images/sfbcallout6.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.    <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividade do Skype for Business](activity-report.md) Você pode ver o quanto os usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados em Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens instantâneas e reuniões.
    
- [Relatório de atividade do organizador de conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver o quanto os usuários estão organizando conferências que usam mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, Web, dial-in/out-terceiro e discagem/saída-Microsoft.
    
- [Relatório atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver a quantidade de mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, conferência discada da Web e conferência que está sendo participada.
    
- [Relatório de atividade ponto a ponto do Skype for Business](peer-to-peer-activity-report.md) Você pode ver o quanto os usuários estão usando mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório de uso de PSTN do Skype for Business](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas.

- [Relatório de usuários bloqueados do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Relatório de grupos de minutos PSTN do Skype for Business](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual dentro de sua organização.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 