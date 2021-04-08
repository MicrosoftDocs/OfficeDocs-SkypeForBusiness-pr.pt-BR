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
description: Saiba como configurar o recurso Chamar-me no Teams para que os usuários possam ingressar na parte de áudio por telefone ao usar o computador para áudio, talvez não seja possível.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623124"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="bd57b-103">Configurar o recurso Telefonar para Mim para os usuários</span><span class="sxs-lookup"><span data-stu-id="bd57b-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="bd57b-104">No Microsoft Teams, o **recurso Chamar-me** oferece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="bd57b-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="bd57b-105">Isso pode ser útil em cenários ao usar um computador para áudio.</span><span class="sxs-lookup"><span data-stu-id="bd57b-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="bd57b-106">Os usuários obterão a parte de áudio da reunião por meio de seu telefone celular ou linha fixa e a parte de conteúdo da reunião, como quando outro participante da reunião compartilha sua tela ou reproduz um vídeo por meio de seu &mdash; &mdash; computador.</span><span class="sxs-lookup"><span data-stu-id="bd57b-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="bd57b-107">Em períodos com quantidade elevada de reuniões (que estamos passando durante a epidemia de COVID-19), recomendamos que os usuários ingressem em reuniões clicando no botão <strong>Participar de reunião do Teams</strong> em vez de discarem usando os números de conferência PSTN ou usando o <strong>Ligar para mim em</strong>.</span><span class="sxs-lookup"><span data-stu-id="bd57b-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="bd57b-108">Isso ajuda a garantir a qualidade do áudio durante os períodos em que grandes quantidades de reunião estão congestionando a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="bd57b-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="bd57b-109">A experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="bd57b-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="bd57b-110">Participar de uma reunião usando telefone para áudio</span><span class="sxs-lookup"><span data-stu-id="bd57b-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="bd57b-111">Clique **em Participar** para participar de uma reunião, em seguida, **telefone** áudio na tela Escolher **suas** opções de vídeo e áudio e clique em Ingressar **agora**.</span><span class="sxs-lookup"><span data-stu-id="bd57b-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="bd57b-112">A partir daqui, os usuários podem fazer a chamada de reunião e juná-los ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="bd57b-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de tela da opção de áudio do telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="bd57b-114">**Permitir a chamada de reunião do Teams**</span><span class="sxs-lookup"><span data-stu-id="bd57b-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="bd57b-115">Na tela **Usar telefone para áudio,** o usuário entra no número de telefone e clica em **Chamar-me**.</span><span class="sxs-lookup"><span data-stu-id="bd57b-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="bd57b-116">A reunião chama o usuário e os une à reunião.</span><span class="sxs-lookup"><span data-stu-id="bd57b-116">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de tela da opção Chamar-me na tela Usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="bd57b-118">**Discar manualmente**</span><span class="sxs-lookup"><span data-stu-id="bd57b-118">**Dial in manually**</span></span>

<span data-ttu-id="bd57b-119">Outra maneira de ingressar é discar diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="bd57b-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="bd57b-120">Na tela **Usar telefone para áudio,** clique em **Discar manualmente** para obter uma lista de números de telefone a usar para discar para a reunião.</span><span class="sxs-lookup"><span data-stu-id="bd57b-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de tela da opção Discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="bd57b-122">Receber uma chamada de volta quando algo der errado com o áudio durante uma reunião</span><span class="sxs-lookup"><span data-stu-id="bd57b-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="bd57b-123">Se um usuário tiver problemas de áudio ao usar o computador durante uma reunião, o usuário poderá facilmente alternar para usar seu telefone para áudio.</span><span class="sxs-lookup"><span data-stu-id="bd57b-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="bd57b-124">O Teams detecta quando ocorre um problema de áudio ou dispositivo e redireciona o usuário para usar seu telefone exibindo uma opção **Retornar** chamada.</span><span class="sxs-lookup"><span data-stu-id="bd57b-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="bd57b-125">Aqui está um exemplo da mensagem e da opção **Chamar-me** de volta que é exibida quando o Teams não detecta um microfone.</span><span class="sxs-lookup"><span data-stu-id="bd57b-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de tela da opção Chamar-me de volta](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="bd57b-127">O usuário clica em **Chamar-me de volta**, que traz a **tela Usar telefone para** áudio.</span><span class="sxs-lookup"><span data-stu-id="bd57b-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="bd57b-128">A partir daqui, eles podem inserir seu número de telefone e fazer a chamada de reunião do Teams e ingressá-los na reunião ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="bd57b-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="bd57b-129">Configurar o recurso Chamar-me</span><span class="sxs-lookup"><span data-stu-id="bd57b-129">Set up the Call me feature</span></span>

<span data-ttu-id="bd57b-130">Para habilitar o recurso Chamar-me para usuários em sua organização, o seguinte deve ser configurado:</span><span class="sxs-lookup"><span data-stu-id="bd57b-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="bd57b-131">A Audioconferência está habilitada para usuários em sua organização que agendam reuniões (organizadores de reuniões).</span><span class="sxs-lookup"><span data-stu-id="bd57b-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="bd57b-132">Para saber mais, confira [Configurar Audioconferência](set-up-audio-conferencing-in-teams.md) para o Teams e Gerenciar as configurações de [Audioconferência para](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)um usuário no Teams .</span><span class="sxs-lookup"><span data-stu-id="bd57b-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="bd57b-133">O organizador da reunião pode discar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="bd57b-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="bd57b-134">Para saber mais, confira Gerenciar as configurações de [Audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bd57b-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="bd57b-135">Se o organizador da reunião não tiver o discagem de reuniões  habilitada, a opção De áudio por telefone na tela Escolher suas opções de vídeo e áudio não estará disponível para ninguém, e outros usuários não poderão receber uma chamada para infilá-los na reunião. </span><span class="sxs-lookup"><span data-stu-id="bd57b-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="bd57b-136">Para usuários com discagem habilitada, depois de ingressar na reunião, eles podem ingressar em outras pessoas discando seu número no ícone **Mostrar participantes.**</span><span class="sxs-lookup"><span data-stu-id="bd57b-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
