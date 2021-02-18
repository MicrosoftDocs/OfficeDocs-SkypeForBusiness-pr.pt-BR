---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Saiba mais sobre como usar o parque de chamada e recuperá-lo para colocar uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278711"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="e5e89-103">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5e89-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="e5e89-104">O parque de chamada e recuperação é um recurso que permite que um usuário coloque uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="e5e89-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="e5e89-105">Quando uma chamada é parada, o serviço gera um código exclusivo para recuperação de chamada.</span><span class="sxs-lookup"><span data-stu-id="e5e89-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="e5e89-106">O usuário que estacionou a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="e5e89-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="e5e89-107">(Consulte Parque [uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obter detalhes.)</span><span class="sxs-lookup"><span data-stu-id="e5e89-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="e5e89-108">Alguns dos cenários comuns para usar o parque de chamada são:</span><span class="sxs-lookup"><span data-stu-id="e5e89-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="e5e89-109">Um recepcionista faz uma chamada para alguém trabalhando em uma fábrica.</span><span class="sxs-lookup"><span data-stu-id="e5e89-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="e5e89-110">Em seguida, o recepcionista anuncia a chamada e o número do código no sistema de endereços público.</span><span class="sxs-lookup"><span data-stu-id="e5e89-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="e5e89-111">O usuário para quem a chamada é, em seguida, pode pegar um telefone do Teams no chão de fábrica e inserir o código para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="e5e89-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="e5e89-112">Um usuário para de fazer uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia.</span><span class="sxs-lookup"><span data-stu-id="e5e89-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="e5e89-113">Em seguida, o usuário pode inserir o código para recuperar a chamada de um telefone de mesa do Teams.</span><span class="sxs-lookup"><span data-stu-id="e5e89-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="e5e89-114">Um representante de suporte para uma chamada de cliente e envia um comunicado em um canal do Teams para que um especialista recupere a chamada e ajude o cliente.</span><span class="sxs-lookup"><span data-stu-id="e5e89-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="e5e89-115">Um especialista ins chave o código nos clientes do Teams para recuperar a chamada</span><span class="sxs-lookup"><span data-stu-id="e5e89-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="e5e89-116">Para parque e recuperação de chamadas, um usuário deve ser um usuário do Enterprise Voice e deve ser incluído em uma política de parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="e5e89-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="e5e89-117">O parque de chamadas e a recuperação só está disponível no modo de implantação somente do [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e não tem suporte em telefones IP do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e5e89-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="e5e89-118">Configurar o parque de chamada e recuperar</span><span class="sxs-lookup"><span data-stu-id="e5e89-118">Configure call park and retrieve</span></span>

<span data-ttu-id="e5e89-119">Você deve ser um administrador do Teams para configurar o parque de chamada e recuperá-lo.</span><span class="sxs-lookup"><span data-stu-id="e5e89-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="e5e89-120">Ele é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="e5e89-120">It is disabled by default.</span></span> <span data-ttu-id="e5e89-121">Você pode habilita-lo para usuários e criar grupos de usuários usando a política de parque de chamada.</span><span class="sxs-lookup"><span data-stu-id="e5e89-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="e5e89-122">Quando você aplica a mesma política a um conjunto de usuários, eles podem parquer e recuperar chamadas entre si.</span><span class="sxs-lookup"><span data-stu-id="e5e89-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="e5e89-123">Para habilitar uma política de parque de chamada</span><span class="sxs-lookup"><span data-stu-id="e5e89-123">To enable a call park policy</span></span>

1. <span data-ttu-id="e5e89-124">Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **as** políticas do parque de  >  **Chamada de Voz.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="e5e89-125">Na guia **Gerenciar políticas,** clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="e5e89-126">Dê um nome à política e, em seguida, **alternar Permitir parque de chamada** para **1.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Captura de tela das configurações de política do parque de chamada](media/call-park-add-policy.png)

4. <span data-ttu-id="e5e89-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5e89-128">Select **Save**.</span></span>

<span data-ttu-id="e5e89-129">Você pode editar a política selecionando-a na lista e clicando em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="e5e89-130">Para que a política funcione, ela deve ser atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e5e89-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="e5e89-131">Você pode [atribuir a política aos usuários individualmente](assign-policies.md) ou atribuí-la a um grupo.</span><span class="sxs-lookup"><span data-stu-id="e5e89-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="e5e89-132">Para atribuir uma política de parte de chamada a um grupo</span><span class="sxs-lookup"><span data-stu-id="e5e89-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="e5e89-133">Na página **Políticas do parque de** chamada, na guia de atribuição de política **de** grupo, clique em **Adicionar grupo.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="e5e89-134">Pesquise o grupo que você deseja usar e clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="e5e89-135">Escolha uma classificação em comparação com outras atribuições de grupo.</span><span class="sxs-lookup"><span data-stu-id="e5e89-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="e5e89-136">Em **Selecionar uma política,** escolha a política à qual você deseja atribuir esse grupo.</span><span class="sxs-lookup"><span data-stu-id="e5e89-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![imagem de políticas de parque](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="e5e89-138">Selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="e5e89-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5e89-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e5e89-139">Related topics</span></span>

[<span data-ttu-id="e5e89-140">Fazer uma chamada no Teams</span><span class="sxs-lookup"><span data-stu-id="e5e89-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="e5e89-141">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="e5e89-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="e5e89-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="e5e89-142">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="e5e89-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="e5e89-143">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="e5e89-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="e5e89-144">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
