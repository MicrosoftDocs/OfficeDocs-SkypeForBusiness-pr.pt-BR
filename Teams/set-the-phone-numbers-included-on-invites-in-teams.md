---
title: Definir os números de telefone incluídos em convites no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas para criar um número de telefone padrão para os chamadores participarem de uma reunião do Microsoft Teams. '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882956"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="addce-103">Definir os números de telefone incluídos em convites no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="addce-103">For information about meeting invite phone numbers in Microsoft Teams, see Set the phone numbers included on invites in Microsoft Teams.</span></span>

<span data-ttu-id="addce-104">A audioconferência do Office 365 permite que os usuários da sua organização criem reuniões do Microsoft Teams e permitem que os usuários disquem para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="addce-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="addce-105">No Office 365, você tem a opção de usar uma ponte de audioconferência da Microsoft ou uma ponte de audioconferência de terceiros hospedada por um provedor de serviços de audioconferência (ACP) aprovado.</span><span class="sxs-lookup"><span data-stu-id="addce-105">In Office 365, you have the option of using a Microsoft dial-in conferencing bridge or to use a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="addce-106">Uma ponte de conferência fornece um conjunto de números de telefone de discagem para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="addce-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="addce-107">Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.</span><span class="sxs-lookup"><span data-stu-id="addce-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="addce-108">Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="addce-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="addce-109">Definir ou alterar o número de telefone de audioconferência padrão para um usuário ou organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="addce-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="addce-110">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="addce-110">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

    ![Mostra a seleção de usuários no Centro de Administração do Microsoft Teams e do Skype for Business](media/teamsselectusers.png)

2. <span data-ttu-id="addce-112">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="addce-112">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

    ![Clique no Centro de Administração do Microsoft Teams e do Skype for Business](media/teamsedituser.png)

3. <span data-ttu-id="addce-114">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="addce-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Clique em Editar próximo a Audioconferência](media/teamseditaudioconf.png)

4. <span data-ttu-id="addce-116">Use os campos **Número tarifado** ou **Número gratuito** para inserir os números para o usuário.</span><span class="sxs-lookup"><span data-stu-id="addce-116">A third-party is the provider: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="addce-117">Ao alterar as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Microsoft Teams precisam ser atualizadas e enviadas aos participantes.</span><span class="sxs-lookup"><span data-stu-id="addce-117">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="addce-118">Deseja usar o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="addce-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="addce-p103">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="addce-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="addce-122">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="addce-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="addce-123">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="addce-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="addce-124">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="addce-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="addce-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="addce-125">Related topics</span></span>

[<span data-ttu-id="addce-126">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="addce-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
