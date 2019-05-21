---
title: Relatório de atividades
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: df46f6a8fa029936911d8cafd463e683d25b4551
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298014"
---
# <a name="activity-report"></a>Relatório de atividades

O novo painel **Relatórios** do Office 365 mostra a visão geral das atividades em todos os produtos do Office 365 da sua organização. Ele permite que você faça drill-in para relatórios de nível de produto individuais para dar a você uma visão mais granular sobre as atividades de cada produto. Por exemplo, você pode usar o relatório **atividade do Skype for Business** para ver quanto seus usuários estão usando sessões de conferência ponto a ponto ou organizadas ou quanto elas estão participando de sessões de conferência. 

Confira a [visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para saber mais.
  
Esse relatório, juntamente com os outros relatórios do Skype for Business, fornece informações sobre atividades em toda a organização. Esses detalhes são muito úteis na investigação, no planejamento e na tomada de outras decisões de negócios para a sua organização.
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logon como administrador no centro de administração do Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Como obter o relatório de atividade do Skype for Business

1. Vá para o **Centro** > de administração do Office 365**uso**dos**relatórios** > .
    
2. Na página **uso** , clique em **atividade do Skype for Business** na **lista Selecionar um relatório** à esquerda ou clique no widget **atividade do Skype for Business** .
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Dependendo da assinatura do Office 365 que você tem, talvez você não veja todos os produtos e relatórios exibidos aqui. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar o relatório de atividade do Skype for Business

Para visualizar a atividade de seus usuários no Skype for Business, examine os gráficos **Atividade** e **Usuários**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
O relatório de atividade de email de **atividade do Skype for Business** pode ser visto para obter tendências nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um dia específico no relatório, a tabela (Veja o número 7) mostrará os dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).

> [!NOTE]
> Se você clicar nos detalhes de um dia específico, a tabela mostrará somente os dados dos 30 dias até a data em que o relatório foi gerado.

***
![Número 2](../images/sfbcallout2.png)<br/>
Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 a 48 horas a partir do momento da atividade. 
***
![Número 3](../images/sfbcallout3.png)<br/>Use os dados do gráfico interativo **Atividade** para conhecer as tendências de uso e ver o número de atividades de conferência que estão sendo realizadas na sua organização. Ele mostrará o número total e os tipos de **Sessões ponto a ponto**, sessões de conferência **Organizadas** e **Participadas** em toda a organização.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Use os dados do gráfico interativo **Usuários** para conhecer as tendências de uso e ver o número de usuários exclusivos participantes das atividades de conferência que estão sendo realizadas na sua organização. Ele mostrará o número total de usuários juntamente com os tipos de **sessões ponto a ponto**, organizadas e **** participando de **** sessões de conferência.
***
![Número 5](../images/sfbcallout5.png)<br/>
Para filtrar a série apresentada no gráfico, clique no item da legenda. Por exemplo, no gráfico **atividade** , clique ou toque em **sessões ponto a ponto**, organizadas **** ou participou **** para ver apenas as informações relacionadas a cada uma delas. Essa seleção não altera as informações contidas na tabela de grade. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tem um eixo "X" (horizontal) e um "Y" (vertical).
*    No gráfico **atividade** , o eixo Y é o número total de sessões ponto a ponto, organizadas e participadas em sessões de conferência que são mantidas.
*    No gráfico de atividades **usuários** , o eixo Y é o número de usuários exclusivos que participam de cada tipo de ponto a ponto, organizado e participou em conferência.

O eixo X em ambos os gráficos é o intervalo de datas selecionado para esse relatório específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
A tabela mostra uma divisão de todas as atividades de conferência por usuário. Isso mostra todos os usuários que têm o Skype for Business atribuído a eles e suas atividades de conferência. Você pode adicionar mais colunas à tabela.
* **Nome** de usuário é o nome do usuário.
* **Excluído** indica que a licença do usuário foi removida.<br/><br/>
  > [!NOTE]
  > A atividade para um usuário excluído ainda será exibida em um relatório desde que ele tenha sido licenciado em algum momento durante o período de tempo selecionado. The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.
     
* **Deleted date** is the date on which the user's license was removed.
* **Data da última atividade (UTC)** é a última vez que o usuário se envolveu em uma sessão entre pares, organizou uma conferência ou participou de uma.
* **Ponto a ponto** mostra o número total de sessões de conferência ponto a ponto que o usuário usou.
* **Conferências organizadas** mostra o número total de conferências que foram organizadas por esse usuário.
* **Conferências participadas** mostra o número total de conferências das quais esse usuário participou.
* **Produto atribuído** são os produtos do Office 365 atribuídos a esse usuário.<br/>

Se as políticas da sua organização impedirem você de exibir relatórios nos quais as informações do usuário sejam identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **ocultar detalhes do usuário na seção relatórios** nos [relatórios de atividades no centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Número 8](../images/sfbcallout8.png)<br/>
Clique ou toque no ícone de **colunas** em qualquer uma das colunas para adicionar ou remover colunas do relatório.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar em **Exportar**.                                            <br/> ![Botão Exportar relatório do Skype for Business.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados em Windows e dispositivos móveis, que têm o aplicativo Skype for Business instalado e o estão usando para mensagens instantâneas e reuniões.
    
- [Relatório de atividade do organizador de conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver o quanto os usuários estão organizando conferências que usam mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, Web, dial-in/out-terceiro e discagem/saída-Microsoft.
    
- [Relatório de atividade ponto a ponto do Skype for Business](peer-to-peer-activity-report.md) Você pode ver o quanto os usuários estão usando mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório de usuários bloqueados do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.
    
- [Relatório de uso de PSTN do Skype for Business](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas.

- [Relatório de grupos de minutos PSTN do Skype for Business](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual dentro de sua organização.

- [Relatório de detalhes da sessão do Skype for Business](session-details-report.md) Você pode ver detalhes sobre as experiências de chamadas de um usuário individual.

    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
