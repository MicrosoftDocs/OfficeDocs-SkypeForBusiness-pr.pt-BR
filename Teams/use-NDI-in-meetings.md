---
title: Usar o NDI no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o NDI no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 24e4312af520bf783c0382b7543190644bfc1ff0
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47323985"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="7c022-103">Usar a tecnologia® do NDI no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c022-103">Use NDI® technology in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

 <span data-ttu-id="7c022-104">NDI® (interface de dispositivo de rede) é uma solução moderna para conexão de dispositivos de mídia (como uma câmera e mixer de estúdio).</span><span class="sxs-lookup"><span data-stu-id="7c022-104">NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="7c022-105">Em vez de usar conexões físicas, o NDI® tecnologia permite a conectividade em uma intranet local, incluindo em um computador local.</span><span class="sxs-lookup"><span data-stu-id="7c022-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="7c022-106">NewTek NDI® tecnologia tornou-se uma solução padrão do setor para a produção de conteúdo dinâmico para fluxos e ganhou conhecimento e adoção significativos no mundo da transmissão profissional.</span><span class="sxs-lookup"><span data-stu-id="7c022-106">NewTek NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="7c022-107">O Skype adicionou NDI a funcionalidade®-out ao Skype no fim do 2018.</span><span class="sxs-lookup"><span data-stu-id="7c022-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="7c022-108">O Microsoft Teams aproveita essa funcionalidade para melhorar a experiência da reunião.</span><span class="sxs-lookup"><span data-stu-id="7c022-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="7c022-109">NDI® tecnologia está limitada a uma rede local e só deve ser considerada uma parte do fluxo de trabalho de produção, não uma solução de transmissão.</span><span class="sxs-lookup"><span data-stu-id="7c022-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="7c022-110">Ativar a tecnologia® do NDI</span><span class="sxs-lookup"><span data-stu-id="7c022-110">Turn on NDI® technology</span></span>

<span data-ttu-id="7c022-111">NDI® tecnologia exige que duas etapas sejam ativadas para um usuário.</span><span class="sxs-lookup"><span data-stu-id="7c022-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="7c022-112">O administrador de locatários deve habilitar a propriedade ' AllowNDIStreaming ' em CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="7c022-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="7c022-113">Depois que essa alteração tiver sido completada, o usuário final precisará ativar o NDI® tecnologia para o cliente específico nas permissões de **configurações**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="7c022-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="7c022-114">Quando um usuário ingressa em uma reunião, ele vê uma mensagem que informa que a reunião está sendo transmitida.</span><span class="sxs-lookup"><span data-stu-id="7c022-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="7c022-115">Se os usuários não quiserem ser incluídos na transmissão, eles precisarão ser descartados da reunião.</span><span class="sxs-lookup"><span data-stu-id="7c022-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="7c022-116">A imagem a seguir mostra a mensagem de faixa que o usuário vê em uma reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="7c022-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Uma imagem da faixa de tecnologia® do NDI que é exibida em uma reunião do teams.](media/NDI-disclosure.png)

<span data-ttu-id="7c022-118">A faixa tem um link para a [política de privacidade da Microsoft](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="7c022-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="7c022-119">Locais e tipos de usuários com suporte</span><span class="sxs-lookup"><span data-stu-id="7c022-119">Supported locales and user types</span></span>

<span data-ttu-id="7c022-120">NDI® tecnologia tem suporte em todas as localidades.</span><span class="sxs-lookup"><span data-stu-id="7c022-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="7c022-121">Os seguintes usuários estão incluídos em um fluxo de tecnologia de® NDI, mas nem todos os usuários podem acessar o fluxo de tecnologia de® do NDI:</span><span class="sxs-lookup"><span data-stu-id="7c022-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="7c022-122">In-locatário – suporte completo, entregue com base em anel/tenantid/userId (controlado por política de reuniões)</span><span class="sxs-lookup"><span data-stu-id="7c022-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="7c022-123">Federado – sem acesso de fluxo (mesmo quando eles têm a tecnologia de® de NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7c022-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="7c022-124">Freemium-sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="7c022-124">Freemium - no stream access</span></span>
- <span data-ttu-id="7c022-125">Anônimo – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="7c022-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="7c022-126">Convidado – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="7c022-126">Guest – no stream access</span></span>  

<span data-ttu-id="7c022-127"><sup>1</sup> dispositivos têm uma configuração de tecnologia NDI® que está ativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="7c022-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="7c022-128">Se um participante da reunião estiver usando um dispositivo com NDI® tecnologia desligada, ele precisará ativar o NDI® tecnologia.</span><span class="sxs-lookup"><span data-stu-id="7c022-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
