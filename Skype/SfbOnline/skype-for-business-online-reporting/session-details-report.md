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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: O painel Relatórios mostra a visão geral da atividade nos produtos Microsoft 365 ou Office 365 em sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto.
ms.openlocfilehash: 30d6f28c193f303d4cbc21467fb05e260e75a595
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726680"
---
# <a name="session-details-report"></a>Relatório de detalhes da sessão

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

O **painel Relatórios** mostra a visão geral da atividade nos produtos Microsoft 365 ou Office 365 em sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto. Por exemplo, você pode usar o relatório de Skype for Business **de** sessão para ver detalhes sobre as experiências de chamada individuais do usuário.
  
Confira Visão [geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obter mais relatórios disponíveis.
  
Este relatório, juntamente com os outros relatórios Skype for Business, dão detalhes sobre a atividade, incluindo os detalhes da sessão em toda a sua organização. Esses detalhes são muito úteis ao investigar, planejar e tomar outras decisões de negócios para sua organização e para configurar [créditos de comunicação.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios Skype for Business quando fizer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Como chegar ao relatório de Skype for Business de sessão

1. Vá para o centro de administração > **Relatórios**
    
2. Selecione **Relatórios** no menu esquerdo e clique em **Uso**.
    
3. Na lista em **Selecionar um relatório,** clique **Skype for Business Detalhes da Sessão.**
    
    > [!TIP]
    > Se você não vir esse relatório listado, vá para o centro **de** administração Skype for Business  >  **Detalhes** da  >  **Sessão de Relatórios.** 
  
    > [!IMPORTANT]
    > Dependendo da assinatura Microsoft 365 ou Office 365 você tem, talvez você não veja todos os produtos e relatórios mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar o relatório Skype for Business de detalhes da sessão

Você pode obter uma exibição nos detalhes da sessão de Skype for Business do usuário, analisando cada uma das colunas exibidas.
  
Esta é a aparência do relatório.
  
![Skype for Business Painel relatório de detalhes da sessão.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1.](../images/sfbcallout1.png)<br/>**Pesquisar usuário por alias** permite que você pesquise por um único usuário e exibe todos os detalhes da sessão do usuário na tabela abaixo. 
***
![Número 2.](../images/sfbcallout2.png)<br/>**Insira a partir da hora** de data permite que você coloque a data de início. Você pode usar o calendário para selecionar a data ou inserir a data manualmente. Esse campo deve ser preenchido.
***
![Número 3.](../images/sfbcallout3.png)<br/>**Inserir a hora de data** permite que você coloque a data de término. Você pode usar o calendário para selecionar a data ou inserir a data manualmente. Se nenhuma data de término for definida, o padrão será 30 dias a partir da data de início.
***
![Número 4.](../images/sfbcallout4.png)<br/>A tabela mostra um detalhamento de todos os detalhes da sessão por usuário. Isso mostra todos os usuários que Skype for Business atribuídos a eles e suas informações de sessão. Você pode adicionar/remover colunas na tabela. <br/><br/>A tabela tem as seguintes colunas para cada sessão:
*    **A ID da** caixa de diálogo é a ID do identificador exclusivo da sessão SIP.
*    **A descrição** dos tipos de mídia descreve se a sessão é uma chamada de conferência ou uma sessão P2P e o tipo de mídia usada (Compartilhamento de áudio/vídeo/aplicativo).
*    **A hora de** início é a hora em que a sessão foi iniciada.
*    **Hora de** término é a hora em que a sessão terminou.
*    **A partir do URI** é o URI do usuário ou serviço que iniciou a sessão. Pode estar em branco se o usuário iniciou a sessão de um telefone PSTN.
*    **To URI** is the URI of the user or service that was the target of the session initiation. No caso da conferência, esse é o URI do organizador. Pode estar em branco se o destino da sessão fosse um número de telefone PSTN.
*    **Na versão do** cliente informa o Agente de Usuário e a versão do cliente usado pelo usuário ou serviço que iniciou a sessão.
*    **A versão do** cliente informa o Agente de Usuário e a versão do cliente usado pelo usuário ou serviço que foi o destino do início da sessão.
*    **URL da** conferência é a URL SIP da conferência, se a sessão foi uma chamada de conferência. Todos os usuários na mesma chamada de conferência terão a mesma URL de conferência. 
*    **O número tel** é o número de telefone que foi o destino da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos por 'x' para proteger a privacidade do usuário.
*    **Para o número tel** é o número de telefone que foi o destino da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos por 'x' para proteger a privacidade do usuário.
*    **A ID do Ponto de** Extremidade é um GUID exclusivo do ponto de extremidade usado pelo usuário From. Usado para identificar se o usuário está comunicando várias sessões do mesmo ponto de extremidade. Pode estar em branco se o usuário estiver usando um telefone PSTN ou se a sessão foi iniciada a partir de um serviço.
*    **To Endpoint Id** is a unique GUID of the endpoint used by the To user. Usado para identificar se o usuário está comunicando várias sessões do mesmo ponto de extremidade. Pode estar em branco se o usuário estiver usando um telefone PSTN, se a sessão tiver sido iniciada de um serviço ou se uma sessão não tiver sido estabeleçada.
*    **Conf Instance** é um GUID exclusivo para a instância da conferência usando a URL da conferência. Reuniões recorrentes terão a mesma URL de Conferência, mas cada instância da reunião terá uma diferença Conf Instance.
*    **Em Nome do URI é** o URI do delegator em cujo nome a sessão está sendo estabelecida. <br/> **Referido por URI** é o URI do usuário que se referiu ao estabelecimento de uma sessão.
*    **Código de** Resposta é o código de resposta SIP para o estabelecimento da sessão que indica se a sessão foi estabelecida com êxito.

Para cada sessão, há uma sub tabela com dados diferentes disponíveis, dependendo do cenário. O seguinte lista as guias disponíveis na sub tabela para o usuário ou serviços De e Para.
*    A guia SESSÃO mostra dados sobre máquinas e sistemas operacionais.
*    A guia MEDIALINES mostra informações de conectividade de rede e informações do dispositivo.
*    A guia AUDIOSTREAMS mostra dados de desempenho de rede sobre os fluxos de áudio envolvidos na sessão.
*    A guia AUDIOCLIENTEVENTS mostra dados sobre problemas detectados pelo cliente que impactam a experiência de áudio.
*    A guia AUDIOSIGNALS mostra dados sobre o processamento de sinal de áudio para a sessão.
*    A guia APPSHARINGSTREAMS mostra dados de desempenho de rede sobre o compartilhamento de aplicativos ou fluxos de compartilhamento de área de trabalho envolvidos na sessão.
*    A guia VIDEOCLIENTEVENTS mostra dados sobre problemas detectados pelo cliente que impactam a experiência de vídeo.
*    A guia VIDEOSTREAMS mostra dados de desempenho da rede sobre os fluxos de vídeo envolvidos na sessão.
*    A guia TRACEROUTES mostra os saltos de rede coletados por meio de traceroute durante a sessão. O caminho de mídia real usado para a sessão pode variar e esses dados só estarão disponíveis quando houver áudio na sessão.
*    A guia FEEDBACKREPORTS mostra qualquer fim dos dados de pesquisa de chamada fornecidos pelos usuários na sessão.
***
![Número 5.](../images/sfbcallout5.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 6.](../images/sfbcallout6.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.    <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros Skype for Business relatórios?

- [Skype for Business relatório de atividades](activity-report.md) Você pode ver o quanto seus usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Skype for Business de uso do dispositivo](device-usage-report.md) Você pode ver os dispositivos, incluindo Windows operacionais baseados em Windows dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para IM e reuniões.
    
- [Skype for Business relatório de atividades do organizador da conferência](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam IM, áudio/vídeo, compartilhamento de aplicativos, Web, discagem/saída - terceiros e discagem de terceiros - Microsoft.
    
- [Skype for Business relatório de atividade do participante da conferência](conference-participant-activity-report.md) Você pode ver quantas conferências de IM, áudio/vídeo, compartilhamento de aplicativos, Web e conferência discada/saída estão sendo participadas.
    
- [Skype for Business relatório de atividades ponto a ponto](peer-to-peer-activity-report.md) Você pode ver o quanto seus usuários estão usando IM, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype for Business relatório de uso PSTN](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas.

- [Skype for Business relatório bloqueado de usuários](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Skype for Business pools de minutos PSTN](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual em sua organização.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
