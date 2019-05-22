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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas necessárias para alterar as configurações de uma ponte de conferência que é usada para solicitar chamadas e obter nomes e Pins para organizadores da reunião quando eles não estiverem usando o Skype for Business ou aplicativos do Microsoft Teams. '
ms.openlocfilehash: eaccf6b09499c819451aabd4c1785b326f98ac6d
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344865"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="026cb-103">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="026cb-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="026cb-104">Ao configurar a conferência de áudio no Office 365, você receberá números de telefone para seus usuários do que é chamado de ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="026cb-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="026cb-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="026cb-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="026cb-106">Esses números de telefone são usados quando os chamadores discam para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="026cb-107">O número de telefone está incluído na parte inferior do convite de reunião do Skype for Business ou do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="026cb-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="026cb-108">A ponte de conferência atende a uma chamada e solicita o chamador com prompts de voz usando um atendedor automático de reunião e, em seguida, dependendo das suas configurações, ele pode executar notificações, pedir para os chamadores gravarem o nome e controlar as configurações de pino.</span><span class="sxs-lookup"><span data-stu-id="026cb-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="026cb-109">Os PINs são fornecidos aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estão usando um aplicativo Skype for Business ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="026cb-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="026cb-110">Um PIN só é necessário para o organizador da reunião quando um usuário do Skype for Business ou do aplicativo do Microsoft Teams ainda não iniciou a reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="026cb-111">Se todos estiverem discando para a reunião, o PIN será necessário para que o organizador da reunião inicie a reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="026cb-113">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="026cb-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="026cb-114">No painel de navegação esquerdo, vá para **reuniões** > **conferência pontes**.</span><span class="sxs-lookup"><span data-stu-id="026cb-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="026cb-115">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="026cb-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="026cb-116">No painel **configurações de ponte** , selecione:</span><span class="sxs-lookup"><span data-stu-id="026cb-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="026cb-117">**Notificações de entrada e saída de reunião** Se você desativar esta opção, os usuários que já participaram da reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="026cb-118">Ao ativar as **notificações de entrada e saída de reunião**, você pode selecionar estas opções:</span><span class="sxs-lookup"><span data-stu-id="026cb-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="026cb-119">**Nomes ou números de telefone** Quando os usuários discarem para uma reunião, o número de telefone deles será reproduzido quando ele ingressar.</span><span class="sxs-lookup"><span data-stu-id="026cb-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="026cb-120">**Toques** Quando os usuários discarem para uma reunião, um tom de áudio será reproduzido quando ele ingressar.</span><span class="sxs-lookup"><span data-stu-id="026cb-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="026cb-121">**Pedir para os chamadores gravarem o nome antes de ingressar na reunião** Se você desativar essa opção, os chamadores não serão solicitados a gravarem o nome antes de participarem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="026cb-122">Para definir o comprimento do PIN para reuniões, selecione o número de dígitos que você deseja para o pino na lista **comprimento do pino** .</span><span class="sxs-lookup"><span data-stu-id="026cb-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="026cb-123">Para especificar se deseja enviar emails para seus usuários, habilite ou desabilite **enviar emails automaticamente aos usuários se as alterações de configuração de audioconferência forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="026cb-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="026cb-124">Veja os [emails enviados automaticamente para os usuários quando as configurações de audioconferência forem alteradas no Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou emails [enviados para os usuários quando as configurações forem alteradas no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="026cb-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="026cb-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="026cb-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![SFB-logo-30x30. png](media/sfb-logo-30x30.png)  <span data-ttu-id="026cb-127">Usar o Centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="026cb-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="026cb-128">**Configurar a experiência da reunião quando os chamadores entrarem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="026cb-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="026cb-129">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para configurações de ponte de **áudio** > da**Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="026cb-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="026cb-130">Na página **configurações da ponte da Microsoft** , em **experiência de ingresso na reunião**, selecione:</span><span class="sxs-lookup"><span data-stu-id="026cb-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="026cb-131">**Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="026cb-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="026cb-132">Se você desmarcar a caixa de seleção, os usuários que já ingressaram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="026cb-133">Quando você seleciona **a opção habilitar notificações de entrada e saída de reunião para ser ativada**, você pode selecionar essas opções na lista **tipo de anúncio de entrada/saída** :</span><span class="sxs-lookup"><span data-stu-id="026cb-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="026cb-134">**Nomes ou números de telefone** Quando os usuários discarem para uma reunião, o número de telefone deles será reproduzido quando ele ingressar.</span><span class="sxs-lookup"><span data-stu-id="026cb-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="026cb-135">**Toques** Quando os usuários discarem para uma reunião, um tom de áudio será reproduzido quando ele ingressar.</span><span class="sxs-lookup"><span data-stu-id="026cb-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="026cb-136">**Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="026cb-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="026cb-137">Se você desmarcar a caixa de seleção, os chamadores não serão solicitados a gravarem o nome antes de participarem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="026cb-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="026cb-138">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="026cb-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="026cb-139">**Definir o comprimento do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="026cb-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="026cb-140">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="026cb-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="026cb-141">Vá para o **Centro** > de administração do Microsoft 365**Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="026cb-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="026cb-142">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="026cb-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="026cb-143">Na página **configurações da ponte da Microsoft** , em **segurança**, insira o número de dígitos que você deseja para o pino na lista **comprimento do PIN** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="026cb-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="026cb-144">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="026cb-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="026cb-145">**Selecione se deseja enviar emails para seus usuários**</span><span class="sxs-lookup"><span data-stu-id="026cb-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="026cb-146">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="026cb-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="026cb-147">Vá para o **Centro** > de administração do Microsoft 365**Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="026cb-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="026cb-148">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="026cb-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="026cb-149">Na página **configurações da ponte da Microsoft** , marque ou desmarque **enviar emails automaticamente aos usuários se as informações de discagem forem alteradas**e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="026cb-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="026cb-150">Veja os [emails enviados automaticamente para os usuários quando as configurações de audioconferência forem alteradas no Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou emails [enviados para os usuários quando as configurações forem alteradas no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="026cb-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="026cb-151">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="026cb-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="026cb-152">Para poupar tempo ou automatizar esse processo, você pode usar o cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .</span><span class="sxs-lookup"><span data-stu-id="026cb-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="026cb-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="026cb-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="026cb-156">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="026cb-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="026cb-157">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="026cb-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="026cb-158">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="026cb-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="026cb-159">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="026cb-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="026cb-160">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="026cb-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="026cb-161">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="026cb-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="026cb-162">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="026cb-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="026cb-p109">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="026cb-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="026cb-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="026cb-165">Related topics</span></span>

[<span data-ttu-id="026cb-166">Configurar Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="026cb-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="026cb-167">Configurar a conferência de áudio para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="026cb-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
