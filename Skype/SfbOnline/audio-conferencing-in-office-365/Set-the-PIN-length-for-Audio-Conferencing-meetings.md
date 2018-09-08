---
title: Definir o tamanho PIN para reuniões de conferência de áudio no Skype para Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: c5add9cff2855fd969b76d96647f05e6e6dab290
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883591"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="95acb-103">Definir o tamanho PIN para reuniões de conferência de áudio no Skype para Business Online</span><span class="sxs-lookup"><span data-stu-id="95acb-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="95acb-104">Para obter informações sobre como definir o tamanho do PIN no Teams da Microsoft, consulte [definir o comprimento PIN para reuniões de conferência de áudio em equipes da Microsoft](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="95acb-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="95acb-105">Quando você estiver configurando serviços de audioconferência para Skype for Business, você receberá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="95acb-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="95acb-106">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="95acb-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="95acb-107">O número de telefone que você definir será incluído em convites de reunião para o Skype para o aplicativo de negócios.</span><span class="sxs-lookup"><span data-stu-id="95acb-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="95acb-108">A ponte de conferência de áudio atende uma chamada para pessoas que estão discando para uma reunião usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="95acb-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="95acb-109">Ela atende do chamador com prompts de voz de um atendedor automático e em seguida, dependendo de suas definições, pode reproduzir notificações e será feita aos chamadores a registrar seu nome.</span><span class="sxs-lookup"><span data-stu-id="95acb-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="95acb-110">**Configurações de ponte da Microsoft** permitem que você alterar as configurações de notificações de reunião e experiência de ingresso na reunião e definir o tamanho dos pinos que são usados pelo organizadores de reunião.</span><span class="sxs-lookup"><span data-stu-id="95acb-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="95acb-111">Organizadores de reunião usam PINs para iniciar reuniões, se eles não podem ingressar na reunião usando o Skype para o aplicativo de negócios.</span><span class="sxs-lookup"><span data-stu-id="95acb-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="95acb-112">Configurar o tamanho do PIN</span><span class="sxs-lookup"><span data-stu-id="95acb-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="95acb-113">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="95acb-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="95acb-114">Em **segurança** > **comprimento do PIN**, selecione o número de dígitos que você deseja para o PIN e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="95acb-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="95acb-p103">[!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="95acb-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="95acb-119">Quer saber mais sobre configurações de PIN?</span><span class="sxs-lookup"><span data-stu-id="95acb-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="95acb-120">PINs podem ter entre 4 para 12 dígitos; o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="95acb-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="95acb-121">Somente números são usados para criar PINs.</span><span class="sxs-lookup"><span data-stu-id="95acb-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="95acb-122">Letras e caracteres especiais não são usados.</span><span class="sxs-lookup"><span data-stu-id="95acb-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="95acb-123">Um PIN só é necessário para o organizador da reunião quando um Skype para o usuário de negócios já não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="95acb-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="95acb-124">Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.</span><span class="sxs-lookup"><span data-stu-id="95acb-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="95acb-p106">As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte.</span><span class="sxs-lookup"><span data-stu-id="95acb-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="95acb-127">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="95acb-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="95acb-128">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="95acb-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="95acb-129">Para definir o número de dígitos do PIN como 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="95acb-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="95acb-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="95acb-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="95acb-133">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="95acb-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="95acb-134">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95acb-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="95acb-135">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="95acb-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="95acb-136">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="95acb-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="95acb-137">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95acb-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="95acb-138">Como usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95acb-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="95acb-139">Como usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95acb-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="95acb-140">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95acb-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="95acb-p109">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="95acb-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="95acb-143">Ver também</span><span class="sxs-lookup"><span data-stu-id="95acb-143">See also</span></span>

[<span data-ttu-id="95acb-144">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="95acb-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
