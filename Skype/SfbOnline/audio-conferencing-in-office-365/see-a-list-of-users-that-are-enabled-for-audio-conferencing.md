---
title: Ver uma lista de usuários habilitados para conferências de áudio no Skype for Business Online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como exibir uma lista de usuários em sua organização que estão habilitados para conferência discada a partir do centro de administração do Skype for Business. '
ms.openlocfilehash: 9fb3a5ca8e21969ea5c09a5ac5c282dc4b816eff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298927"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Ver uma lista de usuários habilitados para conferências de áudio no Skype for Business Online

> [!NOTE]
> Para obter informações sobre os usuários habilitados no Microsoft Teams, confira [Ver uma lista de usuários que estão habilitados para Audioconferência no Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

After you have enabled Skype for Business users in your organization for Audio Conferencing, you can view the list of those users who have been enabled. When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Exibir uma lista de usuários

   
- No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**.

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Quando você vê a lista de usuários habilitados, pode selecionar um usuário na lista e usar o painel de ação para editar as configurações de videoconferência para esse usuário.
    
- Ao selecionar um único usuário configurado para usar a Microsoft como provedor de serviços de audioconferência, você pode visualizar o número de telefone padrão e se a sua organização está habilitada para IDs de conferência dinâmicas, e você pode redefinir a ID de conferência para reuniões que o o usuário organiza.
    
- Ao selecionar um único usuário configurado para usar um provedor de serviços de audioconferência de terceiros, você pode exibir o nome do provedor de serviços de audioconferência, o número de telefone de chamada tarifada e o número de telefone de chamada gratuita (se estiver configurado).
    
- Você pode usar as opções de filtro para exibir os usuários com:
    
  - **Audioconferência ativada**
    
  - **Audioconferência desativada**
    
  - **Provedor de conferência - Microsoft**
    
  - **Provedor de conferência - outros**
    
- Você pode usar o botão de pesquisa para procurar um usuário individual na lista
    
- Você pode selecionar mais de um usuário e fazer o seguinte:
    
  - Selecionar um número padrão diferente para esses usuários.
    
  - Desative a conferência de áudio para o usuário alterando o provedor para **nenhum**.
    
  - Alterne para a Microsoft como o provedor de serviços de audioconferência, se o usuário tiver recebido uma licença de **conferência de áudio** .
    
  - Permitir/proibir que usuários anônimos ativem as reuniões por telefone dos usuários selecionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
