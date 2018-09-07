---
title: Definir o telefone números incluídos no convidam em Microsfot equipes
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas para criar um número de telefone padrão para os chamadores ingressar em uma reunião de equipes Microsfot. '
ms.openlocfilehash: 54778aac19d090b4c609da1c5a63da3ba146ae44
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857443"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="23b85-103">Definir o telefone números incluídos no convidam no Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="23b85-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="23b85-104">Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar reuniões Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="23b85-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="23b85-105">No Office 365, você tem a opção de usar uma ponte de conferência de áudio da Microsoft ou uma ponte de conferência de áudio de terceiros que é hospedada por um provedor de serviços de audioconferência aprovada (ACP).</span><span class="sxs-lookup"><span data-stu-id="23b85-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="23b85-106">Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização.</span><span class="sxs-lookup"><span data-stu-id="23b85-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="23b85-107">Todos eles podem ser usados para ingressar as reuniões que criou um organizador de reunião, mas você pode selecionar quais serão incluídos em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="23b85-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23b85-108">Pode haver um máximo de chamada um Tarifada e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também existe um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="23b85-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="23b85-109">Definir ou alterar o número de telefone de conferência de áudio padrão para um usuário ou o organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="23b85-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="23b85-110">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="23b85-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Mostra a seleção de usuários no Microsoft Teams e Skype para centro de administração do Business](media/teamsselectusers.png)

2. <span data-ttu-id="23b85-112">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="23b85-112">At the top of the page, click **Edit**.</span></span>

    ![Clique em Editar no Microsoft equipes e Skype para Business Admin Center](media/teamsedituser.png)

3. <span data-ttu-id="23b85-114">Ao lado de **Conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="23b85-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Clique em Editar ao lado de conferência de áudio](media/teamseditaudioconf.png)

4. <span data-ttu-id="23b85-116">Use os campos de **número de Chamada Tarifada** ou **número de chamada gratuito** para inserir os números para o usuário.</span><span class="sxs-lookup"><span data-stu-id="23b85-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="23b85-117">Quando você altera as configurações de conferência de áudio de um usuário, recorrentes e futuras reuniões de Teams da Microsoft devem ser atualizados e enviados aos participantes.</span><span class="sxs-lookup"><span data-stu-id="23b85-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="23b85-118">Você deseja usar o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="23b85-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="23b85-p103">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="23b85-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="23b85-122">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="23b85-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="23b85-123">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23b85-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="23b85-124">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="23b85-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="23b85-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="23b85-125">Related topics</span></span>

[<span data-ttu-id="23b85-126">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="23b85-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
