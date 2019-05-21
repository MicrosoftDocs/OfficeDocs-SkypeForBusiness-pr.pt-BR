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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use o parque de chamadas e recupere para colocar uma chamada em espera no serviço do teams na nuvem.
ms.openlocfilehash: fc33ef6c36a9764e39840f384dc70aa1a692579c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283497"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="6800e-103">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6800e-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="6800e-104">O estacionamento de chamadas e a recuperação são um recurso que permite que um usuário faça uma chamada em espera no serviço do teams na nuvem.</span><span class="sxs-lookup"><span data-stu-id="6800e-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="6800e-105">Quando uma chamada está estacionada, o serviço gera um código exclusivo para recuperação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6800e-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="6800e-106">O usuário que estacionau a chamada ou outra pessoa pode usar esse código e um aplicativo ou dispositivo com suporte para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="6800e-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="6800e-107">Alguns dos cenários comuns para usar o parque de chamadas são:</span><span class="sxs-lookup"><span data-stu-id="6800e-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="6800e-108">Um recepcionista é um pedido de alguém trabalhando em uma fábrica.</span><span class="sxs-lookup"><span data-stu-id="6800e-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="6800e-109">Em seguida, o recepcionista anuncia a chamada e o número do código pelo sistema de endereços público.</span><span class="sxs-lookup"><span data-stu-id="6800e-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="6800e-110">O usuário para o qual a chamada é para pode pegar um telefone de equipe no chão de fábrica e digitar o código para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="6800e-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="6800e-111">Um usuário representa uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia.</span><span class="sxs-lookup"><span data-stu-id="6800e-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="6800e-112">Em seguida, o usuário pode inserir o código para recuperar a chamada em um telefone de mesa do teams.</span><span class="sxs-lookup"><span data-stu-id="6800e-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="6800e-113">Um representante de suporte tem um representante do cliente e envia um comunicado em um canal de equipe para que um especialista para recuperar a chamada e ajudar o cliente.</span><span class="sxs-lookup"><span data-stu-id="6800e-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="6800e-114">Um especialista insere o código em clientes do teams para recuperar a chamada</span><span class="sxs-lookup"><span data-stu-id="6800e-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6800e-115">Esse recurso só está disponível no modo de implantação do teams.</span><span class="sxs-lookup"><span data-stu-id="6800e-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="6800e-116">Para obter mais informações sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6800e-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6800e-117">Licença necessária</span><span class="sxs-lookup"><span data-stu-id="6800e-117">License required</span></span>

