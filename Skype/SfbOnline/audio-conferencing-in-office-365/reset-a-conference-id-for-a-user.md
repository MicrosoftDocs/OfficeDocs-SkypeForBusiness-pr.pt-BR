---
title: Redefinir um ID de conferência para um usuário no Skype Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba as etapas para redefinir um usuário da reunião ID de conferência no Skype para Business Online e get links para ferramentas de atualização e migração da reunião. '
ms.openlocfilehash: 748664ec8e6584adcbcb0630147f1bcd60be9482
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229267"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Redefinir um ID de conferência para um usuário no Skype Business Online

> [!NOTE]
> Para obter informações sobre como redefinir o ID de conferência no Microsoft Teams, consulte [Redefinir uma ID de conferência para um usuário em equipes da Microsoft](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Uma ID de conferência dinâmico é incluída na parte inferior da reunião convites, juntamente com os números de telefone de discagem que podem ser usados por chamadores para efetuar uma chamada para uma reunião. Quando o usuário disca o número de telefone, o atendedor automático para a reunião pedirá que o chamador para inserir esta ID de conferência, de forma que eles podem participar da reunião.
  
> [!NOTE]
> Se seu provedor de conferência for Microsoft, IDs de conferência dos usuários são definidos para somente dinâmico. Isso não pode ser alterado. IDs de conferência são definidas automaticamente somente para Skype para usuários de negócios habilitados para conferência de áudio. 

## <a name="resetting-the-conference-id-for-a-user"></a>Redefinindo o ID de conferência para um usuário
   
1. No **Skype para centro de administração de negócios**, clique em **conferência de áudio** > **usuários**, selecione um usuário e clique em **Redefinir**no painel de ação em **ID da conferência** .
    
2. No **Redefinir ID de conferência?** janela, clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.
    
> [!NOTE]
> [!OBSERVAçãO] Depois de redefinir a ID de conferência, um email com a nova ID de conferência será enviado para o usuário. Esse email será enviado para o endereço de email primário do usuário. Em muitos casos, para a caixa de correio do Office 365. O email contém a nova ID de conferência, o(s) número(s) de telefone padrão de discagem e as instruções de como usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência via email** para o usuário no painel de ações. Isso não envia o PIN.
    
- Uma ID de conferência conterá 7 dígitos, e você não poderá alterar seu tamanho no Skype para centro de administração de negócios ou usando o Windows PowerShell.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- O ID de conferência para um usuário para conferência de áudio pode ser exibido na parte inferior do painel de ação em **conferência de áudio** quando você seleciona o usuário na página **usuários** .
    
- [!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. Os usuários podem usar Skype para ferramenta de reunião de negócios para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, ferramenta de migração de reuniões (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, ferramenta de migração de reuniões (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin.md)
