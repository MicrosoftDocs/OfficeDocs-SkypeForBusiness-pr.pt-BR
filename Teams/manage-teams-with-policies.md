---
title: Gerenciar o Teams com políticas
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368e71820100ba8cfccb28eef63864f47cd8ce85
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421296"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="ac12d-102">Gerenciar o Teams com políticas</span><span class="sxs-lookup"><span data-stu-id="ac12d-102">Manage Teams with policies</span></span>

<span data-ttu-id="ac12d-103">As políticas são uma parte importante do gerenciamento do Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-103">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="ac12d-104">Use este artigo para navegar sobre como usar políticas para beneficiar sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac12d-104">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="ac12d-105">Para o que você usa políticas</span><span class="sxs-lookup"><span data-stu-id="ac12d-105">What you use policies for</span></span>

<span data-ttu-id="ac12d-106">As políticas são usadas para realizar muitas tarefas em sua organização em diferentes áreas, como mensagens, reuniões e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ac12d-106">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="ac12d-107">Algumas das coisas que você pode fazer incluem permitir que os usuários agendem reuniões em um canal de equipe, permitindo que os usuários editem mensagens enviadas e controlando se os usuários podem fixar aplicativos na barra de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-107">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="ac12d-108">Como atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="ac12d-108">How to assign policies</span></span>

<span data-ttu-id="ac12d-109">As políticas podem ser atribuídas de várias maneiras diferentes, dependendo do que sua organização está tentando realizar.</span><span class="sxs-lookup"><span data-stu-id="ac12d-109">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="ac12d-110">Você pode fazer e exibir atribuições no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-110">You can make and view assignments in the Teams admin center.</span></span>

![Captura de tela da atribuição de política de grupo.](media/group-policy-assignment.png)

<span data-ttu-id="ac12d-112">Leia mais sobre a atribuição de políticas [aqui](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ac12d-112">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="ac12d-113">Como gerenciar políticas</span><span class="sxs-lookup"><span data-stu-id="ac12d-113">How to manage policies</span></span>

<span data-ttu-id="ac12d-114">As políticas são gerenciadas com o centro de administração do Microsoft Teams ou [usando o PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac12d-114">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="ac12d-115">Por exemplo, uma política de configuração de aplicativo pode permitir que os usuários carreguem aplicativos personalizados, instalem aplicativos em nome de seus usuários e fixem aplicativos na barra de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-115">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="ac12d-116">Essas políticas são configuradas no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-116">These policies are configured in the Teams admin center.</span></span>

![Captura de tela da política de configuração do aplicativo.](media/app-setup-policy.png)

<span data-ttu-id="ac12d-118">Além disso, uma política de reunião pode ser usada para controlar configurações de áudio e vídeo em reuniões do Teams, como transcrições, gravações na nuvem e áudio/vídeo IP.</span><span class="sxs-lookup"><span data-stu-id="ac12d-118">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Captura de tela da política de reunião.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="ac12d-120">Teams para o ensino</span><span class="sxs-lookup"><span data-stu-id="ac12d-120">Teams for Education</span></span>

<span data-ttu-id="ac12d-121">Você também pode usar o assistente de política do [Teams for Education](easy-policy-setup-edu.md) para configurar e gerenciar facilmente políticas para seu ambiente de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="ac12d-121">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Captura de tela do assistente de política do Teams for Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="ac12d-123">Tipos de políticas</span><span class="sxs-lookup"><span data-stu-id="ac12d-123">Types of policies</span></span>

<span data-ttu-id="ac12d-124">As políticas a seguir podem ser gerenciadas com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-124">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="ac12d-125">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="ac12d-125">Policy type</span></span> | <span data-ttu-id="ac12d-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac12d-126">Description</span></span>
------------|------------
[<span data-ttu-id="ac12d-127">Pacotes de política</span><span class="sxs-lookup"><span data-stu-id="ac12d-127">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="ac12d-128">Um pacote de política no Microsoft Teams é uma coleção de políticas e configurações predefinidas que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac12d-128">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="ac12d-129">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="ac12d-129">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="ac12d-130">Uma política de reunião é usada para controlar os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac12d-130">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="ac12d-131">As políticas de reunião incluem os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="ac12d-131">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="ac12d-132">- Políticas de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="ac12d-132">- Audio and video policies</span></span><br> <span data-ttu-id="ac12d-133">- Políticas de compartilhamento de conteúdo e tela</span><span class="sxs-lookup"><span data-stu-id="ac12d-133">- Content and screen sharing policies</span></span><br> <span data-ttu-id="ac12d-134">- Participantes, convidados e políticas de acesso</span><span class="sxs-lookup"><span data-stu-id="ac12d-134">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="ac12d-135">- Políticas gerais</span><span class="sxs-lookup"><span data-stu-id="ac12d-135">- General policies</span></span>
[<span data-ttu-id="ac12d-136">Políticas de voz e chamada</span><span class="sxs-lookup"><span data-stu-id="ac12d-136">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="ac12d-137">As políticas de voz e chamada gerenciam essas configurações por meio de equipes como chamadas de emergência, roteamento de chamadas e ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="ac12d-137">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="ac12d-138">Políticas de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac12d-138">App policies</span></span>](app-policies.md)| <span data-ttu-id="ac12d-139">As políticas de aplicativos são usadas para controlar aplicativos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac12d-139">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="ac12d-140">Os administradores podem permitir ou bloquear quais aplicativos os usuários podem instalar, fixar aplicativos na barra de aplicativos do Teams do usuário e instalar o aplicativo em nome de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ac12d-140">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="ac12d-141">Políticas de mensagens</span><span class="sxs-lookup"><span data-stu-id="ac12d-141">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="ac12d-142">As políticas de mensagens controlam a disponibilidade de recursos de chat e canal.</span><span class="sxs-lookup"><span data-stu-id="ac12d-142">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac12d-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ac12d-143">Related topics</span></span>

* [<span data-ttu-id="ac12d-144">Gerenciar políticas de comentários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac12d-144">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="ac12d-145">Gerenciar políticas de equipes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac12d-145">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="ac12d-146">Prepare-se para eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac12d-146">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="ac12d-147">Pacotes de políticas e políticas do Teams for Education</span><span class="sxs-lookup"><span data-stu-id="ac12d-147">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
