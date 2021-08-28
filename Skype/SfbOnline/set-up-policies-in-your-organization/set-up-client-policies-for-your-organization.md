---
title: Configurar políticas de clientes para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
ms.openlocfilehash: e5fe976e3adb566c469d2c58a5d2b6a976776ac3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619247"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurar políticas de clientes para sua organização

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
  
As configurações de política de cliente podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-client-policies"></a>Definir suas políticas de cliente

> [!NOTE]
> Para todas as configurações de política do cliente no Skype for Business Online,  você deve usar o Windows PowerShell e não pode usar o centro de administração Skype for Business **cliente.** 
  
### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
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
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Desabilitar emoticons e notificações de presença e impedir a economia de IMs

- Para criar uma nova política para essas configurações, execute:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Consulte mais no cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar as configurações aos seus usuários.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas

- Para criar uma nova política para essas configurações, execute:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Consulte mais no cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar as configurações aos seus usuários.
  
### <a name="prevent-showing-recent-contacts"></a>Impedir a exibição de contatos recentes

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Consulte mais no cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Para conceder a nova política criada para o Amos Marble, execute:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar as configurações aos seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365 ou Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
