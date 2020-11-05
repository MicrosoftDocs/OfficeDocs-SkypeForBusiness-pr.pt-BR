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
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908650"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="d7794-103">Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário</span><span class="sxs-lookup"><span data-stu-id="d7794-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="d7794-104">Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d7794-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="d7794-105">Os controles de chamada de saída podem ser aplicados por usuário e fornecer os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="d7794-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="d7794-106">Por padrão, ambos os controles são definidos para permitir chamadas internacionais e domésticas de saída.</span><span class="sxs-lookup"><span data-stu-id="d7794-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="d7794-107">Controle</span><span class="sxs-lookup"><span data-stu-id="d7794-107">Control</span></span>|<span data-ttu-id="d7794-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7794-108">Description</span></span>|<span data-ttu-id="d7794-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="d7794-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7794-110">Chamadas PSTN de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="d7794-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="d7794-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="d7794-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="d7794-112">chamadas que são permitidas dentro</span><span class="sxs-lookup"><span data-stu-id="d7794-112">calls that are allowed from within</span></span> </br><span data-ttu-id="d7794-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="d7794-113">meetings organized by a user.</span></span>|<span data-ttu-id="d7794-114">Qualquer destino (padrão)</span><span class="sxs-lookup"><span data-stu-id="d7794-114">Any destination (default)</span></span></br><span data-ttu-id="d7794-115">No mesmo país ou região do organizador</span><span class="sxs-lookup"><span data-stu-id="d7794-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="d7794-116">[Zona para apenas países ou regiões](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="d7794-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="d7794-117">Não permitir</span><span class="sxs-lookup"><span data-stu-id="d7794-117">Don't allow</span></span>|
|<span data-ttu-id="d7794-118">Chamadas PSTN do usuário final</span><span class="sxs-lookup"><span data-stu-id="d7794-118">End user PSTN calls</span></span>|<span data-ttu-id="d7794-119">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="d7794-119">Restricts the type of calls</span></span> </br><span data-ttu-id="d7794-120">que podem ser feitas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="d7794-120">that can be made by a user.</span></span>|<span data-ttu-id="d7794-121">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="d7794-121">International and Domestic (default)</span></span></br><span data-ttu-id="d7794-122">Doméstico</span><span class="sxs-lookup"><span data-stu-id="d7794-122">Domestic</span></span></br><span data-ttu-id="d7794-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7794-123">None</span></span>|

<span data-ttu-id="d7794-124">Para descobrir quais países e regiões são considerados zona A, consulte [zonas de país e região para videoconferências](audio-conferencing-zones.md).</span><span class="sxs-lookup"><span data-stu-id="d7794-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d7794-125">Uma chamada será considerada doméstica se o número discado estiver no mesmo país em que o Microsoft 365 ou o Office 365 foi configurado para o organizador da reunião (no caso de videoconferência) ou o usuário final (no caso de chamadas PSTN do usuário final).</span><span class="sxs-lookup"><span data-stu-id="d7794-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="d7794-126">Restringir chamadas de saída de áudio videoconferência</span><span class="sxs-lookup"><span data-stu-id="d7794-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="d7794-127">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d7794-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d7794-128">Na navegação à esquerda, clique em **usuários** e, em seguida, clique no nome para exibição do usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d7794-128">In the left navigation, click **Users** , and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="d7794-129">Ao lado de **conferência de áudio** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d7794-129">Next to **Audio Conferencing** , click **Edit**.</span></span>

4. <span data-ttu-id="d7794-130">Em **discagem de reuniões** , selecione a opção de restrição de discagem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="d7794-130">Under **Dial-out from meetings** , select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="d7794-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d7794-131">Click **Save**.</span></span> 

<span data-ttu-id="d7794-132">![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d7794-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d7794-133">No **centro de administração do Skype for Business** , no painel de navegação esquerdo, vá para **Audio conferencing**  >  **usuários** de audioconferência e, em seguida, selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d7794-133">In the **Skype for Business admin center** , in the left navigation, go to **Audio conferencing** > **Users** , and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d7794-134">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d7794-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="d7794-135">Em **restrições a chamadas discadas de reuniões desse usuário** , selecione a opção de restrição discada que você deseja.</span><span class="sxs-lookup"><span data-stu-id="d7794-135">Under **Restrictions to dial-outs from meetings of this user** , select the dial-out restriction option you want.</span></span>

      ![Restrições às opções de discagem](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="d7794-137">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d7794-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="d7794-138">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d7794-138">**Using PowerShell**</span></span>

<span data-ttu-id="d7794-139">Restrições de chamadas de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo Restriction para cada.</span><span class="sxs-lookup"><span data-stu-id="d7794-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="d7794-140">A política não pode ser personalizada, em vez disso, há instâncias de política predefinidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="d7794-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="d7794-141">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamadas de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="d7794-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="d7794-142">(Observe que o cmdlet Grant não contém a palavra "online" como o cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="d7794-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="d7794-143">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="d7794-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d7794-144">Identity = ' marca: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d7794-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="d7794-145">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário também pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="d7794-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="d7794-146">Identity = ' marca: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d7794-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="d7794-147">O usuário na conferência pode discar para números domésticos e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="d7794-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="d7794-148">Identity = ' marca: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d7794-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="d7794-149">O usuário na conferência não pode fazer dial-out. Este usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="d7794-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="d7794-150">Identity = ' marca: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d7794-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="d7794-151">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="d7794-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="d7794-152">Identity = ' marca: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d7794-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="d7794-153">O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="d7794-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="d7794-154">Identity = ' marca: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d7794-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="d7794-155">O usuário na conferência pode discar para números domésticos e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="d7794-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="d7794-156">Identity = ' marca: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d7794-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="d7794-157">O usuário na conferência pode discar para números domésticos e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="d7794-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="d7794-158">Identity = ' marca: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d7794-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="d7794-159">O usuário na conferência não pode fazer dial-out, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="d7794-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="d7794-160">Identity = ' marca: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d7794-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="d7794-161">O usuário na conferência não pode fazer dial-out, e este usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.</span><span class="sxs-lookup"><span data-stu-id="d7794-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="d7794-162">Identity = ' marca: DialoutCPCZoneAPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d7794-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="d7794-163">O usuário na conferência só pode discar para [países e regiões da região](audio-conferencing-zones.md), e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.</span><span class="sxs-lookup"><span data-stu-id="d7794-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="d7794-164">Identity = ' marca: DialoutCPCZoneAPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d7794-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="d7794-165">O usuário na conferência só pode discar para [países e regiões da região](audio-conferencing-zones.md), e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="d7794-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="d7794-166">Identity = ' marca: DialoutCPCZoneAPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d7794-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="d7794-167">O usuário na conferência só pode discar para [países e regiões da região](audio-conferencing-zones.md), e esse usuário não pode fazer chamadas de saída para números PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="d7794-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
