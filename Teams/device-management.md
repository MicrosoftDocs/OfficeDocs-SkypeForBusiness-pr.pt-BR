---
title: Gerenciar seus dispositivos no Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Saiba como gerenciar dispositivos usados com o Microsoft Teams em sua organização.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587313"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="9aa31-103">Gerenciar seus dispositivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9aa31-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="9aa31-104">Como administrador, você pode gerenciar os dispositivos usados com o Microsoft Teams em sua organização usando o centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9aa31-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="9aa31-105">Você pode exibir e gerenciar o inventário de dispositivos da sua organização e executar tarefas como atualizar, reiniciar e monitorar o diagnóstico de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9aa31-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="9aa31-106">Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9aa31-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="9aa31-107">Quais dispositivos você pode gerenciar?</span><span class="sxs-lookup"><span data-stu-id="9aa31-107">What devices can you manage?</span></span>
<span data-ttu-id="9aa31-108">Você pode gerenciar qualquer dispositivo certificado e inscrito no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9aa31-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="9aa31-109">Um dispositivo é registrado automaticamente na primeira vez que o usuário entra no Microsoft Teams no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9aa31-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="9aa31-110">Para obter uma lista de dispositivos certificados que podem ser gerenciados, consulte:</span><span class="sxs-lookup"><span data-stu-id="9aa31-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="9aa31-111">Telefones de conferência</span><span class="sxs-lookup"><span data-stu-id="9aa31-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="9aa31-112">Telefones de mesa</span><span class="sxs-lookup"><span data-stu-id="9aa31-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="9aa31-113">Barras de colaboração</span><span class="sxs-lookup"><span data-stu-id="9aa31-113">Collaboration bars</span></span>

<span data-ttu-id="9aa31-114">Os dispositivos são gerenciados no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) em **dispositivos** na navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="9aa31-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="9aa31-115">Se você tiver o Microsoft Intune, os dispositivos são registrados automaticamente no Intune.</span><span class="sxs-lookup"><span data-stu-id="9aa31-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="9aa31-116">Depois que um dispositivo é registrado, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9aa31-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="9aa31-117">Gerenciar telefones e barras de colaboração no Teams</span><span class="sxs-lookup"><span data-stu-id="9aa31-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="9aa31-118">Embora os telefones e as barras de colaboração sejam gerenciados da mesma maneira no centro de administração do Microsoft Teams, eles têm suas próprias seções na navegação à esquerda em **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="9aa31-119">Isso permite que você gerencie cada tipo de dispositivo separadamente.</span><span class="sxs-lookup"><span data-stu-id="9aa31-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="9aa31-120">Aqui, você pode exibir e gerenciar telefones e barras de colaboração registrados no Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9aa31-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="9aa31-121">As informações que você verá para cada dispositivo inclui o nome do dispositivo, o fabricante, o modelo, o usuário, o status, a ação, o último visto e o histórico.</span><span class="sxs-lookup"><span data-stu-id="9aa31-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="9aa31-122">Você pode personalizar o modo de exibição para mostrar as informações que atendem às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="9aa31-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="9aa31-123">Veja alguns exemplos de como você pode gerenciar os dispositivos da equipe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9aa31-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="9aa31-124">Para fazer isso...</span><span class="sxs-lookup"><span data-stu-id="9aa31-124">To do this...</span></span>  |<span data-ttu-id="9aa31-125">Fazer isso</span><span class="sxs-lookup"><span data-stu-id="9aa31-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="9aa31-126">Alterar as informações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9aa31-126">Change device information</span></span>   | <span data-ttu-id="9aa31-127">Selecione um dispositivo > **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-127">Select a device > **Edit**.</span></span> <span data-ttu-id="9aa31-128">Você pode editar detalhes, como o nome do dispositivo, a marca de ativos e adicionar anotações.</span><span class="sxs-lookup"><span data-stu-id="9aa31-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="9aa31-129">Gerenciar atualizações de software</span><span class="sxs-lookup"><span data-stu-id="9aa31-129">Manage software updates</span></span>   |<span data-ttu-id="9aa31-130">Selecione um dispositivo > **atualização**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-130">Select a device > **Update**.</span></span> <span data-ttu-id="9aa31-131">Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a serem instaladas.</span><span class="sxs-lookup"><span data-stu-id="9aa31-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="9aa31-132">Reiniciar um dispositivo</span><span class="sxs-lookup"><span data-stu-id="9aa31-132">Restart a device</span></span>   |<span data-ttu-id="9aa31-133">Selecione um dispositivo > **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="9aa31-134">Exibir o histórico de dispositivos</span><span class="sxs-lookup"><span data-stu-id="9aa31-134">View device history</span></span>  | <span data-ttu-id="9aa31-135">Selecione um > **histórico**de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9aa31-135">Select a device > **History**.</span></span> <span data-ttu-id="9aa31-136">Você pode exibir o histórico de atualizações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9aa31-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="9aa31-137">Exibir diagnósticos</span><span class="sxs-lookup"><span data-stu-id="9aa31-137">View diagnostics</span></span>  | <span data-ttu-id="9aa31-138">Selecione um dispositivo > **diagnóstico**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="9aa31-139">Usar perfis de configuração no Teams</span><span class="sxs-lookup"><span data-stu-id="9aa31-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="9aa31-140">Use perfis de configuração para gerenciar as configurações e os recursos dos dispositivos de equipe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9aa31-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="9aa31-141">Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que você deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9aa31-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="9aa31-142">Criar um perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="9aa31-142">Create a configuration profile</span></span>

1. <span data-ttu-id="9aa31-143">No painel de navegação esquerdo, vá para**perfis de configuração**de **dispositivos** > .</span><span class="sxs-lookup"><span data-stu-id="9aa31-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="9aa31-144">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-144">Click **Add**.</span></span>
3. <span data-ttu-id="9aa31-145">Digite um nome para o perfil e, se desejar, adicione uma descrição amigável.</span><span class="sxs-lookup"><span data-stu-id="9aa31-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="9aa31-146">Especifique as configurações desejadas para o perfil e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="9aa31-147">Atribuir um perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="9aa31-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="9aa31-148">No painel de navegação esquerdo, vá para**perfis de configuração**de **dispositivos** > .</span><span class="sxs-lookup"><span data-stu-id="9aa31-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="9aa31-149">Selecione o **perfil de configuração** que você deseja atribuir e clique em **atribuir a dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="9aa31-150">No painel **atribuir dispositivos a um perfil de configuração** , procure e selecione os dispositivos que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="9aa31-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="9aa31-151">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9aa31-151">Click **Save**.</span></span>
