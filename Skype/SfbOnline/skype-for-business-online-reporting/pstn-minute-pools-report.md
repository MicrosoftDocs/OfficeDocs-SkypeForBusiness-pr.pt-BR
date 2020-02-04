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
description: A nova área de relatórios do centro de administração do Skype for Business mostra a atividade de chamadas e conferência de áudio em sua organização. Ele permite que você faça uma busca detalhada nos relatórios para dar a você uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de grupos de minutos PSTN do Skype for Business para ver o número de minutos consumidos durante o mês atual em sua organização.
ms.openlocfilehash: 2777b4f32b99a086110b75ca527eda29b0842b6e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692426"
---
# <a name="pstn-minute-pools-report"></a>Relatório de pools de minutos PSTN

>[!NOTE]
>Este relatório só está disponível para visualizar clientes.

A nova área de **relatórios** do centro de administração do Skype for Business mostra a atividade de chamadas e conferência de áudio em sua organização. Ele permite que você faça uma busca detalhada nos relatórios para dar a você uma visão mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório de **grupos de minutos PSTN do Skype for Business** para ver o número de minutos consumidos durante o mês atual em sua organização.
  
Confira a [visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver mais relatórios disponíveis.
  
Esse relatório, juntamente com os outros relatórios do Skype for Business, fornece informações sobre atividades em toda a organização. Esses detalhes são muito úteis durante a investigação, o planejamento e a realização de outras decisões empresariais para a sua organização e para a configuração de [créditos de comunicações](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business ao fazer logon como administrador no centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Como acessar o relatório de grupos de minutos PSTN do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

- Vá para o centro de administração > **centros** > de administração o**Centro** > de administração do Skype for Business**relata** > **pools de minutos PSTN**.
    
> [!NOTE]
> Dependendo da assinatura do Office 365, talvez você não veja todos os mesmos detalhes mostrados aqui. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretar o relatório de grupos de minutos PSTN do Skype for Business

Você pode obter uma visão dos pools de minutos do Skype for Business do seu usuário examinando cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
## 

![Relatório de grupos de minutos PSTN do Skype for Business](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>A tabela mostra uma divisão de pools de minutos por licença (funcionalidade) e localização de uso. 
*    **Recurso** é o plano de licença/serviço usado para a chamada. Os planos de licença/serviço que você pode ver neste relatório incluem:
     * MCOPSTN1-plano de chamadas domésticas (3000-minuto-minutos/1200-minuto-planos da União Europeia
     * MCOPSTN2-um plano de chamadas internacionais & doméstico do qual você verá um pool de pessoas (3000-minutos para os EUA/Canadá/PR, países europeus de 1200 minutos) e um pool internacional (600-minutos). O limite de minutos é atingido sempre que a Cap doméstica ou internacional é atingida dentro do mês do calendário. 
     * MCOPSTN5-plano de chamadas domésticas (plano de chamadas de 120 minutos)
     * MCOPSTN6-plano de chamadas domésticas (plano de chamadas de 240 minutos)
     * MCOMEETADD-audioconferência
*    **Descrição da funcionalidade** é uma descrição do tipo de licença utilizado para a chamada.
*    O **pool de minutos do país** é o local de uso da licença do (s) usuário (s) que compartilham o pool de minutos. 
*    **Minutos usados** é o número de minutos usados a cada mês.
*    **Total de minutos** é o número total de minutos disponíveis para o mês. 
*    O **percentual usado** é a porcentagem de minutos usada para o mês. 
***
![Número 2](../images/sfbcallout2.png)<br/>Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. 
***
![Número 3](../images/sfbcallout3.png)<br/>Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.    <br/><br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividade do Skype for Business](activity-report.md) Você pode ver o quanto os usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados em Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens instantâneas e reuniões.
    
- [Relatório de atividade do organizador de conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver quanto seus usuários estão organizando conferências que usam mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, Web,/dial out-terceiro e/dial-Microsoft.
    
- [Relatório atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver quantas mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, conferências de áudio da Web e de discagem estão sendo participadas.
    
- [Relatório de atividade ponto a ponto do Skype for Business](peer-to-peer-activity-report.md) Você pode ver o quanto os usuários estão usando mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório de usuários bloqueados do Skype for Business](users-blocked-report.md) Você pode ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN.

- [Relatório de detalhes da sessão do Skype for Business](session-details-report.md) Você pode ver detalhes sobre as experiências de chamadas de um usuário individual.
    
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
