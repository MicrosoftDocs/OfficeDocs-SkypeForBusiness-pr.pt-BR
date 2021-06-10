---
title: Gerenciar políticas de reunião
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Aprenda a gerenciar as configurações das políticas de reunião no Teams e a usá-las para controlar os recursos disponíveis para os participantes da reunião nas reuniões agendadas pelos usuários.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598694"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="18efe-103">Gerenciar políticas de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="18efe-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="18efe-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="18efe-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="18efe-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="18efe-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="18efe-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="18efe-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="18efe-107">As políticas de reunião são usadas para controlar os recursos disponibilizados para os participantes de reuniões programadas pelos usuários de sua organização.</span><span class="sxs-lookup"><span data-stu-id="18efe-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="18efe-108">Você pode usar a política global (padrão em toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas. </span><span class="sxs-lookup"><span data-stu-id="18efe-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="18efe-109">Você gerencia as políticas de reunião no Centro de Administração do Microsoft Teams ou usando o [PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="18efe-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="18efe-110">Para obter informações sobre como usar as funções para gerenciar as permissões de apresentadores e participantes da reunião, confira [funções em uma reunião no Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span><span class="sxs-lookup"><span data-stu-id="18efe-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="18efe-111">Você pode implementar políticas das seguintes maneiras, o que afeta a experiência da reunião para os usuários antes, durante, ou depois de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="18efe-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="18efe-112">Tipo de implementação</span><span class="sxs-lookup"><span data-stu-id="18efe-112">Implementation type</span></span>  |<span data-ttu-id="18efe-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="18efe-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="18efe-114">Por organizador</span><span class="sxs-lookup"><span data-stu-id="18efe-114">Per-organizer</span></span>    |<span data-ttu-id="18efe-115">Ao implementar uma política por organizador, todos os participantes da reunião herdam a política do organizador.</span><span class="sxs-lookup"><span data-stu-id="18efe-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="18efe-116">Por exemplo, **Admitir pessoas automaticamente** é uma política por organizador e controla se os usuários entram na reunião diretamente ou se esperam o lobby das reuniões agendadas pelo usuário que recebeu a política.</span><span class="sxs-lookup"><span data-stu-id="18efe-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="18efe-117">Por usuário</span><span class="sxs-lookup"><span data-stu-id="18efe-117">Per-user</span></span>    |<span data-ttu-id="18efe-118">Ao implementar uma política por usuário, somente a política por usuário se aplica à restrições de certos recursos para o organizador e/ou os participantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="18efe-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="18efe-119">Por exemplo, **Permitir Reunir agora nos canais** é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="18efe-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="18efe-120">Por organizador e por usuário</span><span class="sxs-lookup"><span data-stu-id="18efe-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="18efe-121">Ao implementar uma combinação de uma política por organizador e por usuário, alguns recursos são restritos para os participantes da reunião com base em sua política e a política do organizador.</span><span class="sxs-lookup"><span data-stu-id="18efe-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="18efe-122">Por exemplo, **Permitir gravação na nuvem** é uma política por organizador e por usuário.</span><span class="sxs-lookup"><span data-stu-id="18efe-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="18efe-123">Ative essa configuração para permitir que o organizador da reunião e os participantes iniciem e interrompam uma gravação.</span><span class="sxs-lookup"><span data-stu-id="18efe-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="18efe-124">Você pode editar as configurações na política global ou criar e atribuir uma ou mais políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="18efe-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="18efe-125">Os usuários terão a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="18efe-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="18efe-126">O botão detalhes da reunião estará disponível se um usuário tiver as licenças de conferência de áudio habilitadas ou se o usuário permitir a conferência de áudio, caso contrário, os detalhes da reunião não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="18efe-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="18efe-127">Criar uma política de reunião personalizada</span><span class="sxs-lookup"><span data-stu-id="18efe-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="18efe-128">Na barra de navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Reuniões** > **Políticas de Reunião**.</span><span class="sxs-lookup"><span data-stu-id="18efe-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="18efe-129">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="18efe-129">Click **Add**.</span></span>
3. <span data-ttu-id="18efe-130">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="18efe-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="18efe-131">O nome não pode conter caracteres especiais ou ter mais de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18efe-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="18efe-132">Escolha as configurações que deseja.</span><span class="sxs-lookup"><span data-stu-id="18efe-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="18efe-133">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18efe-133">Click **Save**.</span></span>

<span data-ttu-id="18efe-134">Por exemplo, digamos que você tenha um grupo de usuários e queira limitar a quantidade de largura de banda que a reunião exigiria.</span><span class="sxs-lookup"><span data-stu-id="18efe-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="18efe-135">Você criaria uma nova política personalizada chamada "Largura de banda limitada" e desativaria as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="18efe-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="18efe-136">Em **Áudio e vídeo**:</span><span class="sxs-lookup"><span data-stu-id="18efe-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="18efe-137">Desative a opção Permitir gravação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="18efe-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="18efe-138">Desative a opção Permitir vídeo IP.</span><span class="sxs-lookup"><span data-stu-id="18efe-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="18efe-139">Em **Compartilhamento de conteúdo**:</span><span class="sxs-lookup"><span data-stu-id="18efe-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="18efe-140">Desative o modo de compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="18efe-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="18efe-141">Desative a opção Permitir quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="18efe-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="18efe-142">Desative a opção Permitir anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="18efe-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="18efe-143">Em seguida, atribua a política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="18efe-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="18efe-144">Editar uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="18efe-144">Edit a meeting policy</span></span>

<span data-ttu-id="18efe-145">Você pode editar a política global e as políticas personalizadas que criar.</span><span class="sxs-lookup"><span data-stu-id="18efe-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="18efe-146">Na barra de navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Reuniões** > **Políticas de Reunião**.</span><span class="sxs-lookup"><span data-stu-id="18efe-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="18efe-147">Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="18efe-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="18efe-148">A partir daqui, faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="18efe-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="18efe-149">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18efe-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="18efe-150">Um usuário pode receber apenas uma política de reunião por vez.</span><span class="sxs-lookup"><span data-stu-id="18efe-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="18efe-151">Atribuir uma política de reunião aos usuários</span><span class="sxs-lookup"><span data-stu-id="18efe-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="18efe-152">Você não pode excluir uma política se usuários estiverem atribuídos a ela.</span><span class="sxs-lookup"><span data-stu-id="18efe-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="18efe-153">Primeiro, você deve atribuir uma política diferente a todos os usuários afetados. em seguida, é possível excluir a política original.</span><span class="sxs-lookup"><span data-stu-id="18efe-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="18efe-154">Configurações de política de reunião</span><span class="sxs-lookup"><span data-stu-id="18efe-154">Meeting policy settings</span></span>

<span data-ttu-id="18efe-155">Ao selecionar uma política existente na página de **Políticas de reunião** ou selecionar **Adicionar** para adicionar uma nova política, você pode definir as configurações para o seguinte.</span><span class="sxs-lookup"><span data-stu-id="18efe-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="18efe-156">Geral</span><span class="sxs-lookup"><span data-stu-id="18efe-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="18efe-157">Áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="18efe-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="18efe-158">Compartilhamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="18efe-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="18efe-159">Participantes e convidados</span><span class="sxs-lookup"><span data-stu-id="18efe-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="18efe-160">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="18efe-160">Related topics</span></span>

- [<span data-ttu-id="18efe-161">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="18efe-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="18efe-162">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18efe-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="18efe-163">Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários</span><span class="sxs-lookup"><span data-stu-id="18efe-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)