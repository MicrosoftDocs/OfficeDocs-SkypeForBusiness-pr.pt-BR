---
title: Ativar ou desativar mensagens offline para administradores
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568751"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Ativar ou desativar mensagens offline para administradores

Você pode enviar mensagens de IMs do Skype for Business para seus contatos mesmo que eles não sejam assinados. Esse recurso permite que seus contatos saibam que você está tentando entrar em contato. Você não precisa esperar até que alguém fique online antes de enviar uma mensagem.

Para mensagens offline, é importante saber:

- Mensagens offline não serão arquivadas na caixa de correio do usuário.

- As mensagens offline serão enviadas para a caixa de correio do usuário e o usuário será notificado quando fizer logoff no Skype for Business.

- Se o status do destinatário da mensagem estiver definido como **Não** Incomodar ou Apresentar **,** ele receberá uma mensagem perdida enviada do cliente skype for Business do destinatário.

Para obter mais informações, [consulte Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Para começar

> [!NOTE]
> O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell. Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Conector do Skype for Business Online.
1. Instale o [módulo do Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Se você quiser mais informações sobre como começar Windows PowerShell, consulte Conectar-se a todos os serviços do [Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>Ativar ou desativar mensagens instantâneas offline

> [!NOTE]
> As mensagens  offline só estão disponíveis na versão mais recente do cliente Do Skype for Business clique para executar e não estão disponíveis quando um Skype for Business mais antigo é usado ou um arquivo *.msi foi usado para instalar o cliente skype for Business.

Para habilitar ou desabilitar mensagens offline enviar mensagens offline para usuários em sua organização, de definir  _EnableIMAutoArchiving_ como `True` ou `False` . Por padrão, isso é definido como `True` .

Para desativá-lo, use o cmdlet **Set-CsClientPolicy** e execute:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar ou desabilitar mensagens offline enviar mensagens offline para um usuário, de definir  _EnableIMAutoArchiving_ como `True` ou `False` . Por padrão, ele é definido como  `True`. Você pode usar uma política existente ou criar uma como o exemplo abaixo.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
