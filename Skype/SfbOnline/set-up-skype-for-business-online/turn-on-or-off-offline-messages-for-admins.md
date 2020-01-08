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
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 3e083f7bf0d4f83ba5e904452721eaa92ed9e652
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962829"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Ativar ou desativar mensagens offline para administradores

Você pode enviar mensagens instantâneas do Skype for Business para seus contatos, mesmo que elas não estejam conectadas. Esse recurso permite que seus contatos saibam que você está tentando contatá-los. Você não precisa esperar até que alguém esteja online antes de enviar uma mensagem.

Para mensagens offline, é importante saber:

- Mensagens offline não serão arquivadas na caixa de correio do usuário.

- Mensagens offline serão enviadas para a caixa de correio do usuário e o usuário será notificado quando fizer logon no Skype for Business.

- Se o status do destinatário da mensagem estiver definido como não **incomodar** ou **apresentando**, ele receberá uma mensagem perdida que é enviada do cliente Skype for Business do destinatário.

Para obter mais informações, consulte [usar mensagens offline no Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Para começar

## #

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**

1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.

2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.

3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.

4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.

Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

## #

 **Iniciar uma sessão do Windows PowerShell**

1. No **Menu Iniciar** > **Windows PowerShell**.

2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:

    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Ativar ou desativar mensagens instantâneas offline

> [!NOTE]
> As mensagens offline **só** estão disponíveis na versão mais recente do cliente do Skype for Business clique para executar e não estão disponíveis quando um clique para executar o Skype for Business mais antigo é usado ou um arquivo *. msi foi usado para instalar o cliente Skype for Business.

Para habilitar ou desabilitar mensagens offline, envie mensagens offline para os usuários de sua organização __ , defina `True` opção enableimautoarchiving `False`como ou. Por padrão, isso é definido como `True`.

Para desativá-lo, use o cmdlet **Set-CsClientPolicy** e execute:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar ou desabilitar mensagens offline, envie mensagens offline para um usuário, __ defina opção enableimautoarchiving `True` como `False`ou. Por padrão, ele é definido como  `True`. Você pode usar uma política existente ou criar uma como o exemplo abaixo.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)


