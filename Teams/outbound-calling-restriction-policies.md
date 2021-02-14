---
title: Restrições de chamada de saída - AudioConferência & chamadas PSTN
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
description: Os administradores podem controlar o tipo de audioconferência e chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908650"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="6028c-103">Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário</span><span class="sxs-lookup"><span data-stu-id="6028c-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="6028c-104">Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6028c-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="6028c-105">Os controles de chamada de saída podem ser aplicados por usuário e fornecem os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="6028c-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="6028c-106">Por padrão, os dois controles são definidos para permitir chamadas internacionais e domésticas.</span><span class="sxs-lookup"><span data-stu-id="6028c-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="6028c-107">Controle</span><span class="sxs-lookup"><span data-stu-id="6028c-107">Control</span></span>|<span data-ttu-id="6028c-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="6028c-108">Description</span></span>|<span data-ttu-id="6028c-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="6028c-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6028c-110">Chamadas PSTN de audioconferência</span><span class="sxs-lookup"><span data-stu-id="6028c-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="6028c-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="6028c-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="6028c-112">chamadas que são permitidas a partir de dentro</span><span class="sxs-lookup"><span data-stu-id="6028c-112">calls that are allowed from within</span></span> </br><span data-ttu-id="6028c-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="6028c-113">meetings organized by a user.</span></span>|<span data-ttu-id="6028c-114">Qualquer destino (padrão)</span><span class="sxs-lookup"><span data-stu-id="6028c-114">Any destination (default)</span></span></br><span data-ttu-id="6028c-115">No mesmo país ou região que o organizador</span><span class="sxs-lookup"><span data-stu-id="6028c-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="6028c-116">[Zona A somente países ou regiões](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="6028c-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="6028c-117">Não permitir</span><span class="sxs-lookup"><span data-stu-id="6028c-117">Don't allow</span></span>|
|<span data-ttu-id="6028c-118">Chamadas PSTN do usuário final</span><span class="sxs-lookup"><span data-stu-id="6028c-118">End user PSTN calls</span></span>|<span data-ttu-id="6028c-119">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="6028c-119">Restricts the type of calls</span></span> </br><span data-ttu-id="6028c-120">que podem ser feitas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="6028c-120">that can be made by a user.</span></span>|<span data-ttu-id="6028c-121">Internacional e Doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="6028c-121">International and Domestic (default)</span></span></br><span data-ttu-id="6028c-122">Doméstico</span><span class="sxs-lookup"><span data-stu-id="6028c-122">Domestic</span></span></br><span data-ttu-id="6028c-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6028c-123">None</span></span>|

<span data-ttu-id="6028c-124">Para descobrir quais países e regiões são considerados Zona A, confira as zonas país e [região para Audioconferência.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="6028c-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="6028c-125">Uma chamada é considerada doméstica se o número discado estiver no mesmo país em que o Microsoft 365 ou o Office 365 foi configurada para o organizador da reunião (no caso de audioconferência) ou para o usuário final (no caso de chamadas PSTN do usuário final).</span><span class="sxs-lookup"><span data-stu-id="6028c-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="6028c-126">Restringir chamadas de saída de audioconferência</span><span class="sxs-lookup"><span data-stu-id="6028c-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="6028c-127">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="6028c-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6028c-128">Na navegação à esquerda, clique em **Usuários** e clique no nome de exibição do usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6028c-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="6028c-129">Ao lado **de Audioconferência,** clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="6028c-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="6028c-130">Em **Discagem de reuniões,** selecione a opção de restrição de discagem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="6028c-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="6028c-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6028c-131">Click **Save**.</span></span> 

<span data-ttu-id="6028c-132">![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="6028c-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="6028c-133">No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para Usuários de **Audioconferência** e selecione o usuário na lista  >  de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6028c-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="6028c-134">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6028c-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="6028c-135">Em **Restrições para discagem de reuniões** deste usuário, selecione a opção de restrição de discagem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="6028c-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![As restrições às opções de discagem](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="6028c-137">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6028c-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="6028c-138">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6028c-138">**Using PowerShell**</span></span>

<span data-ttu-id="6028c-139">As restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy, que tem um atributo de restrição para cada um.</span><span class="sxs-lookup"><span data-stu-id="6028c-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="6028c-140">A política não pode ser personalizada, em vez disso, há instâncias de política pré-definidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="6028c-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="6028c-141">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy de saída.</span><span class="sxs-lookup"><span data-stu-id="6028c-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="6028c-142">(Observe que o cmdlet Grant não contém a palavra "Online" como o cmdlet Obter.)</span><span class="sxs-lookup"><span data-stu-id="6028c-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="6028c-143">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="6028c-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6028c-144">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="6028c-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="6028c-145">O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário também pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="6028c-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="6028c-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="6028c-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="6028c-147">O usuário na conferência só pode discar para números domésticos, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="6028c-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="6028c-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="6028c-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="6028c-149">O usuário da conferência não pode fazer discagem. Esse usuário pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="6028c-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="6028c-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="6028c-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="6028c-151">O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.</span><span class="sxs-lookup"><span data-stu-id="6028c-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="6028c-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="6028c-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="6028c-153">O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="6028c-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="6028c-154">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="6028c-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="6028c-155">O usuário na conferência só pode discar para números domésticos, e esse usuário só pode fazer chamada de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="6028c-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="6028c-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="6028c-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="6028c-157">O usuário na conferência só pode discar para números domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="6028c-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="6028c-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="6028c-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="6028c-159">O usuário da conferência não pode fazer discagem, e esse usuário só pode fazer chamada de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="6028c-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="6028c-160">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="6028c-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="6028c-161">O usuário da conferência não pode fazer discagem, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="6028c-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="6028c-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="6028c-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="6028c-163">O usuário na conferência só pode discar para países e regiões da Zona [A,](audio-conferencing-zones.md)e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="6028c-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="6028c-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="6028c-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="6028c-165">O usuário na conferência só pode discar para países e regiões da Zona [A,](audio-conferencing-zones.md)e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.</span><span class="sxs-lookup"><span data-stu-id="6028c-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="6028c-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="6028c-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="6028c-167">O usuário na conferência só pode discar para países e regiões da Zona [A,](audio-conferencing-zones.md)e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="6028c-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
