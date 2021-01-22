---
title: Alterar as configurações de uma ponte de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Altere as configurações de ponte de áudio audioconferência, incluindo notificações de entrada e de saída, executar nomes ou números de telefone, tons e solicitar aos chamadores gravarem o nome.
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918697"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="3f128-103">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="3f128-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="3f128-p101">Ao configurar a conferência de áudio no Microsoft 365 ou no Office 365, você receberá números de telefone para seus usuários a partir de uma ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do convite de reunião do Skype for Business ou do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f128-p101">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="3f128-p102">A ponte de conferência atende a uma chamada e solicita o chamador com prompts de voz usando um atendedor automático de reunião e, em seguida, dependendo das suas configurações, ele pode executar notificações, pedir para os chamadores gravarem o nome e controlar as configurações de pino. Os PINs são fornecidos aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estão usando um aplicativo Skype for Business ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f128-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="3f128-p103">Um PIN só é necessário para o organizador da reunião quando um usuário do Skype for Business ou do aplicativo do Microsoft Teams ainda não iniciou a reunião. Se todos estiverem discando para a reunião, o PIN será necessário para que o organizador da reunião inicie a reunião.</span><span class="sxs-lookup"><span data-stu-id="3f128-p103">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="3f128-113">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f128-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3f128-114">No painel de navegação esquerdo, vá para **reuniões**  >  **conferência pontes**.</span><span class="sxs-lookup"><span data-stu-id="3f128-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="3f128-115">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="3f128-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="3f128-116">No painel **configurações de ponte** , selecione:</span><span class="sxs-lookup"><span data-stu-id="3f128-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="3f128-117">**Notificações de entrada e saída de reunião** Se você desativar esta opção, os usuários que já participaram da reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="3f128-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="3f128-118">Ao ativar as **notificações de entrada e saída de reunião**, você pode selecionar estas opções:</span><span class="sxs-lookup"><span data-stu-id="3f128-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="3f128-119">**Nomes ou números de telefone** Quando os usuários discarem para uma reunião, o número de telefone deles será reproduzido quando ele ingressar.</span><span class="sxs-lookup"><span data-stu-id="3f128-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="3f128-120">**Toques** Quando os usuários discarem para uma reunião, um tom de áudio será reproduzido quando ele ingressar.</span><span class="sxs-lookup"><span data-stu-id="3f128-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="3f128-121">**Pedir para os chamadores gravarem o nome antes de ingressar na reunião** Se você desativar essa opção, os chamadores não serão solicitados a gravarem o nome antes de participarem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="3f128-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="3f128-122">Para definir o comprimento do PIN para reuniões, selecione o número de dígitos que você deseja para o pino na lista **comprimento do pino** .</span><span class="sxs-lookup"><span data-stu-id="3f128-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="3f128-123">Para especificar se deseja enviar emails para seus usuários, habilite ou desabilite **enviar emails automaticamente aos usuários se as alterações de configuração de audioconferência forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="3f128-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="3f128-124">Veja os [emails enviados automaticamente para os usuários quando as configurações de audioconferência forem alteradas no Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [emails enviados para os usuários quando as configurações forem alteradas no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3f128-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="3f128-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3f128-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3f128-126">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3f128-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3f128-127">Para poupar tempo ou automatizar esse processo, você pode usar o cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .</span><span class="sxs-lookup"><span data-stu-id="3f128-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="3f128-128">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="3f128-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3f128-129">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="3f128-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="3f128-130">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3f128-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3f128-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="3f128-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3f128-132">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f128-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3f128-133">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="3f128-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3f128-134">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3f128-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3f128-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f128-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3f128-136">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f128-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3f128-137">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f128-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3f128-p107">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="3f128-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3f128-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3f128-140">Related topics</span></span>

[<span data-ttu-id="3f128-141">Configurar Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f128-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="3f128-142">Configurar a conferência de áudio para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f128-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
