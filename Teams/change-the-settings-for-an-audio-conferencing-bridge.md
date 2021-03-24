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
description: Altere as configurações da ponte de audioconferência, incluindo notificações de entrada e saída, reproduza nomes ou números de telefone, tons e chamadores de prompt para registrar seu nome.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102637"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="614cf-103">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="614cf-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="614cf-104">Ao configurar a Audioconferência no Microsoft 365 ou No Office 365, você receberá números de telefone para seus usuários do que é chamado de ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="614cf-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="614cf-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="614cf-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="614cf-106">Esses números de telefone são usados quando os chamadores discam para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="614cf-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="614cf-107">O número de telefone está incluído na parte inferior do convite de reunião do Skype for Business ou do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="614cf-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="614cf-108">A ponte de conferência atende a uma chamada e solicita ao chamador prompts de voz usando um atendedor automático de reunião e, dependendo das configurações, pode reproduzir notificações, pedir que os chamadores gravem seus nomes e controlem as configurações de PIN.</span><span class="sxs-lookup"><span data-stu-id="614cf-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="614cf-109">Os PINs são dados aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estão usando um aplicativo do Skype for Business ou do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="614cf-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="614cf-110">Um PIN só é necessário para o organizador da reunião quando um usuário de aplicativo do Skype for Business ou do Microsoft Teams ainda não iniciou a reunião.</span><span class="sxs-lookup"><span data-stu-id="614cf-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="614cf-111">Se todos estão discando para a reunião, o PIN será necessário para que o organizador da reunião inicie a reunião.</span><span class="sxs-lookup"><span data-stu-id="614cf-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="614cf-113">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="614cf-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="614cf-114">Na navegação à esquerda, vá para   >  **Pontes de Conferência de Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="614cf-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="614cf-115">Na parte superior da página **Pontes de** Conferência, clique em **Configurações de ponte.**</span><span class="sxs-lookup"><span data-stu-id="614cf-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="614cf-116">No painel **Configurações de** ponte, selecione:</span><span class="sxs-lookup"><span data-stu-id="614cf-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="614cf-117">**Notificações de entrada e saída de reunião** Se você desativar isso, os usuários que já ingressaram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="614cf-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="614cf-118">Ao ativar as notificações de entrada e saída **de reunião,** você pode selecionar estas opções:</span><span class="sxs-lookup"><span data-stu-id="614cf-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="614cf-119">**Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será tocado quando eles ingressarem.</span><span class="sxs-lookup"><span data-stu-id="614cf-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="614cf-120">**Tons** Quando os usuários discam para uma reunião, um tom de áudio será tocado quando eles ingressarem.</span><span class="sxs-lookup"><span data-stu-id="614cf-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="614cf-121">**Peça que os chamadores gravem seu nome antes de ingressar na reunião** Se você desativar isso, os chamadores não serão solicitados a gravar seus nomes antes de ingressarem em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="614cf-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="614cf-122">Para definir o tamanho do PIN para reuniões, selecione o número de dígitos que você deseja para o PIN na lista de comprimento **do PIN.**</span><span class="sxs-lookup"><span data-stu-id="614cf-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="614cf-123">Para especificar se deve enviar emails para seus usuários, habilitar ou desabilitar Enviar emails automaticamente para os usuários se a configuração **de audioconferência** mudar.</span><span class="sxs-lookup"><span data-stu-id="614cf-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="614cf-124">Consulte [Emails enviados automaticamente aos](emails-sent-to-users-when-their-settings-change-in-teams.md) usuários quando suas configurações de Audioconferência mudam no Microsoft Teams ou Emails enviados aos usuários quando suas configurações mudam no [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="614cf-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="614cf-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="614cf-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="614cf-126">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="614cf-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="614cf-127">Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)</span><span class="sxs-lookup"><span data-stu-id="614cf-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="614cf-128">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="614cf-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="614cf-129">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="614cf-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="614cf-130">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="614cf-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="614cf-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="614cf-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="614cf-132">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="614cf-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="614cf-133">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="614cf-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="614cf-134">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="614cf-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="614cf-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="614cf-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="614cf-136">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="614cf-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="614cf-137">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="614cf-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="614cf-p107">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="614cf-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="614cf-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="614cf-140">Related topics</span></span>

[<span data-ttu-id="614cf-141">Configurar Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="614cf-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="614cf-142">Configurar Audioconferência para Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="614cf-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)