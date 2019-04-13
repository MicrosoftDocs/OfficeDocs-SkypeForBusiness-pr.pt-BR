---
title: Política de chamada no Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Saiba mais sobre as configurações de política de chamada do Teams da Microsoft.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860254"
---
<a name="calling-policy-in-microsoft-teams"></a><span data-ttu-id="d8444-103">Política de chamada no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8444-103">Calling policy in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="d8444-104">No Microsoft Teams, chamando políticas controlam quais chamadas e recursos de encaminhamento de chamadas estão disponíveis aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d8444-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="d8444-105">As políticas de chamada determinam se um usuário pode fazer chamadas privadas, use o encaminhamento de chamadas ou usam rotear as chamadas para caixa postal, chamadas de envio para grupos de chamada, toque para outros usuários ou números de telefone externo simultâneo, delegação para chamadas de entrada e saídas, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d8444-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="d8444-106">Uma política global de padrão é criada automaticamente, mas os administradores também podem criar e atribuir políticas personalizadas de chamada.</span><span class="sxs-lookup"><span data-stu-id="d8444-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="d8444-107">Configurações de política de chamada</span><span class="sxs-lookup"><span data-stu-id="d8444-107">Calling policy settings</span></span>

|<span data-ttu-id="d8444-108">Configuração de política de chamada</span><span class="sxs-lookup"><span data-stu-id="d8444-108">Calling policy setting</span></span> | <span data-ttu-id="d8444-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="d8444-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="d8444-110">Usuário pode fazer chamadas particulares</span><span class="sxs-lookup"><span data-stu-id="d8444-110">User can make private calls</span></span> | <span data-ttu-id="d8444-111">Controla a todos os recursos de chamada em equipes.</span><span class="sxs-lookup"><span data-stu-id="d8444-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="d8444-112">Desativar Isso desativará todas as funcionalidades de chamada em equipes.</span><span class="sxs-lookup"><span data-stu-id="d8444-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="d8444-113">Encaminhamento de chamadas e toque simultâneo para outros usuários</span><span class="sxs-lookup"><span data-stu-id="d8444-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="d8444-114">Controla se as chamadas de entrada podem ser encaminhadas para outros usuários ou podem ligar para outra pessoa ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d8444-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="d8444-115">Encaminhamento de chamadas e toque simultâneo aos números de telefone externo</span><span class="sxs-lookup"><span data-stu-id="d8444-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="d8444-116">Controla se as chamadas de entrada podem ser encaminhadas para um número externo ou ligar para um número externo ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d8444-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="d8444-117">Caixa postal está disponível para roteamento de chamadas de entrada para os usuários</span><span class="sxs-lookup"><span data-stu-id="d8444-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="d8444-118">Chamadas de entrada permite que sejam enviadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d8444-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="d8444-119">Opções válidas são **sempre habilitada**, **sempre desabilitados**ou **usuário controlados**.</span><span class="sxs-lookup"><span data-stu-id="d8444-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="d8444-120">Chamadas de entrada podem ser roteadas para chamar a grupos</span><span class="sxs-lookup"><span data-stu-id="d8444-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="d8444-121">Controla se as chamadas recebidas podem ser encaminhadas para um grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="d8444-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="d8444-122">Permite a delegação de chamadas de entrada e saídas</span><span class="sxs-lookup"><span data-stu-id="d8444-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="d8444-123">Permite que as chamadas de entrada sejam roteadas para os representantes; permite que representantes para fazer chamadas de saída em nome dos usuários para o qual eles têm permissões delegadas.</span><span class="sxs-lookup"><span data-stu-id="d8444-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="d8444-124">Impedir que o desvio de Chamada Tarifada e enviar chamadas pela PSTN</span><span class="sxs-lookup"><span data-stu-id="d8444-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="d8444-125">Essa configuração para **ativado** enviará chamadas através de PSTN e incorrer encargos em vez de utilizar a rede e obter isenção das tarifas.</span><span class="sxs-lookup"><span data-stu-id="d8444-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="d8444-126">Ocupado em ocupado está disponível durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="d8444-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="d8444-127">Configura as chamadas recebidas como são manipulados quando um usuário já estiver em uma chamada ou conferência.</span><span class="sxs-lookup"><span data-stu-id="d8444-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="d8444-128">Chamadas de entrada ou novas podem ser rejeitadas com um sinal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="d8444-128">New or incoming calls can be rejected with a busy signal.</span></span> |

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="d8444-129">Criar uma política personalizada de chamada</span><span class="sxs-lookup"><span data-stu-id="d8444-129">Create a custom calling policy</span></span>

