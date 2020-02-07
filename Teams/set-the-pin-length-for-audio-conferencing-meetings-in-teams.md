---
title: Definir o tamanho do PIN para reuniões de Audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: Aprenda os parâmetros de tamanho e requisitos de um PIN e veja como definir o tamanho das reuniões no Microsoft Teams.
ms.openlocfilehash: 2827845cb53aa822f09ebdd0948cc06e679e4c0a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838071"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="79eb2-103">Definir o tamanho do PIN para reuniões de Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79eb2-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="79eb2-104">Quando você estiver configurando a audioconferência para o Microsoft Teams, você receberá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="79eb2-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="79eb2-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="79eb2-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="79eb2-106">O número de telefone que você definir será incluído nos convites da reunião para o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79eb2-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="79eb2-107">A ponte de audioconferência atende uma chamada feita por uma pessoa que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="79eb2-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="79eb2-108">Ela atende o chamador com comandos de voz de um atendedor automático e, dependendo das suas configurações, pode reproduzir notificações e pedir para o chamador gravar o nome dele.</span><span class="sxs-lookup"><span data-stu-id="79eb2-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="79eb2-109">As **configurações de ponte da Microsoft** permitem que você altere as configurações de notificação da reunião e a experiência de participação da reunião, além de definir o tamanho dos PINs usados pelos organizadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="79eb2-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="79eb2-110">Os organizadores da reunião usam PINs para iniciar reuniões se não conseguem entrar usando o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79eb2-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="79eb2-111">Configurar o tamanho do PIN</span><span class="sxs-lookup"><span data-stu-id="79eb2-111">Setting the PIN length</span></span>

<span data-ttu-id="79eb2-112">![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="79eb2-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="79eb2-113">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="79eb2-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="79eb2-114">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="79eb2-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="79eb2-115">No painel **configurações de ponte** , em **comprimento do pino**, selecione o número de dígitos que você deseja para o PIN.</span><span class="sxs-lookup"><span data-stu-id="79eb2-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="79eb2-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79eb2-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="79eb2-p103">[!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="79eb2-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="79eb2-121">Quer saber mais sobre as configurações de PIN?</span><span class="sxs-lookup"><span data-stu-id="79eb2-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="79eb2-122">Os pinos podem ter de 4 a 12 dígitos; o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="79eb2-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="79eb2-123">Somente números são usados para criar PINs.</span><span class="sxs-lookup"><span data-stu-id="79eb2-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="79eb2-124">Letras e caracteres especiais não são usados.</span><span class="sxs-lookup"><span data-stu-id="79eb2-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="79eb2-125">Um PIN só é necessário para o organizador da reunião quando um usuário do Microsoft Teams ainda não iniciou a reunião.</span><span class="sxs-lookup"><span data-stu-id="79eb2-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="79eb2-126">Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.</span><span class="sxs-lookup"><span data-stu-id="79eb2-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="79eb2-p106">As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte.</span><span class="sxs-lookup"><span data-stu-id="79eb2-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="79eb2-129">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="79eb2-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="79eb2-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="79eb2-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="79eb2-133">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="79eb2-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="79eb2-134">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79eb2-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="79eb2-135">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="79eb2-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="79eb2-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="79eb2-136">Related topics</span></span>

[<span data-ttu-id="79eb2-137">Experimentar ou comprar audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="79eb2-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
