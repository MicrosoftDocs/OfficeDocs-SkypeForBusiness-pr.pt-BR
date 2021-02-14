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
description: O painel Relatórios mostra a visão geral das atividades em todos os produtos do Microsoft 365 ou office 365 em sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto.
ms.openlocfilehash: 951f93aabe66bdb7e6b92f9b2c6cf1627e7e1a10
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205502"
---
# <a name="session-details-report"></a>Relatório de detalhes da sessão

O **painel** Relatórios mostra a visão geral das atividades em todos os produtos do Microsoft 365 ou office 365 em sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto. Por exemplo, você pode usar o relatório de detalhes da Sessão do **Skype for Business** para ver detalhes sobre as experiências de chamada de um usuário individual.
  
Confira a [visão geral de](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) relatórios para obter mais relatórios disponíveis.
  
Este relatório, juntamente com os outros relatórios do Skype for Business, dão detalhes sobre a atividade, incluindo detalhes da sessão em toda a organização. Esses detalhes são muito úteis ao investigar, planejar e tomar outras decisões de negócios para sua organização e para configurar [Créditos de Comunicação.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Como acessar o relatório de detalhes da Sessão do Skype for Business

1. Ir para o centro de administração > **Relatórios**
    
2. Selecione **Relatórios** no menu à esquerda e clique em **Uso.**
    
3. Na lista em **Selecionar um relatório,** clique em **Detalhes da Sessão do Skype for Business.**
    
    > [!TIP]
    > Se você não vir este relatório listado, acesse os detalhes da Sessão de Relatórios do Centro de administração do **Skype for**  >    >  **Business.** 
  
    > [!IMPORTANT]
    > Dependendo da assinatura do Microsoft 365 ou do Office 365 que você tem, talvez você não veja todos os produtos e relatórios mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar o relatório de detalhes da Sessão do Skype for Business

Você pode ver os detalhes da sessão do Skype for Business do usuário olhando para cada uma das colunas exibidas.
  
Esta é a aparência do relatório.
  
![Painel de relatório de detalhes da sessão do Skype for Business.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Pesquisar usuário por alias** permite pesquisar um único usuário e exibe todos os detalhes da sessão do usuário na tabela abaixo. 
***
![Número 2](../images/sfbcallout2.png)<br/>**Inserir a partir da data** permite que você insira a data de início. Você pode usar o calendário para selecionar a data ou inserir a data manualmente. Esse campo deve ser preenchido.
***
![Número 3](../images/sfbcallout3.png)<br/>**Inserir a data de** data permite que você coloque a data de término. Você pode usar o calendário para selecionar a data ou inserir a data manualmente. Se nenhuma data de término for definida, o padrão será 30 dias a partir da data de início.
***
![Número 4](../images/sfbcallout4.png)<br/>A tabela mostra uma divisão de todos os detalhes da sessão por usuário. Isso mostra todos os usuários que têm o Skype for Business atribuído a eles e suas informações de sessão. Você pode adicionar/remover colunas na tabela. <br/><br/>A tabela tem as seguintes colunas para cada sessão:
*    **A ID da caixa** de diálogo é a ID do identificador exclusivo da sessão SIP.
*    **A descrição dos** tipos de mídia descreve se a sessão é uma chamada em conferência ou uma sessão P2P e o tipo de mídia usada (Áudio/Vídeo/Compartilhamento de Aplicativos).
*    **A hora de** início é a hora em que a sessão começou.
*    **A hora de** término é a hora em que a sessão terminou.
*    **Do URI** está o URI do usuário ou serviço que iniciou a sessão. Pode estar em branco se o usuário iniciou a sessão a partir de um telefone PSTN.
*    **Para URI** é o URI do usuário ou serviço que foi o destino do início da sessão. No caso da conferência, este é o URI do organizador. Pode estar em branco se o destino da sessão fosse um número de telefone PSTN.
*    **A versão do** cliente informa o Agente do Usuário e a versão do cliente usado pelo usuário ou serviço que iniciou a sessão.
*    **A versão do cliente** informa o Agente do Usuário e a versão do cliente usado pelo usuário ou serviço que foi o destino do início da sessão.
*    **A URL da** conferência é a URL SIP da conferência, se a sessão era uma chamada em conferência. Todos os usuários na mesma chamada em conferência terão a mesma URL de conferência. 
*    **No número Tel** está o número de telefone que foi o destino da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos por 'x' para proteger a privacidade do usuário.
*    **Para o número Tel,** é o número de telefone que foi o destino da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos por 'x' para proteger a privacidade do usuário.
*    **A ID do Ponto de Extremidade** é um GUID exclusivo do ponto de extremidade usado pelo usuário De. Usado para identificar se o usuário está comunicando várias sessões do mesmo ponto de extremidade. Pode estar em branco se o usuário estiver usando um telefone PSTN ou se a sessão tiver sido iniciada a partir de um serviço.
*    **A ID do Ponto de** Extremidade é um GUID exclusivo do ponto de extremidade usado pelo usuário Para. Usado para identificar se o usuário está comunicando várias sessões do mesmo ponto de extremidade. Pode estar em branco se o usuário estiver usando um telefone PSTN, se a sessão tiver sido iniciada a partir de um serviço ou se uma sessão não tiver sido estabeleça.
*    **Conf Instance** é um GUID exclusivo para a instância da conferência usando a URL da Conferência. As reuniões recorrentes terão a mesma URL de Conferência, mas cada instância da reunião terá uma diferença Conf Instance.
*    **Em nome do URI,** está o URI do delegador em nome do qual a sessão está sendo estabelecida. <br/> **O URI referido** é o URI do usuário que indicou o estabelecimento de uma sessão.
*    **Código de** Resposta é o código de resposta SIP para o estabelecimento da sessão que indica se a sessão foi estabelecida com êxito.

Para cada sessão, há uma sub tabela com dados diferentes disponíveis, dependendo do cenário. A lista a seguir lista as guias disponíveis na sub tabela para o usuário ou serviços De e Para.
*    A guia SESSÃO mostra dados sobre máquinas e sistemas operacionais.
*    A guia MEDIALINES mostra informações de conectividade de rede e informações do dispositivo.
*    A guia AUDIOSTREAMS mostra dados de desempenho de rede sobre os fluxos de áudio envolvidos na sessão.
*    A guia AUDIOCLIENTEVENTS mostra dados sobre problemas detectados pelo cliente que estão afetando a experiência de áudio.
*    A guia AUDIOSIGNALS mostra dados sobre o processamento do sinal de áudio para a sessão.
*    A guia APPSHARINGSTREAMS mostra dados de desempenho de rede sobre o compartilhamento de aplicativos ou fluxos de compartilhamento da área de trabalho envolvidos na sessão.
*    A guia VIDEOCLIENTEVENTS mostra dados sobre problemas detectados pelo cliente que estão afetando a experiência do vídeo.
*    A guia VIDEOSTREAMS mostra dados de desempenho de rede sobre os fluxos de vídeo envolvidos na sessão.
*    A guia TRACEROUTES mostra os saltos de rede coletados via traceroute durante a sessão. O caminho de mídia real usado para a sessão pode variar e esses dados só estarão disponíveis quando houver áudio na sessão.
*    A guia FEEDBACKREPORTS mostra qualquer fim dos dados da pesquisa de chamada fornecidos pelos usuários na sessão.
***
![Número 5](../images/sfbcallout5.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 6](../images/sfbcallout6.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.    <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividades do Skype for Business](activity-report.md) Você pode ver o quanto seus usuários estão usando ponto a ponto, organizaram e participaram de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados no Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens de mensagens e reuniões.
    
- Relatório de atividade do organizador de [conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam mensagens de iM, áudio/vídeo, compartilhamento de aplicativos, Web, discagem – terceiros e discagem – Microsoft.
    
- [Relatório de atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver em quantas conferências de IM, áudio/vídeo, compartilhamento de aplicativos, Web e conferência discada estão participando.
    
- [Relatório de atividade ponto a ponto](peer-to-peer-activity-report.md) do Skype for Business Você pode ver o quanto seus usuários estão usando mensagens de texto, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório de uso de PSTN do Skype for Business](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas.

- [Relatório bloqueado de usuários do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Pools de minutos PSTN](pstn-minute-pools-report.md) do Skype for Business relatam o número de minutos consumidos durante o mês atual em sua organização.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 