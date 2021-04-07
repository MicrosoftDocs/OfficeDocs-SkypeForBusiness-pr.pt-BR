---
title: Usar a NDI no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar a NDI no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598460"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="13010-103">Usar a tecnologia ® NDI no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13010-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="13010-104">A tecnologia NewTek NDI® (Interface de Dispositivo de Rede) é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer).</span><span class="sxs-lookup"><span data-stu-id="13010-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="13010-105">Em vez de usar conexões físicas, a tecnologia ® NDI habilita a conectividade em uma intranet local, inclusive em uma máquina local.</span><span class="sxs-lookup"><span data-stu-id="13010-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="13010-106">A tecnologia ® NDI se tornou uma solução padrão do setor para produzir conteúdo ao vivo para fluxos e ganhou uma conscientização significativa e adoção no mundo da transmissão profissional.</span><span class="sxs-lookup"><span data-stu-id="13010-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="13010-107">O Skype adicionou anteriormente a funcionalidade ® NDI ao Skype no final de 2018.</span><span class="sxs-lookup"><span data-stu-id="13010-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="13010-108">O Microsoft Teams usa essa funcionalidade para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="13010-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="13010-109">A ® NDI está limitada a uma rede local e deve ser considerada apenas uma parte do fluxo de trabalho de produção, não uma solução de transmissão.</span><span class="sxs-lookup"><span data-stu-id="13010-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="13010-110">Ativar a tecnologia NDI®</span><span class="sxs-lookup"><span data-stu-id="13010-110">Turn on NDI® technology</span></span>

<span data-ttu-id="13010-111">A tecnologia ® NDI requer duas etapas para ser 1 para um usuário.</span><span class="sxs-lookup"><span data-stu-id="13010-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="13010-112">O administrador do locatário deve habilitar a propriedade 'AllowNDIStreaming' em CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="13010-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="13010-113">Depois que essa alteração for preenchida, o usuário final deverá ativar a tecnologia NDI® para seu cliente específico a partir **de Permissões**  >  **de Configurações.**</span><span class="sxs-lookup"><span data-stu-id="13010-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="13010-114">Quando um usuário ingressar em uma reunião, ele verá uma mensagem que notifica que a reunião está sendo transmitida.</span><span class="sxs-lookup"><span data-stu-id="13010-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="13010-115">Se os usuários não quiserem ser incluídos na transmissão, eles precisarão sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="13010-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="13010-116">A imagem a seguir mostra a mensagem em faixa que um usuário vê em uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="13010-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![ele NDI® faixa de tecnologia que é exibida em uma reunião do Teams.](media/NDI-disclosure.png)

<span data-ttu-id="13010-118">O banner tem um link para a [política de privacidade da Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="13010-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="13010-119">NDI® é ativado somente por sessão.</span><span class="sxs-lookup"><span data-stu-id="13010-119">NDI® is activated per session only.</span></span> <span data-ttu-id="13010-120">No próximo logon, o usuário deve ativá-lo antes de usar o NDI®.</span><span class="sxs-lookup"><span data-stu-id="13010-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="13010-121">Localidades e tipos de usuário com suporte</span><span class="sxs-lookup"><span data-stu-id="13010-121">Supported locales and user types</span></span>

<span data-ttu-id="13010-122">A ® NDI é suportada em todas as localidades.</span><span class="sxs-lookup"><span data-stu-id="13010-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="13010-123">Os usuários a seguir estão incluídos em um fluxo de tecnologia NDI®, mas nem todos os usuários podem acessar o fluxo de tecnologia NDI®:</span><span class="sxs-lookup"><span data-stu-id="13010-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="13010-124">In-tenant – suporte completo, fornecido com base em ring/tenantId/userId (controlado pela Política de Reuniões)</span><span class="sxs-lookup"><span data-stu-id="13010-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="13010-125">Federado – sem acesso a fluxo (mesmo quando eles têm a tecnologia ® NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13010-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="13010-126">Premium - sem acesso a fluxo</span><span class="sxs-lookup"><span data-stu-id="13010-126">Premium - no stream access</span></span>
- <span data-ttu-id="13010-127">Anônimo – sem acesso a fluxo</span><span class="sxs-lookup"><span data-stu-id="13010-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="13010-128">Convidado – sem acesso a fluxo</span><span class="sxs-lookup"><span data-stu-id="13010-128">Guest – no stream access</span></span>  

<span data-ttu-id="13010-129"><sup>1</sup> Os dispositivos têm uma configuração de tecnologia ® NDI que está em uso por padrão.</span><span class="sxs-lookup"><span data-stu-id="13010-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="13010-130">Se um participante da reunião estiver usando um dispositivo com a tecnologia ® NDI desligada, ele precisará ativar a tecnologia ® NDI.</span><span class="sxs-lookup"><span data-stu-id="13010-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
