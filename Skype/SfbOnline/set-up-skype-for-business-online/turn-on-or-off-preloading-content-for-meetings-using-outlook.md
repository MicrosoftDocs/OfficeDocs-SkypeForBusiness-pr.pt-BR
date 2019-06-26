---
title: Ativar ou desativar a permissão para que o conteúdo seja pré-carregado para reuniões usando o Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: a9f09212e4f883b0fd97f9d1cc596c3f63c13055
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221016"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="e7621-103">Ativar ou desativar a permissão para que o conteúdo seja pré-carregado para reuniões usando o Outlook</span><span class="sxs-lookup"><span data-stu-id="e7621-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="e7621-104">Os usuários podem pré-carregar conteúdo, arquivos ou anexos anexados a um convite de reunião do Outlook para uma reunião do Skype for Business Online, mas você pode ativá-lo ou desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="e7621-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="e7621-105">Ele está ativado por padrão para todas as organizações que usam o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="e7621-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="e7621-106">Veja como [Pré-carregar anexos de uma reunião do Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="e7621-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7621-107">Atualmente, não há cmdlets disponíveis no Skype for Business online para configurar ou exibir valores online do _MaxContentStorageMB_ e do _MaxUploadFileMB_.</span><span class="sxs-lookup"><span data-stu-id="e7621-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="e7621-108">Eles estão disponíveis apenas para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="e7621-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="e7621-109">É importante saber que o conteúdo não será carregado em uma reunião se o conteúdo anexado exceder o _MaxUploadFileSizeMB_ ou se o limite _MaxContentStorageMB_ for atingido.</span><span class="sxs-lookup"><span data-stu-id="e7621-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="e7621-110">Para começar</span><span class="sxs-lookup"><span data-stu-id="e7621-110">To get you started</span></span>

### 

 <span data-ttu-id="e7621-111">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="e7621-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="e7621-112">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e7621-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="e7621-113">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e7621-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="e7621-114">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7621-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="e7621-115">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="e7621-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="e7621-116">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="e7621-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="e7621-p104">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="e7621-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="e7621-120">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7621-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="e7621-121">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e7621-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="e7621-122">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e7621-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="e7621-123">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="e7621-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7621-124">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="e7621-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="e7621-125">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e7621-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="e7621-126">Ativar ou desativar o recurso</span><span class="sxs-lookup"><span data-stu-id="e7621-126">Turning it on or off</span></span>

<span data-ttu-id="e7621-127">A capacidade de pré-carregar conteúdo anexado a um convite de reunião do Outlook para reuniões do Skype for Business online está ativada por padrão, mas talvez seja necessário impedir que os usuários em sua organização precarreguem conteúdo em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="e7621-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7621-128">Esta configuração só pode ser ativada ou desativada para toda a sua organização; Você não pode ativá-lo ou desativá-lo para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="e7621-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="e7621-129">**Para desativá-la, abra o Windows PowerShell e faça o seguinte:**</span><span class="sxs-lookup"><span data-stu-id="e7621-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="e7621-130">**Se quiser ativá-la, abra o Windows PowerShell e faça o seguinte:**</span><span class="sxs-lookup"><span data-stu-id="e7621-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e7621-131">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e7621-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="e7621-132">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="e7621-132">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e7621-133">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="e7621-133">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e7621-134">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e7621-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e7621-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e7621-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e7621-136">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365</span><span class="sxs-lookup"><span data-stu-id="e7621-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="e7621-p106">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e7621-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e7621-139">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7621-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="e7621-140">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e7621-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e7621-141">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e7621-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="e7621-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7621-142">Related topics</span></span>
[<span data-ttu-id="e7621-143">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e7621-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e7621-144">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="e7621-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
