---
title: Dispositivo de teste criar novo ou editar existente
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ela será exibida na lista na página Testar dispositivo do Skype para painel de controle do Business Server.
ms.openlocfilehash: 1bb61f99ceab29eb3915e7650e1a760b1798f0db
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215876"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="935e6-107">Dispositivo de Teste: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="935e6-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="935e6-108">O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="935e6-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="935e6-109">É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção.</span><span class="sxs-lookup"><span data-stu-id="935e6-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="935e6-110">É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site.</span><span class="sxs-lookup"><span data-stu-id="935e6-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="935e6-111">Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série.</span><span class="sxs-lookup"><span data-stu-id="935e6-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="935e6-112">Quando você adiciona um dispositivo, ela será exibida na lista na página **Testar dispositivo** do Skype para painel de controle do Business Server.</span><span class="sxs-lookup"><span data-stu-id="935e6-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="935e6-113">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="935e6-113">Tasks you can perform</span></span>

<span data-ttu-id="935e6-114">É possível executar as seguintes tarefas na página  **Novo Dispositivo de Teste** ou **Editar Dispositivo de Teste**:</span><span class="sxs-lookup"><span data-stu-id="935e6-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="935e6-115">Adicionar um novo dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="935e6-115">Add a new test device.</span></span>

- <span data-ttu-id="935e6-116">Modificar as propriedades de um dispositivo de teste existente.</span><span class="sxs-lookup"><span data-stu-id="935e6-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="935e6-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="935e6-117">UI Reference</span></span>

<span data-ttu-id="935e6-118">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="935e6-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="935e6-119">**Escopo** Identifica o escopo (Global ou Site) do dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="935e6-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="935e6-120">**Nome** É possível adicionar ou modificar o nome do dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="935e6-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="935e6-121">**Nome do dispositivo** É possível adicionar ou modificar o nome do dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="935e6-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="935e6-122">**Tipo de identificador** Você pode selecionar o método utilizado para identificar o dispositivo selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="935e6-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="935e6-123">**Endereço MAC**</span><span class="sxs-lookup"><span data-stu-id="935e6-123">**MAC address**</span></span>

  - <span data-ttu-id="935e6-124">**Número de série**</span><span class="sxs-lookup"><span data-stu-id="935e6-124">**Serial number**</span></span>

- <span data-ttu-id="935e6-125">**Identificador exclusivo** Você pode digitar o endereço MAC ou número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="935e6-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="935e6-126">Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="935e6-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="935e6-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="935e6-127">See also</span></span>

[<span data-ttu-id="935e6-128">Dispositivo de Teste</span><span class="sxs-lookup"><span data-stu-id="935e6-128">Test Device</span></span>](ms.lync.lscp.ClientDeviceTestMain.md)

[<span data-ttu-id="935e6-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="935e6-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="935e6-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="935e6-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="935e6-131">Exibir atualizações de Software para dispositivos em sua organização</span><span class="sxs-lookup"><span data-stu-id="935e6-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
