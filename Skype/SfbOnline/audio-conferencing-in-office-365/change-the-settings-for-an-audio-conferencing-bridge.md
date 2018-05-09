---
title: Alterar as configurações de uma ponte de conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas que necessárias para alterar configurações para uma ponte de conferência que é usado para solicitar que os chamadores e coletar nomes e pins para organizadores de reunião, quando eles não estão usando Skype para aplicativos de negócios ou Teams da Microsoft. '
ms.openlocfilehash: c58c1b3031da9e9ebe8408568bed0fd4b8c9ae9b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="6d48a-103">Alterar as configurações de uma ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="6d48a-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="6d48a-104">Quando você estiver configurando a conferência de áudio no Office 365, você receberá os números de telefone para seus usuários a partir o que é acionado uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="6d48a-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="6d48a-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="6d48a-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="6d48a-106">Esses números de telefone são usados quando os chamadores discam para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="6d48a-107">O número de telefone está incluído na parte inferior do Skype para o convite de reunião de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d48a-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="6d48a-108">A ponte de conferência atende uma chamada e solicita que o chamador com os prompts de voz usando um automático de reunião attendant e em seguida, dependendo das suas configurações, ele pode reproduzir notificações, será feita aos chamadores registrar seus nomes e controlar as configurações de PIN.</span><span class="sxs-lookup"><span data-stu-id="6d48a-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="6d48a-109">PINs são fornecidas aos organizadores de reuniões para permitir que eles para iniciar uma reunião quando forem não estiver usando um Skype para aplicativo de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d48a-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="6d48a-110">Um PIN só é necessário para o organizador da reunião quando um Skype para o usuário de aplicativo de negócios ou Microsoft Teams já não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="6d48a-111">Se todos estiver discando para a reunião, o PIN é necessário para o organizador da reunião iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngimagesteams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) <span data-ttu-id="6d48a-113">Usando equipes da Microsoft e Skype para Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="6d48a-113">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="6d48a-114">No painel de navegação esquerdo, vá para **reuniões** > **pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="6d48a-115">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="6d48a-116">No painel de **configurações de ponte** , selecione:</span><span class="sxs-lookup"><span data-stu-id="6d48a-116">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="6d48a-117">**Entrada de reunião e sair notificações** Se você desativar esse recurso, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="6d48a-118">Quando você ativa **as notificações de entrada e saída de reunião**, você pode selecionar estas opções:</span><span class="sxs-lookup"><span data-stu-id="6d48a-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="6d48a-119">**Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando eles entrarem-lo.</span><span class="sxs-lookup"><span data-stu-id="6d48a-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="6d48a-120">**Toques** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles entrarem-lo.</span><span class="sxs-lookup"><span data-stu-id="6d48a-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="6d48a-121">**Chamadores Ask registrar seus nomes antes de ingressar na reunião** Se você desativar esse recurso, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="6d48a-122">Para definir o tamanho PIN para reuniões, selecione o número de dígitos que você deseja para o PIN na lista **tamanho PIN** .</span><span class="sxs-lookup"><span data-stu-id="6d48a-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="6d48a-123">Para especificar se deseja enviar email para seus usuários, habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se altera sua configuração de serviços de audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="6d48a-124">Para obter mais informações, consulte [Emails enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="6d48a-124">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="6d48a-125">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-125">Click **Apply**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png)  <span data-ttu-id="6d48a-127">Usar o Centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d48a-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="6d48a-128">**Configurar a experiência da reunião, quando os chamadores ingressem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="6d48a-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="6d48a-129">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="6d48a-130">Na página **configurações de ponte da Microsoft** , em que a **experiência de participação da reunião**, selecione:</span><span class="sxs-lookup"><span data-stu-id="6d48a-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="6d48a-131">**Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="6d48a-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="6d48a-132">Se você desmarcar a caixa de seleção, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="6d48a-133">Quando você seleciona **Ativar entrada de reunião e sair notificações para ser ativado**, você pode selecionar essas opções na lista **tipo de anúncio de entrada/saída** :</span><span class="sxs-lookup"><span data-stu-id="6d48a-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="6d48a-134">**Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando eles entrarem-lo.</span><span class="sxs-lookup"><span data-stu-id="6d48a-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="6d48a-135">**Toques** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles entrarem-lo.</span><span class="sxs-lookup"><span data-stu-id="6d48a-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
  - <span data-ttu-id="6d48a-136">**Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="6d48a-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="6d48a-137">Se você desmarcar a caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="6d48a-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="6d48a-138">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="6d48a-139">**Definir o tamanho PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="6d48a-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="6d48a-140">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="6d48a-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="6d48a-141">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="6d48a-142">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="6d48a-143">Na página **configurações de ponte da Microsoft** , em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6d48a-144">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="6d48a-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="6d48a-145">**Selecione se deseja enviar o email para seus usuários**</span><span class="sxs-lookup"><span data-stu-id="6d48a-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="6d48a-146">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="6d48a-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="6d48a-147">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="6d48a-148">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="6d48a-149">Na página **configurações de ponte da Microsoft** , marque ou desmarque **Enviar automaticamente os e-mails para os usuários se altera suas informações de discagem**e, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d48a-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="6d48a-150">Para obter mais informações, consulte [Emails enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="6d48a-150">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6d48a-151">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6d48a-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6d48a-152">Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="6d48a-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="6d48a-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6d48a-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6d48a-156">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="6d48a-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6d48a-157">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d48a-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="6d48a-158">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="6d48a-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6d48a-159">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6d48a-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6d48a-160">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d48a-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6d48a-161">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d48a-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6d48a-162">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d48a-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="6d48a-p109">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="6d48a-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6d48a-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6d48a-165">Related topics</span></span>

[<span data-ttu-id="6d48a-166">Configurar a audioconferência</span><span class="sxs-lookup"><span data-stu-id="6d48a-166">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
