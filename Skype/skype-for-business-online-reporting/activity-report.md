---
title: "Relatório de atividades"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: O365E_ReportsS4BActivity
ms.custom: Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: be0cba752c5d516a65ee8533750add2e46345455
ms.sourcegitcommit: 5ef156b78eb64a4370ad8e73b16e1ab5fd8fc976
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2018
---
# <a name="activity-report"></a>Relatório de atividades

O novo painel de controle do Office 365 **relatórios** mostra a visão geral de atividade entre os produtos do Office 365 em sua organização. Ele permite analisado relatórios de nível de produtos individuais para proporcionar mais granular insight sobre as atividades dentro de cada produto. Por exemplo, você pode usar o relatório do **Skype para atividade de negócios** para ver quanto os usuários estão usando-a-ponto ou organizados sessões de conferência, ou quanto eles estiver participando de sessões de conferência. 

Confira a [Visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para saber mais.
  
Nesse relatório, juntamente com o outro Skype para relatórios de negócios, oferece detalhes sobre a atividade em toda a organização. Esses detalhes são muito úteis quando você estiver investigando, planejamento e fazendo outras decisões de negócios para sua organização.
  
> [!NOTE]
> Você pode ver todos o Skype para relatórios de negócios quando você fizer logon como administrador no Centro de administração do Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Como obter o relatório de atividade do Skype for Business

1. Vá para o **Centro de administração do Office 365** > **relatórios** > **uso**.
    
2. Na página de **uso** , clique **Skype para atividade de negócios** , em **Selecionar uma lista de relatório** no lado esquerdo ou clique widget **Skype para atividade de negócios** .
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Dependendo da assinatura do Office 365, que você tem, você não pode ver todos os produtos e relatórios mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretar o relatório de atividade do Skype for Business

Para visualizar a atividade de seus usuários no Skype for Business, examine os gráficos **Atividade** e **Usuários**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>
No relatório **Atividade do Skype for Business**, é possível ver as tendências dos últimos sete, 30, 90 ou 180 dias.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Número 2](../images/sfbcallout2.png)<br/>
Cada relatório tem uma data para quando este relatório foi gerado. Geralmente, os relatórios refletem uma latência de 24 a 48 horas de tempo de atividade. 
***
![Número 3](../images/sfbcallout3.png)<br/>Use os dados do gráfico interativo **Atividade** para conhecer as tendências de uso e ver o número de atividades de conferência que estão sendo realizadas na sua organização. Ele mostrará o número total e os tipos de **Sessões ponto a ponto**, sessões de conferência **Organizadas** e **Participadas** em toda a organização.  
***
![Número 4](../images/sfbcallout4.png)<br/>
Use os dados de gráfico interativo do gráfico de **usuários** para entender as tendências de uso e para ver o número de usuários exclusivos que estão participando de atividades de conferência que estão sendo mantidas em sua organização. Ele mostrará o número total de usuários, juntamente com os tipos de **sessões ponto a ponto**, **organizado**e **Participated** em sessões de conferência.
***
![Número 5](../images/sfbcallout5.png)<br/>
Você pode filtrar a série, que você pode ver no gráfico clicando em um item na legenda. Por exemplo, no gráfico de **atividade** , clique ou toque em **sessões ponto a ponto**, **organizado**ou **Participated** para ver apenas as informações relacionadas a cada uma delas. Alterar essa opção não altera as informações na tabela de grade. 
***
![Número 6](../images/sfbcallout6.png)<br/>
Cada gráfico tem um eixo "X" (horizontal) e um "Y" (vertical).
*    No gráfico de **atividade** , o eixo Y é o número total de ponto a ponto, organizado e participado em sessões de conferência que são mantidas.
*    No gráfico de atividade de **usuários** , o eixo Y é o número de usuários exclusivos que estão participando de cada tipo de ponto a ponto, organizados e participou da conferência.

O eixo X em ambos os gráficos é o intervalo de datas selecionado para esse relatório específico. 
***
![Número 7](../images/sfbcallout7.png)<br/>
A tabela mostra uma análise detalhada de todas as atividades de conferência por usuário. Mostra todos os usuários que têm Skype para negócios atribuídos a eles e suas atividades de conferência. Você pode adicionar colunas adicionais à tabela.
*    **Nome de usuário** é o nome do usuário.
*    **Excluído** indica que a licença do usuário foi removida. <br/> <br/> **Observação:** Atividade de um usuário excluído ainda será exibida em um relatório, desde que ele foi licenciado em algum momento durante o período de tempo selecionado. A coluna **Deleted** ajuda você a Observe que o usuário pode não estar mais ativo, mas contribuíram para os dados no relatório.<br/><br/>
*    **Deleted data** é a data em que a licença do usuário foi removida.
*    **Data da última atividade (UTC)** é a última vez que o usuário se envolveu em uma sessão entre pares, organizou uma conferência ou participou de uma.
*    **-A-ponto** mostra o número total de sessões de conferência ponto a ponto que o usuário tiver usado.
*    **Conferências organizadas** mostra o número total de conferências que foram organizadas por esse usuário.
*    **Conferências participadas** mostra o número total de conferências das quais esse usuário participou.
*    **Produto atribuído** são os produtos do Office 365 atribuídos a esse usuário.<br/>

Se diretivas da sua organização impedirem a exibição relatórios onde as informações do usuário são identificáveis, você poderá alterar a configuração de privacidade para todos esses relatórios. Confira a seção **Ocultar detalhes nos relatórios do usuário** nos [Relatórios de atividade no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Número 8](../images/sfbcallout8.png)<br/>
Clique ou toque no ícone de **colunas** em qualquer uma das colunas para adicionar ou remover colunas do relatório.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Número 9](../images/sfbcallout9.png)<br/>
Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar em **Exportar**.           <br/> ![Botão Exportar do Skype para relatórios de negócios.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Isso exporta os dados de todos os usuários e permite que você faça simples de classificação e filtragem para análise adicional. Se houver menos do que 2.000 usuários, você pode classificar e filtrar dentro da tabela no relatório em si. Se você tiver mais do que 2.000 usuários, na ordem para filtrar e classificar, você precisará exportar os dados. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype para o relatório de uso do dispositivo de negócios](device-usage-report.md) Você pode para ver os dispositivos, incluindo os sistemas operacionais baseados no Windows e dispositivos móveis, que têm o Skype para o aplicativo de negócios instalados e usá-lo para mensagens Instantâneas e reuniões.
    
- [Skype para relatório de atividade do organizador de conferência de negócios](conference-organizer-activity-report.md) Você pode ver quanto a seus usuários são organizem conferências que utilizam o IM, áudio/vídeo, compartilhamento de aplicativo, Web, de terceiros confiáveis dial-in/out - 3rd e dial-in/out - Microsoft.
    
- [Skype para relatório de atividade ponto a ponto de negócios](peer-to-peer-activity-report.md) Você pode ver quanto os usuários estão usando o aplicativo de áudio/vídeo, mensagens Instantâneas, compartilhamento e transferência de arquivos.
    
- [Skype para usuários comerciais bloqueados relatório](users-blocked-report.md) Você pode ver os usuários em sua organização que foram bloqueados façam chamadas PSTN.
    
- [Skype para relatório de uso de PSTN de negócios](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e de custo para essas chamadas.

- [Skype para relatório de minuto pools corporativos PSTN](pstn-minute-pools-report.md) , que você pode ver o número de minutos gastos durante o mês atual dentro da sua organização.

- [Skype para relatório de detalhes de sessão de negócios](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada do usuário individual.

    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividade no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

