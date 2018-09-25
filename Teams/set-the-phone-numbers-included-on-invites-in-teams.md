---
title: Definir o telefone números incluídos no convidam no Teams da Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas para criar um número de telefone padrão para os chamadores ingressar em uma reunião do Microsoft Teams. '
ms.openlocfilehash: f62a6e63181c474d19f403d6c81f858177bd8cd0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016193"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="8f1b6-103">Definir os números de telefone incluídos em convites no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f1b6-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="8f1b6-104">Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar reuniões Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="8f1b6-105">No Office 365, você tem a opção de usar uma ponte de conferência de áudio da Microsoft ou uma ponte de conferência de áudio de terceiros que é hospedada por um provedor de serviços de audioconferência aprovada (ACP).</span><span class="sxs-lookup"><span data-stu-id="8f1b6-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="8f1b6-106">Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="8f1b6-107">Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f1b6-108">Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="8f1b6-109">Definir ou alterar o número de telefone de audioconferência padrão para um usuário ou organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="8f1b6-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="8f1b6-110">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Mostra a seleção de usuários no Centro de Administração do Microsoft Teams e do Skype for Business](media/teamsselectusers.png)

2. <span data-ttu-id="8f1b6-112">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-112">At the top of the page, click **Edit**.</span></span>

    ![Clique no Centro de Administração do Microsoft Teams e do Skype for Business](media/teamsedituser.png)

3. <span data-ttu-id="8f1b6-114">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Clique em Editar próximo a Audioconferência](media/teamseditaudioconf.png)

4. <span data-ttu-id="8f1b6-116">Use os campos **Número tarifado** ou **Número gratuito** para inserir os números para o usuário.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8f1b6-117">Ao alterar as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Microsoft Teams precisam ser atualizadas e enviadas aos participantes.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="8f1b6-118">Deseja usar o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8f1b6-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="8f1b6-p103">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8f1b6-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8f1b6-122">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="8f1b6-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8f1b6-123">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f1b6-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8f1b6-124">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8f1b6-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="8f1b6-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8f1b6-125">Related topics</span></span>

[<span data-ttu-id="8f1b6-126">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="8f1b6-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
