---
title: Relatório de pools de minutos PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: O novo Skype para a área de relatórios do Centro de administração de negócios mostra você chamada e de áudio conferência atividade em sua organização. Ele permite extrair relatórios para proporcionar mais granular insight sobre as atividades de cada usuário. Por exemplo, você pode usar o Skype para relatório de minuto pools corporativos PSTN para ver o número de minutos gastos durante o mês atual dentro da sua organização.
ms.openlocfilehash: 2840ac4bde1234f0f87fe17c41f43b6efad647b5
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182371"
---
# <a name="pstn-minute-pools-report"></a>Relatório de pools de minutos PSTN

>[!NOTE]
>Este relatório só está disponível para clientes de visualização.

O novo Skype para a área do Centro de administração de negócios **relatórios** mostra você chamada e de áudio conferência atividade em sua organização. Ele permite extrair relatórios para proporcionar mais granular insight sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório do **Skype para pools de minuto PSTN de negócios** para ver o número de minutos gastos durante o mês atual dentro da sua organização.
  
Confira a [Visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) mais de relatórios estão disponíveis.
  
Nesse relatório, juntamente com o outro Skype para relatórios de negócios, oferece detalhes sobre a atividade em toda a organização. Esses detalhes são muito úteis quando investigando, planejar e realizar outras decisões de negócios para sua organização e para configurar a [Comunicação créditos](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> [!OBSERVAçãO] Você pode ver todos os relatórios do Skype for Business quando faz logon como administrador no Centro de administração do Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Como obter para o Skype para relatório de minuto pools corporativos PSTN

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

- Vá para **o Centro de administração do Office 365** > **Admin centrais** > **Skype para centro de administração de negócios** > **relatórios** > **pools minutos do PSTN**.
    
> [!NOTE]
> Dependendo da assinatura do Office 365, que você tem, você não poderá ver todos os mesmos detalhes mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar o Skype para relatório de minuto pools corporativos PSTN

Você pode obter um modo de exibição em Skype do usuário para pools de negócios minutos examinando cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
## 

![Relatório de pools Skype minuto PSTN de negócios](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão dos pools minutos por licença (recurso) e o local de uso. 
*    **O recurso** é o plano de serviço/licença usado para a chamada. Os planos de serviço/licença, que talvez você veja neste relatório incluem:
     * MCOPSTN1 - domésticas chamar planejar (3000 minutos planos de 1200/US-minuto UE
     * MCOPSTN2 - doméstico & internacional chamar planejar a partir do qual você verá um pool doméstico (3000 minutos EUA/Canadá/PR, minuto de 1200 países europeu) e um pool internacional (600 minutos). Cobrir minuto é atingida sempre que o limite de bits OR-internacional doméstico for atingido dentro do mês do calendário. 
     * MCOPSTN5 - domésticas chamar Plan (plano de chamada de 120 minutos)
     * MCOPSTN6 - domésticas chamar Plan (plano de chamada 240 minutos)
     * MCOMEETADD - serviços de audioconferência
*    **Descrição do recurso** é uma descrição do tipo de licença utilizado para a chamada.
*    **País minuto Pool** é o local de uso de licença do (s) que compartilham o pool de minuto. 
*    **Minutos usado** é o número de minutos usados por mês.
*    **Total de minutos** é o número total de minutos disponíveis para o mês. 
*    **% Usada** é a porcentagem de minutos usados para o mês. 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 3](../images/sfbcallout3.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.   <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se houver menos do que 2.000 usuários, você pode classificar e filtrar dentro da tabela no relatório em si. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype para relatório de atividade de negócios](activity-report.md) Você pode ver quanto os usuários estão usando-a-ponto, organizada e participado em sessões de conferência.
    
- [Skype para o relatório de uso do dispositivo de negócios](device-usage-report.md) Você pode para ver os dispositivos, incluindo os sistemas operacionais baseados no Windows e dispositivos móveis que têm o Skype para o aplicativo de negócios instalados e usá-lo para mensagens Instantâneas e reuniões.
    
- [Skype para relatório de atividade do organizador de conferência de negócios](conference-organizer-activity-report.md) Você pode ver quanto os usuários são organizem conferências que utilizam a mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativo, Web, /dial check-out de terceiros - 3rd e /dial check-out - Microsoft.
    
- [Skype para relatório de atividade de participante de conferência de negócios](conference-participant-activity-report.md) Você pode ver quantos compartilhamento de aplicativos de mensagens Instantâneas, áudio/vídeo, webconferências e conferências de áudio de discagem estão sendo participou.
    
- [Skype para relatório de atividade ponto a ponto de negócios](peer-to-peer-activity-report.md) Você pode ver quanto os usuários estão usando mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype para usuários comerciais bloqueados relatório](users-blocked-report.md) Você pode ver os usuários em sua organização que foram bloqueados façam chamadas PSTN.

- [Skype para relatório de detalhes de sessão de negócios](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada do usuário individual.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
