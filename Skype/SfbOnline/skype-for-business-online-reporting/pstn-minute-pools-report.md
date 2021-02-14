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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: A nova área Relatórios do Centro de Administração do Skype for Business mostra a atividade de chamadas e audioconferências em sua organização. Ele permite detalhar relatórios para lhe dar informações mais granulares sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de pools de minutos PSTN do Skype for Business para ver o número de minutos consumidos durante o mês atual em sua organização.
ms.openlocfilehash: ac27e88b6e0f4945dde90f5e5f7bade31f20fe6a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776246"
---
# <a name="pstn-minute-pools-report"></a>Relatório de pools de minutos PSTN

>[!NOTE]
>Este relatório só está disponível para clientes de visualização.

A nova área Relatórios do Centro de Administração **do** Skype for Business mostra a atividade de chamadas e audioconferências em sua organização. Ele permite detalhar relatórios para lhe dar informações mais granulares sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de pools de minutos **PSTN** do Skype for Business para ver o número de minutos consumidos durante o mês atual em sua organização.
  
Confira a visão geral [de Relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obter mais relatórios disponíveis.
  
Este relatório, juntamente com os outros relatórios do Skype for Business, fornece detalhes sobre as atividades em toda a sua organização. Esses detalhes são muito úteis ao investigar, planejar e tomar outras decisões de negócios para sua organização e para configurar [Créditos de Comunicação](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Como acessar o relatório de pools de minutos PSTN do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

- Vá para o centro de administração > **administradores** do Centro de administração do Skype  >  **for Business** reportam pools de minutos  >    >  **PSTN.**
    
> [!NOTE]
> Dependendo da assinatura do Microsoft 365 ou do Office 365 que você tem, talvez você não veja todos os mesmos detalhes mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar o relatório de pools de minutos PSTN do Skype for Business

Você pode ver os pools de minutos do Skype for Business do usuário olhando para cada uma das colunas exibidas.
  
Esta é a aparência do relatório.
  
## 

![Relatório de pools de minutos PSTN do Skype for Business](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão dos pools de minutos por licença (recurso) e local de uso. 
*    **O recurso** é a licença/plano de serviço usado para a chamada. Os planos de licença/serviço que você pode ver neste relatório incluem:
     * MCOPSTN1 - Plano de Chamada Doméstica (planos da UE de 3.000 minutos para os EUA/1200 minutos
     * MCOPSTN2 - Plano de Chamada Internacional & doméstico do qual você verá um pool doméstico (3.000 minutos EUA/Canadá/PR, países europeus de 1200 minutos) e um pool internacional (600 minutos). O limite de minutos é atingido sempre que o limite doméstico -OU- internacional é atingido dentro do mês do calendário. 
     * MCOPSTN5 - Plano de Chamada Doméstica (plano de chamada de 120 minutos)
     * MCOPSTN6 - Plano de Chamada Doméstica (plano de chamada de 240 minutos)
     * MCOMEETADD - Audioconferência
*    **A Descrição do** Recurso é uma descrição do tipo de licença usada para a chamada.
*    **O Pool de Minutos** do País é o local de uso da licença dos usuários que compartilham o pool de minutos. 
*    **Minutos Usados** é o número de minutos usados a cada mês.
*    **Total de** Minutos é o número total de minutos disponíveis para o mês. 
*    **Porcentagem Usada** é a porcentagem de minutos usada para o mês. 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 3](../images/sfbcallout3.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.    <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividades do Skype for Business](activity-report.md) Você pode ver o quanto seus usuários estão usando ponto a ponto, organizaram e participaram de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados no Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens de mensagens e reuniões.
    
- Relatório de atividade do organizador de [conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam mensagens de iM, áudio/vídeo, compartilhamento de aplicativos, Web, /discagem – terceiros e /discagem – Microsoft.
    
- [Relatório de atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver em quantas conferências de áudio, áudio/ vídeo, mensagens de áudio, compartilhamento de aplicativos, Web e discagem estão participando.
    
- [Relatório de atividade ponto a ponto](peer-to-peer-activity-report.md) do Skype for Business Você pode ver o quanto seus usuários estão usando mensagens de texto, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório bloqueado de usuários do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Relatório de detalhes da sessão do Skype for Business](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada de um usuário individual.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
