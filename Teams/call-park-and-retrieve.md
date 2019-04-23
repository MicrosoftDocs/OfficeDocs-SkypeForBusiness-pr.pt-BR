---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use o estacionamento de chamada e recuperação para colocar uma chamada em espera no serviço de equipes na nuvem.
ms.openlocfilehash: 798e53ef9a0638be659da8567419b7bd3d3c3555
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993498"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="bac8a-103">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bac8a-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="bac8a-104">Estacionamento de chamada e recuperação é um recurso que permite ao usuário colocar uma chamada em espera no serviço de equipes na nuvem.</span><span class="sxs-lookup"><span data-stu-id="bac8a-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="bac8a-105">Quando uma chamada estiver estacionada, o serviço gera um código exclusivo para recuperação de chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="bac8a-106">O usuário que a colocou a chamada ou outra pessoa, em seguida, pode usar esse código e um dispositivo ou aplicativo suportados para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="bac8a-107">Estes são alguns dos cenários comuns para o uso de estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="bac8a-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="bac8a-108">Um recepcionista parques uma chamada para alguém trabalhando em uma fábrica.</span><span class="sxs-lookup"><span data-stu-id="bac8a-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="bac8a-109">O recepcionista comunica a chamada e o número de código sobre o sistema de endereço público.</span><span class="sxs-lookup"><span data-stu-id="bac8a-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="bac8a-110">Em seguida, o usuário que a chamada é para pode Pegue um telefone de equipes na fábrica e digite o código para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="bac8a-111">Um usuário parques uma chamada em um dispositivo móvel, pois a bateria do dispositivo está ficando sem energia.</span><span class="sxs-lookup"><span data-stu-id="bac8a-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="bac8a-112">O usuário pode, em seguida, insira o código para recuperar a chamada de um telefone de mesa de equipes.</span><span class="sxs-lookup"><span data-stu-id="bac8a-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="bac8a-113">Um parques representante de suporte um cliente chamar e envia um anúncio em um canal de equipes para um especialista recuperar a chamada e ajudar o cliente.</span><span class="sxs-lookup"><span data-stu-id="bac8a-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="bac8a-114">Com um perito indica o código nos clientes de equipes para recuperar a chamada</span><span class="sxs-lookup"><span data-stu-id="bac8a-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bac8a-115">Este recurso só está disponível no modo exclusivo para as equipes de implantação.</span><span class="sxs-lookup"><span data-stu-id="bac8a-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="bac8a-116">Para obter mais informações sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="bac8a-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="bac8a-117">É necessária uma licença</span><span class="sxs-lookup"><span data-stu-id="bac8a-117">License required</span></span>