<span data-ttu-id="6800e-118">Para estacionar e recuperar chamadas, um usuário deve ser um usuário de voz empresarial, e um administrador deve conceder ao usuário uma política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6800e-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="6800e-119">Para obter mais informações sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6800e-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="6800e-120">Ligar para o parque da chamada e recuperar a disponibilidade de recursos</span><span class="sxs-lookup"><span data-stu-id="6800e-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="6800e-121">O estacionamento de chamadas e a recuperação têm suporte no momento pelos seguintes clientes e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6800e-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="6800e-122">(Compatível com o modo somente Teams, com ou sem conectividade PSTN)</span><span class="sxs-lookup"><span data-stu-id="6800e-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="6800e-123">Potencial</span><span class="sxs-lookup"><span data-stu-id="6800e-123">Capability</span></span> | <span data-ttu-id="6800e-124">Teams desktop</span><span class="sxs-lookup"><span data-stu-id="6800e-124">Teams Desktop</span></span> | <span data-ttu-id="6800e-125">Aplicativo Teams Mac</span><span class="sxs-lookup"><span data-stu-id="6800e-125">Teams Mac App</span></span> | <span data-ttu-id="6800e-126">Aplicativo Web do Teams (Edge)</span><span class="sxs-lookup"><span data-stu-id="6800e-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="6800e-127">Aplicativo móvel do teams para iOS/Android</span><span class="sxs-lookup"><span data-stu-id="6800e-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="6800e-128">Telefone IP do teams</span><span class="sxs-lookup"><span data-stu-id="6800e-128">Teams IP phone</span></span> | <span data-ttu-id="6800e-129">Telefone IP do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6800e-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="6800e-130">Estacionar uma chamada</span><span class="sxs-lookup"><span data-stu-id="6800e-130">Park a call</span></span> | <span data-ttu-id="6800e-131">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-131">Yes</span></span> | <span data-ttu-id="6800e-132">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-132">Yes</span></span> | <span data-ttu-id="6800e-133">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-133">Yes</span></span> | <span data-ttu-id="6800e-134">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-134">Yes</span></span> | <span data-ttu-id="6800e-135">Em breve</span><span class="sxs-lookup"><span data-stu-id="6800e-135">Coming soon</span></span>| <span data-ttu-id="6800e-136">Não</span><span class="sxs-lookup"><span data-stu-id="6800e-136">No</span></span> |
| <span data-ttu-id="6800e-137">Recuperar uma chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="6800e-137">Retrieve a parked call</span></span> | <span data-ttu-id="6800e-138">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-138">Yes</span></span> | <span data-ttu-id="6800e-139">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-139">Yes</span></span> | <span data-ttu-id="6800e-140">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-140">Yes</span></span> | <span data-ttu-id="6800e-141">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-141">Yes</span></span> | <span data-ttu-id="6800e-142">Em breve</span><span class="sxs-lookup"><span data-stu-id="6800e-142">Coming soon</span></span>| <span data-ttu-id="6800e-143">Não</span><span class="sxs-lookup"><span data-stu-id="6800e-143">No</span></span> |
| <span data-ttu-id="6800e-144">Retorno de chamada não recuperado</span><span class="sxs-lookup"><span data-stu-id="6800e-144">Unretrieved call ring back</span></span> | <span data-ttu-id="6800e-145">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-145">Yes</span></span> | <span data-ttu-id="6800e-146">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-146">Yes</span></span> | <span data-ttu-id="6800e-147">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-147">Yes</span></span> | <span data-ttu-id="6800e-148">Sim</span><span class="sxs-lookup"><span data-stu-id="6800e-148">Yes</span></span> | <span data-ttu-id="6800e-149">Em breve</span><span class="sxs-lookup"><span data-stu-id="6800e-149">Coming soon</span></span>| <span data-ttu-id="6800e-150">Não</span><span class="sxs-lookup"><span data-stu-id="6800e-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="6800e-151">Configurar o estacionamento de chamadas e recuperar</span><span class="sxs-lookup"><span data-stu-id="6800e-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="6800e-152">Você deve ser um administrador para configurar o estacionamento de chamadas e a recuperação, e o recurso está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6800e-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="6800e-153">Você pode habilitá-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6800e-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="6800e-154">Quando você aplica a mesma política a um conjunto de usuários, ele pode estacionar e recuperar chamadas entre si.</span><span class="sxs-lookup"><span data-stu-id="6800e-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="6800e-155">Para configurar os grupos de usuários do parque de chamadas para usuários e criar grupos de usuários do parque de chamadas, siga o procedimento de [política atribuir um estacionamento de chamada](#assign-a-call-park-policy) abaixo.</span><span class="sxs-lookup"><span data-stu-id="6800e-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="6800e-156">Para obter informações sobre como usar o recurso Park e retrieve Call, consulte [estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="6800e-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="6800e-157">Habilitar uma política de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="6800e-157">Enable a call park policy</span></span>

<span data-ttu-id="6800e-158">Siga estas etapas para habilitar uma política de estacionamento de chamadas:</span><span class="sxs-lookup"><span data-stu-id="6800e-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="6800e-159">Vá para**políticas de estacionamento de chamada**de**voz** >  **do centro** > de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6800e-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="6800e-160">Selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="6800e-160">Select **New policy**.</span></span>
3. <span data-ttu-id="6800e-161">Dê um nome à política e, em seguida, alterne **permitir estacionamento de chamada** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="6800e-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="6800e-162">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="6800e-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="6800e-163">Atribuir uma política de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="6800e-163">Assign a call park policy</span></span>

<span data-ttu-id="6800e-164">Siga estas etapas para atribuir uma política de estacionamento de chamadas a um ou mais usuários:</span><span class="sxs-lookup"><span data-stu-id="6800e-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="6800e-165">Vá para**políticas de estacionamento de chamada**de**voz** >  **do centro** > de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6800e-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="6800e-166">Selecione a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="6800e-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6800e-167">Selecione **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="6800e-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="6800e-168">No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6800e-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6800e-169">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="6800e-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6800e-170">Quando terminar de adicionar usuários, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="6800e-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="6800e-171">Configurar o estacionamento de chamadas e recuperar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6800e-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="6800e-172">Use o cmdlet [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) do PowerShell para criar uma política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6800e-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="6800e-173">Use o cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) do PowerShell para conceder uma política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6800e-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="6800e-174">Você pode alterar a configuração padrão usando [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6800e-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="6800e-175">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6800e-175">Troubleshooting</span></span>

<span data-ttu-id="6800e-176">Se os usuários não conseguirem ver o botão Park ou retrieve:</span><span class="sxs-lookup"><span data-stu-id="6800e-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="6800e-177">Verifique se o usuário tem a política de estacionamento de chamadas habilitada.</span><span class="sxs-lookup"><span data-stu-id="6800e-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="6800e-178">Se um usuário tentar recuperar uma chamada e não tiver êxito, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6800e-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="6800e-179">Verifique se o usuário está usando o cliente do teams ou um dispositivo/telefone habilitado para equipes</span><span class="sxs-lookup"><span data-stu-id="6800e-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="6800e-180">Agrupamento – o usuário é membro do grupo de estacionamento de chamadas?</span><span class="sxs-lookup"><span data-stu-id="6800e-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="6800e-181">Modo ilha – o parque de chamadas e a recuperação não está disponível no modo da ilha Teams.</span><span class="sxs-lookup"><span data-stu-id="6800e-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="6800e-182">A chamada já foi recuperada ou terminada.</span><span class="sxs-lookup"><span data-stu-id="6800e-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="6800e-183">Mais informações</span><span class="sxs-lookup"><span data-stu-id="6800e-183">More information</span></span>

<span data-ttu-id="6800e-184">[Estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="6800e-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>