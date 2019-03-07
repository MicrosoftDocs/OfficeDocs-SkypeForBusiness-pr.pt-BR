---
title: Definir os números de telefone incluídos em convites no Microsoft Teams
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
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas para criar um número de telefone padrão para os chamadores ingressar em uma reunião do Microsoft Teams. '
ms.openlocfilehash: 3e6aae2c01962a4cd3c704cded1e284dc2975d28
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464240"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="e4f3d-103">Definir os números de telefone incluídos em convites no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4f3d-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="e4f3d-104">Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar reuniões Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="e4f3d-105">Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="e4f3d-106">Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4f3d-107">Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="e4f3d-108">Atribuição inicial dos números de telefone que estão incluídos na reunião convida para novos usuários</span><span class="sxs-lookup"><span data-stu-id="e4f3d-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="e4f3d-109">Os números de telefone que serão incluídos na reunião convidam de usuários habilitados para conferência de áudio são definidas pelas configurações de padrão conferência telefone gratuitos número do usuário e o número de telefone de Chamada Tarifada de conferência padrão.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="e4f3d-110">Cada configuração especifica qual Chamada Tarifada e o número de chamada gratuito serão incluídas no convite da reunião de um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="e4f3d-111">Conforme observado anteriormente, cada convite de reunião contém o número de chamada um Tarifada, um número de chamada gratuito opcional e um link que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma reunião determinada.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="e4f3d-112">Para um novo usuário, os números de Chamada Tarifada conferência padrão é atribuído com base no país que está definido no Office 365 perfil do usuário quando o usuário está habilitado para o serviço de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="e4f3d-113">Se houver um número de Chamada Tarifada na ponte de conferência que coincida com o país do usuário, esse número será atribuído automaticamente como o número de Chamada Tarifada padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="e4f3d-114">Se não houver um, o número que é definido como o número de Chamada Tarifada do padrão de ponte de conferência será atribuído como o número de Chamada Tarifada padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="e4f3d-115">Depois que o usuário estiver habilitado para o serviço de conferência de áudio, a chamada Tarifada do padrão e números de telefone gratuitos do usuário podem ser alterados pelo administrador do locatário de seus valores iniciais a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="e4f3d-116">Definir ou alterar o número de telefone de conferência de áudio padrão para um usuário ou o organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="e4f3d-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="e4f3d-117">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="e4f3d-117">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e4f3d-118">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-118">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Mostra a seleção de usuários no Centro de administração do Microsoft Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. <span data-ttu-id="e4f3d-120">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-120">At the top of the page, click **Edit**.</span></span>

    ![Clique em Editar no Centro de administração do Microsoft Teams](media/teams-set-phone-numbers-on-invites-image2.png)

3. <span data-ttu-id="e4f3d-122">Ao lado de **Conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-122">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Clique em Editar ao lado de conferência de áudio](media/teams-set-phone-numbers-on-invites-image3.png)

4. <span data-ttu-id="e4f3d-124">Use os campos de **número de Chamada Tarifada** ou **número de chamada gratuito** para inserir os números para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-124">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e4f3d-125">Quando você altera as configurações de conferência de áudio de um usuário, recorrentes e futuras reuniões de Teams da Microsoft devem ser atualizados e enviados aos participantes.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-125">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="e4f3d-126">Você deseja usar o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e4f3d-126">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="e4f3d-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e4f3d-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e4f3d-130">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="e4f3d-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e4f3d-131">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4f3d-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e4f3d-132">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e4f3d-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="e4f3d-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e4f3d-133">Related topics</span></span>

[<span data-ttu-id="e4f3d-134">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="e4f3d-134">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