<span data-ttu-id="d8444-130">Siga estas etapas para criar uma nova política personalizada chamada.</span><span class="sxs-lookup"><span data-stu-id="d8444-130">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="d8444-131">No Centro de administração do Microsoft Teams, selecione **voz** > **política de chamada**.</span><span class="sxs-lookup"><span data-stu-id="d8444-131">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="d8444-132">Selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="d8444-132">Select **New policy**.</span></span>
3. <span data-ttu-id="d8444-133">Ative os recursos que você deseja usar na sua política de chamada.</span><span class="sxs-lookup"><span data-stu-id="d8444-133">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="d8444-134">Todas as seleções estão **desligadas** por padrão.</span><span class="sxs-lookup"><span data-stu-id="d8444-134">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="d8444-135">Para controlar se os usuários podem rotear chamadas de entrada para a caixa postal, selecione **sempre habilitada** ou **usuário controlados**.</span><span class="sxs-lookup"><span data-stu-id="d8444-135">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="d8444-136">Para impedir o roteamento para a caixa postal, selecione **sempre desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="d8444-136">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="d8444-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8444-137">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="d8444-138">Modificar uma política de chamada existente</span><span class="sxs-lookup"><span data-stu-id="d8444-138">Modify an existing calling policy</span></span>

<span data-ttu-id="d8444-139">Siga estas etapas para modificar uma política de chamada existente.</span><span class="sxs-lookup"><span data-stu-id="d8444-139">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="d8444-140">No Centro de administração do Microsoft Teams, selecione **voz** > **política de chamada**.</span><span class="sxs-lookup"><span data-stu-id="d8444-140">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="d8444-141">Clique em Avançar para a política que você deseja modificar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d8444-141">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="d8444-142">Ative os recursos que você deseja usar na sua política de chamada.</span><span class="sxs-lookup"><span data-stu-id="d8444-142">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="d8444-143">Todas as seleções estão **desligadas** por padrão.</span><span class="sxs-lookup"><span data-stu-id="d8444-143">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="d8444-144">Para controlar se os usuários podem rotear chamadas de entrada para a caixa postal, selecione **sempre habilitada** ou **usuário controlados**.</span><span class="sxs-lookup"><span data-stu-id="d8444-144">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="d8444-145">Para impedir o roteamento para a caixa postal, selecione **sempre desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="d8444-145">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="d8444-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8444-146">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="d8444-147">Atribuir uma política de chamada a um usuário</span><span class="sxs-lookup"><span data-stu-id="d8444-147">Assign a calling policy to a user</span></span>

<span data-ttu-id="d8444-148">Siga estas etapas para atribuir uma política de chamada personalizada a um usuário.</span><span class="sxs-lookup"><span data-stu-id="d8444-148">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="d8444-149">No Centro de administração do Microsoft Teams, selecione **voz** > **política de chamada**.</span><span class="sxs-lookup"><span data-stu-id="d8444-149">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="d8444-150">Clique em ao lado do nome de política para selecioná-lo e selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="d8444-150">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="d8444-151">No painel de **Gerenciar usuários** , procure o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="d8444-151">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="d8444-152">(Você deve inserir pelo menos três caracteres).</span><span class="sxs-lookup"><span data-stu-id="d8444-152">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="d8444-153">Selecione o nome do usuário e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d8444-153">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="d8444-154">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8444-154">Select **Save**.</span></span>
