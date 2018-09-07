---
title: Consulte uma lista de usuários que estão habilitados para Audioconferência no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como exibir uma lista de usuários em sua organização que estão habilitados para conferência discada a partir do centro de administração do Skype for Business. '
ms.openlocfilehash: 5cb792a3706c93c764f119075fca657b2179a383
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849849"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Consulte uma lista de usuários que estão habilitados para Audioconferência no Skype for Business Online

> [!NOTE]
> Para obter informações sobre os usuários habilitados no Microsoft Teams, confira [Ver uma lista de usuários que estão habilitados para Audioconferência no Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

Depois de habilitar o Skype for Business para os usuários da sua organização para Audioconferência, você pode ver a lista dos usuários que foram habilitados. Quando examinar a lista, você também verá, para cada usuário na lista, o tipo de provedor de serviços de teleconferência que ele usa, o número de telefone de discagem padrão, e se a sua organização não estiver habilitada para IDs dinâmicos de conferência, os IDs de conferência estáticos para reuniões de teleconferência que ele organiza.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Exibir uma lista de usuários

   
- No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**.

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Ao visualizar a lista de usuários habilitados, você pode selecionar um usuário da lista e usar o painel Ação para editar as configurações de Audioconferência dele.
    
- Quando você seleciona um único usuário que está configurado para usar a Microsoft como provedor de serviços de Audioconferência, você pode ver o número de telefone padrão de discagem e se a sua organização está habilitada para IDs dinâmicos de conferência e você pode redefinir os IDs de conferência para reuniões de teleconferência que ele organiza.
    
- Ao selecionar um único usuário configurado para usar um provedor de audiconferência de terceiros, você pode ver o nome do provedor e os números de telefone para chamadas tarifadas e gratuitas (se estiverem configurados).
    
- Você pode usar as opções de filtro para exibir os usuários com:
    
  - **Audioconferência ativada**
    
  - **Audioconferência desativada**
    
  - **Provedor de conferência - Microsoft**
    
  - **Provedor de conferência - outros**
    
- Você pode usar o botão de pesquisa para procurar um usuário individual na lista.
    
- Você pode selecionar mais de um usuário e fazer o seguinte:
    
  - Selecionar um número padrão diferente para esses usuários.
    
  - Desative o serviços de audioconferência para o usuário, alterando o provedor para **Nenhum**.
    
  - Alterne para a Microsoft como provedor de serviços de audioconferência se uma licença de **Audioconferência** tiver sido atribuída para o usuário.
    
  - Permitir/proibir que usuários anônimos ativem as reuniões por telefone dos usuários selecionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
