---
title: Restrições de chamadas de saída-conferências de áudio & chamadas PSTN
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
- seo-marvel-mar2020
description: Os administradores podem controlar o tipo de conferência de áudio e as chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: 84acbed4017a709b63e657f12ef0bbe3c1eb620c
ms.sourcegitcommit: 5a88788bd0a0b2ccbc5b977b38dcfe4681cd5d10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "44278174"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="c84d9-103">Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário</span><span class="sxs-lookup"><span data-stu-id="c84d9-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="c84d9-104">Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c84d9-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="c84d9-105">Os controles de chamada de saída podem ser aplicados por usuário e fornecer os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="c84d9-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="c84d9-106">Por padrão, ambos os controles são definidos para permitir chamadas internacionais e domésticas de saída.</span><span class="sxs-lookup"><span data-stu-id="c84d9-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="c84d9-107">Controle</span><span class="sxs-lookup"><span data-stu-id="c84d9-107">Control</span></span>|<span data-ttu-id="c84d9-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="c84d9-108">Description</span></span>|<span data-ttu-id="c84d9-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="c84d9-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c84d9-110">Chamadas PSTN de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="c84d9-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="c84d9-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="c84d9-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="c84d9-112">chamadas que são permitidas dentro</span><span class="sxs-lookup"><span data-stu-id="c84d9-112">calls that are allowed from within</span></span> </br><span data-ttu-id="c84d9-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="c84d9-113">meetings organized by a user.</span></span>|<span data-ttu-id="c84d9-114">Qualquer destino (padrão)</span><span class="sxs-lookup"><span data-stu-id="c84d9-114">Any destination (default)</span></span></br><span data-ttu-id="c84d9-115">No mesmo país ou região da organizor</span><span class="sxs-lookup"><span data-stu-id="c84d9-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="c84d9-116">Zona para apenas países ou regiões</span><span class="sxs-lookup"><span data-stu-id="c84d9-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="c84d9-117">Não permitir</span><span class="sxs-lookup"><span data-stu-id="c84d9-117">Don't allow</span></span>|
|<span data-ttu-id="c84d9-118">Chamadas PSTN do usuário final</span><span class="sxs-lookup"><span data-stu-id="c84d9-118">End user PSTN calls</span></span>|<span data-ttu-id="c84d9-119">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="c84d9-119">Restricts the type of calls</span></span> </br><span data-ttu-id="c84d9-120">que podem ser feitas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="c84d9-120">that can be made by a user.</span></span>|<span data-ttu-id="c84d9-121">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="c84d9-121">International and Domestic (default)</span></span></br><span data-ttu-id="c84d9-122">Doméstico</span><span class="sxs-lookup"><span data-stu-id="c84d9-122">Domestic</span></span></br><span data-ttu-id="c84d9-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c84d9-123">None</span></span>|

<span data-ttu-id="c84d9-124">Para descobrir quais são os países/regiões que são considerados zona A, consulte [zona a países/regiões](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="c84d9-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="c84d9-125">Uma chamada será considerada doméstica se o número discado estiver no mesmo país/região em que o Office 365 foi configurado para o organizador da reunião (no caso de videoconferência) ou o usuário final (no caso de chamadas PSTN do usuário final).</span><span class="sxs-lookup"><span data-stu-id="c84d9-125">A call is considered domestic if the number dialed is in the same country/region where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="c84d9-126">Restringir chamadas de saída de áudio videoconferência</span><span class="sxs-lookup"><span data-stu-id="c84d9-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="c84d9-127">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="c84d9-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c84d9-128">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c84d9-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c84d9-129">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c84d9-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c84d9-130">Ao lado de **conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c84d9-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="c84d9-131">Em **permissão de discagem de reuniões**, selecione a opção de restrição de discagem desejada.</span><span class="sxs-lookup"><span data-stu-id="c84d9-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="c84d9-132">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c84d9-132">Click **Save**.</span></span> 

<span data-ttu-id="c84d9-133">![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="c84d9-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="c84d9-134">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audio conferencing**  >  **usuários**de audioconferência e, em seguida, selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c84d9-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="c84d9-135">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c84d9-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="c84d9-136">Em **restrições a chamadas discadas de reuniões desse usuário**, selecione a opção de restrição discada que você deseja.</span><span class="sxs-lookup"><span data-stu-id="c84d9-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Restrições às opções de discagem](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="c84d9-138">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c84d9-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="c84d9-139">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c84d9-139">**Using PowerShell**</span></span>

<span data-ttu-id="c84d9-140">Restrições de chamadas de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo Restriction para cada.</span><span class="sxs-lookup"><span data-stu-id="c84d9-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="c84d9-141">A política não pode ser personalizada, em vez disso, há instâncias de política predefinidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="c84d9-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="c84d9-142">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamadas de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="c84d9-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="c84d9-143">(Observe que o cmdlet Grant não contém a palavra "online" como o cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="c84d9-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="c84d9-144">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="c84d9-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c84d9-145">Identity = ' marca: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="c84d9-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="c84d9-146">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário também pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="c84d9-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="c84d9-147">Identity = ' marca: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="c84d9-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="c84d9-148">O usuário na conferência pode discar para números domésticos e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="c84d9-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c84d9-149">Identity = ' marca: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="c84d9-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="c84d9-150">O usuário na conferência não pode fazer dial-out. Este usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="c84d9-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c84d9-151">Identity = ' marca: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="c84d9-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="c84d9-152">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="c84d9-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="c84d9-153">Identity = ' marca: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="c84d9-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="c84d9-154">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="c84d9-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c84d9-155">Identity = ' marca: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="c84d9-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="c84d9-156">O usuário na conferência pode discar para números domésticos e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="c84d9-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="c84d9-157">Identity = ' marca: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="c84d9-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="c84d9-158">O usuário na conferência pode discar para números domésticos e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="c84d9-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c84d9-159">Identity = ' marca: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="c84d9-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="c84d9-160">O usuário na conferência não pode fazer dial-out, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="c84d9-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="c84d9-161">Identity = ' marca: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="c84d9-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="c84d9-162">O usuário na conferência não pode fazer dial-out, e este usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="c84d9-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c84d9-163">Identity = ' marca: DialoutCPCZoneAPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="c84d9-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="c84d9-164">O usuário na conferência só pode discar para países e regiões da região, e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="c84d9-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c84d9-165">Identity = ' marca: DialoutCPCZoneAPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="c84d9-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="c84d9-166">O usuário na conferência só pode discar para países e regiões da região, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="c84d9-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="c84d9-167">Identity = ' marca: DialoutCPCZoneAPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="c84d9-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="c84d9-168">O usuário na conferência só pode discar para países e regiões da região, e esse usuário não pode fazer chamadas de saída para números PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="c84d9-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
