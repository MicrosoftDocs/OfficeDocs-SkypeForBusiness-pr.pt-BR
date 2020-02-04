---
title: Relatório de usuários bloqueados
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
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
description: 'Esse relatório, juntamente com outros relatórios do Skype for Business, fornece detalhes sobre atividades, incluindo o uso da PSTN em toda a sua organização. '
ms.openlocfilehash: d5fa69d096f5dc5f2af6f8b5a3c04a3155b8cd9e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692326"
---
# <a name="users-blocked-report"></a>Relatório de usuários bloqueados

O novo painel de **relatórios** do Skype for Business mostra a visão geral da atividade em todos os produtos do Skype for Business em sua organização. Ele permite que você faça drill-in para relatórios de nível de produto individuais para dar a você uma visão mais granular sobre as atividades de cada produto. Por exemplo, você pode usar o relatório de **usuários bloqueados do Skype for Business** para ver os usuários em sua organização que foram impedidos de fazer chamadas PSTN. Esse relatório, juntamente com outros relatórios do Skype for Business, fornece detalhes sobre atividades, incluindo o uso da PSTN em toda a sua organização.
  
 Confira a [visão geral de relatórios](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver mais relatórios disponíveis.
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business quando entra como administrador no centro de administração do Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Como acessar o relatório de usuários bloqueados do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

- Vá para o centro de administração > **centros** > de administração o**Centro** > de administração do Skype for Business**relata** > **aos usuários bloqueados**.
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpretar o relatório de usuários bloqueados do Skype for Business

Você pode obter uma visão de usuários bloqueados examinando cada uma das colunas exibidas.
  
Esta é a aparência do relatório. 
  
![Relatório de usuários bloqueados](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

A tabela mostra um detalhamento de todos os usuários que estão bloqueados para fazerem chamadas. Isso mostra todos os usuários que têm um sistema de telefonia ou conferência de áudio atribuído a eles. Você pode adicionar/remover colunas na tabela.
***
![Número 1](../images/sfbcallout1.png)
*   **ID de usuário** é a entrada do usuário.
*   **Número de telefone** é o número atribuído a um usuário. 
*   **Tempo de ação de bloqueio** é o tempo (UTC) pelo qual o usuário foi bloqueado para fazerem chamadas.
*   **Ação de bloqueio** é o tipo de ação que foi realizada para bloquear o usuário.
*   **Motivo da ação de bloqueio** é o motivo pelo qual o usuário foi bloqueado para fazerem chamadas.
***
![Número 2](../images/sfbcallout2.png)<br/>
Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas.
***
![Número 3](../images/sfbcallout3.png)<br/>
Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.   

Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Deseja ver outros relatórios do Skype for Business?

- [Relatório de atividade do Skype for Business](activity-report.md) Você pode ver o quanto os usuários estão usando ponto a ponto, organizado e participando de sessões de conferência.
    
- [Relatório de uso de dispositivos do Skype for Business](device-usage-report.md) Você pode ver os dispositivos, incluindo sistemas operacionais baseados em Windows e dispositivos móveis que têm o aplicativo Skype for Business instalado e o estão usando para mensagens instantâneas e reuniões.
    
- [Relatório de atividade do organizador de conferências do Skype for Business](conference-organizer-activity-report.md) Você pode ver o quanto os usuários estão organizando conferências que usam mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, Web, dial-in/out-terceiro e discagem/saída-Microsoft.
    
- [Relatório atividade de participantes de conferências do Skype for Business](conference-participant-activity-report.md) Você pode ver a quantidade de mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos, conferência discada da Web e conferência que está sendo participada.
    
- [Relatório de atividade ponto a ponto do Skype for Business](peer-to-peer-activity-report.md) Você pode ver o quanto os usuários estão usando mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
    
- [Relatório de uso de PSTN do Skype for Business](pstn-usage-report.md) Você pode ver o número de minutos gastos em chamadas de entrada/saída e o custo dessas chamadas.

- [Relatório de grupos de minutos PSTN do Skype for Business](pstn-minute-pools-report.md) você pode ver o número de minutos consumidos durante o mês atual dentro de sua organização.

- [Relatório de detalhes da sessão do Skype for Business](session-details-report.md) Você pode ver detalhes sobre as experiências de chamadas de um usuário individual.
   
## <a name="related-topics"></a>Tópicos relacionados
[Relatórios de atividades no centro de administração](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 