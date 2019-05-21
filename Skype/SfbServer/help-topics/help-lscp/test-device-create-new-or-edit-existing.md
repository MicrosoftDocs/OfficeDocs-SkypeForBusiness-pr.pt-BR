---
title: Dispositivo de teste criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do dispositivo de teste do painel de controle do Skype for Business Server.
ms.openlocfilehash: 18cc276889e479a9aea7ac87950e2f50bb627578
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293225"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="5fa54-107">Dispositivo de Teste: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="5fa54-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="5fa54-108">O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5fa54-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="5fa54-109">É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção.</span><span class="sxs-lookup"><span data-stu-id="5fa54-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="5fa54-110">É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site.</span><span class="sxs-lookup"><span data-stu-id="5fa54-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="5fa54-111">Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série.</span><span class="sxs-lookup"><span data-stu-id="5fa54-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="5fa54-112">Quando você adiciona um dispositivo, ele é exibido na lista da página do **dispositivo de teste** do painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5fa54-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5fa54-113">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="5fa54-113">Tasks you can perform</span></span>

<span data-ttu-id="5fa54-114">É possível executar as seguintes tarefas na página  **Novo Dispositivo de Teste** ou **Editar Dispositivo de Teste**:</span><span class="sxs-lookup"><span data-stu-id="5fa54-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="5fa54-115">Adicionar um novo dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="5fa54-115">Add a new test device.</span></span>

- <span data-ttu-id="5fa54-116">Modificar as propriedades de um dispositivo de teste existente.</span><span class="sxs-lookup"><span data-stu-id="5fa54-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5fa54-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="5fa54-117">UI Reference</span></span>

<span data-ttu-id="5fa54-118">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="5fa54-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="5fa54-119">**Escopo** Identifica o escopo (global ou site) do dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="5fa54-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="5fa54-120">**Nome** Você pode adicionar ou modificar o nome do dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="5fa54-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="5fa54-121">**Nome do dispositivo** Você pode adicionar ou modificar o nome do dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="5fa54-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="5fa54-122">**Tipo de identificador** Você pode selecionar o método a ser usado para identificar o dispositivo selecionando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fa54-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="5fa54-123">**Endereço MAC**</span><span class="sxs-lookup"><span data-stu-id="5fa54-123">**MAC address**</span></span>

  - <span data-ttu-id="5fa54-124">**Número de série**</span><span class="sxs-lookup"><span data-stu-id="5fa54-124">**Serial number**</span></span>

- <span data-ttu-id="5fa54-125">**Identificador exclusivo** Você pode digitar o endereço MAC ou o número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5fa54-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="5fa54-126">Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="5fa54-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5fa54-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="5fa54-127">See also</span></span>

[<span data-ttu-id="5fa54-128">Dispositivo de Teste</span><span class="sxs-lookup"><span data-stu-id="5fa54-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="5fa54-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="5fa54-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="5fa54-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="5fa54-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="5fa54-131">Exibir atualizações de software para dispositivos em sua organização</span><span class="sxs-lookup"><span data-stu-id="5fa54-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
