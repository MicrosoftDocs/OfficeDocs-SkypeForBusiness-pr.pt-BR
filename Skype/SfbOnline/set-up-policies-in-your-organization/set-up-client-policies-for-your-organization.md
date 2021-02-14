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
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814350"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurar políticas de clientes para sua organização

A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
  
As configurações de política de cliente podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-client-policies"></a>Definir suas políticas de cliente

> [!NOTE]
> Para todas as configurações de política de cliente no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.** 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
    1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
        
    2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
        
    3. Se você não tiver a versão 3.0 ou superior, será necessário baixar e instalar atualizações para o Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
        
    4. Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. 
    
    Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.
    
- **Iniciar uma sessão do Windows PowerShell**
    
    1. No **Menu Iniciar** > **Windows PowerShell**.
        
    2. Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:
    
    > [!NOTE]
    > No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
    >
    > Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Desabilitar emoticons e notificações de presença e impedir o salvar de IMs

- Para criar uma nova política para essas configurações, execute:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Veja mais no [cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Veja mais no [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Se você já criou uma política, pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos usuários.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas

- Para criar uma nova política para essas configurações, execute:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Veja mais no [cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Veja mais no [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Se você já criou uma política, pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos usuários.
  
### <a name="prevent-showing-recent-contacts"></a>Impedir a exibição de contatos recentes

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Veja mais no [cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Para conceder a nova política criada ao Amos Marble, execute:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Veja mais no [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
  Se você já criou uma política, pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
