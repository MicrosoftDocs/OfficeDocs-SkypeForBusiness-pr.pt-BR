---
title: Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Compartilhamento de chamadas e retirada de chamada do grupo, que permitem aos usuários compartilhar chamadas recebidas com colegas, de forma que as chamadas podem ser capturadas quando o usuário não está disponível.
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993577"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="ee386-103">Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee386-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="ee386-104">O compartilhamento de chamada e o grupo de chamada pickup recursos de compartilhamento de permitem que os usuários do Microsoft Teams seu as chamadas de entrada com colegas para que os colegas podem atender as chamadas que ocorrem enquanto o usuário não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ee386-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="ee386-105">Retirada de chamada do grupo é menos interrupções para destinatários que outras formas de chamada de compartilhamento (por exemplo, encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como desejam ser notificado sobre uma chamada de entrada compartilhada (por meio de notificação de áudio e vídeo, apenas, visual ou faixas do aplicativo de equipes em), e eles podem decidir atendê-la.</span><span class="sxs-lookup"><span data-stu-id="ee386-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="ee386-106">Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamada e adiciona os usuários que desejam compartilhar suas chamadas com.</span><span class="sxs-lookup"><span data-stu-id="ee386-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="ee386-107">Em seguida, eles escolher um toque simultâneo ou encaminham configuração.</span><span class="sxs-lookup"><span data-stu-id="ee386-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="ee386-108">Para obter detalhes, consulte [chamada Toque simultâneo e de encaminhamento em equipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="ee386-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee386-109">Membros do grupo de chamada, o proprietário do grupo de chamada e os usuários devem estar no modo somente as equipes de implantação.</span><span class="sxs-lookup"><span data-stu-id="ee386-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="ee386-110">Para obter mais detalhes sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="ee386-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="ee386-111">É necessária uma licença</span><span class="sxs-lookup"><span data-stu-id="ee386-111">License required</span></span>

<span data-ttu-id="ee386-112">Os usuários precisam ser habilitada para configurar e usar o compartilhamento de chamada e chamada retirada de grupo do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ee386-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="ee386-113">Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ee386-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="ee386-114">Configurar a retirada de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="ee386-114">Configure group call pickup</span></span>

<span data-ttu-id="ee386-115">Para configurar a retirada de chamada do grupo, um usuário configura pela primeira vez um grupo de chamada (isso não é o mesmo como um grupo de segurança ou de um grupo do Office 365) e, em seguida, adiciona os usuários que desejam compartilhar suas chamadas com.</span><span class="sxs-lookup"><span data-stu-id="ee386-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="ee386-116">Em seguida, eles escolher um toque simultâneo ou configuração de encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ee386-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="ee386-117">Para obter mais informações e procedimentos passo a passo, consulte a [chamada Toque simultâneo e de encaminhamento em equipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="ee386-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="ee386-118">Chamar a criação de grupo e notificação preferências são recursos controlado pelo usuário; os administradores não devem configurar esses recursos para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ee386-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="ee386-119">Grupos de chamada não não possível criar grupos de segurança ou grupos do Office 365; eles devem ser criados em equipes.</span><span class="sxs-lookup"><span data-stu-id="ee386-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="ee386-120">Administradores devem habilitar grupos de chamada por meio da configuração de **TeamsCallingPolicy AllowCallGroups** para um usuário.</span><span class="sxs-lookup"><span data-stu-id="ee386-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="ee386-121">Os administradores podem controlar apenas, se esse usuário pode configurar grupos de chamada.</span><span class="sxs-lookup"><span data-stu-id="ee386-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="ee386-122">Depois que o bit for definido como true, administradores não pode impedir o usuário de configuração e adicionando os usuários do grupo de chamada de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="ee386-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="ee386-123">Limitações</span><span class="sxs-lookup"><span data-stu-id="ee386-123">Limitations</span></span>

<span data-ttu-id="ee386-124">Um locatário pode conter um máximo de grupos de 32.768 chamada.</span><span class="sxs-lookup"><span data-stu-id="ee386-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="ee386-125">Pode haver um máximo de 5 usuários em cada grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="ee386-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="ee386-126">Mais informações</span><span class="sxs-lookup"><span data-stu-id="ee386-126">More information</span></span>

[<span data-ttu-id="ee386-127">Encaminhamento de chamadas e toque simultâneo em equipes</span><span class="sxs-lookup"><span data-stu-id="ee386-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)