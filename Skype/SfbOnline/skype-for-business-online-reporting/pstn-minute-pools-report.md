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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: A nova Skype for Business de Relatórios do Centro de Administração mostra a atividade de chamada e audioconferência em sua organização. Ele permite que você faça uma análise de relatórios para dar uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório Skype for Business pools de minutos PSTN para ver o número de minutos consumidos durante o mês atual em sua organização.
ms.openlocfilehash: d3b75fd81628e4cfcd49b7b120ceed3e3f327bdc
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727990"
---
# <a name="pstn-minute-pools-report"></a>Relatório de pools de minutos PSTN

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>Este relatório só está disponível para visualizar clientes.

A nova Skype for Business de  Relatórios do Centro de Administração mostra a atividade de chamada e audioconferência em sua organização. Ele permite que você faça uma análise de relatórios para dar uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório Skype for Business pools de minutos **PSTN** para ver o número de minutos consumidos durante o mês atual em sua organização.
  
Confira a visão geral [relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para obter mais relatórios disponíveis.
  
Este relatório, juntamente com os outros relatórios Skype for Business, fornece detalhes sobre as atividades em toda a sua organização. Esses detalhes são muito úteis ao investigar, planejar e tomar outras decisões de negócios para sua organização e para configurar [créditos de comunicação](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios Skype for Business quando fizer logoff como administrador no Centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Como chegar ao relatório de pools de minutos Skype for Business PSTN

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**

- Vá para o centro de administração > **centros de** administração Skype for Business de administração Relatórios de pools de minutos  >    >    >  **PSTN**.
    
> [!NOTE]
> Dependendo da assinatura Microsoft 365 ou Office 365 você tem, talvez você não veja todos os mesmos detalhes mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar o Skype for Business de pools de minutos PSTN

Você pode obter uma exibição nos pools de Skype for Business de minuto do usuário, observando cada uma das colunas exibidas.
  
Esta é a aparência do relatório.

![Skype for Business Relatório de pools de minutos PSTN.](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1.](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão de pools de minutos por licença (funcionalidade) e local de uso. 
*    **A funcionalidade** é o plano de licença/serviço usado para a chamada. Os planos de licença/serviço que você pode ver neste relatório incluem:
     * MCOPSTN1 - Plano de Chamada Doméstica (planos da UE de 3.000 minutos dos EUA/1200 minutos
     * MCOPSTN2 - Plano de Chamada & Doméstico do qual você verá um pool doméstico (3.000 minutos EUA/Canadá/PR, países europeus de 1200 minutos) e um pool internacional (600 minutos). O limite de minutos é atingido sempre que o limite internacional -OR doméstico é atingido dentro do mês do calendário. 
     * MCOPSTN5 - Plano de Chamada Doméstica (plano de chamada de 120 minutos)
     * MCOPSTN6 - Plano de Chamada Doméstica (plano de chamada de 240 minutos)
     * MCOMEETADD - Audioconferência
*    **Descrição da funcionalidade** é uma descrição do tipo de licença utilizado para a chamada.
*    **Pool de Minutos** do País é o local de uso da licença dos usuários que compartilham o pool de minutos. 
*    **Minutos usados** é o número de minutos usados por mês.
*    **Total de** minutos é o número total de minutos disponíveis para o mês. 
*    **Percent Used** é a porcentagem de minutos usadas para o mês. 
***
![Número 2.](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 3.](../images/sfbcallout3.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.    <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Skype for Business relatório de atividades](activity-report.md) Você pode ver o quanto seus usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Skype for Business de uso do dispositivo](device-usage-report.md) Você pode ver os dispositivos, incluindo Windows operacionais baseados em Windows dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para IM e reuniões.
    
- [Skype for Business relatório de atividades do organizador da conferência](conference-organizer-activity-report.md) Você pode ver o quanto seus usuários estão organizando conferências que usam IM, áudio/vídeo, compartilhamento de aplicativos, Web, /dial out - terceiros e /dial-out - Microsoft.
    
- [Skype for Business relatório de atividade do participante da conferência](conference-participant-activity-report.md) Você pode ver quantos IM, áudio/vídeo, compartilhamento de aplicativos, Web e conferências de áudio discada estão sendo participadas.
    
- [Skype for Business relatório de atividades ponto a ponto](peer-to-peer-activity-report.md) Você pode ver o quanto seus usuários estão usando IM, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Skype for Business relatório bloqueado de usuários](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Skype for Business de detalhes da sessão](session-details-report.md) Você pode ver detalhes sobre as experiências de chamada de cada usuário.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
