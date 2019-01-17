---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use o estacionamento de chamada e recuperação para colocar uma chamada em espera no serviço de equipes na nuvem.
ms.openlocfilehash: 2433a8836a037b530fbd895f7a37567f24d63b50
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328305"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="0dc48-103">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0dc48-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="0dc48-104">Estacionamento de chamada e recuperação é um recurso que permite ao usuário colocar uma chamada em espera no serviço de equipes na nuvem.</span><span class="sxs-lookup"><span data-stu-id="0dc48-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="0dc48-105">Quando uma chamada estiver estacionada, o serviço gera um código exclusivo para recuperação de chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="0dc48-106">O usuário que a colocou a chamada ou outra pessoa, em seguida, pode usar esse código e um dispositivo ou aplicativo suportados para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="0dc48-107">Estes são alguns dos cenários comuns para o uso de estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="0dc48-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="0dc48-108">Um recepcionista parques uma chamada para alguém trabalhando em uma fábrica.</span><span class="sxs-lookup"><span data-stu-id="0dc48-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="0dc48-109">O recepcionista comunica a chamada e o número de código sobre o sistema de endereço público.</span><span class="sxs-lookup"><span data-stu-id="0dc48-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="0dc48-110">Em seguida, o usuário que a chamada é para pode Pegue um telefone de equipes na fábrica e digite o código para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="0dc48-111">Um usuário parques uma chamada em um dispositivo móvel, pois a bateria do dispositivo está ficando sem energia.</span><span class="sxs-lookup"><span data-stu-id="0dc48-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="0dc48-112">O usuário pode digitar então de código para recuperar a chamada de um telefone de mesa de equipes.</span><span class="sxs-lookup"><span data-stu-id="0dc48-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="0dc48-113">Um parques representante de suporte um cliente chamar e envia um anúncio em um canal de equipes para um especialista recuperar a chamada e ajudar o cliente.</span><span class="sxs-lookup"><span data-stu-id="0dc48-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="0dc48-114">Com um perito indica o código nos clientes de equipes para recuperar a chamada</span><span class="sxs-lookup"><span data-stu-id="0dc48-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dc48-115">Este recurso só está disponível no modo exclusivo para as equipes de implantação.</span><span class="sxs-lookup"><span data-stu-id="0dc48-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="0dc48-116">Para obter mais detalhes sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="0dc48-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="0dc48-117">É necessária uma licença</span><span class="sxs-lookup"><span data-stu-id="0dc48-117">License required</span></span>

