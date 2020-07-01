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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Saiba como usar o estacionamento de chamadas e recuperar para colocar uma chamada em espera no serviço do teams na nuvem.
ms.openlocfilehash: a9518705cd5edff3834be21732f78dd47352cd63
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938530"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="b37da-103">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b37da-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="b37da-104">O estacionamento de chamadas e a recuperação são um recurso que permite que um usuário faça uma chamada em espera no serviço do teams na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b37da-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="b37da-105">Quando uma chamada está estacionada, o serviço gera um código exclusivo para recuperação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b37da-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="b37da-106">O usuário que estacionau a chamada ou outra pessoa pode usar esse código e um aplicativo ou dispositivo com suporte para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="b37da-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="b37da-107">Alguns dos cenários comuns para usar o parque de chamadas são:</span><span class="sxs-lookup"><span data-stu-id="b37da-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="b37da-108">Um recepcionista é um pedido de alguém trabalhando em uma fábrica.</span><span class="sxs-lookup"><span data-stu-id="b37da-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="b37da-109">Em seguida, o recepcionista anuncia a chamada e o número do código pelo sistema de endereços público.</span><span class="sxs-lookup"><span data-stu-id="b37da-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="b37da-110">O usuário para o qual a chamada é para pode pegar um telefone de equipe no chão de fábrica e digitar o código para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="b37da-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="b37da-111">Um usuário representa uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia.</span><span class="sxs-lookup"><span data-stu-id="b37da-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="b37da-112">Em seguida, o usuário pode inserir o código para recuperar a chamada em um telefone de mesa do teams.</span><span class="sxs-lookup"><span data-stu-id="b37da-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="b37da-113">Um representante de suporte tem um representante do cliente e envia um comunicado em um canal de equipe para que um especialista para recuperar a chamada e ajudar o cliente.</span><span class="sxs-lookup"><span data-stu-id="b37da-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="b37da-114">Um especialista insere o código em clientes do teams para recuperar a chamada</span><span class="sxs-lookup"><span data-stu-id="b37da-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b37da-115">Esse recurso só está disponível no modo de implantação do teams.</span><span class="sxs-lookup"><span data-stu-id="b37da-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="b37da-116">Para obter mais informações sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="b37da-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="b37da-117">Licença necessária</span><span class="sxs-lookup"><span data-stu-id="b37da-117">License required</span></span>

