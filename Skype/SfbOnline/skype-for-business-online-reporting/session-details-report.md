---
title: "Relatório de detalhes de sessão"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
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
description: "O novo painel Relatórios do Office 365 mostra a visão geral das atividades em todos os produtos do Office 365 na sua organização. Ele permite analisar detalhes dos relatórios no nível dos produtos individualmente para oferecer uma visão mais granular das atividades dentro de cada produto."
ms.openlocfilehash: 3760a5dc6caf3ebf5f70290031f1014af9e04ef6
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2018
---
# <a name="session-details-report"></a>Relatório de detalhes de sessão

O novo painel **Relatórios** do Office 365 mostra a visão geral das atividades em todos os produtos do Office 365 da sua organização. Ele permite analisar detalhes dos relatórios em nível de produtos individuais para ter informações mais granulares das atividades dentro de cada produto. Por exemplo, você pode usar o relatório do **Skype para obter detalhes de sessão de negócios** para ver detalhes sobre as experiências de chamada do usuário individual.
  
Confira a [Visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) mais de relatórios estão disponíveis.
  
Nesse relatório, juntamente com o outro Skype para relatórios de negócios fornecem detalhes sobre a atividade em toda a organização, incluindo detalhes de sessão. Esses detalhes são muito úteis quando você investigando, planejamento e tornando outros negócios decisões para sua organização e para configurar [créditos de comunicações](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md).
  
> [!NOTE]
> [!OBSERVAçãO] Você pode ver todos os relatórios do Skype for Business ao fazer logon como um administrador no Centro de administração do Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Relatório de detalhes de como obter para o Skype para sessão de negócios

1. Vá para o **Centro de administração do Office 365** > **relatórios**
    
2. Selecione **relatórios** no menu à esquerda e clique em **uso**.
    
3. Na lista em **Selecione um relatório**, clique em **Skype para obter detalhes de sessão de negócios**.
    
    > [!TIP]
    > Se você não vir esse relatório listado, vá para **Skype para centro de administração de negócios** > **relatórios** > **detalhes da sessão**. 
  
    > [!IMPORTANT]
    > [!IMPORTANTE] Dependendo da sua assinatura do Office 365, talvez você não veja todos os produtos e relatórios mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretar o Skype para relatório de detalhes de sessão de negócios

