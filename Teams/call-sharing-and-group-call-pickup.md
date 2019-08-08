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
ms.openlocfilehash: caf472f9829f9cf68ccb87a5081bc0b5cfae28f8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237157"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="221f3-103">Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="221f3-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="221f3-104">Os recursos de compartilhamento de chamadas e retirada de chamadas de grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário está indisponível.</span><span class="sxs-lookup"><span data-stu-id="221f3-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="221f3-105">O recebimento de chamadas em grupo é menos prejudicial aos destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como querem ser notificados sobre uma chamada compartilhada de entrada (via áudio e notificação Visual, somente Visual, ou faixa no aplicativo Teams) e elas podem decidir se devem ser respondidas.</span><span class="sxs-lookup"><span data-stu-id="221f3-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="221f3-106">Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamada e adiciona os usuários com quem deseja compartilhar suas chamadas.</span><span class="sxs-lookup"><span data-stu-id="221f3-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="221f3-107">Em seguida, escolha uma configuração de toque ou encaminhamento simultânea.</span><span class="sxs-lookup"><span data-stu-id="221f3-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="221f3-108">Consulte [encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="221f3-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="221f3-109">Os usuários, o proprietário do grupo de chamadas e os membros do grupo de chamadas devem estar no modo de implantação do teams only.</span><span class="sxs-lookup"><span data-stu-id="221f3-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="221f3-110">Para obter mais detalhes sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="221f3-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="221f3-111">Licença necessária</span><span class="sxs-lookup"><span data-stu-id="221f3-111">License required</span></span>

<span data-ttu-id="221f3-112">Os usuários devem ter o Enterprise Voice habilitado para configurar e usar o compartilhamento de chamadas e a retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="221f3-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="221f3-113">Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="221f3-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="221f3-114">Configurar a retirada de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="221f3-114">Configure group call pickup</span></span>

<span data-ttu-id="221f3-115">Para configurar o recebimento de chamadas em grupo, um usuário primeiro configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Office 365) e, em seguida, adiciona os usuários com quem deseja compartilhar suas chamadas.</span><span class="sxs-lookup"><span data-stu-id="221f3-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="221f3-116">Em seguida, eles escolhem uma configuração de toque simultâneo ou encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="221f3-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="221f3-117">Para obter mais informações e procedimentos passo a passo, consulte encaminhamento de [chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="221f3-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="221f3-118">A criação de grupos de chamadas e preferências de notificação são recursos controlados pelo usuário; os administradores não precisam configurar esses recursos para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="221f3-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="221f3-119">Os grupos de chamadas não podem ser criados a partir de grupos de segurança ou grupos do Office 365; Elas devem ser criadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="221f3-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="221f3-120">Os administradores devem habilitar os grupos de chamadas por meio da configuração **TeamsCallingPolicy AllowCallGroups** para um usuário.</span><span class="sxs-lookup"><span data-stu-id="221f3-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="221f3-121">Os administradores também podem habilitá-lo por meio do portal de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="221f3-121">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="221f3-122">Além disso, o usuário configurado também pode configurar seus grupos de chamadas diretamente por meio do cliente.</span><span class="sxs-lookup"><span data-stu-id="221f3-122">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="221f3-123">Os usuários finais ou administradores não podem bloquear a configuração de cada uma, mas o portal de administração do Teams e o cliente das equipes devem mostrar essa relação com precisão em ambos os locais.</span><span class="sxs-lookup"><span data-stu-id="221f3-123">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="221f3-124">Importante: quando os administradores desativarem os grupos de chamadas para usuários (depois que ele for ativado e os relacionamentos do grupo de chamadas estiverem configurados), os administradores precisarão limpar as relações de grupo de chamadas para usuários no centro de administração do teams para evitar o roteamento de chamadas incorretas.</span><span class="sxs-lookup"><span data-stu-id="221f3-124">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="221f3-125">Relacionadas</span><span class="sxs-lookup"><span data-stu-id="221f3-125">Limitations</span></span>

<span data-ttu-id="221f3-126">Um locatário pode conter um máximo de grupos de chamadas do 32.768.</span><span class="sxs-lookup"><span data-stu-id="221f3-126">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="221f3-127">Pode haver no máximo 25 usuários em cada grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="221f3-127">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="221f3-128">Mais informações</span><span class="sxs-lookup"><span data-stu-id="221f3-128">More information</span></span>

[<span data-ttu-id="221f3-129">Encaminhamento de chamadas e toque simultâneo no Teams</span><span class="sxs-lookup"><span data-stu-id="221f3-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
