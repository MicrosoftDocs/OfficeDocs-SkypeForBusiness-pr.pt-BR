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
ms.openlocfilehash: abaa8887dbf206e24d232f8614c585329e7a44f6
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221012"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="e2ad1-103">Ativar ou desativar mensagens offline para administradores</span><span class="sxs-lookup"><span data-stu-id="e2ad1-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="e2ad1-104">Você pode enviar mensagens instantâneas do Skype for Business para seus contatos, mesmo que elas não estejam conectadas.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="e2ad1-105">Esse recurso permite que seus contatos saibam que você está tentando entrar em contato.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="e2ad1-106">Você não precisa esperar até que alguém fique online antes de enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="e2ad1-107">Para mensagens offline, é importante saber:</span><span class="sxs-lookup"><span data-stu-id="e2ad1-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="e2ad1-108">Mensagens offline não serão arquivadas na caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="e2ad1-109">Mensagens offline serão enviadas para a caixa de correio do usuário e o usuário será notificado quando fizer logon no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="e2ad1-110">Se o status do destinatário da mensagem estiver definido como não **incomodar** ou **apresentando**, ele receberá uma mensagem perdida que é enviada do cliente Skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="e2ad1-111">Para obter mais informações, consulte [usar mensagens offline no Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="e2ad1-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="e2ad1-112">Para começar</span><span class="sxs-lookup"><span data-stu-id="e2ad1-112">To get you started</span></span>

## #

 <span data-ttu-id="e2ad1-113">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="e2ad1-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="e2ad1-114">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="e2ad1-115">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="e2ad1-116">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="e2ad1-117">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="e2ad1-118">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="e2ad1-p103">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="e2ad1-122">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="e2ad1-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="e2ad1-123">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e2ad1-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="e2ad1-124">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="e2ad1-125">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="e2ad1-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2ad1-126">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="e2ad1-127">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e2ad1-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="e2ad1-128">Ativar ou desativar mensagens instantâneas offline</span><span class="sxs-lookup"><span data-stu-id="e2ad1-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="e2ad1-129">As mensagens offline **só** estão disponíveis na versão mais recente do cliente do Skype for Business clique para executar e não estão disponíveis quando um clique para executar o Skype for Business mais antigo é usado ou um arquivo \*. msi foi usado para instalar o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="e2ad1-130">Para habilitar ou desabilitar mensagens offline, envie mensagens offline para os usuários de sua organização __ , defina `True` opção enableimautoarchiving `False`como ou.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="e2ad1-131">Por padrão, isso é definido como `True`.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="e2ad1-132">Para desativá-lo, use o cmdlet **Set-CsClientPolicy** e execute:</span><span class="sxs-lookup"><span data-stu-id="e2ad1-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="e2ad1-133">Para habilitar ou desabilitar mensagens offline, envie mensagens offline para um usuário, __ defina opção enableimautoarchiving `True` como `False`ou.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="e2ad1-134">Por padrão, ele é definido como  `True`.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="e2ad1-135">Você pode usar uma política existente ou criar uma como o exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-135">You can use an existing policy or create one like the example below.</span></span>


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e2ad1-136">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e2ad1-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="e2ad1-137">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e2ad1-138">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="e2ad1-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e2ad1-139">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e2ad1-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="e2ad1-140">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2ad1-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="e2ad1-141">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365</span><span class="sxs-lookup"><span data-stu-id="e2ad1-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="e2ad1-p107">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e2ad1-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="e2ad1-144">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2ad1-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="e2ad1-145">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2ad1-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="e2ad1-146">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2ad1-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="e2ad1-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2ad1-147">Related topics</span></span>
[<span data-ttu-id="e2ad1-148">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2ad1-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e2ad1-149">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="e2ad1-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


