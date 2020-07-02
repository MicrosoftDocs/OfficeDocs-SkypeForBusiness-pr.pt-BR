---
title: Atualizar dispositivos do Microsoft Teams remotamente
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Atualizar os telefones e as barras de colaboração do Microsoft Teams remotamente usando o centro de administração do teams
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944075"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="d127b-103">Atualizar dispositivos do Microsoft Teams remotamente</span><span class="sxs-lookup"><span data-stu-id="d127b-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="d127b-104">Usando o centro de administração do Microsoft Teams, você pode atualizar seus dispositivos de equipe, como telefones e barras de colaboração, remotamente, e pode escolher o comportamento de atualização automática do firmware do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d127b-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="d127b-105">Você pode atualizar o seguinte em seus dispositivos usando o centro de administração do teams:</span><span class="sxs-lookup"><span data-stu-id="d127b-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="d127b-106">Agente de administração do Teams e aplicativos do teams</span><span class="sxs-lookup"><span data-stu-id="d127b-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="d127b-107">Aplicativo do portal da empresa</span><span class="sxs-lookup"><span data-stu-id="d127b-107">Company portal app</span></span>
- <span data-ttu-id="d127b-108">Aplicativo de agente OEM</span><span class="sxs-lookup"><span data-stu-id="d127b-108">OEM agent app</span></span>
- <span data-ttu-id="d127b-109">Firmware do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d127b-109">Device firmware</span></span>

<span data-ttu-id="d127b-110">As atualizações de firmware de dispositivo podem ser aplicadas automaticamente ou agendadas para uma data e hora futuras.</span><span class="sxs-lookup"><span data-stu-id="d127b-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="d127b-111">Outras atualizações de dispositivo disponíveis não são aplicadas automaticamente, mas podem ser aplicadas manualmente ou agendadas para uma data e hora futuras.</span><span class="sxs-lookup"><span data-stu-id="d127b-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="d127b-112">Enquanto as atualizações de firmware do dispositivo podem ser agendadas, se a data e a hora programadas ficarão após o máximo de 30 ou 90, a atualização do firmware será aplicada quando o atraso máximo for atingido.</span><span class="sxs-lookup"><span data-stu-id="d127b-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="d127b-113">A data e a hora programadas são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="d127b-113">The scheduled date and time are ignored.</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="d127b-114">Escolher o comportamento de atualização automática do firmware do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d127b-114">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="d127b-115">As atualizações do firmware do dispositivo são aplicadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d127b-115">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="d127b-116">Você pode decidir se deseja aplicar as atualizações assim que uma for liberada ou 30 ou 90 dias após o lançamento de uma atualização.</span><span class="sxs-lookup"><span data-stu-id="d127b-116">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="d127b-117">Por padrão, as atualizações do firmware do dispositivo são aplicadas 30 dias, uma lançada.</span><span class="sxs-lookup"><span data-stu-id="d127b-117">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d127b-118">A versão mais recente da atualização do firmware não é aplicada ao seu dispositivo de equipe.</span><span class="sxs-lookup"><span data-stu-id="d127b-118">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="d127b-119">Em vez disso, a atualização aplicada automaticamente ao seu dispositivo é atrasada em uma versão.</span><span class="sxs-lookup"><span data-stu-id="d127b-119">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="d127b-120">Por exemplo, suponha que o dispositivo tenha a versão "10" aplicada e a versão "11" seja lançada.</span><span class="sxs-lookup"><span data-stu-id="d127b-120">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="d127b-121">A versão "11" ainda não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="d127b-121">Version "11" won't be applied yet.</span></span> <span data-ttu-id="d127b-122">Em vez disso, seu dispositivo só será atualizado para a versão "11" após a versão "12" ser liberada.</span><span class="sxs-lookup"><span data-stu-id="d127b-122">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="d127b-123">Para escolher o comportamento de atualização automática para seus dispositivos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d127b-123">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="d127b-124">Acesse o centro de administração do Microsoft Teams visitandohttps://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d127b-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="d127b-125">Navegar pelos **dispositivos**  >  **telefones** ou **barras de colaboração**</span><span class="sxs-lookup"><span data-stu-id="d127b-125">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="d127b-126">Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar** .</span><span class="sxs-lookup"><span data-stu-id="d127b-126">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="d127b-127">Em **atualização automática de firmware**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d127b-127">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="d127b-128">Assim **que disponível** O segundo-atualização do firmware do dispositivo mais recente é aplicada o mais rápido possível depois que a atualização mais recente é lançada.</span><span class="sxs-lookup"><span data-stu-id="d127b-128">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="d127b-129">**Adiar 30 dias** Segundo-a atualização mais recente do firmware do dispositivo é aplicada 30 dias após o lançamento da atualização mais recente.</span><span class="sxs-lookup"><span data-stu-id="d127b-129">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="d127b-130">**Adiar 90 dias** O segundo-atualização do firmware do dispositivo mais recente é aplicada 90 dias após o lançamento da atualização mais recente.</span><span class="sxs-lookup"><span data-stu-id="d127b-130">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="d127b-131">Selecionar **atualização**</span><span class="sxs-lookup"><span data-stu-id="d127b-131">Select **Update**</span></span>

