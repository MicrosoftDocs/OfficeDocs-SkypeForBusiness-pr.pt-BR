---
title: Ver uma lista de usuários habilitados para conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: 28fb899586c6a0904126249b769e6fb0004878ca
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing"></a>Ver uma lista de usuários habilitados para conferência de áudio

Depois que você habilitou Skype para usuários corporativos ou Teams da Microsoft na sua organização para conferência de áudio, você pode exibir a lista dos usuários que tiverem sido habilitados. Quando você examinar a lista, você verá também para cada usuário na lista o tipo de provedor de serviços de audioconferência que estão usando, o número de telefone de discagem padrão para o usuário, e se a sua organização não está habilitada para IDs de conferência dinâmico, as IDs de conferência estático para reuniões de conferência de áudio que eles organizam.
  
## <a name="viewing-a-list-of-users"></a>Exibir uma lista de usuários

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

- No painel de navegação esquerdo, clique em **usuários**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
    
- No painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Ao exibir a lista de usuários que estão habilitados, você pode selecione um usuário na lista e use o painel de ação para editar as configurações de serviços de audioconferência para esse usuário.
    
- Quando você seleciona um único usuário que está configurado para usar o Microsoft como um provedor de serviços de audioconferência, você pode exibir o número de telefone padrão e se a sua organização está habilitada para IDs de conferência dinâmico e você pode redefinir a ID de conferência para reuniões que o organizadas pelo usuário.
    
- Quando você seleciona um único usuário que está configurado para usar um provedor de serviços de audioconferência de terceiros, você pode exibir o nome do provedor de serviços de audioconferência, o número de telefone de Chamada Tarifada e o número de telefone gratuitos (se eles estão configurados).
    
- Você pode usar as opções de filtro para exibir os usuários com:
    
  - **Serviços de audioconferência em**
    
  - **Serviços de audioconferência desativado**
    
  - **Provedor de conferência - Microsoft**
    
  - **Provedor de conferência - outros**
    
- Você pode usar o botão de pesquisa para procurar um usuário individual na lista
    
- Você pode selecionar mais de um usuário e fazer o seguinte:
    
  - Selecionar um número padrão diferente para esses usuários.
    
  - Desative o serviços de audioconferência para o usuário, alterando o provedor como **Nenhum**.
    
  - Alternar para a Microsoft como um provedor de serviços de audioconferência se o usuário tiver sido atribuído uma licença de **Serviços de audioconferência** .
    
  - Permitir/proibir que usuários anônimos ativem as reuniões por telefone dos usuários selecionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
