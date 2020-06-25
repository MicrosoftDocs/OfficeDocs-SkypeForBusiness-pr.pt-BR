---
title: Suporte para o uso da funcionalidade SEFAUtil no PowerShell no Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: saiba como usar o PowerShell para obter a funcionalidade do SEFAUtil no Skype for Business Server 2019 depois de instalar a atualização cumulativa 1.'
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868548"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="86f2e-103">Usando a funcionalidade do SEFAUtil por meio do PowerShell no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="86f2e-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="86f2e-104">SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Skype for Business Server e os agentes de assistência técnica configurem as configurações de separação de chamada, encaminhamento de chamada e de grupo em nome de um usuário do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="86f2e-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="86f2e-105">Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="86f2e-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="86f2e-106">Após a instalação da atualização cumulativa de julho do Skype for Business Server 2019, as seguintes funcionalidades que podem ser gerenciadas apenas por meio do SEFAUtil também poderão ser gerenciadas por meio do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="86f2e-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="86f2e-107">Configurações de encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="86f2e-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="86f2e-108">Configurações de delegação</span><span class="sxs-lookup"><span data-stu-id="86f2e-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="86f2e-109">Membros da equipe e configurações relacionadas</span><span class="sxs-lookup"><span data-stu-id="86f2e-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="86f2e-110">Configurações de encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="86f2e-110">Call forwarding settings</span></span>

<span data-ttu-id="86f2e-111">Os administradores podem alterar as configurações de encaminhamento de chamadas usando o seguinte cmdlet no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="86f2e-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="86f2e-112">Este cmdlet retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela.</span><span class="sxs-lookup"><span data-stu-id="86f2e-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="86f2e-113">Este cmdlet modifica as configurações de encaminhamento de chamadas do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="86f2e-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="86f2e-114">Este cmdlet retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela, em caso de êxito.</span><span class="sxs-lookup"><span data-stu-id="86f2e-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="86f2e-115">No caso de falha, uma mensagem de erro apropriada será mostrada.</span><span class="sxs-lookup"><span data-stu-id="86f2e-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="86f2e-116">Este cmdlet desabilita as configurações de encaminhamento de chamadas do usuário (mostramos dois exemplos de parâmetros diferentes aqui).</span><span class="sxs-lookup"><span data-stu-id="86f2e-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="86f2e-117">Este cmdlet modifica as configurações de encaminhamento de chamadas do usuário.</span><span class="sxs-lookup"><span data-stu-id="86f2e-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="86f2e-118">Este cmdlet modifica as configurações de toque simultâneo (novamente, com dois exemplos de parâmetro, um para não responder à caixa postal e o segundo que não está respondendo a outros).</span><span class="sxs-lookup"><span data-stu-id="86f2e-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="86f2e-119">Configurações de delegação</span><span class="sxs-lookup"><span data-stu-id="86f2e-119">Delegation settings</span></span>

<span data-ttu-id="86f2e-120">Os administradores podem alterar as configurações de delegação usando o seguinte cmdlet no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="86f2e-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="86f2e-121">Este cmdlet retorna um objeto da lista de representantes e exibe a lista de representante do usuário especificado, em caso de êxito.</span><span class="sxs-lookup"><span data-stu-id="86f2e-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="86f2e-122">No caso de falha, uma mensagem de erro apropriada será mostrada.</span><span class="sxs-lookup"><span data-stu-id="86f2e-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="86f2e-123">Este cmdlet modifica as configurações de delegação do usuário especificado, retorna um objeto da lista de representantes e exibe a lista de representantes, em caso de êxito.</span><span class="sxs-lookup"><span data-stu-id="86f2e-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="86f2e-124">No caso de falha, uma mensagem de erro apropriada será mostrada.</span><span class="sxs-lookup"><span data-stu-id="86f2e-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="86f2e-125">Este cmdlet adiciona ou remove um representante.</span><span class="sxs-lookup"><span data-stu-id="86f2e-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="86f2e-126">Este cmdlet define uma lista de representantes para delegados específicos.</span><span class="sxs-lookup"><span data-stu-id="86f2e-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="86f2e-127">Membros da equipe e configurações relacionadas</span><span class="sxs-lookup"><span data-stu-id="86f2e-127">Team members and related settings</span></span>

<span data-ttu-id="86f2e-128">Os administradores podem alterar os membros da equipe e as configurações relacionadas usando o seguinte cmdlet no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="86f2e-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="86f2e-129">Este cmdlet retorna um objeto que contém uma lista de membros da equipe e exibe o objeto na tela, em caso de êxito.</span><span class="sxs-lookup"><span data-stu-id="86f2e-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="86f2e-130">No caso de falha, uma mensagem de erro apropriada será mostrada.</span><span class="sxs-lookup"><span data-stu-id="86f2e-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="86f2e-131">Este cmdlet modifica a lista de membros da equipe do usuário especificado, retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela, em caso de êxito.</span><span class="sxs-lookup"><span data-stu-id="86f2e-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="86f2e-132">No caso de falha, uma mensagem de erro apropriada será mostrada.</span><span class="sxs-lookup"><span data-stu-id="86f2e-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="86f2e-133">Este cmdlet adiciona ou remove membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="86f2e-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="86f2e-134">Este cmdlet define uma lista de equipes para membros específicos.</span><span class="sxs-lookup"><span data-stu-id="86f2e-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="86f2e-135">Mais informações</span><span class="sxs-lookup"><span data-stu-id="86f2e-135">More information</span></span>

<span data-ttu-id="86f2e-136">Para implantações locais, os cmdlets introduzidos neste recurso só podem ser executados por membros dos seguintes grupos, conforme o nível de acesso especificado abaixo:</span><span class="sxs-lookup"><span data-stu-id="86f2e-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="86f2e-137">CsAdministrator – obter e definir para todos os cmdlets</span><span class="sxs-lookup"><span data-stu-id="86f2e-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="86f2e-138">CsVoiceAdministrator-Get e Set para todos os cmdlets</span><span class="sxs-lookup"><span data-stu-id="86f2e-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="86f2e-139">CsHelpDesk-obter todos os cmdlets</span><span class="sxs-lookup"><span data-stu-id="86f2e-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="86f2e-140">Para obter mais informações sobre essas funções de administrador, consulte [criar administradores do painel de controle do Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="86f2e-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="86f2e-141">O administrador pode acessar esses cmdlets de modo direto ou remoto fazendo logon em um computador servidor.</span><span class="sxs-lookup"><span data-stu-id="86f2e-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="86f2e-142">Para uma implantação híbrida, os administradores do Skype for Business devem ser capazes de chamar get e Set para todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="86f2e-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="86f2e-143">Para obter mais informações sobre a lista completa de funções, consulte [sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="86f2e-143">For more information about the full list of roles, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="86f2e-144">A descoberta automática do servidor deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="86f2e-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="86f2e-145">Nenhum requisito adicional de licenciamento será introduzido para uso dos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="86f2e-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
