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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Compartilhamento de chamadas e retirada de chamadas em grupo permitem que os usuários compartilhem chamadas com colegas para que as chamadas possam ser capturadas quando o usuário não estiver disponível.
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283475"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="b2582-103">Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2582-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="b2582-104">Os recursos de compartilhamento de chamadas e retirada de chamadas de grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário está indisponível.</span><span class="sxs-lookup"><span data-stu-id="b2582-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="b2582-105">O recebimento de chamadas em grupo é menos prejudicial aos destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como querem ser notificados sobre uma chamada compartilhada de entrada (via áudio e notificação Visual, somente Visual, ou faixa no aplicativo Teams) e elas podem decidir se devem ser respondidas.</span><span class="sxs-lookup"><span data-stu-id="b2582-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="b2582-106">Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamada e adiciona os usuários com quem deseja compartilhar suas chamadas.</span><span class="sxs-lookup"><span data-stu-id="b2582-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="b2582-107">Em seguida, escolha uma configuração de toque ou encaminhamento simultânea.</span><span class="sxs-lookup"><span data-stu-id="b2582-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="b2582-108">Consulte [encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="b2582-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2582-109">Os usuários, o proprietário do grupo de chamadas e os membros do grupo de chamadas devem estar no modo de implantação do teams only.</span><span class="sxs-lookup"><span data-stu-id="b2582-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="b2582-110">Para obter mais detalhes sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="b2582-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="b2582-111">Licença necessária</span><span class="sxs-lookup"><span data-stu-id="b2582-111">License required</span></span>

<span data-ttu-id="b2582-112">Os usuários devem ter o Enterprise Voice habilitado para configurar e usar o compartilhamento de chamadas e a retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="b2582-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="b2582-113">Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="b2582-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="b2582-114">Configurar a retirada de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="b2582-114">Configure group call pickup</span></span>

<span data-ttu-id="b2582-115">Para configurar o recebimento de chamadas em grupo, um usuário primeiro configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Office 365) e, em seguida, adiciona os usuários com quem deseja compartilhar suas chamadas.</span><span class="sxs-lookup"><span data-stu-id="b2582-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="b2582-116">Em seguida, eles escolhem uma configuração de toque simultâneo ou encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b2582-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="b2582-117">Para obter mais informações e procedimentos passo a passo, consulte encaminhamento de [chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="b2582-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="b2582-118">A criação de grupos de chamadas e preferências de notificação são recursos controlados pelo usuário; os administradores não precisam configurar esses recursos para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b2582-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="b2582-119">Os grupos de chamadas não podem ser criados a partir de grupos de segurança ou grupos do Office 365; Elas devem ser criadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="b2582-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="b2582-120">Os administradores devem habilitar os grupos de chamadas por meio da configuração **TeamsCallingPolicy AllowCallGroups** para um usuário.</span><span class="sxs-lookup"><span data-stu-id="b2582-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="b2582-121">Os administradores podem controlar apenas se este usuário pode configurar grupos de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b2582-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="b2582-122">Quando o bit é definido como true, os administradores não podem impedir que o usuário configure e adicione os usuários do grupo de chamada de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="b2582-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="b2582-123">Relacionadas</span><span class="sxs-lookup"><span data-stu-id="b2582-123">Limitations</span></span>

<span data-ttu-id="b2582-124">Um locatário pode conter um máximo de grupos de chamadas do 32.768.</span><span class="sxs-lookup"><span data-stu-id="b2582-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="b2582-125">Pode haver um máximo de cinco usuários em cada grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="b2582-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="b2582-126">Mais informações</span><span class="sxs-lookup"><span data-stu-id="b2582-126">More information</span></span>

[<span data-ttu-id="b2582-127">Encaminhamento de chamadas e toque simultâneo no Teams</span><span class="sxs-lookup"><span data-stu-id="b2582-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)