<span data-ttu-id="0dc48-118">Para estacionar e recuperar chamadas, um usuário deve ser um usuário do Enterprise Voice e um administrador deve conceder ao usuário uma política de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="0dc48-119">Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0dc48-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="0dc48-120">Estacionamento de chamada e recuperar a disponibilidade de recursos</span><span class="sxs-lookup"><span data-stu-id="0dc48-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="0dc48-121">Estacionamento de chamada e recuperação no momento é suportado pelos seguintes clientes e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0dc48-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="0dc48-122">(Suportado no equipes somente modo, com ou sem conectividade PSTN).</span><span class="sxs-lookup"><span data-stu-id="0dc48-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="0dc48-123">Recurso</span><span class="sxs-lookup"><span data-stu-id="0dc48-123">Capability</span></span> | <span data-ttu-id="0dc48-124">Área de trabalho de equipes</span><span class="sxs-lookup"><span data-stu-id="0dc48-124">Teams Desktop</span></span> | <span data-ttu-id="0dc48-125">As equipes Mac App</span><span class="sxs-lookup"><span data-stu-id="0dc48-125">Teams Mac App</span></span> | <span data-ttu-id="0dc48-126">As equipes Web App (borda)</span><span class="sxs-lookup"><span data-stu-id="0dc48-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="0dc48-127">As equipes móveis iOS/Android App</span><span class="sxs-lookup"><span data-stu-id="0dc48-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="0dc48-128">Telefone IP de equipes</span><span class="sxs-lookup"><span data-stu-id="0dc48-128">Teams IP phone</span></span> | <span data-ttu-id="0dc48-129">Skype para negócios IP phone</span><span class="sxs-lookup"><span data-stu-id="0dc48-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="0dc48-130">Estacionar uma chamada</span><span class="sxs-lookup"><span data-stu-id="0dc48-130">Park a call</span></span> | <span data-ttu-id="0dc48-131">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-131">Yes</span></span> | <span data-ttu-id="0dc48-132">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-132">Yes</span></span> | <span data-ttu-id="0dc48-133">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-133">Yes</span></span> | <span data-ttu-id="0dc48-134">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-134">Yes</span></span> | <span data-ttu-id="0dc48-135">Em breve</span><span class="sxs-lookup"><span data-stu-id="0dc48-135">Coming soon</span></span>| <span data-ttu-id="0dc48-136">Não</span><span class="sxs-lookup"><span data-stu-id="0dc48-136">No</span></span> |
| <span data-ttu-id="0dc48-137">Recuperar uma chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="0dc48-137">Retrieve a parked call</span></span> | <span data-ttu-id="0dc48-138">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-138">Yes</span></span> | <span data-ttu-id="0dc48-139">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-139">Yes</span></span> | <span data-ttu-id="0dc48-140">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-140">Yes</span></span> | <span data-ttu-id="0dc48-141">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-141">Yes</span></span> | <span data-ttu-id="0dc48-142">Em breve</span><span class="sxs-lookup"><span data-stu-id="0dc48-142">Coming soon</span></span>| <span data-ttu-id="0dc48-143">Não</span><span class="sxs-lookup"><span data-stu-id="0dc48-143">No</span></span> |
| <span data-ttu-id="0dc48-144">Toque de chamada não recuperados novamente</span><span class="sxs-lookup"><span data-stu-id="0dc48-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="0dc48-145">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-145">Yes</span></span> | <span data-ttu-id="0dc48-146">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-146">Yes</span></span> | <span data-ttu-id="0dc48-147">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-147">Yes</span></span> | <span data-ttu-id="0dc48-148">Sim</span><span class="sxs-lookup"><span data-stu-id="0dc48-148">Yes</span></span> | <span data-ttu-id="0dc48-149">Em breve</span><span class="sxs-lookup"><span data-stu-id="0dc48-149">Coming soon</span></span>| <span data-ttu-id="0dc48-150">Não</span><span class="sxs-lookup"><span data-stu-id="0dc48-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="0dc48-151">Configurando o estacionamento de chamada e recuperação</span><span class="sxs-lookup"><span data-stu-id="0dc48-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="0dc48-152">Você deve ser um administrador para configurar o estacionamento de chamada e recuperação, e o recurso é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0dc48-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="0dc48-153">Você pode habilitá-lo para usuários e criar grupos de usuários usando a diretiva de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="0dc48-154">Quando você aplica a mesma política a um conjunto de usuários, eles poderão estacionar e recuperar chamadas entre si.</span><span class="sxs-lookup"><span data-stu-id="0dc48-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="0dc48-155">Para configurar o estacionamento de chamadas para usuários e criar grupos de usuários de estacionamento de chamada, siga o procedimento abaixo.</span><span class="sxs-lookup"><span data-stu-id="0dc48-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="0dc48-156">Para obter informações sobre como usar o estacionamento de chamada e recuperar um recurso, consulte [estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0dc48-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="0dc48-157">Configurar o estacionamento de chamada e recuperar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dc48-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="0dc48-158">Use o cmdlet [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) do PowerShell para criar uma política de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="0dc48-159">Use o cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) do PowerShell para conceder uma política de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="0dc48-160">Você pode alterar a configuração padrão usando [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0dc48-160">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="0dc48-161">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="0dc48-161">Troubleshooting</span></span>

<span data-ttu-id="0dc48-162">Se os usuários não podem ver o estacionamento ou recuperar botão:</span><span class="sxs-lookup"><span data-stu-id="0dc48-162">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="0dc48-163">Verifique se o usuário tem a diretiva de estacionamento de chamada ativada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-163">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="0dc48-164">Se um usuário tenta recuperar uma chamada e for bem sucedido, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dc48-164">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="0dc48-165">Verificar se o usuário está usando o cliente de equipes ou um equipes dispositivo/telefone habilitado</span><span class="sxs-lookup"><span data-stu-id="0dc48-165">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="0dc48-166">Agrupamento – é o usuário membro do grupo de estacionamento de chamada?</span><span class="sxs-lookup"><span data-stu-id="0dc48-166">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="0dc48-167">Modo de ilha – estacionamento de chamada e recuperar não está disponível no modo de ilha de equipes.</span><span class="sxs-lookup"><span data-stu-id="0dc48-167">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="0dc48-168">A chamada já foi recuperada ou encerrada.</span><span class="sxs-lookup"><span data-stu-id="0dc48-168">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="0dc48-169">Mais informações</span><span class="sxs-lookup"><span data-stu-id="0dc48-169">More information</span></span>

<span data-ttu-id="0dc48-170">[Estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0dc48-170">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>