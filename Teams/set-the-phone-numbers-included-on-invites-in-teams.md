---
title: Definir os números de telefone incluídos em convites
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
- seo-marvel-mar2020
description: Siga estas etapas para criar um número de telefone padrão para os chamadores ingressarem em uma Microsoft Teams reunião.
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117169"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="940fe-103">Definir os números de telefone incluídos em convites no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="940fe-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="940fe-104">A audioconferência em Microsoft 365 e Office 365 permite que os usuários em sua organização criem reuniões Microsoft Teams e, em seguida, permitir que os usuários discem para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="940fe-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="940fe-105">Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização.</span><span class="sxs-lookup"><span data-stu-id="940fe-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="940fe-106">Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.</span><span class="sxs-lookup"><span data-stu-id="940fe-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="940fe-107">Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="940fe-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="940fe-108">Atribuição inicial de números de telefone incluídos nos convites da reunião para novos usuários</span><span class="sxs-lookup"><span data-stu-id="940fe-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="940fe-109">Os números de telefone que são incluídos nos convites de reunião de usuários habilitados para Audioconferência são definidos pelo número de telefone de chamada de chamada de conferência padrão e pelas configurações padrão do número de telefone gratuito de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="940fe-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="940fe-110">Cada configuração especifica qual número gratuito e de tarifa será incluído no convite de reunião de um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="940fe-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="940fe-111">Conforme mencionado acima, cada convite de reunião contém um número de chamada gratuita, um número gratuito opcional e um link que abre a lista completa de todos os números de telefone discados que podem ser usados para ingressar em uma determinada reunião.</span><span class="sxs-lookup"><span data-stu-id="940fe-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="940fe-112">Para um novo usuário, os números de tarifa de conferência padrão são atribuídos com base no Local de Uso definido no centro de administração Microsoft 365 do usuário quando o usuário está habilitado para o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="940fe-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="940fe-113">Se houver um número de pedágio na ponte de conferência que corresponde ao país do usuário, esse número será atribuído automaticamente como o número de tarifa padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="940fe-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="940fe-114">Se não houver um, o número definido como o número de tarifa padrão da ponte de conferência será atribuído como o número de tarifa padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="940fe-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="940fe-115">Depois que o usuário for habilitado para o serviço de Audioconferência, os números de telefone de chamada gratuita e de chamada padrão do usuário poderão ser alterados pelo administrador de locatários de seus valores iniciais a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="940fe-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="940fe-116">Definir ou alterar o número de telefone de audioconferência padrão para um organizador de reunião ou usuário</span><span class="sxs-lookup"><span data-stu-id="940fe-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="940fe-117">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="940fe-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="940fe-118">Você deve ser um administrador de serviço do Teams para fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="940fe-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="940fe-119">Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.</span><span class="sxs-lookup"><span data-stu-id="940fe-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="940fe-120">Faça logoff no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="940fe-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="940fe-121">Na navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="940fe-121">In the left navigation, click **Users**.</span></span>

    ![Mostra a seleção de usuários no Microsoft Teams de administração](media/Admin-users.png)

3. <span data-ttu-id="940fe-123">Clique no nome do usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="940fe-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="940fe-124">Ao lado **de Audioconferência,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="940fe-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Clique em Editar ao lado de Audioconferência](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="940fe-126">Use os **campos Número de Telefone** ou Número **gratuito** para inserir os números do usuário.</span><span class="sxs-lookup"><span data-stu-id="940fe-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="940fe-127">Quando você altera as configurações de audioconferência de um usuário, reuniões Microsoft Teams reuniões recorrentes e futuras devem ser atualizadas e enviadas aos participantes.</span><span class="sxs-lookup"><span data-stu-id="940fe-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="940fe-128">Deseja usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="940fe-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="940fe-129">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="940fe-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="940fe-130">Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="940fe-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="940fe-131">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="940fe-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="940fe-132">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="940fe-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="940fe-133">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="940fe-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="940fe-134">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="940fe-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="940fe-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="940fe-135">Related topics</span></span>

[<span data-ttu-id="940fe-136">Experimente ou compre Audioconferência em Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="940fe-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="940fe-137">Alterar os números de telefone em sua ponte de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="940fe-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)