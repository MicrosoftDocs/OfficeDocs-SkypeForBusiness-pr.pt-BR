---
title: Configurar o recurso ligar para mim para seus usuários
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como configurar o recurso ligar para mim no Microsoft Teams para que os usuários possam ingressar na parte de áudio por telefone em cenários em que o uso do computador para áudio pode não ser possível.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432115"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="8b9fa-103">Configurar o recurso ligar para mim para seus usuários</span><span class="sxs-lookup"><span data-stu-id="8b9fa-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="8b9fa-104">No Microsoft Teams, o recurso **Call me** fornece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="8b9fa-105">Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="8b9fa-106">Os usuários obtêm a parte de áudio da reunião por meio de seu telefone celular ou linha terrestre e a parte&mdash;de conteúdo da reunião, quando outro participante da reunião compartilha sua&mdash;tela ou reproduz um vídeo por meio de seu computador.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="8b9fa-107">A experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="8b9fa-107">The user experience</span></span>

<span data-ttu-id="8b9fa-108">Clique \*\*\*\* em ingressar para ingressar em uma reunião e, em seguida, clique em **áudio do telefone** na tela **escolher suas configurações de áudio e vídeo** .</span><span class="sxs-lookup"><span data-stu-id="8b9fa-108">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="8b9fa-109">Aqui, os usuários podem ter a chamada de reunião e participar delas ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-109">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de tela da opção áudio do telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="8b9fa-111">**Permitir que a reunião do teams seja chamada**</span><span class="sxs-lookup"><span data-stu-id="8b9fa-111">**Let the Teams meeting call**</span></span>

<span data-ttu-id="8b9fa-112">Na tela **usar telefone para áudio** , o usuário insere o número de telefone e, em seguida, clica em **telefonar para mim**.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-112">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="8b9fa-113">A reunião chama o usuário e a une à reunião.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-113">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de tela da opção ligar para mim na tela usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="8b9fa-115">**Discar manualmente**</span><span class="sxs-lookup"><span data-stu-id="8b9fa-115">**Dial in manually**</span></span>

<span data-ttu-id="8b9fa-116">Outra maneira de ingressar é discar diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-116">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="8b9fa-117">Na tela **usar telefone para áudio** , clique em **discar manualmente** para obter uma lista de números de telefone a serem usados para discar para a reunião.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-117">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de tela da opção discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="8b9fa-119">Configurar o recurso ligar para mim</span><span class="sxs-lookup"><span data-stu-id="8b9fa-119">Set up the Call me feature</span></span>

<span data-ttu-id="8b9fa-120">Para habilitar o recurso ligar para mim para os usuários de sua organização, é necessário configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b9fa-120">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="8b9fa-121">A audioconferência está habilitada para os usuários de sua organização que agendam reuniões (organizadores da reunião).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-121">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="8b9fa-122">Para saber mais, consulte [Configurar a conferência de áudio para](set-up-audio-conferencing-in-teams.md) o Microsoft Teams e [gerenciar as configurações de audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8b9fa-122">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="8b9fa-123">Os usuários podem discar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-123">Users can dial out from meetings.</span></span> <span data-ttu-id="8b9fa-124">Para saber mais, consulte [gerenciar as configurações de audioconferência de áudio para um usuário no](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-124">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="8b9fa-125">Se um usuário não tiver discagem de reuniões habilitada, a opção **ligar para mim** não estará disponível e o usuário não receberá uma chamada para ingressar nela na reunião.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-125">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="8b9fa-126">Em vez disso, o usuário vê uma lista de números de telefone na tela **usar telefone para áudio** que pode ser usada para discar manualmente para a reunião em seu telefone.</span><span class="sxs-lookup"><span data-stu-id="8b9fa-126">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

