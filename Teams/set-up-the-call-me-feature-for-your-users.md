---
title: Configurar o recurso Telefonar para Mim para os usuários
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o recurso ligar para mim no Microsoft Teams para que os usuários possam ingressar na parte de áudio por telefone quando o uso do computador para áudio pode não ser possível.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138011"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="804a3-103">Configurar o recurso Telefonar para Mim para os usuários</span><span class="sxs-lookup"><span data-stu-id="804a3-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="804a3-104">No Microsoft Teams, o recurso **Call me** fornece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="804a3-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="804a3-105">Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível.</span><span class="sxs-lookup"><span data-stu-id="804a3-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="804a3-106">Os usuários obtêm a parte de áudio da reunião por meio de seu telefone celular ou linha terrestre e a parte de conteúdo da reunião &mdash; , como quando outro participante da reunião compartilha sua tela ou reproduz um vídeo &mdash; por meio de seu computador.</span><span class="sxs-lookup"><span data-stu-id="804a3-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="804a3-107">Durante períodos de alto volume de reunião (que estamos enfrentando em conjunto com a COVID-19 epidemia), recomendamos que os usuários ingressem em reuniões clicando no botão <strong>ingressar em reuniões</strong> com o Microsoft Teams, em vez de discar usando os números de conferência PSTN ou usando ligar para <strong>mim</strong>.</span><span class="sxs-lookup"><span data-stu-id="804a3-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="804a3-108">Isso ajuda a garantir o áudio de qualidade durante o tempo em que o volume de reunião alta está causando congestionamento na rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="804a3-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="804a3-109">Durante a duração da epidemia de COVID-19, recomendamos que os usuários ingressem nas reuniões clicando no botão **Participar das reuniões do Teams** em vez de discarem usando os números de conferência PSTN ou usando o **Ligue para mim em**</strong>.</span><span class="sxs-lookup"><span data-stu-id="804a3-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="804a3-110">Isso é principalmente devido ao congestionamento nas infraestruturas de telefonia dos países afetados por COVID-19.</span><span class="sxs-lookup"><span data-stu-id="804a3-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="804a3-111">Ao evitar chamadas PSTN, você provavelmente terá uma melhor qualidade de áudio.</span><span class="sxs-lookup"><span data-stu-id="804a3-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="804a3-112">A experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="804a3-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="804a3-113">Ingressar em uma reunião usando o telefone para áudio</span><span class="sxs-lookup"><span data-stu-id="804a3-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="804a3-114">Clique em **ingressar** para ingressar em uma reunião e, em seguida, clique em **áudio do telefone** na tela **escolher suas configurações de áudio e vídeo** .</span><span class="sxs-lookup"><span data-stu-id="804a3-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="804a3-115">Aqui, os usuários podem ter a chamada de reunião e participar delas ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="804a3-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de tela da opção áudio do telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="804a3-117">**Permitir que a reunião do teams seja chamada**</span><span class="sxs-lookup"><span data-stu-id="804a3-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="804a3-118">Na tela **usar telefone para áudio** , o usuário insere o número de telefone e, em seguida, clica em **telefonar para mim**.</span><span class="sxs-lookup"><span data-stu-id="804a3-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="804a3-119">A reunião chama o usuário e a une à reunião.</span><span class="sxs-lookup"><span data-stu-id="804a3-119">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de tela da opção ligar para mim na tela usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="804a3-121">**Discar manualmente**</span><span class="sxs-lookup"><span data-stu-id="804a3-121">**Dial in manually**</span></span>

<span data-ttu-id="804a3-122">Outra maneira de ingressar é discar diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="804a3-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="804a3-123">Na tela **usar telefone para áudio** , clique em **discar manualmente** para obter uma lista de números de telefone a serem usados para discar para a reunião.</span><span class="sxs-lookup"><span data-stu-id="804a3-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de tela da opção discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="804a3-125">Fazer uma chamada de retorno quando algo der errado com o áudio durante uma reunião</span><span class="sxs-lookup"><span data-stu-id="804a3-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="804a3-126">Se um usuário enfrentar problemas de áudio ao usar o computador durante uma reunião, o usuário poderá facilmente alternar para usar o telefone de áudio.</span><span class="sxs-lookup"><span data-stu-id="804a3-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="804a3-127">O Microsoft Teams detecta quando um problema de áudio ou dispositivo ocorre e redireciona o usuário para usar o telefone ao exibir uma opção **ligar para mim** .</span><span class="sxs-lookup"><span data-stu-id="804a3-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="804a3-128">Veja um exemplo da mensagem e a opção **ligar para mim** que é exibida quando o Microsoft Teams não detecta um microfone.</span><span class="sxs-lookup"><span data-stu-id="804a3-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de tela da opção ligar para fazer chamadas](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="804a3-130">O usuário clica em **ligar para mim de volta**, que exibe a tela **usar telefone para áudio** .</span><span class="sxs-lookup"><span data-stu-id="804a3-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="804a3-131">A partir daqui, eles podem digitar seu número de telefone e fazer com que as equipes de reunião liguem e ingressem na reunião ou discarem manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="804a3-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="804a3-132">Configurar o recurso ligar para mim</span><span class="sxs-lookup"><span data-stu-id="804a3-132">Set up the Call me feature</span></span>

<span data-ttu-id="804a3-133">Para habilitar o recurso ligar para mim para os usuários de sua organização, é necessário configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="804a3-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="804a3-134">A audioconferência está habilitada para os usuários de sua organização que agendam reuniões (organizadores da reunião).</span><span class="sxs-lookup"><span data-stu-id="804a3-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="804a3-135">Para saber mais, consulte [Configurar a conferência de áudio para o Microsoft Teams](set-up-audio-conferencing-in-teams.md) e [gerenciar as configurações de audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="804a3-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="804a3-136">Os usuários podem discar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="804a3-136">Users can dial out from meetings.</span></span> <span data-ttu-id="804a3-137">Para saber mais, consulte [gerenciar as configurações de audioconferência de áudio para um usuário no Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="804a3-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="804a3-138">Se um usuário não tiver discagem de reuniões habilitada, a opção **ligar para mim** não estará disponível e o usuário não receberá uma chamada para ingressar nela na reunião.</span><span class="sxs-lookup"><span data-stu-id="804a3-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="804a3-139">Em vez disso, o usuário vê uma lista de números de telefone na tela **usar telefone para áudio** que pode ser usada para discar manualmente para a reunião em seu telefone.</span><span class="sxs-lookup"><span data-stu-id="804a3-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