Você pode obter um modo de exibição em Skype do seu usuário para obter detalhes de sessão de negócios examinando cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
![Skype para painel de relatório de detalhes de sessão de negócios.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Usuário de pesquisa por alias** permite que você pesquise um único usuário e exibe todos os detalhes de sessão do usuário na tabela a seguir. 
***
![Número 2](../images/sfbcallout2.png)<br/>**ENTER de data hora** permite que você colocar na data de início. Você pode usar o calendário para selecionar a data ou insira a data manualmente. Este campo deve ser preenchido.
***
![Número 3](../images/sfbcallout3.png)<br/>**Digite a data hora** permite que você colocar na data final. Você pode usar o calendário para selecionar a data ou insira a data manualmente. Se nenhuma data final estiver definida, o padrão é 30 dias a partir da data de início.
***
![Número 4](../images/sfbcallout4.png)<br/>A tabela mostra uma divisão das todos os detalhes de sessão por usuário. Todos os usuários que possuem Skype para negócios atribuídos a eles e suas informações de sessão é exibida. Você pode adicionar/remover colunas na tabela. <br/><br/>A tabela tem as seguintes colunas para cada sessão:
*    **ID de diálogo** é a ID para o identificador exclusivo da sessão SIP.
*    **Descrição de tipos de mídia** descreve se a sessão é uma chamada em conferência ou uma sessão de P2P e o tipo de mídia usado (compartilhamento de áudio/vídeo/aplicativo).
*    **Hora de início** é a hora de início da sessão.
*    **Hora de término** é o horário em que a sessão terminou.
*    **Do URI** é o URI do usuário ou serviço que iniciou a sessão. Poderá estar vazia se o usuário que iniciou a sessão de um telefone PSTN.
*    **URI** é o URI do usuário ou serviço que foi o destino de iniciação de sessão. No caso de conferência, esse é o URI do organizador. Poderá estar vazia se o destino da sessão fosse um número de telefone da PSTN.
*    **Da versão do cliente** informa o agente de usuário e a versão do cliente usado pelo usuário ou serviço que iniciou a sessão.
*    **A versão de cliente** informa o agente de usuário e a versão do cliente usado pelo usuário ou serviço que foi o destino de iniciação de sessão.
*    **URL de conferência** é a URL do SIP da conferência, se a sessão foi uma chamada em conferência. Todos os usuários na mesma chamada em conferência terá a mesma URL de conferência. 
*    **Número de Tel** é o número de telefone que foi o destino da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos pelo x para proteger a privacidade do usuário.
*    **Número de Tel para** é o número de telefone que foi o destino da sessão, se aplicável. Os últimos dígitos do número de telefone podem ser substituídos pelo x para proteger a privacidade do usuário.
*    **Do ponto de extremidade Id** é um GUID exclusivo do ponto de extremidade usado pelo usuário From. Usado para identificar se o usuário está se comunicando várias sessões do mesmo ponto de extremidade. Poderá estar vazia se o usuário está usando um telefone PSTN ou se a sessão foi iniciada a partir de um serviço.
*    **A Id de ponto de extremidade** é um GUID exclusivo do ponto de extremidade usado pelo usuário para. Usado para identificar se o usuário está se comunicando várias sessões do mesmo ponto de extremidade. Poderá estar vazia se o usuário está usando um telefone PSTN, se a sessão foi iniciada a partir de um serviço ou uma sessão falhou ao estabelecer.
*    **Instância conf** é um GUID exclusivo para a instância de uma conferência usando a URL de conferência. Reuniões recorrentes terá a mesma URL de conferência, mas cada instância da reunião terá uma diferença Conf instância.
*    **Em nome de URI** é o URI do representante em cujo nome a sessão seja estabelecida. <br/> **Conhecido por URI** é o URI do usuário que se refere o estabelecimento de uma sessão.
*    **Código de resposta** é o código de resposta SIP para o estabelecimento da sessão que indica se a sessão foi estabelecida com êxito.

Para cada sessão, há uma tabela de sub com dados diferentes disponíveis, dependendo do cenário. A seguir lista as guias disponíveis na tabela sub para From e para o usuário ou serviços.
*    Guia de sessão mostra dados sobre os sistemas operacionais e de máquinas.
*    Guia MEDIALINES mostra informações de conectividade de rede e informações do dispositivo.
*    Guia AUDIOSTREAMS mostra dados de desempenho de rede sobre os fluxos de áudio envolvido na sessão.
*    Guia AUDIOCLIENTEVENTS mostra dados sobre problemas de cliente detectada afeta a experiência de áudio.
*    Guia AUDIOSIGNALS mostra dados sobre o sinal de áudio de processamento para a sessão.
*    Guia APPSHARINGSTREAMS mostra os dados de desempenho de rede sobre o compartilhamento de aplicativos ou fluxos de compartilhamento da área de trabalho envolvido na sessão.
*    Guia VIDEOCLIENTEVENTS mostra dados sobre problemas de cliente detectada afeta a experiência de vídeo.
*    Guia VIDEOSTREAMS mostra dados de desempenho de rede sobre os fluxos de vídeo envolvido na sessão.
*    Guia de rastrear ROTAS mostra os saltos de rede coletados via traceroute durante a sessão. O caminho de mídia real usado para a sessão pode variar e esses dados só estão disponíveis quando não há áudio na sessão.
*    Guia FEEDBACKREPORTS mostra qualquer fim dos dados de pesquisa de chamada fornecidos pelos usuários na sessão.
***
![Número 5](../images/sfbcallout5.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 6](../images/sfbcallout6.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.  <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype para relatório de atividade de negócios](activity-report.md) Você pode ver quanto os usuários estão usando-a-ponto, organizada e participado em sessões de conferência.
    
- [Skype para o relatório de uso do dispositivo de negócios](device-usage-report.md) Você pode para ver os dispositivos, incluindo os sistemas operacionais baseados no Windows e dispositivos móveis que têm o Skype para o aplicativo de negócios instalados e usá-lo para mensagens Instantâneas e reuniões.
    
- [Skype para relatório de atividade do organizador de conferência de negócios](conference-organizer-activity-report.md) Você pode ver quanto a seus usuários são organizem conferências que utilizam o IM, áudio/vídeo, compartilhamento de aplicativo, Web, de terceiros confiáveis dial-in/out - 3rd e dial-in/out - Microsoft.
    
- [Skype para relatório de atividade de participante de conferência de negócios](conference-participant-activity-report.md) Você pode ver quantas mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativo, Web e e conferências de conferência de discagem/saída estão sendo participou.
    
- [Skype para relatório de atividade ponto a ponto de negócios](peer-to-peer-activity-report.md) Você pode ver quanto os usuários estão usando mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype para relatório de uso de PSTN de negócios](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e de custo para essas chamadas.

- [Skype para usuários comerciais bloqueados relatório](users-blocked-report.md) Você pode ver os usuários em sua organização que foram bloqueados façam chamadas PSTN.

- [Skype para relatório de minuto pools corporativos PSTN](pstn-minute-pools-report.md) , que você pode ver o número de minutos gastos durante o mês atual dentro da sua organização.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

## <a name="feedback"></a>Comentários?
Para fornecer comentários sobre o produto ou para saber como estamos indo, consulte [Skype para comentários de negócios](https://www.skypefeedback.com).