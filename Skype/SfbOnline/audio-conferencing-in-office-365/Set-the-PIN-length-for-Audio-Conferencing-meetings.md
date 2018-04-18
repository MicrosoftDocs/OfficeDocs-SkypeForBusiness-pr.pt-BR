---
title: Definir o tamanho PIN para reuniões de conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: b20e782955b946f676cca5221f63b06cdd4d1be1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a><span data-ttu-id="b5f98-103">Definir o tamanho PIN para reuniões de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="b5f98-103">Set the PIN length for Audio Conferencing meetings</span></span>

<span data-ttu-id="b5f98-104">Quando você estiver configurando serviços de audioconferência para Skype para negócios ou Teams da Microsoft, você receberá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="b5f98-104">When you are setting up audio conferencing for Skype for Business or Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="b5f98-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="b5f98-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="b5f98-106">O número de telefone que você definir será incluído em convites de reunião para Skype para aplicativos de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5f98-106">The phone number you set will be included on the meeting invites for Skype for Business and Microsoft Teams apps.</span></span>
  
<span data-ttu-id="b5f98-107">A ponte de conferência de áudio atende uma chamada para pessoas que estão discando para uma reunião usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="b5f98-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="b5f98-108">Ela atende do chamador com prompts de voz de um atendedor automático e em seguida, dependendo de suas definições, pode reproduzir notificações e será feita aos chamadores a registrar seu nome.</span><span class="sxs-lookup"><span data-stu-id="b5f98-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="b5f98-109">**Configurações de ponte da Microsoft** permitem que você alterar as configurações de notificações de reunião e experiência de ingresso na reunião e definir o tamanho dos pinos que são usados pelo organizadores de reunião.</span><span class="sxs-lookup"><span data-stu-id="b5f98-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="b5f98-110">Organizadores de reunião usam PINs para iniciar reuniões, se eles não podem ingressar na reunião usando o Skype para aplicativos de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5f98-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business or Microsoft Teams app.</span></span>
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="b5f98-111">Configurar o tamanho do PIN</span><span class="sxs-lookup"><span data-stu-id="b5f98-111">Setting the PIN length</span></span>

<span data-ttu-id="b5f98-112">**Usando equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="b5f98-112">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="b5f98-113">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="b5f98-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="b5f98-114">Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="b5f98-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="b5f98-115">No painel de **configurações de ponte** , em **tamanho do PIN**, selecione o número de dígitos que você deseja para o PIN.</span><span class="sxs-lookup"><span data-stu-id="b5f98-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="b5f98-116">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b5f98-116">Click **Apply**.</span></span>

<span data-ttu-id="b5f98-117">**Usando o Skype para o Centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="b5f98-117">**Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="b5f98-118">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b5f98-118">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="b5f98-119">Em **segurança** > **comprimento do PIN**, selecione o número de dígitos que você deseja para o PIN e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b5f98-119">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5f98-p103">[!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="b5f98-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 
  
## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="b5f98-124">Quer saber mais sobre configurações de PIN?</span><span class="sxs-lookup"><span data-stu-id="b5f98-124">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="b5f98-125">PINs podem ter entre 4 para 12 dígitos; o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="b5f98-125">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="b5f98-126">Somente números são usados para criar PINs.</span><span class="sxs-lookup"><span data-stu-id="b5f98-126">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="b5f98-127">Letras e caracteres especiais não são usados.</span><span class="sxs-lookup"><span data-stu-id="b5f98-127">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="b5f98-128">Um PIN só é necessário para o organizador da reunião quando um Skype para usuário de negócios ou Microsoft Teams já não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="b5f98-128">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="b5f98-129">Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.</span><span class="sxs-lookup"><span data-stu-id="b5f98-129">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="b5f98-p106">As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte.</span><span class="sxs-lookup"><span data-stu-id="b5f98-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b5f98-132">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b5f98-132">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b5f98-133">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="b5f98-133">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="b5f98-134">Para definir o número de dígitos do PIN como 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="b5f98-134">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="b5f98-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b5f98-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b5f98-138">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="b5f98-138">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b5f98-139">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5f98-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b5f98-140">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="b5f98-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="b5f98-141">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b5f98-141">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b5f98-142">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b5f98-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b5f98-143">Como usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b5f98-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="b5f98-144">Como usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b5f98-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b5f98-145">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b5f98-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b5f98-p109">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="b5f98-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5f98-148">Ver também</span><span class="sxs-lookup"><span data-stu-id="b5f98-148">See also</span></span>

[<span data-ttu-id="b5f98-149">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="b5f98-149">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
