---
title: Configurar o recurso ligar para mim para seus usuários
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o recurso ligar para mim no Microsoft Teams para que os usuários possam ingressar na parte de áudio por telefone em cenários em que o uso do computador para áudio pode não ser possível.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54e9d90a3380358abd0c1e984b90834455eb44e2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243168"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="6603e-103">Configurar o recurso ligar para mim para seus usuários</span><span class="sxs-lookup"><span data-stu-id="6603e-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="6603e-104">No Microsoft Teams, o recurso **Call me** fornece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="6603e-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="6603e-105">Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível.</span><span class="sxs-lookup"><span data-stu-id="6603e-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="6603e-106">Os usuários obtêm a parte de áudio da reunião por meio de seu telefone celular ou linha terrestre e a parte&mdash;de conteúdo da reunião, quando outro participante da reunião compartilha sua&mdash;tela ou reproduz um vídeo por meio de seu computador.</span><span class="sxs-lookup"><span data-stu-id="6603e-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="6603e-107">A experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="6603e-107">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="6603e-108">Ingressar em uma reunião usando o telefone para áudio</span><span class="sxs-lookup"><span data-stu-id="6603e-108">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="6603e-109">Clique \*\*\*\* em ingressar para ingressar em uma reunião e, em seguida, clique em **áudio do telefone** na tela **escolher suas configurações de áudio e vídeo** .</span><span class="sxs-lookup"><span data-stu-id="6603e-109">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="6603e-110">Aqui, os usuários podem ter a chamada de reunião e participar delas ou discar manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="6603e-110">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Captura de tela da opção áudio do telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="6603e-112">**Permitir que a reunião do teams seja chamada**</span><span class="sxs-lookup"><span data-stu-id="6603e-112">**Let the Teams meeting call**</span></span>

<span data-ttu-id="6603e-113">Na tela **usar telefone para áudio** , o usuário insere o número de telefone e, em seguida, clica em **telefonar para mim**.</span><span class="sxs-lookup"><span data-stu-id="6603e-113">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="6603e-114">A reunião chama o usuário e a une à reunião.</span><span class="sxs-lookup"><span data-stu-id="6603e-114">The meeting calls the user and joins them to the meeting.</span></span>

![Captura de tela da opção ligar para mim na tela usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="6603e-116">**Discar manualmente**</span><span class="sxs-lookup"><span data-stu-id="6603e-116">**Dial in manually**</span></span>

<span data-ttu-id="6603e-117">Outra maneira de ingressar é discar diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="6603e-117">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="6603e-118">Na tela **usar telefone para áudio** , clique em **discar manualmente** para obter uma lista de números de telefone a serem usados para discar para a reunião.</span><span class="sxs-lookup"><span data-stu-id="6603e-118">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Captura de tela da opção discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="6603e-120">Fazer uma chamada de retorno quando algo der errado com o áudio durante uma reunião</span><span class="sxs-lookup"><span data-stu-id="6603e-120">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="6603e-121">Se um usuário enfrentar problemas de áudio ao usar o computador durante uma reunião, o usuário poderá facilmente alternar para usar o telefone de áudio.</span><span class="sxs-lookup"><span data-stu-id="6603e-121">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="6603e-122">O Microsoft Teams detecta quando um problema de áudio ou dispositivo ocorre e redireciona o usuário para usar o telefone ao exibir uma opção **ligar para mim** .</span><span class="sxs-lookup"><span data-stu-id="6603e-122">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="6603e-123">Veja um exemplo da mensagem e a opção **ligar para mim** que é exibida quando o Microsoft Teams não detecta um microfone.</span><span class="sxs-lookup"><span data-stu-id="6603e-123">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Captura de tela da opção ligar para fazer chamadas](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="6603e-125">O usuário clica em **ligar para mim de volta**, que exibe a tela **usar telefone para áudio** .</span><span class="sxs-lookup"><span data-stu-id="6603e-125">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="6603e-126">A partir daqui, eles podem digitar seu número de telefone e fazer com que as equipes de reunião liguem e ingressem na reunião ou discarem manualmente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="6603e-126">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="6603e-127">Configurar o recurso ligar para mim</span><span class="sxs-lookup"><span data-stu-id="6603e-127">Set up the Call me feature</span></span>

<span data-ttu-id="6603e-128">Para habilitar o recurso ligar para mim para os usuários de sua organização, é necessário configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6603e-128">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="6603e-129">A audioconferência está habilitada para os usuários de sua organização que agendam reuniões (organizadores da reunião).</span><span class="sxs-lookup"><span data-stu-id="6603e-129">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="6603e-130">Para saber mais, consulte [Configurar a conferência de áudio para](set-up-audio-conferencing-in-teams.md) o Microsoft Teams e [gerenciar as configurações de audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6603e-130">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="6603e-131">Os usuários podem discar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="6603e-131">Users can dial out from meetings.</span></span> <span data-ttu-id="6603e-132">Para saber mais, consulte [gerenciar as configurações de audioconferência de áudio para um usuário no](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6603e-132">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="6603e-133">Se um usuário não tiver discagem de reuniões habilitada, a opção **ligar para mim** não estará disponível e o usuário não receberá uma chamada para ingressar nela na reunião.</span><span class="sxs-lookup"><span data-stu-id="6603e-133">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="6603e-134">Em vez disso, o usuário vê uma lista de números de telefone na tela **usar telefone para áudio** que pode ser usada para discar manualmente para a reunião em seu telefone.</span><span class="sxs-lookup"><span data-stu-id="6603e-134">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
