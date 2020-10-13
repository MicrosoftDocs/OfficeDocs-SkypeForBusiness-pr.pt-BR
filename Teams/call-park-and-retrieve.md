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
description: Saiba mais sobre como usar o estacionamento de chamadas e recuperar para fazer uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424573"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="c89ed-103">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c89ed-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="c89ed-104">O estacionamento de chamadas e a recuperação são um recurso que permite que um usuário faça uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="c89ed-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="c89ed-105">Quando uma chamada está estacionada, o serviço gera um código exclusivo para recuperação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c89ed-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="c89ed-106">O usuário que estacionau a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c89ed-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="c89ed-107">(Veja Confira [o parque de uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obter detalhes.)</span><span class="sxs-lookup"><span data-stu-id="c89ed-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="c89ed-108">Alguns dos cenários comuns para usar o parque de chamadas são:</span><span class="sxs-lookup"><span data-stu-id="c89ed-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="c89ed-109">Um recepcionista é um pedido de alguém trabalhando em uma fábrica.</span><span class="sxs-lookup"><span data-stu-id="c89ed-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="c89ed-110">Em seguida, o recepcionista anuncia a chamada e o número do código pelo sistema de endereços público.</span><span class="sxs-lookup"><span data-stu-id="c89ed-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="c89ed-111">O usuário para o qual a chamada é para pode pegar um telefone de equipe no chão de fábrica e digitar o código para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c89ed-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="c89ed-112">Um usuário representa uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia.</span><span class="sxs-lookup"><span data-stu-id="c89ed-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="c89ed-113">Em seguida, o usuário pode inserir o código para recuperar a chamada em um telefone de mesa do teams.</span><span class="sxs-lookup"><span data-stu-id="c89ed-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="c89ed-114">Um representante de suporte tem um representante do cliente e envia um comunicado em um canal de equipe para que um especialista para recuperar a chamada e ajudar o cliente.</span><span class="sxs-lookup"><span data-stu-id="c89ed-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="c89ed-115">Um especialista insere o código em clientes do teams para recuperar a chamada</span><span class="sxs-lookup"><span data-stu-id="c89ed-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="c89ed-116">Para estacionar e recuperar chamadas, um usuário deve ser um usuário do Enterprise Voice e deve ser incluído em uma política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c89ed-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c89ed-117">O estacionamento e a recuperação de chamadas só estão disponíveis no [modo de implantação do teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e não são compatíveis com telefones IP do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c89ed-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="c89ed-118">Configurar o estacionamento e a recuperação de chamadas</span><span class="sxs-lookup"><span data-stu-id="c89ed-118">Configure call park and retrieve</span></span>

<span data-ttu-id="c89ed-119">Você deve ser um administrador do teams para configurar o estacionamento e a recuperação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c89ed-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="c89ed-120">Ele é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c89ed-120">It is disabled by default.</span></span> <span data-ttu-id="c89ed-121">Você pode habilitá-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c89ed-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="c89ed-122">Quando você aplica a mesma política a um conjunto de usuários, ele pode estacionar e recuperar chamadas entre si.</span><span class="sxs-lookup"><span data-stu-id="c89ed-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="c89ed-123">Para habilitar uma política de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="c89ed-123">To enable a call park policy</span></span>

1. <span data-ttu-id="c89ed-124">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de estacionamento de chamada**de voz.</span><span class="sxs-lookup"><span data-stu-id="c89ed-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="c89ed-125">Na guia **gerenciar políticas** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="c89ed-126">Dê um nome à política e, em seguida, alterne **permitir estacionamento de chamada** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Captura de tela das configurações de política do estacionamento de chamada](media/call-park-add-policy.png)

4. <span data-ttu-id="c89ed-128">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-128">Select **Save**.</span></span>

<span data-ttu-id="c89ed-129">Você pode editar a política selecionando-a na lista e clicando em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="c89ed-130">Para que a política funcione, ela deve ser atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="c89ed-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="c89ed-131">Você pode [atribuir a política a usuários individualmente](assign-policies.md) ou atribuí-las a um grupo.</span><span class="sxs-lookup"><span data-stu-id="c89ed-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="c89ed-132">Para atribuir uma política de peça de chamada a um grupo</span><span class="sxs-lookup"><span data-stu-id="c89ed-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="c89ed-133">Na página **políticas de estacionamento de chamada** , na guia **atribuição de política de grupo** , clique em **Adicionar grupo**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="c89ed-134">Procure o grupo que você deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="c89ed-135">Escolha uma classificação em comparação com outras tarefas de grupo.</span><span class="sxs-lookup"><span data-stu-id="c89ed-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="c89ed-136">Em **Selecione uma política**, escolha a política à qual você deseja atribuir esse grupo.</span><span class="sxs-lookup"><span data-stu-id="c89ed-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="c89ed-137">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c89ed-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c89ed-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c89ed-138">Related topics</span></span>

[<span data-ttu-id="c89ed-139">Estacionar uma chamada no Teams</span><span class="sxs-lookup"><span data-stu-id="c89ed-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="c89ed-140">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="c89ed-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="c89ed-141">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="c89ed-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="c89ed-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="c89ed-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="c89ed-143">Grant CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="c89ed-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)