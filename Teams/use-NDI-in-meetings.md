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
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588285"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="09a40-103">Usar o NDI no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09a40-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="09a40-104">O NDI (Network Device Interface) é uma solução moderna para conexão de dispositivos de mídia (como uma câmera e mixer de estúdio).</span><span class="sxs-lookup"><span data-stu-id="09a40-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="09a40-105">Em vez de usar conexões físicas, o NDI permite a conectividade em uma intranet local, incluindo em um computador local.</span><span class="sxs-lookup"><span data-stu-id="09a40-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="09a40-106">NewTek NDI® tornou-se uma solução padrão do setor para a produção de conteúdo ao vivo para fluxos e ganhou conhecimento e adoção significativos no mundo da transmissão profissional.</span><span class="sxs-lookup"><span data-stu-id="09a40-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="09a40-107">O Skype adicionou anteriormente a funcionalidade NDI ao Skype no fim de 2018.</span><span class="sxs-lookup"><span data-stu-id="09a40-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="09a40-108">O Microsoft Teams aproveita essa funcionalidade para melhorar a experiência da reunião.</span><span class="sxs-lookup"><span data-stu-id="09a40-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="09a40-109">O NDI limita-se a uma rede local e só deve ser considerado parte do fluxo de trabalho de produção, não uma solução de transmissão.</span><span class="sxs-lookup"><span data-stu-id="09a40-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="09a40-110">Ativar o NDI</span><span class="sxs-lookup"><span data-stu-id="09a40-110">Turn on NDI</span></span>

<span data-ttu-id="09a40-111">O NDI exige que duas etapas sejam ativadas para um usuário.</span><span class="sxs-lookup"><span data-stu-id="09a40-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="09a40-112">O administrador de locatários deve habilitar a propriedade ' AllowNDIStreaming ' em CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="09a40-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="09a40-113">Depois que essa alteração tiver sido completada, o usuário final precisará ativar o NDI para o cliente específico das permissões de **configurações**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="09a40-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="09a40-114">Quando um usuário ingressa em uma reunião, ele vê uma mensagem que informa que a reunião está sendo transmitida.</span><span class="sxs-lookup"><span data-stu-id="09a40-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="09a40-115">Se os usuários não quiserem ser incluídos na transmissão, eles precisarão ser descartados da reunião.</span><span class="sxs-lookup"><span data-stu-id="09a40-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="09a40-116">A imagem a seguir mostra a mensagem de faixa que o usuário vê em uma reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="09a40-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Uma imagem da faixa NDI exibida em uma reunião do teams.](media/NDI-disclosure.png)

<span data-ttu-id="09a40-118">A faixa tem um link para a [política de privacidade da Microsoft](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="09a40-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="09a40-119">Locais e tipos de usuários com suporte</span><span class="sxs-lookup"><span data-stu-id="09a40-119">Supported locales and user types</span></span>

<span data-ttu-id="09a40-120">NDI é compatível com todas as localidades.</span><span class="sxs-lookup"><span data-stu-id="09a40-120">NDI is supported in all locales.</span></span> <span data-ttu-id="09a40-121">Os seguintes usuários têm suporte em uma reunião do NDI:</span><span class="sxs-lookup"><span data-stu-id="09a40-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="09a40-122">In-locatário – suporte completo, entregue com base em anel/tenantid/userId (controlado por política de reuniões)</span><span class="sxs-lookup"><span data-stu-id="09a40-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="09a40-123">Federado – não (mesmo quando eles têm NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="09a40-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="09a40-124">Freemium-não (valor padrão)</span><span class="sxs-lookup"><span data-stu-id="09a40-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="09a40-125">Anônimo – não (valor padrão)</span><span class="sxs-lookup"><span data-stu-id="09a40-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="09a40-126">Convidado – não (valor padrão)</span><span class="sxs-lookup"><span data-stu-id="09a40-126">Guest – no  (default value)</span></span>

<span data-ttu-id="09a40-127"><sup>1</sup> dispositivos têm uma configuração NDI ativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="09a40-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="09a40-128">Se um participante da reunião estiver usando um dispositivo com o NDI desligado, ele precisará ativar o NDI.</span><span class="sxs-lookup"><span data-stu-id="09a40-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
