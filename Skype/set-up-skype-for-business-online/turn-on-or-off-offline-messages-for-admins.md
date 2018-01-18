---
title: Ativar ou desativar mensagens offline para administradores
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 2210f7f0acb2609b7557afe781bbb4349d76c73f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Ativar ou desativar mensagens offline para administradores

Você pode enviar Skype para negócios IMs aos seus contatos, mesmo se eles não estão conectados. Esse recurso permite que seus contatos saibam a você tentar acessar essa pessoa. Você não precisa aguardar até que alguém está online antes de enviá-los em uma mensagem. 
  
Para mensagens offline, é importante saber:
  
- Mensagens offline não serão arquivadas na caixa de correio do usuário.
    
- Mensagens offline serão enviadas à caixa de correio do usuário e o usuário será notificado quando eles fazem logon Skype para negócios.
    
- Se o status do remetente da mensagem é definido como **Não incomodar** ou **apresentando**, eles receberão uma mensagem perdida que é enviada do Skype do destinatário para o cliente de negócios.
    
Para obter mais informações, consulte [uso de mensagens offline do Skype para negócios](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).
  
## <a name="to-get-you-started"></a>Para começar

### 

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### 

 **Iniciar uma sessão do Windows PowerShell**
  
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="turning-on-or-off-offline-im"></a>Ativar ou desativar mensagens instantâneas offline

> [!NOTE]
> Mensagens offline são **apenas** disponíveis na versão mais recente do Skype Click-to-Run para o cliente de negócios e não estão disponíveis quando um Skype Click-to-Run mais antigo para a empresa é usada ou um arquivo MSI foi usado para instalar o Skype para o cliente de negócios.
  
Para habilitar ou desabilitar Offline mensagens enviar mensagens Offline para usuários em sua organização, defina _EnableIMAutoArchiving_ `True` ou `False`. Por padrão, isso é definido como `True`.
  
Para desativá-lo, use o cmdlet **Set-CsClientPolicy** e execute:
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar ou desabilitar o envio de mensagens Offline mensagens Offline para um usuário, defina _EnableIMAutoArchiving_ como `True` ou `False`. Por padrão, isso é definido como `True`. Você pode usar uma política existente ou criar um como o exemplo a seguir.
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
