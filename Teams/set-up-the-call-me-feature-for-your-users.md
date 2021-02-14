---
title: Configurar o recurso Telefonar para Mim para os usuários
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o recurso Telefonar para mim no Teams para que os usuários possam ingressar na parte de áudio por telefone ao usar o computador para áudio.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821091"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="d4964-103">Configurar o recurso Telefonar para Mim para os usuários</span><span class="sxs-lookup"><span data-stu-id="d4964-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="d4964-104">No Microsoft Teams, o **recurso Telefonar para mim** oferece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="d4964-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="d4964-105">Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível.</span><span class="sxs-lookup"><span data-stu-id="d4964-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="d4964-106">Os usuários ficam com a parte de áudio da reunião por meio de seu celular ou telefone fixo e a parte de conteúdo da reunião, como quando outro participante da reunião compartilha sua tela ou reproduz um vídeo pelo &mdash; &mdash; computador.</span><span class="sxs-lookup"><span data-stu-id="d4964-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="d4964-107">Em períodos com quantidade elevada de reuniões (que estamos passando durante a epidemia de COVID-19), recomendamos que os usuários ingressem em reuniões clicando no botão <strong>Participar de reunião do Teams</strong> em vez de discarem usando os números de conferência PSTN ou usando o <strong>Ligar para mim em</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4964-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="d4964-108">Isso ajuda a garantir a qualidade do áudio durante os períodos em que grandes quantidades de reunião estão congestionando a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="d4964-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d4964-109">Durante a duração da epidemia de COVID-19, recomendamos que os usuários ingressem nas reuniões clicando no botão **Participar das reuniões do Teams** em vez de discarem usando os números de conferência PSTN ou usando o **Ligue para mim em**</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4964-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="d4964-110">Isso é principalmente devido ao congestionamento nas infraestruturas de telefonia dos países afetados por COVID-19.</span><span class="sxs-lookup"><span data-stu-id="d4964-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="d4964-111">Ao evitar chamadas PSTN, você provavelmente terá uma melhor qualidade de áudio.</span><span class="sxs-lookup"><span data-stu-id="d4964-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="d4964-112">A experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="d4964-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="d4964-113">Ingressar em uma reunião usando o telefone para áudio</span><span class="sxs-lookup"><span data-stu-id="d4964-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="d4964-114">Clique **em** Ingressar para ingressar  em uma reunião e, em seguida, clique em Áudio do telefone na tela Escolher suas configurações **de áudio e** vídeo.</span><span class="sxs-lookup"><span data-stu-id="d4964-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="d4964-115">A partir daqui, os usuários podem fazer a chamada de reunião e ingressar neles ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="d4964-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de tela da opção de áudio Telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="d4964-117">**Permitir a chamada de reunião do Teams**</span><span class="sxs-lookup"><span data-stu-id="d4964-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="d4964-118">Na tela **Usar telefone para áudio,** o usuário ins lista seu número de telefone e, em seguida, clica **em Telefonar para mim.**</span><span class="sxs-lookup"><span data-stu-id="d4964-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="d4964-119">A reunião chamará o usuário e o ingressará na reunião.</span><span class="sxs-lookup"><span data-stu-id="d4964-119">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de tela da opção Telefonar para mim na tela Usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="d4964-121">**Discar manualmente**</span><span class="sxs-lookup"><span data-stu-id="d4964-121">**Dial in manually**</span></span>

<span data-ttu-id="d4964-122">Outra maneira de ingressar é discar diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="d4964-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="d4964-123">Na tela Usar telefone para **áudio,** clique em Discar **manualmente** para obter uma lista de números de telefone a usar para discar para a reunião.</span><span class="sxs-lookup"><span data-stu-id="d4964-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de tela da opção Discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="d4964-125">Receber uma chamada de volta quando algo der errado com o áudio durante uma reunião</span><span class="sxs-lookup"><span data-stu-id="d4964-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="d4964-126">Se um usuário tiver problemas de áudio ao usar o computador durante uma reunião, o usuário poderá facilmente alternar para o uso do telefone para áudio.</span><span class="sxs-lookup"><span data-stu-id="d4964-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="d4964-127">O Teams detecta quando ocorre um problema de áudio ou dispositivo e redireciona o usuário para usar seu telefone exibindo uma opção **Telefonar para** mim de volta.</span><span class="sxs-lookup"><span data-stu-id="d4964-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="d4964-128">Veja um exemplo da mensagem e da opção Ligar para mim **de** volta que é exibida quando o Teams não detecta um microfone.</span><span class="sxs-lookup"><span data-stu-id="d4964-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de tela da opção Chamar-me de volta](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="d4964-130">O usuário clica em Telefonar para mim de **volta,** que exibe a **tela Usar telefone para** áudio.</span><span class="sxs-lookup"><span data-stu-id="d4964-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="d4964-131">A partir daqui, eles podem inserir o número de telefone e fazer a chamada de reunião do Teams e ingressar na reunião ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="d4964-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="d4964-132">Configurar o recurso Telefonar para mim</span><span class="sxs-lookup"><span data-stu-id="d4964-132">Set up the Call me feature</span></span>

<span data-ttu-id="d4964-133">Para habilitar o recurso Telefonar para mim para usuários em sua organização, o seguinte deve ser configurado:</span><span class="sxs-lookup"><span data-stu-id="d4964-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="d4964-134">A audioconferência está habilitada para usuários em sua organização que agendam reuniões (organizadores da reunião).</span><span class="sxs-lookup"><span data-stu-id="d4964-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="d4964-135">Para saber mais, confira [Configurar a Audioconferência](set-up-audio-conferencing-in-teams.md) para o Teams e gerenciar as configurações de [Audioconferência de](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)um usuário no Teams.</span><span class="sxs-lookup"><span data-stu-id="d4964-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="d4964-136">Os usuários podem discar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="d4964-136">Users can dial out from meetings.</span></span> <span data-ttu-id="d4964-137">Para saber mais, confira [Gerenciar as configurações de Audioconferência de um usuário no Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d4964-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="d4964-138">Se um usuário não tiver a discagem  de reuniões habilitada, a opção Telefonar para mim não estará disponível e o usuário não receberá uma chamada para ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="d4964-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="d4964-139">Em vez disso, o usuário vê  uma lista de números de telefone na tela Usar telefone para áudio que ele pode usar para discar manualmente para a reunião em seu telefone.</span><span class="sxs-lookup"><span data-stu-id="d4964-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
