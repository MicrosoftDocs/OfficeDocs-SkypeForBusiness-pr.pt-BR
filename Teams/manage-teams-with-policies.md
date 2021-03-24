---
title: Gerenciar o Teams com políticas
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Incline-se sobre as políticas do Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b54c64c637d44132ac0f978561267ef34f720e67
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101097"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="da206-103">Gerenciar o Teams com políticas</span><span class="sxs-lookup"><span data-stu-id="da206-103">Manage Teams with policies</span></span>

<span data-ttu-id="da206-104">As políticas são uma parte importante do gerenciamento do Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="da206-105">Use este artigo para navegar sobre como usar políticas para beneficiar sua organização.</span><span class="sxs-lookup"><span data-stu-id="da206-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="da206-106">Para o que você usa políticas</span><span class="sxs-lookup"><span data-stu-id="da206-106">What you use policies for</span></span>

<span data-ttu-id="da206-107">As políticas são usadas para realizar muitas tarefas em sua organização em diferentes áreas, como mensagens, reuniões e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="da206-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="da206-108">Algumas das coisas que você pode fazer incluem permitir que os usuários agendem reuniões em um canal de equipe, permitindo que os usuários editem mensagens enviadas e controlando se os usuários podem fixar aplicativos na barra de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="da206-109">Como atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="da206-109">How to assign policies</span></span>

<span data-ttu-id="da206-110">As políticas podem ser atribuídas de várias maneiras diferentes, dependendo do que sua organização está tentando realizar.</span><span class="sxs-lookup"><span data-stu-id="da206-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="da206-111">Você pode fazer e exibir atribuições no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-111">You can make and view assignments in the Teams admin center.</span></span>

![Captura de tela da atribuição de política de grupo.](media/group-policy-assignment.png)

<span data-ttu-id="da206-113">Leia mais sobre a atribuição de políticas [aqui](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="da206-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="da206-114">Como gerenciar políticas</span><span class="sxs-lookup"><span data-stu-id="da206-114">How to manage policies</span></span>

<span data-ttu-id="da206-115">As políticas são gerenciadas com o centro de administração do Microsoft Teams ou [usando o PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="da206-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="da206-116">Por exemplo, uma política de configuração de aplicativo pode permitir que os usuários carreguem aplicativos personalizados, instalem aplicativos em nome de seus usuários e fixem aplicativos na barra de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="da206-117">Essas políticas são configuradas no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-117">These policies are configured in the Teams admin center.</span></span>

![Captura de tela da política de configuração do aplicativo.](media/app-setup-policy.png)

<span data-ttu-id="da206-119">Além disso, uma política de reunião pode ser usada para controlar configurações de áudio e vídeo em reuniões do Teams, como transcrições, gravações na nuvem e áudio/vídeo IP.</span><span class="sxs-lookup"><span data-stu-id="da206-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Captura de tela da política de reunião.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="da206-121">Teams para o ensino</span><span class="sxs-lookup"><span data-stu-id="da206-121">Teams for Education</span></span>

<span data-ttu-id="da206-122">Você também pode usar o assistente de política do [Teams for Education](easy-policy-setup-edu.md) para configurar e gerenciar facilmente políticas para seu ambiente de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="da206-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Captura de tela do assistente de política do Teams for Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="da206-124">Tipos de políticas</span><span class="sxs-lookup"><span data-stu-id="da206-124">Types of policies</span></span>

<span data-ttu-id="da206-125">As políticas a seguir podem ser gerenciadas com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="da206-126">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="da206-126">Policy type</span></span> | <span data-ttu-id="da206-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="da206-127">Description</span></span>
------------|------------
[<span data-ttu-id="da206-128">Pacotes de política</span><span class="sxs-lookup"><span data-stu-id="da206-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="da206-129">Um pacote de política no Microsoft Teams é uma coleção de políticas e configurações predefinidas que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="da206-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="da206-130">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="da206-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="da206-131">Uma política de reunião é usada para controlar os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="da206-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="da206-132">As políticas de reunião incluem os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="da206-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="da206-133">- Políticas de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="da206-133">- Audio and video policies</span></span><br> <span data-ttu-id="da206-134">- Políticas de compartilhamento de conteúdo e tela</span><span class="sxs-lookup"><span data-stu-id="da206-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="da206-135">- Participantes, convidados e políticas de acesso</span><span class="sxs-lookup"><span data-stu-id="da206-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="da206-136">- Políticas gerais</span><span class="sxs-lookup"><span data-stu-id="da206-136">- General policies</span></span>
[<span data-ttu-id="da206-137">Políticas de voz e chamada</span><span class="sxs-lookup"><span data-stu-id="da206-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="da206-138">As políticas de voz e chamada gerenciam essas configurações por meio de equipes como chamadas de emergência, roteamento de chamadas e ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="da206-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="da206-139">Políticas de aplicativo</span><span class="sxs-lookup"><span data-stu-id="da206-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="da206-140">As políticas de aplicativos são usadas para controlar aplicativos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="da206-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="da206-141">Os administradores podem permitir ou bloquear quais aplicativos os usuários podem instalar, fixar aplicativos na barra de aplicativos do Teams do usuário e instalar o aplicativo em nome de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="da206-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="da206-142">Políticas de mensagens</span><span class="sxs-lookup"><span data-stu-id="da206-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="da206-143">As políticas de mensagens controlam a disponibilidade de recursos de chat e canal.</span><span class="sxs-lookup"><span data-stu-id="da206-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da206-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="da206-144">Related topics</span></span>

* [<span data-ttu-id="da206-145">Gerenciar políticas de comentários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da206-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="da206-146">Gerenciar políticas de equipes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da206-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="da206-147">Exibir atribuições de política no Log de Atividades</span><span class="sxs-lookup"><span data-stu-id="da206-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="da206-148">Prepare-se para eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da206-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="da206-149">Pacotes de políticas e políticas do Teams for Education</span><span class="sxs-lookup"><span data-stu-id="da206-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)