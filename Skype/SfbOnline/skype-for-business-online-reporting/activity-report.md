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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 1f6a54e75c240a3a2a1381597598f8486afa25d5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730250"
---
# <a name="activity-report"></a>Relatório de atividades

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

O **painel Relatórios** mostra a visão geral da atividade nos produtos Microsoft 365 ou Office 365 em sua organização. Ele permite que você faça uma análise de relatórios individuais no nível do produto para dar uma visão mais granular sobre as atividades em cada produto. Por exemplo, você pode usar o relatório de atividades do Skype for Business para ver o quanto seus usuários estão usando sessões de conferência ponto **a** ponto ou organizadas ou quanto eles estão participando de sessões de conferência. 

Confira a visão [geral relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para saber mais.
  
Este relatório, juntamente com os outros relatórios Skype for Business, fornece detalhes sobre as atividades em toda a sua organização. Esses detalhes são muito úteis na investigação, no planejamento e na tomada de outras decisões de negócios para a sua organização.
  
> [!NOTE]
> Você pode ver todos os relatórios Skype for Business quando fizer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Como obter o relatório de atividade do Skype for Business

1. Vá para o centro de administração > **Uso de**  >  **Relatórios.**
    
2. Na página **Uso,** escolha **Skype for Business** Atividade na lista Selecionar um relatório à esquerda ou clique no widget de Skype for Business  >   **atividade.** 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar o relatório de atividade do Skype for Business

Para visualizar a atividade de seus usuários no Skype for Business, examine os gráficos **Atividade** e **Usuários**.
  
![Skype for Business Relatório de Atividades Online.](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1.](../images/sfbcallout1.png)<br/>
O **Skype for Business** atividade de email atividade de atividade de atividade pode ser exibido para tendências nos últimos 7, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um determinado dia no relatório, a tabela (veja o número 7) mostrará dados por até 28 dias a partir da data atual (não a data em que o relatório foi gerado).

> [!NOTE]
> Se você clicar nos detalhes de um dia específico, a tabela mostrará apenas os dados dos 30 dias até a data em que o relatório foi gerado.

***
![Número 2.](../images/sfbcallout2.png)<br/>
Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. 
***
![Número 3.](../images/sfbcallout3.png)<br/>Use os dados do gráfico interativo **Atividade** para conhecer as tendências de uso e ver o número de atividades de conferência que estão sendo realizadas na sua organização. Ele mostrará o número total e os tipos de **Sessões ponto a ponto**, sessões de conferência **Organizadas** e **Participadas** em toda a organização.  
***
![Número 4.](../images/sfbcallout4.png)<br/>
Use os dados do gráfico interativo **Usuários** para conhecer as tendências de uso e ver o número de usuários exclusivos participantes das atividades de conferência que estão sendo realizadas na sua organização. Ele mostrará o número total de usuários juntamente com os tipos de sessões ponto a **ponto,** **organizadas** e **participadas** de sessões de conferência.
***
![Número 5.](../images/sfbcallout5.png)<br/>
Para filtrar a série apresentada no gráfico, clique no item da legenda. Por exemplo, no gráfico **Atividade,** clique ou toque em Sessões  ponto a **ponto,** Organizadas ou Participadas para ver apenas as informações **relacionadas** a cada uma delas. Essa seleção não altera as informações contidas na tabela de grade. 
***
![Número 6.](../images/sfbcallout6.png)<br/>
Cada gráfico tem um eixo "X" (horizontal) e um "Y" (vertical).
*    No gráfico **Atividade,** o eixo Y é o número total de sessões de conferência ponto a ponto, organizadas e participadas.
*    No gráfico **de atividades** Usuários, o eixo Y é o número de usuários exclusivos que participam de cada tipo de conferência ponto a ponto, organizado e participado da conferência.

O eixo X em ambos os gráficos é o intervalo de datas selecionado para esse relatório específico. 
***
![Número 7.](../images/sfbcallout7.png)<br/>
A tabela mostra uma divisão de todas as atividades de conferência por usuário. Isso mostra todos os usuários que Skype for Business atribuídos a eles e suas atividades de conferência. Você pode adicionar mais colunas à tabela.
* **Nome** de usuário é o nome do usuário.
* **Excluído** indica que a licença do usuário foi removida.<br/><br/>
  > [!NOTE]
  > A atividade de um usuário excluído ainda será exibida em um relatório desde que ele tenha sido licenciado em algum momento durante o período de tempo selecionado. The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.
     
* **Deleted date** is the date on which the user's license was removed.
* **Data da última atividade (UTC)** é a última vez que o usuário se envolveu em uma sessão entre pares, organizou uma conferência ou participou de uma.
* **Ponto a ponto mostra** o número total de sessões de conferência ponto a ponto que o usuário usou.
* **Conferências organizadas** mostra o número total de conferências que foram organizadas por esse usuário.
* **Conferências participadas** mostra o número total de conferências das quais esse usuário participou.
* **O produto atribuído** é o Microsoft 365 ou Office 365 que são atribuídos a esse usuário.<br/>

Se as políticas da sua organização impedirem que você veja relatórios em que as informações do usuário são identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **Ocultar detalhes do usuário na** seção Relatórios de Atividades no centro de [administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Número 8.](../images/sfbcallout8.png)<br/>
Clique ou toque no **ícone Colunas** em qualquer uma das colunas para adicionar ou remover colunas do relatório.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9.](../images/sfbcallout9.png)<br/>
Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar em **Exportar**.                                            <br/> ![Skype for Business Botão Exportar Relatórios.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Esse protocolo exporta os dados de todos os usuários e permite que você execute a classificação e a filtragem simples para análises posteriores. Se você tiver menos de 2.000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype for Business de uso do dispositivo](device-usage-report.md) Você pode ver os dispositivos, incluindo Windows e dispositivos móveis baseados em Skype for Business, que têm o aplicativo Skype for Business instalado e o estão usando para mensagens de IM e reuniões.
    
- [Skype for Business relatório de atividades do organizador da conferência](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam IM, áudio/vídeo, compartilhamento de aplicativos, Web, discagem/saída - terceiros e discagem de terceiros - Microsoft.
    
- [Skype for Business relatório de atividades ponto a ponto](peer-to-peer-activity-report.md) Você pode ver o quanto seus usuários estão usando mensagens IM, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype for Business relatório bloqueado de usuários](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.
    
- [Skype for Business relatório de uso PSTN](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas.

- [Skype for Business pools de minutos PSTN](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual em sua organização.

- [Skype for Business de detalhes da sessão](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada de cada usuário.

    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
