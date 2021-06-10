---
title: Restrições de chamada de saída - Audioconferência & chamadas PSTN
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
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526724"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="37ab3-103">Políticas de restrição de chamadas de saída de Audioconferências e Chamadas PSTN do usuário</span><span class="sxs-lookup"><span data-stu-id="37ab3-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="37ab3-104">Como administrador, você pode usar controles de chamada de saída para restringir o tipo de audioconferência e chamadas PSTN (Rede Telefônica Pública Comucionada) do usuário final que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="37ab3-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="37ab3-105">Os controles de chamada de saída podem ser aplicados por usuário ou por locatário e fornecem os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="37ab3-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="37ab3-106">Por padrão, ambos os controles são definidos para permitir chamadas de saída internacionais e domésticas.</span><span class="sxs-lookup"><span data-stu-id="37ab3-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="37ab3-107">Controle</span><span class="sxs-lookup"><span data-stu-id="37ab3-107">Control</span></span>|<span data-ttu-id="37ab3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="37ab3-108">Description</span></span>|<span data-ttu-id="37ab3-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="37ab3-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37ab3-110">Chamadas PSTN de audioconferência</span><span class="sxs-lookup"><span data-stu-id="37ab3-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="37ab3-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="37ab3-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="37ab3-112">chamadas permitidas de dentro</span><span class="sxs-lookup"><span data-stu-id="37ab3-112">calls that are allowed from within</span></span> </br><span data-ttu-id="37ab3-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="37ab3-113">meetings organized by a user.</span></span>|<span data-ttu-id="37ab3-114">Qualquer destino (padrão)</span><span class="sxs-lookup"><span data-stu-id="37ab3-114">Any destination (default)</span></span></br><span data-ttu-id="37ab3-115">No mesmo país ou região que o organizador</span><span class="sxs-lookup"><span data-stu-id="37ab3-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="37ab3-116">[Zona A somente países ou regiões](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="37ab3-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="37ab3-117">Não permitir</span><span class="sxs-lookup"><span data-stu-id="37ab3-117">Don't allow</span></span>|
|<span data-ttu-id="37ab3-118">Chamadas PSTN de usuário final</span><span class="sxs-lookup"><span data-stu-id="37ab3-118">End-user PSTN calls</span></span>|<span data-ttu-id="37ab3-119">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="37ab3-119">Restricts the type of calls</span></span> </br><span data-ttu-id="37ab3-120">que pode ser feita por um usuário.</span><span class="sxs-lookup"><span data-stu-id="37ab3-120">that can be made by a user.</span></span>|<span data-ttu-id="37ab3-121">Internacional e Doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="37ab3-121">International and Domestic (default)</span></span></br><span data-ttu-id="37ab3-122">Doméstico</span><span class="sxs-lookup"><span data-stu-id="37ab3-122">Domestic</span></span></br><span data-ttu-id="37ab3-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="37ab3-123">None</span></span>|

<span data-ttu-id="37ab3-124">Para descobrir quais países e regiões são considerados Zona A, consulte Zonas de país e [região para Audioconferência](audio-conferencing-zones.md).</span><span class="sxs-lookup"><span data-stu-id="37ab3-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="37ab3-125">Uma chamada é considerada doméstica se o número discado estiver no mesmo país em que Microsoft 365 ou Office 365 foi configurada para o organizador da reunião (no caso da audioconferência) ou para o usuário final (no caso de chamadas PSTN do usuário final).</span><span class="sxs-lookup"><span data-stu-id="37ab3-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="37ab3-126">Restringir chamadas de saída de audioconferência</span><span class="sxs-lookup"><span data-stu-id="37ab3-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="37ab3-127">![o logotipo Microsoft Teams ](media/teams-logo-30x30.png) **usando o Microsoft Teams de administração**</span><span class="sxs-lookup"><span data-stu-id="37ab3-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="37ab3-128">Na navegação à esquerda, selecione **Usuários** e selecione o nome de exibição do usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="37ab3-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="37ab3-129">Ao lado **de Audioconferência,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="37ab3-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="37ab3-130">Em **Discagem de reuniões,** selecione a opção de restrição de discagem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="37ab3-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="37ab3-131">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37ab3-131">Select **Save**.</span></span>

<span data-ttu-id="37ab3-132">![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="37ab3-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="37ab3-133">No centro **Skype for Business** de administração , na navegação à esquerda, vá para Usuários de Audioconferência e selecione o usuário na lista de usuários   >  disponíveis.</span><span class="sxs-lookup"><span data-stu-id="37ab3-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="37ab3-134">No painel Ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="37ab3-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="37ab3-135">Em **Restrições a discagem de reuniões desse usuário,** selecione a opção de restrição de discagem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="37ab3-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![As opções Restrições a discagem](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="37ab3-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37ab3-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="37ab3-138">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="37ab3-138">**Using PowerShell**</span></span>

<span data-ttu-id="37ab3-139">As restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy, que tem um atributo de restrição para cada um.</span><span class="sxs-lookup"><span data-stu-id="37ab3-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="37ab3-140">A política não pode ser personalizada, em vez disso, há instâncias de política pré-definidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="37ab3-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="37ab3-141">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e usar o comando a seguir para a instalação.</span><span class="sxs-lookup"><span data-stu-id="37ab3-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="37ab3-142">**De definir a política em um nível por usuário com o cmdlet a seguir.**</span><span class="sxs-lookup"><span data-stu-id="37ab3-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="37ab3-143">(O cmdlet Grant não contém a palavra "Online" como o cmdlet Get faz.)</span><span class="sxs-lookup"><span data-stu-id="37ab3-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="37ab3-144">**De definir a política no nível do locatário com o cmdlet a seguir.**</span><span class="sxs-lookup"><span data-stu-id="37ab3-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="37ab3-145">Todos os usuários do locatário que não têm nenhuma política de discagem atribuída receberão essa política.</span><span class="sxs-lookup"><span data-stu-id="37ab3-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="37ab3-146">Outros usuários permanecem com sua política atual.</span><span class="sxs-lookup"><span data-stu-id="37ab3-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="37ab3-147">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="37ab3-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="37ab3-148">Cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="37ab3-148">PowerShell cmdlet</span></span>|<span data-ttu-id="37ab3-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="37ab3-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="37ab3-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="37ab3-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="37ab3-151">O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário também pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="37ab3-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="37ab3-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="37ab3-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="37ab3-153">O usuário na conferência só pode discar para números domésticos, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="37ab3-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="37ab3-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="37ab3-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="37ab3-155">O usuário na conferência não pode discar. Esse usuário pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="37ab3-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="37ab3-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="37ab3-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="37ab3-157">O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.</span><span class="sxs-lookup"><span data-stu-id="37ab3-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="37ab3-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="37ab3-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="37ab3-159">O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="37ab3-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="37ab3-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="37ab3-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="37ab3-161">O usuário na conferência só pode discar para números domésticos, e esse usuário só pode fazer chamada de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="37ab3-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="37ab3-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="37ab3-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="37ab3-163">O usuário na conferência só pode discar para números domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="37ab3-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="37ab3-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="37ab3-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="37ab3-165">O usuário na conferência não pode discar e esse usuário só pode fazer chamada de saída para números PSTN domésticos.</span><span class="sxs-lookup"><span data-stu-id="37ab3-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="37ab3-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="37ab3-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="37ab3-167">O usuário na conferência não pode discar e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="37ab3-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="37ab3-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="37ab3-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="37ab3-169">O usuário na conferência só pode discar para zona [A](audio-conferencing-zones.md)países e regiões, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.</span><span class="sxs-lookup"><span data-stu-id="37ab3-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="37ab3-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="37ab3-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="37ab3-171">O usuário na conferência só pode discar para zona [A](audio-conferencing-zones.md)países e regiões, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.</span><span class="sxs-lookup"><span data-stu-id="37ab3-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="37ab3-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="37ab3-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="37ab3-173">O usuário na conferência só pode discar para zona [A](audio-conferencing-zones.md)países e regiões, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.</span><span class="sxs-lookup"><span data-stu-id="37ab3-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
