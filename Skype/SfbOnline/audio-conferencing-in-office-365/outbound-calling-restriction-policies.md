---
title: Saída diretivas de restrição de chamada para chamadas PSTN de conferência de áudio e usuário
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
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários.
ms.openlocfilehash: 0533a15d6c60720f37c859f110b30af617d95774
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703420"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="9b049-103">Saída diretivas de restrição de chamada para chamadas PSTN de conferência de áudio e usuário</span><span class="sxs-lookup"><span data-stu-id="9b049-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="9b049-104">Como administrador, você pode usar controles de chamada de saída para restringir o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9b049-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="9b049-105">Controles de chamada de saída podem ser aplicados em uma base por usuário e fornecem os seguintes dois controles para restringir independentemente de cada tipo de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="9b049-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="9b049-106">Por padrão, ambos os controles são definidos para permitir que as chamadas de saída nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="9b049-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="9b049-107">Controle</span><span class="sxs-lookup"><span data-stu-id="9b049-107">Control</span></span>|<span data-ttu-id="9b049-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b049-108">Description</span></span>|<span data-ttu-id="9b049-109">Opções de controle</span><span class="sxs-lookup"><span data-stu-id="9b049-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b049-110">Chamadas PSTN de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="9b049-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="9b049-111">Restringe o tipo de saída</span><span class="sxs-lookup"><span data-stu-id="9b049-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="9b049-112">chamadas que são permitidas de dentro</span><span class="sxs-lookup"><span data-stu-id="9b049-112">calls that are allowed from within</span></span> </br><span data-ttu-id="9b049-113">reuniões organizadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="9b049-113">meetings organized by a user.</span></span>|<span data-ttu-id="9b049-114">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="9b049-114">International and Domestic (default)</span></span></br><span data-ttu-id="9b049-115">Doméstico</span><span class="sxs-lookup"><span data-stu-id="9b049-115">Domestic</span></span></br><span data-ttu-id="9b049-116">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9b049-116">None</span></span>|
|<span data-ttu-id="9b049-117">Chamadas PSTN de usuário final</span><span class="sxs-lookup"><span data-stu-id="9b049-117">End user PSTN calls</span></span>|<span data-ttu-id="9b049-118">Restringe o tipo de chamadas</span><span class="sxs-lookup"><span data-stu-id="9b049-118">Restricts the type of calls</span></span> </br><span data-ttu-id="9b049-119">que podem ser feitas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="9b049-119">that can be made by a user.</span></span>|<span data-ttu-id="9b049-120">Internacional e doméstico (padrão)</span><span class="sxs-lookup"><span data-stu-id="9b049-120">International and Domestic (default)</span></span></br><span data-ttu-id="9b049-121">Doméstico</span><span class="sxs-lookup"><span data-stu-id="9b049-121">Domestic</span></span></br><span data-ttu-id="9b049-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9b049-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="9b049-123">Uma chamada é considerada domésticas se o número de telefone chamado esteja no mesmo país que o país que tiver sido definido no Office 365 para o organizador da reunião (no caso de serviços de audioconferência) ou o usuário final (no caso de chamadas da PSTN de usuário final).</span><span class="sxs-lookup"><span data-stu-id="9b049-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="9b049-124">Restringir as chamadas de saída de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="9b049-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="9b049-125">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="9b049-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9b049-126">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9b049-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9b049-127">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9b049-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9b049-128">Clique no menu ao lado de **Pontes de conferência**e clique em **Editar** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9b049-128">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="9b049-129">No painel de **provedor de ponte de conferência** , em **restrições a serem dial-outs de reuniões deste usuário**, selecione a opção de restrição de discagem desejado.</span><span class="sxs-lookup"><span data-stu-id="9b049-129">In the **Conference bridge provider** pane, under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="9b049-130">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9b049-130">Click **Apply**.</span></span> 

<span data-ttu-id="9b049-131">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="9b049-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="9b049-132">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9b049-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="9b049-133">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9b049-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="9b049-134">Em **restrições a serem dial-outs de reuniões deste usuário**, selecione a opção de discagem restrição desejada.</span><span class="sxs-lookup"><span data-stu-id="9b049-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![As restrições às opções de discagem-outs](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="9b049-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9b049-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="9b049-137">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9b049-137">**Using PowerShell**</span></span>

<span data-ttu-id="9b049-138">Restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo de restrição para cada um.</span><span class="sxs-lookup"><span data-stu-id="9b049-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="9b049-139">A política não pode ser personalizada, em vez disso, há instâncias de diretiva predefinidas para cada combinação das configurações.</span><span class="sxs-lookup"><span data-stu-id="9b049-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="9b049-140">Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="9b049-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="9b049-141">(Observe que o cmdlet Grant não contêm a palavra "Online" como o cmdlet Get faz.)</span><span class="sxs-lookup"><span data-stu-id="9b049-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="9b049-142">A tabela a seguir fornece uma visão geral de cada política.</span><span class="sxs-lookup"><span data-stu-id="9b049-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9b049-143">Identidade = 'tag: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9b049-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="9b049-144">Usuário na conferência pode discar para números nacionais e internacionais e esse usuário também pode fazer chamadas de saída para números nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="9b049-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="9b049-145">Identidade = 'tag: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9b049-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="9b049-146">Usuário na conferência só pode discar para números nacionais e esse usuário pode fazer chamadas de saída para números nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="9b049-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="9b049-147">Identidade = 'tag: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9b049-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="9b049-148">Usuário na conferência não pode fazer qualquer dial-out. Esse usuário pode fazer chamadas de saída para números nacionais e internacionais.</span><span class="sxs-lookup"><span data-stu-id="9b049-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="9b049-149">Identidade = 'tag: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9b049-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="9b049-150">Usuário na conferência pode discar para números nacionais e internacionais e esse usuário só pode fazer chamadas de saída para o número PSTN doméstica.</span><span class="sxs-lookup"><span data-stu-id="9b049-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="9b049-151">Identidade = 'tag: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9b049-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="9b049-152">Usuário na conferência pode discar para números nacionais e internacionais e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.</span><span class="sxs-lookup"><span data-stu-id="9b049-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="9b049-153">Identidade = 'tag: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9b049-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="9b049-154">Usuário na conferência só pode discar para números nacionais e esse usuário só pode fazer chamadas de saída aos números PSTN domésticas.</span><span class="sxs-lookup"><span data-stu-id="9b049-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="9b049-155">Identidade = 'tag: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9b049-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="9b049-156">Usuário na conferência só pode discar para números nacionais e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.</span><span class="sxs-lookup"><span data-stu-id="9b049-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="9b049-157">Identidade = 'tag: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9b049-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="9b049-158">Usuário na conferência não puder fazer qualquer discagem externa e esse usuário só pode fazer chamadas de saída aos números PSTN domésticas.</span><span class="sxs-lookup"><span data-stu-id="9b049-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="9b049-159">Identidade = 'tag: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9b049-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="9b049-160">Usuário na conferência não puder fazer qualquer discagem externa e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.</span><span class="sxs-lookup"><span data-stu-id="9b049-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
