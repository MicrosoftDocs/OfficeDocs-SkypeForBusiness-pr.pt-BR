---
title: Definir o tamanho PIN para reuniões de conferência de áudio no Microsoft Teams
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Saiba os parâmetros para o comprimento e os requisitos de PIN e veja como definir o tamanho para reuniões no Microsoft Teams.
ms.openlocfilehash: 3c4b0d40e78cda844a443c4ca1d4fc7927dfeed3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867079"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="ee597-103">Definir o tamanho PIN para reuniões de conferência de áudio no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee597-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="ee597-104">Quando você estiver configurando a audioconferência for Microsoft Teams, você receberá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="ee597-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="ee597-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="ee597-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="ee597-106">O número de telefone que você definir será incluído em convites de reunião para o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ee597-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="ee597-107">A ponte de conferência de áudio atende uma chamada para pessoas que estão discando para uma reunião usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="ee597-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="ee597-108">Ela atende do chamador com prompts de voz de um atendedor automático e em seguida, dependendo de suas definições, pode reproduzir notificações e será feita aos chamadores a registrar seu nome.</span><span class="sxs-lookup"><span data-stu-id="ee597-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="ee597-109">**Configurações de ponte da Microsoft** permitem que você alterar as configurações de notificações de reunião e experiência de ingresso na reunião e definir o tamanho dos pinos que são usados pelo organizadores de reunião.</span><span class="sxs-lookup"><span data-stu-id="ee597-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="ee597-110">Organizadores de reunião usam PINs para iniciar reuniões, se eles não podem ingressar na reunião usando o app Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee597-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="ee597-111">Configurar o tamanho do PIN</span><span class="sxs-lookup"><span data-stu-id="ee597-111">Setting the PIN length</span></span>

1. <span data-ttu-id="ee597-112">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="ee597-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ee597-113">Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="ee597-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="ee597-114">No painel de **configurações de ponte** , em **tamanho do PIN**, selecione o número de dígitos que você deseja para o PIN.</span><span class="sxs-lookup"><span data-stu-id="ee597-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="ee597-115">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ee597-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ee597-p103">[!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="ee597-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="ee597-120">Quer saber mais sobre configurações de PIN?</span><span class="sxs-lookup"><span data-stu-id="ee597-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="ee597-121">PINs podem ter entre 4 para 12 dígitos; o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="ee597-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="ee597-122">Somente números são usados para criar PINs.</span><span class="sxs-lookup"><span data-stu-id="ee597-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="ee597-123">Letras e caracteres especiais não são usados.</span><span class="sxs-lookup"><span data-stu-id="ee597-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="ee597-124">Um PIN só é necessária para o organizador da reunião quando um usuário do Microsoft Teams já não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="ee597-124">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="ee597-125">Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.</span><span class="sxs-lookup"><span data-stu-id="ee597-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="ee597-p106">As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte.</span><span class="sxs-lookup"><span data-stu-id="ee597-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ee597-128">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ee597-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ee597-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ee597-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ee597-132">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="ee597-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ee597-133">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee597-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ee597-134">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ee597-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="ee597-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ee597-135">Related topics</span></span>

[<span data-ttu-id="ee597-136">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="ee597-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
