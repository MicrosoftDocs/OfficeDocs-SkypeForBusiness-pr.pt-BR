---
title: Usar NDI no Microsoft Teams
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
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337010"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="58eaf-103">Usar a tecnologia ® NDI no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58eaf-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="58eaf-104">A tecnologia NewTek NDI® (Interface de Dispositivo de Rede) é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer).</span><span class="sxs-lookup"><span data-stu-id="58eaf-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="58eaf-105">Em vez de usar conexões físicas, ® NDI habilita a conectividade em uma intranet local, inclusive em um computador local.</span><span class="sxs-lookup"><span data-stu-id="58eaf-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="58eaf-106">A tecnologia NDI® tornou-se uma solução padrão do setor para a produção de conteúdo ao vivo para fluxos e ganhou reconhecimento e adoção significativas no mundo da transmissão profissional.</span><span class="sxs-lookup"><span data-stu-id="58eaf-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="58eaf-107">O Skype adicionou anteriormente ® NDI ao Skype no final de 2018.</span><span class="sxs-lookup"><span data-stu-id="58eaf-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="58eaf-108">O Microsoft Teams usa essa funcionalidade para melhorar a experiência da reunião.</span><span class="sxs-lookup"><span data-stu-id="58eaf-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="58eaf-109">O NDI® a tecnologia é limitada a uma rede local e só deve ser considerada parte do fluxo de trabalho de produção, não uma solução de transmissão.</span><span class="sxs-lookup"><span data-stu-id="58eaf-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="58eaf-110">Ativar a tecnologia NDI® NDI</span><span class="sxs-lookup"><span data-stu-id="58eaf-110">Turn on NDI® technology</span></span>

<span data-ttu-id="58eaf-111">A tecnologia NDI® requer duas etapas para ser responsabilidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="58eaf-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="58eaf-112">O administrador do locatário deve habilitar a propriedade 'AllowNDIStreaming' no CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="58eaf-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="58eaf-113">Depois que essa alteração for preenchida, o usuário final deverá ativar a tecnologia NDI® para seu cliente específico a partir de  >  **Permissões de Configurações.**</span><span class="sxs-lookup"><span data-stu-id="58eaf-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="58eaf-114">Quando um usuário ingressar em uma reunião, ele verá uma mensagem que o notifica de que a reunião está sendo transmitida.</span><span class="sxs-lookup"><span data-stu-id="58eaf-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="58eaf-115">Se os usuários não quiserem ser incluídos na transmissão, eles precisarão sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="58eaf-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="58eaf-116">A imagem a seguir mostra a mensagem de faixa que um usuário vê em uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="58eaf-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![NDI® faixa de tecnologia que é exibida em uma reunião do Teams.](media/NDI-disclosure.png)

<span data-ttu-id="58eaf-118">A faixa tem um link para a [política de privacidade da Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="58eaf-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="58eaf-119">Localidades e tipos de usuário com suporte</span><span class="sxs-lookup"><span data-stu-id="58eaf-119">Supported locales and user types</span></span>

<span data-ttu-id="58eaf-120">A tecnologia ® NDI é suportada em todas as localidades.</span><span class="sxs-lookup"><span data-stu-id="58eaf-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="58eaf-121">Os seguintes usuários estão incluídos em um fluxo de tecnologia NDI®, mas nem todos os usuários podem acessar o fluxo de tecnologia NDI®:</span><span class="sxs-lookup"><span data-stu-id="58eaf-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="58eaf-122">No locatário – suporte total, fornecido com base no ring/tenantId/userId (controlado pela Política de Reuniões)</span><span class="sxs-lookup"><span data-stu-id="58eaf-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="58eaf-123">Federado – sem acesso de fluxo (mesmo quando eles têm NDI® tecnologia em)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="58eaf-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="58eaf-124">Premium – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="58eaf-124">Premium - no stream access</span></span>
- <span data-ttu-id="58eaf-125">Anônimo – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="58eaf-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="58eaf-126">Convidado – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="58eaf-126">Guest – no stream access</span></span>  

<span data-ttu-id="58eaf-127"><sup>1</sup> Os dispositivos têm uma configuração de ® NDI que está on por padrão.</span><span class="sxs-lookup"><span data-stu-id="58eaf-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="58eaf-128">Se um participante da reunião estiver usando um dispositivo com ® NDI desligado, ele precisará ativar a tecnologia NDI® NDI.</span><span class="sxs-lookup"><span data-stu-id="58eaf-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
