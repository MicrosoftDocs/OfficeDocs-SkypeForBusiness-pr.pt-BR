---
title: Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar o tipo de conferência de áudio e as chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: 830ab45178c10ab485d50aafd66a4bf5d4db9011
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836881"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="ecf1a-103">Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário</span><span class="sxs-lookup"><span data-stu-id="ecf1a-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="ecf1a-104">Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="ecf1a-105">Os controles de chamada de saída podem ser aplicados por usuário e fornecer os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="ecf1a-106">Por padrão, ambos os controles são definidos para permitir chamadas internacionais e domésticas de saída.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="ecf1a-107">Controle</span><span class="sxs-lookup"><span data-stu-id="ecf1a-107">Control</span></span>|<span data-ttu-id="ecf1a-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ecf1a-108">Description</span></span>|<span data-ttu-id="ecf1a-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="ecf1a-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ecf1a-110">Chamadas PSTN de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="ecf1a-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="ecf1a-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="ecf1a-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="ecf1a-112">chamadas que são permitidas dentro</span><span class="sxs-lookup"><span data-stu-id="ecf1a-112">calls that are allowed from within</span></span> </br><span data-ttu-id="ecf1a-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-113">meetings organized by a user.</span></span>|<span data-ttu-id="ecf1a-114">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="ecf1a-114">International and Domestic (default)</span></span></br><span data-ttu-id="ecf1a-115">Doméstico</span><span class="sxs-lookup"><span data-stu-id="ecf1a-115">Domestic</span></span></br><span data-ttu-id="ecf1a-116">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ecf1a-116">None</span></span>|
|<span data-ttu-id="ecf1a-117">Chamadas PSTN do usuário final</span><span class="sxs-lookup"><span data-stu-id="ecf1a-117">End user PSTN calls</span></span>|<span data-ttu-id="ecf1a-118">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="ecf1a-118">Restricts the type of calls</span></span> </br><span data-ttu-id="ecf1a-119">que podem ser feitas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-119">that can be made by a user.</span></span>|<span data-ttu-id="ecf1a-120">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="ecf1a-120">International and Domestic (default)</span></span></br><span data-ttu-id="ecf1a-121">Doméstico</span><span class="sxs-lookup"><span data-stu-id="ecf1a-121">Domestic</span></span></br><span data-ttu-id="ecf1a-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ecf1a-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="ecf1a-123">Uma chamada será considerada doméstica se o número discado estiver no mesmo país em que o Office 365 foi configurado para o organizador da reunião (no caso de videoconferência) ou o usuário final (no caso de chamadas PSTN do usuário final).</span><span class="sxs-lookup"><span data-stu-id="ecf1a-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="ecf1a-124">Restringir chamadas de saída de áudio videoconferência</span><span class="sxs-lookup"><span data-stu-id="ecf1a-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="ecf1a-125">![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ecf1a-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ecf1a-126">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ecf1a-127">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="ecf1a-128">Ao lado de **conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="ecf1a-129">Em **permissão de discagem de reuniões**, selecione a opção de restrição de discagem desejada.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="ecf1a-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-130">Click **Save**.</span></span> 

<span data-ttu-id="ecf1a-131">![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="ecf1a-131">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="ecf1a-132">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para**usuários**de **audioconferência** > e, em seguida, selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="ecf1a-133">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="ecf1a-134">Em **restrições a chamadas discadas de reuniões desse usuário**, selecione a opção de restrição discada que você deseja.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Restrições às opções de discagem](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="ecf1a-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="ecf1a-137">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ecf1a-137">**Using PowerShell**</span></span>

<span data-ttu-id="ecf1a-138">Restrições de chamadas de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo Restriction para cada.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="ecf1a-139">A política não pode ser personalizada, em vez disso, há instâncias de política predefinidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="ecf1a-140">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamadas de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="ecf1a-141">(Observe que o cmdlet Grant não contém a palavra "online" como o cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="ecf1a-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="ecf1a-142">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ecf1a-143">Identity = ' marca: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="ecf1a-144">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário também pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="ecf1a-145">Identity = ' marca: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="ecf1a-146">O usuário na conferência pode discar para números domésticos e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ecf1a-147">Identity = ' marca: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="ecf1a-148">O usuário na conferência não pode fazer dial-out. Este usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ecf1a-149">Identity = ' marca: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="ecf1a-150">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="ecf1a-151">Identity = ' marca: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="ecf1a-152">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ecf1a-153">Identity = ' marca: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="ecf1a-154">O usuário na conferência pode discar para números domésticos e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ecf1a-155">Identity = ' marca: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="ecf1a-156">O usuário na conferência pode discar para números domésticos e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ecf1a-157">Identity = ' marca: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="ecf1a-158">O usuário na conferência não pode fazer dial-out, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ecf1a-159">Identity = ' marca: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="ecf1a-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="ecf1a-160">O usuário na conferência não pode fazer dial-out, e este usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="ecf1a-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