<span data-ttu-id="b37da-118">Para estacionar e recuperar chamadas, um usuário deve ser um usuário de voz empresarial, e um administrador deve conceder ao usuário uma política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b37da-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="b37da-119">Para obter mais informações sobre o modelo de licenciamento, consulte [Descrição de serviço do Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="b37da-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="b37da-120">Ligar para o parque da chamada e recuperar a disponibilidade de recursos</span><span class="sxs-lookup"><span data-stu-id="b37da-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="b37da-121">O estacionamento de chamadas e a recuperação têm suporte no momento pelos seguintes clientes e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b37da-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="b37da-122">(Compatível com o modo somente Teams, com ou sem conectividade PSTN)</span><span class="sxs-lookup"><span data-stu-id="b37da-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="b37da-123">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="b37da-123">Capability</span></span> | <span data-ttu-id="b37da-124">Teams desktop</span><span class="sxs-lookup"><span data-stu-id="b37da-124">Teams Desktop</span></span> | <span data-ttu-id="b37da-125">Aplicativo Teams Mac</span><span class="sxs-lookup"><span data-stu-id="b37da-125">Teams Mac App</span></span> | <span data-ttu-id="b37da-126">Aplicativo Web do Teams (Edge)</span><span class="sxs-lookup"><span data-stu-id="b37da-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="b37da-127">Aplicativo móvel do teams para iOS/Android</span><span class="sxs-lookup"><span data-stu-id="b37da-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="b37da-128">Telefone IP do teams</span><span class="sxs-lookup"><span data-stu-id="b37da-128">Teams IP phone</span></span> | <span data-ttu-id="b37da-129">Telefone IP do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b37da-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="b37da-130">Estacionar uma chamada</span><span class="sxs-lookup"><span data-stu-id="b37da-130">Park a call</span></span> | <span data-ttu-id="b37da-131">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-131">Yes</span></span> | <span data-ttu-id="b37da-132">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-132">Yes</span></span> | <span data-ttu-id="b37da-133">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-133">Yes</span></span> | <span data-ttu-id="b37da-134">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-134">Yes</span></span> | <span data-ttu-id="b37da-135">Sim</span><span class="sxs-lookup"><span data-stu-id="b37da-135">Yes</span></span> | <span data-ttu-id="b37da-136">Não</span><span class="sxs-lookup"><span data-stu-id="b37da-136">No</span></span> |
| <span data-ttu-id="b37da-137">Recuperar uma chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="b37da-137">Retrieve a parked call</span></span> | <span data-ttu-id="b37da-138">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-138">Yes</span></span> | <span data-ttu-id="b37da-139">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-139">Yes</span></span> | <span data-ttu-id="b37da-140">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-140">Yes</span></span> | <span data-ttu-id="b37da-141">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-141">Yes</span></span> | <span data-ttu-id="b37da-142">Sim</span><span class="sxs-lookup"><span data-stu-id="b37da-142">Yes</span></span> | <span data-ttu-id="b37da-143">Não</span><span class="sxs-lookup"><span data-stu-id="b37da-143">No</span></span> |
| <span data-ttu-id="b37da-144">Retorno de chamada não recuperado</span><span class="sxs-lookup"><span data-stu-id="b37da-144">Unretrieved call ring back</span></span> | <span data-ttu-id="b37da-145">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-145">Yes</span></span> | <span data-ttu-id="b37da-146">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-146">Yes</span></span> | <span data-ttu-id="b37da-147">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-147">Yes</span></span> | <span data-ttu-id="b37da-148">Sim </span><span class="sxs-lookup"><span data-stu-id="b37da-148">Yes</span></span> | <span data-ttu-id="b37da-149">Sim</span><span class="sxs-lookup"><span data-stu-id="b37da-149">Yes</span></span> | <span data-ttu-id="b37da-150">Não</span><span class="sxs-lookup"><span data-stu-id="b37da-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="b37da-151">Configurar o estacionamento e a recuperação de chamadas</span><span class="sxs-lookup"><span data-stu-id="b37da-151">Configure call park and retrieve</span></span>

<span data-ttu-id="b37da-152">Você deve ser um administrador para configurar o estacionamento de chamadas e a recuperação, e o recurso está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b37da-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="b37da-153">Você pode habilitá-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b37da-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="b37da-154">Quando você aplica a mesma política a um conjunto de usuários, ele pode estacionar e recuperar chamadas entre si.</span><span class="sxs-lookup"><span data-stu-id="b37da-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="b37da-155">Para configurar os grupos de usuários do parque de chamadas para usuários e criar grupos de usuários do parque de chamadas, siga o procedimento de [política atribuir um estacionamento de chamada](#assign-a-call-park-policy) abaixo.</span><span class="sxs-lookup"><span data-stu-id="b37da-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="b37da-156">Para obter informações sobre como usar o recurso Park e retrieve Call, consulte [estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="b37da-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="b37da-157">Habilitar uma política de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="b37da-157">Enable a call park policy</span></span>

1. <span data-ttu-id="b37da-158">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de estacionamento de chamada**de voz.</span><span class="sxs-lookup"><span data-stu-id="b37da-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="b37da-159">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b37da-159">Select **Add**.</span></span>
3. <span data-ttu-id="b37da-160">Dê um nome à política e, em seguida, alterne **permitir estacionamento de chamada** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="b37da-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="b37da-161">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b37da-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b37da-162">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b37da-162">Using PowerShell</span></span>

<span data-ttu-id="b37da-163">Veja [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b37da-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="b37da-164">Editar uma política de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="b37da-164">Edit a call park policy</span></span>

1. <span data-ttu-id="b37da-165">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de estacionamento de chamada**de voz.</span><span class="sxs-lookup"><span data-stu-id="b37da-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="b37da-166">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b37da-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b37da-167">Alternar para ativar ou **desativar** o estacionamento **de** **chamadas** .</span><span class="sxs-lookup"><span data-stu-id="b37da-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="b37da-168">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b37da-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b37da-169">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b37da-169">Using PowerShell</span></span>

<span data-ttu-id="b37da-170">Consulte [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b37da-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="b37da-171">Por exemplo, para alterar a configuração padrão, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b37da-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="b37da-172">Atribuir uma política de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="b37da-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="b37da-173">Consulte também [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b37da-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b37da-174">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b37da-174">Troubleshooting</span></span>

<span data-ttu-id="b37da-175">Se os usuários não conseguirem ver o botão Park ou retrieve:</span><span class="sxs-lookup"><span data-stu-id="b37da-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="b37da-176">Verifique se o usuário tem a política de estacionamento de chamadas habilitada.</span><span class="sxs-lookup"><span data-stu-id="b37da-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="b37da-177">Se um usuário tentar recuperar uma chamada e não tiver êxito, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b37da-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="b37da-178">Verifique se o usuário está usando o cliente do teams ou um dispositivo/telefone habilitado para equipes</span><span class="sxs-lookup"><span data-stu-id="b37da-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="b37da-179">Agrupamento – é o usuário membro do grupo de estacionamento de chamadas, que se baseia em ter as mesmas equipes de chamada de equipe de estacionamento atribuídas.</span><span class="sxs-lookup"><span data-stu-id="b37da-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="b37da-180">Modo ilha – o parque de chamadas e a recuperação não está disponível no modo da ilha Teams.</span><span class="sxs-lookup"><span data-stu-id="b37da-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="b37da-181">A chamada já foi recuperada ou terminada.</span><span class="sxs-lookup"><span data-stu-id="b37da-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b37da-182">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b37da-182">Related topics</span></span>

[<span data-ttu-id="b37da-183">Estacionar uma chamada no Teams</span><span class="sxs-lookup"><span data-stu-id="b37da-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="b37da-184">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="b37da-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
