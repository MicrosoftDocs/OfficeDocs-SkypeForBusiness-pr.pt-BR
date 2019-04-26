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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
ms.openlocfilehash: 33623e43ed6e7db6edd8af14e042ae798c9c8cd1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237484"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurar políticas de clientes para sua organização

A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
  
Configurações de diretiva do cliente podem ser configuradas no momento em que uma diretiva é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma diretiva existente.
  
## <a name="set-your-client-policies"></a>Definir suas políticas de cliente

> [!NOTE]
> Para todas as configurações de diretiva de cliente no Skype para Business Online, você deve usar o Windows PowerShell e você **não pode usar** o **Skype para centro de administração de negócios**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para o Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Desabilitar notificações de presença e emoticons e evitam que o salvamento de mensagens instantâneas

- Para criar uma nova política para essas configurações, execute:
    
> 
>   ```
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  Consulte obter mais informações sobre o cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Para conceder a nova política que você criou para todos os usuários em sua organização, execute:
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  Consulte obter mais informações sobre o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações para seus usuários.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas

- Para criar uma nova política para essas configurações, execute:
    
> 
>   ```
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  Consulte obter mais informações sobre o cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Para conceder a nova política que você criou para todos os usuários em sua organização, execute:
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  Consulte obter mais informações sobre o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações para seus usuários.
  
### <a name="prevent-showing-recent-contacts"></a>Impedir a exibição de contatos recentes

- Para criar uma nova política para essas configurações, execute:
  > 
  > ```
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  Consulte obter mais informações sobre o cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Para conceder a nova política que você criou para Mármore Amos, execute:
  > 
  > ```
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  Consulte obter mais informações sobre o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
  Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações para seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Transferências de arquivos ponto a ponto de bloqueio](block-point-to-point-file-transfers.md)

[Configurar políticas de conferência na sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
