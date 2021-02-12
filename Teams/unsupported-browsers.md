---
title: Reuniões do Microsoft Teams em navegadores sem suporte
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Saiba como o Teams dá suporte a áudio e vídeo em navegadores sem suporte.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4aca1592a89e36e7a26a9a22b111968e4b44a302
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804521"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="2e4c0-103">Reuniões do Microsoft Teams em navegadores sem suporte</span><span class="sxs-lookup"><span data-stu-id="2e4c0-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="2e4c0-104">Alguns navegadores, como Internet Explorer 11, Safari e Firefox, são suportados pelo aplicativo Web do Microsoft Teams, mas não são suportados por alguns dos recursos de chamada e reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="2e4c0-105">Para resolver essa limitação, o aplicativo Web do Teams permite que os usuários recebam áudio por meio de uma conexão PSTN e permite que eles vejam o conteúdo apresentado (compartilhamento de tela) com uma taxa de exibição reduzida.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="2e4c0-106">Os aplicativos e serviços do Microsoft 365 não terão suporte para o Internet Explorer 11 a partir de 17 de agosto de 2021 (o Microsoft Teams não terá suporte para o Internet Explorer 11 anterior, a partir de 30 de novembro de 2020).</span><span class="sxs-lookup"><span data-stu-id="2e4c0-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="2e4c0-107">[Saiba mais](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="2e4c0-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="2e4c0-108">Observe que o Internet Explorer 11 permanecerá um navegador compatível.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="2e4c0-109">O Internet Explorer 11 é um [](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) componente do sistema operacional Windows e segue a Política de Ciclo de Vida do produto no qual ele está instalado.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="2e4c0-110">Quando o Teams detecta um navegador sem suporte, ele exibe automaticamente uma mensagem explicando o problema e as limitações da sessão.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="2e4c0-111">A mensagem fornece instruções para acessar o áudio da reunião, como instruir o usuário a deixar um número de retorno de chamada para que o Teams possa ligar para o usuário ou instruir o usuário a ligar para o número de conferência incluído no convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="2e4c0-112">A mensagem também incentiva o usuário a baixar e usar o cliente de área de trabalho [do Teams](https://teams.microsoft.com/downloads) para a experiência completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="2e4c0-113">Se o PSTN não estiver disponível, o usuário não verá as instruções para acessar a reunião e não poderá ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="2e4c0-114">Limitações do navegador</span><span class="sxs-lookup"><span data-stu-id="2e4c0-114">Browser limitations</span></span>

<span data-ttu-id="2e4c0-115">As pessoas que usam o aplicativo Web do Teams em navegadores sem suporte terão as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="2e4c0-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="2e4c0-116">O áudio está disponível apenas por meio de uma conexão PSTN.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="2e4c0-117">Os usuários não podem usar o microfone.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="2e4c0-118">Os usuários não podem compartilhar suas câmeras ou ver os vídeos de outros participantes, mas podem exibir o conteúdo apresentado por meio do compartilhamento de tela baseado em imagem.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="2e4c0-119">Os usuários não podem compartilhar suas telas, embora possam ver uma tela que outro participante da reunião compartilha.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="2e4c0-120">Os usuários não podem assumir o controle durante uma sessão de compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="2e4c0-121">Os usuários não receberão notificações de chamada recebidas.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="2e4c0-122">Se a chamada for interrompida, a reunião não será reconectada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="2e4c0-123">Os usuários não podem iniciar reuniões.</span><span class="sxs-lookup"><span data-stu-id="2e4c0-123">Users can't start meetings.</span></span>

<span data-ttu-id="2e4c0-124">Para obter mais informações sobre o suporte ao navegador no Teams, consulte [Limites e especificações do Teams.](/microsoftteams/limits-specifications-teams#browsers)</span><span class="sxs-lookup"><span data-stu-id="2e4c0-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e4c0-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2e4c0-125">Related topics</span></span>

- [<span data-ttu-id="2e4c0-126">Ingressar em uma reunião do Teams em um navegador sem suporte</span><span class="sxs-lookup"><span data-stu-id="2e4c0-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
