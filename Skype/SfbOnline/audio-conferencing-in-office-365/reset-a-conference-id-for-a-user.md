---
title: Redefinir uma ID de conferência para um usuário no Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba as etapas para redefinir a ID da conferência de reunião do usuário no Skype for Business Online e obter links para ferramentas de atualização e migração de reuniões. '
ms.openlocfilehash: 424b0dfb24d6034af20c18a0172221a09bef5ecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114207"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Redefinir uma ID de conferência para um usuário no Skype for Business Online

> [!NOTE]
> Para obter informações sobre como redefinir a ID de conferência no Microsoft Teams, consulte [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Uma ID de conferência dinâmica é incluída na parte inferior dos convites de reunião, juntamente com os números de telefone discados que podem ser usados pelos chamadores para ligar para uma reunião. Quando o usuário discar o número de telefone, o atendedor automático da reunião solicitará que o chamador insira essa ID de conferência para que ele possa participar da reunião.
  
> [!NOTE]
> Se o provedor de conferência for a Microsoft, as IDs de conferência dos usuários serão definidas como Somente Dinâmica. Isso não pode ser alterado. As IDs de conferência são definidas automaticamente somente para usuários do Skype for Business habilitados para Audioconferência. 

## <a name="resetting-the-conference-id-for-a-user"></a>Redefinindo a ID da conferência para um usuário
   
1. No Centro de administração do **Skype for Business,** clique em Usuários de **Audioconferência,** selecione um usuário e, no painel Ação, em ID da Conferência, clique em  >   **Redefinir**. 
    
2. Na janela **Redefinir iD** da conferência? clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desligado.
    
> [!NOTE]
> Depois de redefinir a ID da conferência, um email com a nova ID de conferência será enviado ao usuário. Esse email será enviado para o endereço de email principal, em muitos casos, sua caixa de correio do Microsoft 365 ou office 365. O email contém a nova ID da conferência, os números de telefone de discagem padrão e as instruções para usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e números de telefone discados clicando em Enviar informações de conferência por **email** para o usuário no painel Ação. Isso não envia o PIN.
    
- Uma ID de conferência conterá 7 dígitos e você não poderá alterar seu tamanho no Centro de administração do Skype for Business ou usando Windows PowerShell.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- A ID da conferência de um usuário para audioconferência pode ser exibida na parte inferior do painel Ação em **Audioconferência** quando você seleciona o usuário na **página Usuários.**
    
- [!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. Os usuários podem usar a Ferramenta de Reunião do Skype for Business para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar a Ferramenta de Atualização de Reunião do Skype for Business, consulte:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, ferramenta de migração de reuniões (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, ferramenta de migração de reuniões (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin.md)