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
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337010"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="2a0af-103">Usar a tecnologia® do NDI no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a0af-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="2a0af-104">NewTek NDI® a tecnologia de dispositivo de rede (Network Device Interface) é uma solução moderna para conexão de dispositivos de mídia (como uma câmera e mixer de estúdio).</span><span class="sxs-lookup"><span data-stu-id="2a0af-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="2a0af-105">Em vez de usar conexões físicas, o NDI® tecnologia permite a conectividade em uma intranet local, incluindo em um computador local.</span><span class="sxs-lookup"><span data-stu-id="2a0af-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="2a0af-106">NDI® tecnologia tornou-se uma solução padrão do setor para a produção de conteúdo dinâmico para fluxos e ganhou conscientização significativa e adoção no mundo da transmissão profissional.</span><span class="sxs-lookup"><span data-stu-id="2a0af-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="2a0af-107">O Skype adicionou NDI a funcionalidade®-out ao Skype no fim do 2018.</span><span class="sxs-lookup"><span data-stu-id="2a0af-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="2a0af-108">O Microsoft Teams usa essa funcionalidade para melhorar a experiência da reunião.</span><span class="sxs-lookup"><span data-stu-id="2a0af-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="2a0af-109">NDI® tecnologia está limitada a uma rede local e só deve ser considerada uma parte do fluxo de trabalho de produção, não uma solução de transmissão.</span><span class="sxs-lookup"><span data-stu-id="2a0af-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="2a0af-110">Ativar a tecnologia® do NDI</span><span class="sxs-lookup"><span data-stu-id="2a0af-110">Turn on NDI® technology</span></span>

<span data-ttu-id="2a0af-111">NDI® tecnologia exige que duas etapas sejam ativadas para um usuário.</span><span class="sxs-lookup"><span data-stu-id="2a0af-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="2a0af-112">O administrador de locatários deve habilitar a propriedade ' AllowNDIStreaming ' em CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="2a0af-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="2a0af-113">Depois que essa alteração tiver sido completada, o usuário final precisará ativar o NDI® tecnologia para o cliente específico nas permissões de **configurações**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="2a0af-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="2a0af-114">Quando um usuário ingressa em uma reunião, ele vê uma mensagem que informa que a reunião está sendo transmitida.</span><span class="sxs-lookup"><span data-stu-id="2a0af-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="2a0af-115">Se os usuários não quiserem ser incluídos na transmissão, eles precisarão ser descartados da reunião.</span><span class="sxs-lookup"><span data-stu-id="2a0af-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="2a0af-116">A imagem a seguir mostra a mensagem de faixa que o usuário vê em uma reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="2a0af-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Ele NDI® faixa de tecnologia que é exibida em uma reunião de equipe.](media/NDI-disclosure.png)

<span data-ttu-id="2a0af-118">A faixa tem um link para a [política de privacidade da Microsoft](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="2a0af-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="2a0af-119">Locais e tipos de usuários com suporte</span><span class="sxs-lookup"><span data-stu-id="2a0af-119">Supported locales and user types</span></span>

<span data-ttu-id="2a0af-120">NDI® tecnologia tem suporte em todas as localidades.</span><span class="sxs-lookup"><span data-stu-id="2a0af-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="2a0af-121">Os seguintes usuários estão incluídos em um fluxo de tecnologia de® NDI, mas nem todos os usuários podem acessar o fluxo de tecnologia de® do NDI:</span><span class="sxs-lookup"><span data-stu-id="2a0af-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="2a0af-122">In-locatário – suporte completo, entregue com base em anel/tenantid/userId (controlado por política de reuniões)</span><span class="sxs-lookup"><span data-stu-id="2a0af-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="2a0af-123">Federado – sem acesso de fluxo (mesmo quando eles têm a tecnologia de® de NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2a0af-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="2a0af-124">Premium-sem acesso a fluxo</span><span class="sxs-lookup"><span data-stu-id="2a0af-124">Premium - no stream access</span></span>
- <span data-ttu-id="2a0af-125">Anônimo – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="2a0af-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="2a0af-126">Convidado – sem acesso de fluxo</span><span class="sxs-lookup"><span data-stu-id="2a0af-126">Guest – no stream access</span></span>  

<span data-ttu-id="2a0af-127"><sup>1</sup> dispositivos têm uma configuração de tecnologia NDI® que está ativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="2a0af-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="2a0af-128">Se um participante da reunião estiver usando um dispositivo com NDI® tecnologia desligada, ele precisará ativar o NDI® tecnologia.</span><span class="sxs-lookup"><span data-stu-id="2a0af-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