<span data-ttu-id="bac8a-118">Para estacionar e recuperar chamadas, um usuário deve ser um usuário do Enterprise Voice e um administrador deve conceder ao usuário uma política de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="bac8a-119">Para obter mais informações sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="bac8a-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="bac8a-120">Estacionamento de chamada e recuperar a disponibilidade de recursos</span><span class="sxs-lookup"><span data-stu-id="bac8a-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="bac8a-121">Estacionamento de chamada e recuperação no momento é suportado pelos seguintes clientes e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bac8a-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="bac8a-122">(Suportado no equipes somente modo, com ou sem conectividade PSTN).</span><span class="sxs-lookup"><span data-stu-id="bac8a-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="bac8a-123">Recurso</span><span class="sxs-lookup"><span data-stu-id="bac8a-123">Capability</span></span> | <span data-ttu-id="bac8a-124">Área de trabalho de equipes</span><span class="sxs-lookup"><span data-stu-id="bac8a-124">Teams Desktop</span></span> | <span data-ttu-id="bac8a-125">As equipes Mac App</span><span class="sxs-lookup"><span data-stu-id="bac8a-125">Teams Mac App</span></span> | <span data-ttu-id="bac8a-126">As equipes Web App (borda)</span><span class="sxs-lookup"><span data-stu-id="bac8a-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="bac8a-127">As equipes móveis iOS/Android App</span><span class="sxs-lookup"><span data-stu-id="bac8a-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="bac8a-128">Telefone IP de equipes</span><span class="sxs-lookup"><span data-stu-id="bac8a-128">Teams IP phone</span></span> | <span data-ttu-id="bac8a-129">Skype para negócios IP phone</span><span class="sxs-lookup"><span data-stu-id="bac8a-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="bac8a-130">Estacionar uma chamada</span><span class="sxs-lookup"><span data-stu-id="bac8a-130">Park a call</span></span> | <span data-ttu-id="bac8a-131">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-131">Yes</span></span> | <span data-ttu-id="bac8a-132">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-132">Yes</span></span> | <span data-ttu-id="bac8a-133">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-133">Yes</span></span> | <span data-ttu-id="bac8a-134">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-134">Yes</span></span> | <span data-ttu-id="bac8a-135">Em breve</span><span class="sxs-lookup"><span data-stu-id="bac8a-135">Coming soon</span></span>| <span data-ttu-id="bac8a-136">Não</span><span class="sxs-lookup"><span data-stu-id="bac8a-136">No</span></span> |
| <span data-ttu-id="bac8a-137">Recuperar uma chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="bac8a-137">Retrieve a parked call</span></span> | <span data-ttu-id="bac8a-138">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-138">Yes</span></span> | <span data-ttu-id="bac8a-139">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-139">Yes</span></span> | <span data-ttu-id="bac8a-140">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-140">Yes</span></span> | <span data-ttu-id="bac8a-141">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-141">Yes</span></span> | <span data-ttu-id="bac8a-142">Em breve</span><span class="sxs-lookup"><span data-stu-id="bac8a-142">Coming soon</span></span>| <span data-ttu-id="bac8a-143">Não</span><span class="sxs-lookup"><span data-stu-id="bac8a-143">No</span></span> |
| <span data-ttu-id="bac8a-144">Toque de chamada não recuperado novamente</span><span class="sxs-lookup"><span data-stu-id="bac8a-144">Unretrieved call ring back</span></span> | <span data-ttu-id="bac8a-145">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-145">Yes</span></span> | <span data-ttu-id="bac8a-146">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-146">Yes</span></span> | <span data-ttu-id="bac8a-147">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-147">Yes</span></span> | <span data-ttu-id="bac8a-148">Sim</span><span class="sxs-lookup"><span data-stu-id="bac8a-148">Yes</span></span> | <span data-ttu-id="bac8a-149">Em breve</span><span class="sxs-lookup"><span data-stu-id="bac8a-149">Coming soon</span></span>| <span data-ttu-id="bac8a-150">Não</span><span class="sxs-lookup"><span data-stu-id="bac8a-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="bac8a-151">Configurando o estacionamento de chamada e recuperação</span><span class="sxs-lookup"><span data-stu-id="bac8a-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="bac8a-152">Você deve ser um administrador para configurar o estacionamento de chamada e recuperação, e o recurso é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="bac8a-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="bac8a-153">Você pode habilitá-lo para usuários e criar grupos de usuários usando a diretiva de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="bac8a-154">Quando você aplica a mesma política a um conjunto de usuários, eles podem estacionar e recuperar chamadas entre si.</span><span class="sxs-lookup"><span data-stu-id="bac8a-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="bac8a-155">Para configurar o estacionamento de chamadas para usuários e criar grupos de usuários de estacionamento de chamada, siga o procedimento abaixo [atribuir uma política de estacionamento de chamada](#assign-a-call-park-policy) .</span><span class="sxs-lookup"><span data-stu-id="bac8a-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="bac8a-156">Para obter informações sobre como usar o estacionamento de chamada e recuperar um recurso, consulte [estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="bac8a-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="bac8a-157">Habilitar uma política de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="bac8a-157">Enable a call park policy</span></span>

<span data-ttu-id="bac8a-158">Siga estas etapas para habilitar uma diretiva de estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="bac8a-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="bac8a-159">Vá para **o Centro de administração do Microsoft equipes** > **voz** > **políticas de estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="bac8a-160">Selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-160">Select **New policy**.</span></span>
3. <span data-ttu-id="bac8a-161">Forneça um nome para a diretiva e, em seguida, trocar **Permitir Call park** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="bac8a-162">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="bac8a-163">Atribuir uma política de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="bac8a-163">Assign a call park policy</span></span>

<span data-ttu-id="bac8a-164">Siga estas etapas para atribuir uma política de estacionamento de chamada a um ou mais usuários:</span><span class="sxs-lookup"><span data-stu-id="bac8a-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="bac8a-165">Vá para **o Centro de administração do Microsoft equipes** > **voz** > **políticas de estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="bac8a-166">Selecione a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="bac8a-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="bac8a-167">Selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="bac8a-168">No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="bac8a-169">Repita essa etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="bac8a-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="bac8a-170">Quando terminar de adicionar usuários, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="bac8a-171">Configurar o estacionamento de chamada e recuperar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="bac8a-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="bac8a-172">Use o cmdlet [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) do PowerShell para criar uma política de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="bac8a-173">Use o cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) do PowerShell para conceder uma política de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="bac8a-174">Você pode alterar a configuração padrão usando [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bac8a-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="bac8a-175">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bac8a-175">Troubleshooting</span></span>

<span data-ttu-id="bac8a-176">Se os usuários não podem ver o estacionamento ou recuperar botão:</span><span class="sxs-lookup"><span data-stu-id="bac8a-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="bac8a-177">Verifique se o usuário tem a diretiva de estacionamento de chamada ativada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="bac8a-178">Se um usuário tenta recuperar uma chamada e for bem sucedido, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bac8a-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="bac8a-179">Verificar se o usuário está usando o cliente de equipes ou um equipes dispositivo/telefone habilitado</span><span class="sxs-lookup"><span data-stu-id="bac8a-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="bac8a-180">Agrupamento – é o usuário membro do grupo de estacionamento de chamada?</span><span class="sxs-lookup"><span data-stu-id="bac8a-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="bac8a-181">Modo de ilha – estacionamento de chamada e recuperar não está disponível no modo de ilha de equipes.</span><span class="sxs-lookup"><span data-stu-id="bac8a-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="bac8a-182">A chamada já foi recuperada ou encerrada.</span><span class="sxs-lookup"><span data-stu-id="bac8a-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="bac8a-183">Mais informações</span><span class="sxs-lookup"><span data-stu-id="bac8a-183">More information</span></span>

<span data-ttu-id="bac8a-184">[Estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="bac8a-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>