<span data-ttu-id="d127b-132">Se, por qualquer motivo, você precisar reverter uma atualização de firmware do dispositivo, será necessário redefinir o dispositivo para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d127b-132">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="d127b-133">Redefina o dispositivo usando as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="d127b-133">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="d127b-134">Atualizar manualmente dispositivos remotos</span><span class="sxs-lookup"><span data-stu-id="d127b-134">Manually update remote devices</span></span>

<span data-ttu-id="d127b-135">Ao atualizar um ou mais dispositivos usando o centro de administração, você pode decidir se deseja atualizar os dispositivos imediatamente ou agendar uma atualização para uma data e hora futuras.</span><span class="sxs-lookup"><span data-stu-id="d127b-135">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="d127b-136">Para atualizar manualmente dispositivos remotos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d127b-136">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="d127b-137">Acesse o centro de administração do Microsoft Teams visitandohttps://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d127b-137">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="d127b-138">Navegar pelos **dispositivos**  >  **telefones** ou **barras de colaboração**</span><span class="sxs-lookup"><span data-stu-id="d127b-138">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="d127b-139">Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar** .</span><span class="sxs-lookup"><span data-stu-id="d127b-139">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="d127b-140">Em **Atualizações manuais**, selecione **agendar** se desejar agendar a atualização para uma data e hora futuras.</span><span class="sxs-lookup"><span data-stu-id="d127b-140">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="d127b-141">As atualizações são aplicadas na data e na hora no fuso horário selecionado no **fuso horário**.</span><span class="sxs-lookup"><span data-stu-id="d127b-141">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="d127b-142">O que você verá depende se você tem um ou vários dispositivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="d127b-142">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="d127b-143">A imagem à esquerda abaixo mostra vários dispositivos selecionados enquanto a imagem à direita mostra um único dispositivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d127b-143">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="Modos de exibição de um e vários dispositivos no painel de status de atualização do dispositivo":::

<span data-ttu-id="d127b-145">Ao selecionar vários dispositivos, você pode escolher quais tipos de atualização aplicar a cada dispositivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d127b-145">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="d127b-146">Selecione os tipos de atualização que você deseja aplicar e selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="d127b-146">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="d127b-147">Quando você seleciona um único dispositivo, as atualizações disponíveis para o dispositivo são mostradas.</span><span class="sxs-lookup"><span data-stu-id="d127b-147">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="d127b-148">Se vários tipos de atualização estiverem disponíveis para o dispositivo, selecione cada tipo de atualização para aplicar.</span><span class="sxs-lookup"><span data-stu-id="d127b-148">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="d127b-149">Você pode exibir a **versão atual** aplicada ao dispositivo e a **nova versão** que será aplicada.</span><span class="sxs-lookup"><span data-stu-id="d127b-149">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="d127b-150">Selecione a (s) atualização (ções) que você deseja aplicar e selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="d127b-150">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="d127b-151">Depois de selecionar **Atualizar**, as atualizações são aplicadas aos seus dispositivos na data e hora que você selecionou se agendou uma atualização.</span><span class="sxs-lookup"><span data-stu-id="d127b-151">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="d127b-152">Se você não selecionou uma data e hora futuras, as atualizações são aplicadas aos seus dispositivos dentro de alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="d127b-152">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
