---
title: Enviar um e-mail para um usuário com suas informações de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envie aos sus usuários um e-mail com as informações da audioconferência no Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892088"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="7bc75-103">Enviar um e-mail para um usuário com suas informações de audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7bc75-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="7bc75-104">Às vezes, os usuários do Microsoft Teams podem precisar que você envie as informações da audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7bc75-104">Sometimes users may need you to send them their dial-in conferencing information.</span></span> <span data-ttu-id="7bc75-105">É possível fazer isso clicando em **Enviar informações de conferência por e-mail** nas propriedades de um usuário.</span><span class="sxs-lookup"><span data-stu-id="7bc75-105">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="7bc75-106">O e-mail enviado conterá todas as informações da audioconferência, incluindo:</span><span class="sxs-lookup"><span data-stu-id="7bc75-106">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="7bc75-107">O número de telefone ou de discagem da conferência para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7bc75-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="7bc75-108">O ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="7bc75-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="7bc75-109">Aqui está um exemplo do e-mail que é enviado:</span><span class="sxs-lookup"><span data-stu-id="7bc75-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![E-mail para conferência de discagem](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="7bc75-111">Enviar um e-mail com as informações da audioconferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="7bc75-111">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="7bc75-112">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7bc75-112">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7bc75-113">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7bc75-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="7bc75-114">Em **Audioconferência**, clique em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="7bc75-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="7bc75-115">O que mais preciso saber sobre esse e-mail?</span><span class="sxs-lookup"><span data-stu-id="7bc75-115">What else should you know about this email?</span></span>

- <span data-ttu-id="7bc75-116">Vários e-mails são enviados aos usuários da sua organização depois que são habilitados para a audioconferência:</span><span class="sxs-lookup"><span data-stu-id="7bc75-116">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="7bc75-117">Quando uma licença de **Audioconferência** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="7bc75-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="7bc75-118">Quando você redefine manualmente o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="7bc75-118">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="7bc75-119">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="7bc75-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="7bc75-120">quando uma licença de **Audioconferência** é removida deles.</span><span class="sxs-lookup"><span data-stu-id="7bc75-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="7bc75-121">Quando o provedor de audioconferência de um usuário é transferido da Microsoft para outro provedor ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="7bc75-121">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="7bc75-122">Quando o provedor de audioconferência de um usuário for transferido para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7bc75-122">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="7bc75-123">Por padrão, o remetente dos e-mails será do Office 365, mas é possível alterar o endereço de e-mail e o nome exibido usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7bc75-123">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="7bc75-124">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7bc75-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7bc75-125">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7bc75-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7bc75-p103">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7bc75-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7bc75-129">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="7bc75-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7bc75-130">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bc75-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7bc75-131">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7bc75-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="7bc75-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7bc75-132">Related topics</span></span>

[<span data-ttu-id="7bc75-133">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="7bc75-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
