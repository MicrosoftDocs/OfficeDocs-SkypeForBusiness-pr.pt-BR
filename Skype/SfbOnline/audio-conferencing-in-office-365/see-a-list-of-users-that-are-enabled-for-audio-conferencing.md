---
title: Consulte uma lista de usuários habilitados para Audioconferência no Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como exibir uma lista de usuários em sua organização que estão habilitados para conferência discada a partir do centro de administração do Skype for Business. '
ms.openlocfilehash: b1138d80798791a433956e7b53db2569e1667e3126a81c3744c85a9604475012
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327067"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Consulte uma lista de usuários habilitados para Audioconferência no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Para obter informações sobre os usuários habilitados no Microsoft Teams, confira [Ver uma lista de usuários que estão habilitados para Audioconferência no Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

Depois de habilitar Skype for Business usuários em sua organização para Audioconferência, você poderá exibir a lista dos usuários que foram habilitados. Ao olhar para a lista, você também verá para cada usuário na lista o tipo de provedor de audioconferência que ele está usando, o número de telefone de discagem padrão para o usuário e, se a organização não estiver habilitada para IDs de conferência dinâmica, as IDs de conferência estáticas para reuniões de audioconferência que eles organizam.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Exibir uma lista de usuários

   
- No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**.

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Ao exibir a lista de usuários habilitados, você pode selecionar um usuário na lista e usar o painel Ação para editar as configurações de audioconferência para esse usuário.
    
- Quando você seleciona um único usuário configurado para usar a Microsoft como provedor de audioconferência, você pode exibir o número de telefone padrão e se sua organização está habilitada para IDs de conferência dinâmicas e você pode redefinir a ID da conferência para reuniões que o usuário organiza.
    
- Quando você seleciona um único usuário configurado para usar um provedor de audioconferência de terceiros, você pode exibir o nome do provedor de audioconferência, o número de telefone de chamada telefônica e o número de telefone gratuito (se eles estão configurados).
    
- Você pode usar as opções de filtro para exibir os usuários com:
    
  - **Audioconferência ativada**
    
  - **Audioconferência desativada**
    
  - **Provedor de conferência - Microsoft**
    
  - **Provedor de conferência - outros**
    
- Você pode usar o botão de pesquisa para procurar um usuário individual na lista
    
- Você pode selecionar mais de um usuário e fazer o seguinte:
    
  - Selecionar um número padrão diferente para esses usuários.
    
  - Desativar a audioconferência para o usuário alterando o provedor para **Nenhum**.
    
  - Alternar para a Microsoft como provedor de audioconferência se o usuário tiver sido atribuído uma licença **de Audioconferência.**
    
  - Permitir/proibir que usuários anônimos ativem as reuniões por telefone dos usuários selecionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
