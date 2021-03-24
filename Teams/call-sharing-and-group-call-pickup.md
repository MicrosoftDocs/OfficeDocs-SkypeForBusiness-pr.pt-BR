---
title: Atendimento de chamada de grupo e compartilhamento de chamada
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: O compartilhamento de chamadas e o recebimento de chamadas em grupo permitem que os usuários compartilhem chamadas de entrada com colegas para que as chamadas possam ser capturadas quando o usuário não estiver disponível.
ms.openlocfilehash: 1ec3c389bf2eb69f30e13ebbba6c7d5d1d5fe38c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102787"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="32560-103">Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32560-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="32560-104">Os recursos de compartilhamento de chamadas e recebimento de chamadas em grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário não está disponível.</span><span class="sxs-lookup"><span data-stu-id="32560-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="32560-105">O recebimento de chamadas em grupo é menos prejudicial para destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como eles querem ser notificados de uma chamada compartilhada de entrada (por meio de notificação de áudio e visual, somente visual ou faixa no aplicativo do Teams) e eles podem decidir se a atenderão.</span><span class="sxs-lookup"><span data-stu-id="32560-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="32560-106">Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamadas e adiciona os usuários com os que deseja compartilhar suas chamadas.</span><span class="sxs-lookup"><span data-stu-id="32560-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="32560-107">Em seguida, eles escolhem um anel simultâneo ou uma configuração de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="32560-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="32560-108">Consulte [Encaminhamento de chamada e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="32560-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="32560-109">Observe que os dispositivos móveis só serão notificados se eles estão definidos para faixa e toque.</span><span class="sxs-lookup"><span data-stu-id="32560-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32560-110">Os usuários, o proprietário do grupo de chamada e os membros do grupo de chamada devem estar no modo de implantação somente do Teams.</span><span class="sxs-lookup"><span data-stu-id="32560-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="32560-111">Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="32560-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="32560-112">Licença necessária</span><span class="sxs-lookup"><span data-stu-id="32560-112">License required</span></span>

<span data-ttu-id="32560-113">Os usuários devem Enterprise Voice habilitados para configurar e usar o compartilhamento de chamada e a retirada de chamada em grupo.</span><span class="sxs-lookup"><span data-stu-id="32560-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="32560-114">Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [a descrição do serviço do Microsoft Teams.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="32560-114">For additional details on the licensing model, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="32560-115">Configurar o recolhimento de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="32560-115">Configure group call pickup</span></span>

<span data-ttu-id="32560-116">Para configurar o atendimento de chamadas em grupo, um usuário primeiro configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Microsoft 365) e adiciona os usuários com os quais deseja compartilhar suas chamadas.</span><span class="sxs-lookup"><span data-stu-id="32560-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="32560-117">Em seguida, eles escolhem um toque simultâneo ou uma configuração de encaminhamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="32560-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="32560-118">Para obter mais informações e procedimentos passo a passo, consulte Encaminhamento de chamada e [toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="32560-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="32560-119">As preferências de criação e notificação de grupo de chamada são recursos orientados pelo usuário; os administradores não têm que configurar esses recursos para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="32560-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="32560-120">Os grupos de chamada não podem ser criados a partir de grupos de segurança ou grupos do Microsoft 365; eles devem ser criados no Teams.</span><span class="sxs-lookup"><span data-stu-id="32560-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="32560-121">Os administradores devem habilitar grupos de chamadas por meio da **configuração TeamsCallingPolicy AllowCallGroups** para um usuário.</span><span class="sxs-lookup"><span data-stu-id="32560-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="32560-122">Os administradores também podem habilitar isso por meio do portal de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="32560-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="32560-123">Além disso, o usuário configurado também pode configurar seus grupos de chamada diretamente por meio do cliente.</span><span class="sxs-lookup"><span data-stu-id="32560-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="32560-124">Os usuários administradores ou finais não podem bloquear a configuração uns dos outros, mas o portal de administração do Teams e o cliente do Teams devem mostrar essa relação com precisão em ambos os lugares.</span><span class="sxs-lookup"><span data-stu-id="32560-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="32560-125">Importante: quando os administradores desativarem grupos de chamadas para usuários (depois que ele tiver sido ligado e as relações de grupo de chamadas estiver configuradas), os administradores terão que limpar as relações de grupo de chamadas para usuários no centro de administração do Teams para evitar o roteamento de chamadas incorreto.</span><span class="sxs-lookup"><span data-stu-id="32560-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="32560-126">Limitações</span><span class="sxs-lookup"><span data-stu-id="32560-126">Limitations</span></span>

<span data-ttu-id="32560-127">Um locatário pode conter no máximo 32.768 grupos de chamada.</span><span class="sxs-lookup"><span data-stu-id="32560-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="32560-128">Pode haver no máximo 25 usuários em cada grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="32560-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="32560-129">Mais informações</span><span class="sxs-lookup"><span data-stu-id="32560-129">More information</span></span>

[<span data-ttu-id="32560-130">Encaminhamento de chamada e toque simultâneo no Teams</span><span class="sxs-lookup"><span data-stu-id="32560-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)