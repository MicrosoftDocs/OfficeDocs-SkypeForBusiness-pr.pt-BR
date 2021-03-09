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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569223"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurar políticas de clientes para sua organização

A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
  
As configurações de política de cliente podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-client-policies"></a>Definir suas políticas de cliente

> [!NOTE]
> Para todas as configurações de política de cliente no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.** 
  
### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell. Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Conector do Skype for Business Online.
1. Instale o [módulo do Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Desabilitar emoticons e notificações de presença e impedir a economia de IMs

- Para criar uma nova política para essas configurações, execute:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Consulte mais no cmdlet [New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos seus usuários.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas

- Para criar uma nova política para essas configurações, execute:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Consulte mais no cmdlet [New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos seus usuários.
  
### <a name="prevent-showing-recent-contacts"></a>Impedir a exibição de contatos recentes

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Consulte mais no cmdlet [New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Para conceder a nova política criada para o Amos Marble, execute:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
