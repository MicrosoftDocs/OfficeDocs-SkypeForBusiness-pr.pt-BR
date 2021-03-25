---
title: Ativar ou desativar o relatório de comentários do cliente Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Você pode permitir que seus usuários do Skype for Business usem a ferramenta interna de comentários de aplicativos do Skype for Business para permitir que os usuários reportem problemas e forneçam comentários diretamente à Microsoft sobre sua experiência.
ms.openlocfilehash: 0c9045a899905e1e09176d086a70bc820267643d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106577"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="1a96f-103">Ativar ou desativar o relatório de comentários do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1a96f-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="1a96f-104">Você pode permitir que seus usuários do Skype for Business Online usem a ferramenta interna de comentários de aplicativos do Skype for Business para permitir que os usuários reportem problemas e forneçam comentários diretamente à Microsoft sobre sua experiência.</span><span class="sxs-lookup"><span data-stu-id="1a96f-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Fornecer ícone de feedback](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="1a96f-106">Usando essa ferramenta, um usuário pode copiar os logs do aplicativo em seu dispositivo para ajudar a Microsoft a investigar melhor e solucionar problemas que podem ter.</span><span class="sxs-lookup"><span data-stu-id="1a96f-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Relatar um problema usando o ícone Configurações](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="1a96f-108">Também é possível usar a configuração  _EnableOnlineFeedbackScreenshot_ para que os usuários possam incluir uma captura de tela em seu dispositivo como parte de seu comentário.</span><span class="sxs-lookup"><span data-stu-id="1a96f-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="1a96f-110">Os logs coletados pela ferramenta de comentários do aplicativo serão armazenados por até no máximo 90 dias nos Estados Unidos enquanto o problema está sendo investigado.</span><span class="sxs-lookup"><span data-stu-id="1a96f-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="1a96f-111">Por isso, não habilite essa ferramenta caso ela viole a política de proteção de dados da organização.</span><span class="sxs-lookup"><span data-stu-id="1a96f-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="1a96f-112">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a96f-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="1a96f-113">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="1a96f-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1a96f-114">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1a96f-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="1a96f-115">Instale o [módulo do Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="1a96f-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="1a96f-116">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="1a96f-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="1a96f-117">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1a96f-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="1a96f-118">Ativar o relatório de comentários do aplicativo cliente para todos os usuários de sua organização</span><span class="sxs-lookup"><span data-stu-id="1a96f-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="1a96f-119">Para habilitar relatórios de comentários para usuários em sua organização e permitir que eles enviem capturas de tela do dispositivo, execute:</span><span class="sxs-lookup"><span data-stu-id="1a96f-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1a96f-120">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1a96f-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="1a96f-121">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="1a96f-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1a96f-122">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="1a96f-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1a96f-123">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1a96f-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1a96f-124">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a96f-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1a96f-125">Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="1a96f-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="1a96f-126">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1a96f-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1a96f-127">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1a96f-127">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="1a96f-128">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1a96f-128">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="1a96f-129">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a96f-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1a96f-130">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a96f-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="1a96f-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1a96f-131">Related topics</span></span>
[<span data-ttu-id="1a96f-132">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a96f-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1a96f-133">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="1a96f-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
