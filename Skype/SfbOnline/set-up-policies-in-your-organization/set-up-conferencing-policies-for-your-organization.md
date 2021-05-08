---
title: Configurar políticas de conferência para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
- Setup
description: 'Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.'
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240073"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Configurar políticas de conferência para sua organização

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.
  
É importante que você mantenha o controle das conferências e de suas configurações. Em alguns casos, pode haver preocupação em termos de segurança: por padrão, qualquer pessoa, incluindo usuários não autenticados, pode participar de reuniões e salvar quaisquer slides ou folhetos distribuídos durante aquelas reuniões. Além disso, podem ocorrer preocupações legais ocasionais. Por exemplo, por padrão, os participantes da reunião têm permissão para fazer anotações em conteúdo compartilhado; no entanto, essas anotações não são salvas quando a reunião é arquivada. Se sua organização precisar manter um registro de toda a comunicação eletrônica, talvez você queira desabilitar as anotações. 
  
No Skype for Business Online, as conferências são gerenciadas usando políticas de conferência. As políticas de conferência determinam os recursos e as capacidades que podem ser usados em uma conferência, incluindo tudo desde se a conferência pode ou não incluir áudio e vídeo IP até o número máximo de pessoas que podem participar de uma reunião. Essas políticas podem ser configuradas no escopo global ou no escopo por uso. Isso fornece aos administradores uma flexibilidade enorme no que diz respeito a decidir quais capacidades serão disponibilizadas para quais usuários.
  
As configurações de política podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsConferencingPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-conferencing-policies"></a>Definir suas políticas de conferência

> [!NOTE]
> Para todas as configurações de política de conferência no Skype for Business Online, você  deve usar o Windows PowerShell e não pode usar o centro de administração **Skype for Business.** 

### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

 > [!Note]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.
1. Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquear transferências de arquivo e compartilhamento de área de trabalho durante as reuniões

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   Consulte mais no cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   Consulte mais no cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar as configurações aos seus usuários.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquear o registro de conferências e impedir participantes de reuniões anônimas

- Para criar uma nova política para essas configurações, execute: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   Consulte mais no cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Para conceder a nova política criada para o Amos Marble, execute:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   Consulte mais no cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar as configurações aos seus usuários.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedir que participantes anônimos gravem reuniões e que usuários externos salvem o conteúdo da reunião

- Para criar uma nova política para essas configurações, execute:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   Consulte mais no cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

Consulte mais no cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar as configurações aos seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365 ou Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

  
