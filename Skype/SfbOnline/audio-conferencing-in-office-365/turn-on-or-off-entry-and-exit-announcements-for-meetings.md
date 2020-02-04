---
title: Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Saiba como ativar e desativar anúncios de entrada ou saída em reuniões no Skype for Business Online usando o centro de administração do Skype for Business. '
ms.openlocfilehash: 6c0e54b149dc4b26e590e471876f33c49d8f07f3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680208"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online

> [!Note]
> Para obter informações sobre anúncios de entrada e saída no Microsoft Teams, consulte [Ativar ou desativar anúncios de entrada e saída em reuniões no Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting. 
  
The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security. A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app. You can, however, set it so that a PIN isn't required to start a meeting.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Definir as opções de participação da reunião
    
1. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.
    
2. Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**. This is selected by default. If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.
    
3. Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.
    
4. Marque ou desmarque **a opção pedir para os chamadores gravarem o nome antes de ingressar na reunião**.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
- No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configurações para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos tópicos a seguir: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
