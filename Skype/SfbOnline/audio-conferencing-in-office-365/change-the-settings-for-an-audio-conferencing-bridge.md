---
title: "Alterar as configurações de uma ponte de conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that''s used to prompt callers and gather names and pins for meeting organizers when they''re not using Skype for Business clients. '
ms.openlocfilehash: 62307bf26458ae54134772a0d920bcc602265bdc
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="922da-103">Alterar as configurações de uma ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="922da-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="922da-104">Quando você estiver configurando a conferência de áudio no Office 365, você receberá os números de telefone para seus usuários a partir o que é acionado uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="922da-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="922da-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="922da-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="922da-106">Esses números de telefone são usados quando os chamadores discam para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="922da-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="922da-107">O número de telefone está incluído na parte inferior do Skype para o convite de reunião de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="922da-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="922da-108">A ponte de conferência atende uma chamada e solicita que o chamador com os prompts de voz usando um automático de reunião attendant e em seguida, dependendo das suas configurações, ele pode reproduzir notificações, será feita aos chamadores registrar seus nomes e controlar as configurações de PIN.</span><span class="sxs-lookup"><span data-stu-id="922da-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="922da-109">PINs são fornecidas aos organizadores de reuniões para permitir que eles para iniciar uma reunião quando forem não estiver usando um Skype para aplicativo de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="922da-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="922da-110">Um PIN só é necessário para o organizador da reunião quando um Skype para o usuário de aplicativo de negócios ou Microsoft Teams já não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="922da-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="922da-111">Se todos estiver discando para a reunião, o PIN é necessário para o organizador da reunião iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="922da-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="922da-112">Alterar as configurações de uma ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="922da-112">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="922da-113">**Configurar a experiência da reunião, quando os chamadores ingressem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="922da-113">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="922da-114">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="922da-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="922da-115">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="922da-115">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="922da-116">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="922da-116">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="922da-117">Na página **configurações de ponte da Microsoft** , em que a **experiência de participação da reunião**, selecione:</span><span class="sxs-lookup"><span data-stu-id="922da-117">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="922da-118">**Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="922da-118">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="922da-119">Se você desmarcar a caixa de seleção, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="922da-119">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="922da-120">Quando você seleciona **Ativar entrada de reunião e sair notificações para ser ativado**, você pode selecionar essas opções na lista **tipo de anúncio de entrada/saída** :</span><span class="sxs-lookup"><span data-stu-id="922da-120">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="922da-121">**Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando eles entrarem-lo.</span><span class="sxs-lookup"><span data-stu-id="922da-121">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="922da-122">**Toques** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles entrarem-lo.</span><span class="sxs-lookup"><span data-stu-id="922da-122">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="922da-123">[!OBSERVAçãO] O uso do **Tom** como tipo de comunicado está disponível para todos os clientes de visualização atualmente.</span><span class="sxs-lookup"><span data-stu-id="922da-123">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="922da-124">**Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="922da-124">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="922da-125">Se você desmarcar a caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="922da-125">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="922da-126">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="922da-126">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="922da-127">**Definir o tamanho PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="922da-127">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="922da-128">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="922da-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="922da-129">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="922da-129">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="922da-130">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="922da-130">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="922da-131">Na página **configurações de ponte da Microsoft** , em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="922da-131">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="922da-132">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="922da-132">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="922da-133">**Selecione se deseja enviar o email para seus usuários**</span><span class="sxs-lookup"><span data-stu-id="922da-133">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="922da-134">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="922da-134">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="922da-135">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="922da-135">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="922da-136">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="922da-136">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="922da-137">Na página **configurações de ponte da Microsoft** , marque ou desmarque **Enviar automaticamente os e-mails para os usuários se altera sua configuração de conferência de áudio**e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="922da-137">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="922da-138">Para obter mais informações, consulte [Emails enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="922da-138">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="922da-139">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="922da-139">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="922da-140">Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="922da-140">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="922da-p106">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, veja estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="922da-p106">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="922da-144">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="922da-144">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="922da-145">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="922da-145">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="922da-p107">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="922da-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="922da-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="922da-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="922da-149">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="922da-149">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="922da-150">Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="922da-150">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="922da-p108">[!OBSERVAçãO] O módulo do Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="922da-p108">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="922da-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="922da-153">Related topics</span></span>

[<span data-ttu-id="922da-154">Configurar a audioconferência</span><span class="sxs-lookup"><span data-stu-id="922da-154">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
