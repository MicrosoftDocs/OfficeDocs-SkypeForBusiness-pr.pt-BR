---
title: Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários.
ms.openlocfilehash: 6096816ef9fb98811ec3ebed5a56b90a90b58c29
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490571"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="dc408-103">Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário</span><span class="sxs-lookup"><span data-stu-id="dc408-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="dc408-104">Como administrador, você pode usar controles de chamada de saída para restringir o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="dc408-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="dc408-105">Controles de chamada de saída podem ser aplicados em uma base por usuário e fornecem os seguintes dois controles para restringir independentemente de cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="dc408-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="dc408-106">Por padrão, ambos os controles são definidos para permitir que as chamadas de saída nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="dc408-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="dc408-107">Controle</span><span class="sxs-lookup"><span data-stu-id="dc408-107">Control</span></span>|<span data-ttu-id="dc408-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="dc408-108">Description</span></span>|<span data-ttu-id="dc408-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="dc408-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc408-110">Chamadas PSTN de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="dc408-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="dc408-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="dc408-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="dc408-112">chamadas que são permitidas de dentro</span><span class="sxs-lookup"><span data-stu-id="dc408-112">calls that are allowed from within</span></span> </br><span data-ttu-id="dc408-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="dc408-113">meetings organized by a user.</span></span>|<span data-ttu-id="dc408-114">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="dc408-114">International and Domestic (default)</span></span></br><span data-ttu-id="dc408-115">Doméstico</span><span class="sxs-lookup"><span data-stu-id="dc408-115">Domestic</span></span></br><span data-ttu-id="dc408-116">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc408-116">None</span></span>|
|<span data-ttu-id="dc408-117">Chamadas PSTN de usuário final</span><span class="sxs-lookup"><span data-stu-id="dc408-117">End user PSTN calls</span></span>|<span data-ttu-id="dc408-118">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="dc408-118">Restricts the type of calls</span></span> </br><span data-ttu-id="dc408-119">que podem ser feitas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="dc408-119">that can be made by a user.</span></span>|<span data-ttu-id="dc408-120">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="dc408-120">International and Domestic (default)</span></span></br><span data-ttu-id="dc408-121">Doméstico</span><span class="sxs-lookup"><span data-stu-id="dc408-121">Domestic</span></span></br><span data-ttu-id="dc408-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc408-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="dc408-123">Uma chamada é considerada domésticas se o número de telefone chamado esteja no mesmo país que o país que tiver sido definido no Office 365 para o organizador da reunião (no caso de serviços de audioconferência) ou o usuário final (no caso de chamadas da PSTN de usuário final).</span><span class="sxs-lookup"><span data-stu-id="dc408-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="dc408-124">Restringir as chamadas de saída de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="dc408-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="dc408-125">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="dc408-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="dc408-126">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dc408-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="dc408-127">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dc408-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="dc408-128">Ao lado de **Conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dc408-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="dc408-129">Em **permissão de discagem de reuniões**, selecione a opção de discagem restrição desejada.</span><span class="sxs-lookup"><span data-stu-id="dc408-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="dc408-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dc408-130">Click **Save**.</span></span> 

<span data-ttu-id="dc408-131">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="dc408-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="dc408-132">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dc408-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="dc408-133">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dc408-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="dc408-134">Em **restrições a serem dial-outs de reuniões deste usuário**, selecione a opção de discagem restrição desejada.</span><span class="sxs-lookup"><span data-stu-id="dc408-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![As restrições às opções de discagem-outs](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="dc408-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dc408-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="dc408-137">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dc408-137">**Using PowerShell**</span></span>

<span data-ttu-id="dc408-138">Restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo de restrição para cada um.</span><span class="sxs-lookup"><span data-stu-id="dc408-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="dc408-139">A política não pode ser personalizada, em vez disso, há instâncias de diretiva predefinidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="dc408-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="dc408-140">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="dc408-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="dc408-141">(Observe que o cmdlet Grant não contêm a palavra "Online" como o cmdlet Get faz.)</span><span class="sxs-lookup"><span data-stu-id="dc408-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="dc408-142">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="dc408-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dc408-143">Identidade = 'tag: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="dc408-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="dc408-144">Usuário na conferência pode discar para números nacionais e internacionais e esse usuário também pode fazer chamadas de saída para números nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="dc408-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="dc408-145">Identidade = 'tag: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="dc408-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="dc408-146">Usuário na conferência só pode discar para números nacionais e esse usuário pode fazer chamadas de saída para números nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="dc408-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="dc408-147">Identidade = 'tag: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="dc408-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="dc408-148">Usuário na conferência não pode fazer qualquer dial-out. Esse usuário pode fazer chamadas de saída para números nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="dc408-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="dc408-149">Identidade = 'tag: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="dc408-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="dc408-150">Usuário na conferência pode discar para números nacionais e internacionais e esse usuário só pode fazer chamadas de saída para o número PSTN doméstica.</span><span class="sxs-lookup"><span data-stu-id="dc408-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="dc408-151">Identidade = 'tag: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="dc408-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="dc408-152">Usuário na conferência pode discar para números nacionais e internacionais e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.</span><span class="sxs-lookup"><span data-stu-id="dc408-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="dc408-153">Identidade = 'tag: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="dc408-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="dc408-154">Usuário na conferência só pode discar para números nacionais e esse usuário só pode fazer chamadas de saída aos números PSTN domésticas.</span><span class="sxs-lookup"><span data-stu-id="dc408-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="dc408-155">Identidade = 'tag: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="dc408-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="dc408-156">Usuário na conferência só pode discar para números nacionais e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.</span><span class="sxs-lookup"><span data-stu-id="dc408-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="dc408-157">Identidade = 'tag: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="dc408-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="dc408-158">Usuário na conferência não puder fazer qualquer discagem externa e esse usuário só pode fazer chamadas de saída aos números PSTN domésticas.</span><span class="sxs-lookup"><span data-stu-id="dc408-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="dc408-159">Identidade = 'tag: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="dc408-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="dc408-160">Usuário na conferência não puder fazer qualquer discagem externa e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.</span><span class="sxs-lookup"><span data-stu-id="dc408-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
