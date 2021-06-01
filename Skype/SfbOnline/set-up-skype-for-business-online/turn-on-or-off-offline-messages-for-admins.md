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
ms.openlocfilehash: fc340cff109d33a3a5afeaf6b1b2b09ae7f6ba3b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239157"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="6d3d9-103">Ativar ou desativar mensagens offline para administradores</span><span class="sxs-lookup"><span data-stu-id="6d3d9-103">Turn on or off Offline Messages for admins</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="6d3d9-104">Você pode enviar Skype for Business IMs para seus contatos mesmo que eles não sejam assinados.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="6d3d9-105">Esse recurso permite que seus contatos saibam que você está tentando entrar em contato.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="6d3d9-106">Você não precisa esperar até que alguém fique online antes de enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="6d3d9-107">Para mensagens offline, é importante saber:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="6d3d9-108">Mensagens offline não serão arquivadas na caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="6d3d9-109">As mensagens offline serão enviadas para a caixa de correio do usuário e o usuário será notificado quando fizer logoff Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="6d3d9-110">Se o status do destinatário da mensagem estiver definido como **Não** Incomodar ou Apresentar **,** ele receberá uma mensagem perdida enviada do cliente Skype for Business destinatário.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="6d3d9-111">Para obter mais informações, [consulte Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="6d3d9-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="6d3d9-112">Para começar</span><span class="sxs-lookup"><span data-stu-id="6d3d9-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="6d3d9-113">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="6d3d9-114">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="6d3d9-115">Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="6d3d9-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="6d3d9-116">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="6d3d9-117">Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte [Conexão](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) para todos os serviços Office 365 em uma única janela Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="6d3d9-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="6d3d9-118">Ativar ou desativar mensagens instantâneas offline</span><span class="sxs-lookup"><span data-stu-id="6d3d9-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="6d3d9-119">As mensagens  offline só estão disponíveis na versão mais recente do cliente do Skype for Business Clique para Executar e não estão disponíveis quando um arquivo click-to-Run Skype for Business mais antigo é usado ou um arquivo \*.msi foi usado para instalar o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="6d3d9-120">Para habilitar ou desabilitar mensagens offline enviar mensagens offline para usuários em sua organização, de definir  _EnableIMAutoArchiving_ como `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="6d3d9-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="6d3d9-121">Por padrão, isso é definido como `True` .</span><span class="sxs-lookup"><span data-stu-id="6d3d9-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="6d3d9-122">Para desativá-lo, use o cmdlet **Set-CsClientPolicy** e execute:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="6d3d9-123">Para habilitar ou desabilitar mensagens offline enviar mensagens offline para um usuário, de definir  _EnableIMAutoArchiving_ como `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="6d3d9-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="6d3d9-124">Por padrão, ele é definido como  `True`.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="6d3d9-125">Você pode usar uma política existente ou criar uma como o exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6d3d9-126">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6d3d9-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6d3d9-127">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6d3d9-128">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6d3d9-129">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6d3d9-130">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d3d9-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="6d3d9-131">Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="6d3d9-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="6d3d9-132">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6d3d9-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6d3d9-133">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="6d3d9-134">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6d3d9-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="6d3d9-135">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d3d9-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="6d3d9-136">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d3d9-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="6d3d9-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6d3d9-137">Related topics</span></span>
[<span data-ttu-id="6d3d9-138">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d3d9-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6d3d9-139">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="6d3d9-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
