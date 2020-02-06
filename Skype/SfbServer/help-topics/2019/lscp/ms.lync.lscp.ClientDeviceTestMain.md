---
title: Dispositivo de Teste
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do dispositivo de teste do painel de controle do Skype for Business Server.
ms.openlocfilehash: 547b0f4e0737ab65463dc4b8350fc1050b071a83
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794530"
---
# <a name="test-device"></a><span data-ttu-id="b4416-106">Dispositivo de Teste</span><span class="sxs-lookup"><span data-stu-id="b4416-106">Test Device</span></span>

<span data-ttu-id="b4416-107">É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção.</span><span class="sxs-lookup"><span data-stu-id="b4416-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="b4416-108">É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site.</span><span class="sxs-lookup"><span data-stu-id="b4416-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="b4416-109">Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série.</span><span class="sxs-lookup"><span data-stu-id="b4416-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="b4416-110">Quando você adiciona um dispositivo, ele é exibido na lista da página do **dispositivo de teste** do painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b4416-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b4416-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="b4416-111">Tasks you can perform</span></span>

<span data-ttu-id="b4416-112">Você pode executar as seguintes tarefas na página **testar dispositivo** :</span><span class="sxs-lookup"><span data-stu-id="b4416-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="b4416-113">Adicione um dispositivo de teste globalmente ou para um site específico.</span><span class="sxs-lookup"><span data-stu-id="b4416-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="b4416-114">Modifique as opções de um dispositivo de teste existente.</span><span class="sxs-lookup"><span data-stu-id="b4416-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b4416-115">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="b4416-115">UI Reference</span></span>

<span data-ttu-id="b4416-116">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="b4416-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="b4416-117">**Novo** Você pode adicionar um novo dispositivo de teste com o seguinte escopo:</span><span class="sxs-lookup"><span data-stu-id="b4416-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="b4416-118">Global</span><span class="sxs-lookup"><span data-stu-id="b4416-118">Global</span></span>

  - <span data-ttu-id="b4416-119">Site</span><span class="sxs-lookup"><span data-stu-id="b4416-119">Site</span></span>

- <span data-ttu-id="b4416-120">**Editar** Você pode alterar as opções de um dispositivo de teste na lista.</span><span class="sxs-lookup"><span data-stu-id="b4416-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="b4416-121">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4416-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="b4416-122">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de um dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="b4416-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="b4416-123">**Selecionar tudo** Essa opção seleciona todos os dispositivos de teste na lista.</span><span class="sxs-lookup"><span data-stu-id="b4416-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="b4416-124">**Excluir** Esta opção exclui todos os dispositivos de teste selecionados.</span><span class="sxs-lookup"><span data-stu-id="b4416-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="b4416-125">**Atualização** Você pode atualizar a lista de dispositivos de teste para verificar o status das opções de todos os dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="b4416-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="b4416-126">Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="b4416-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="b4416-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4416-127">See also</span></span>

[<span data-ttu-id="b4416-128">Dispositivo de Teste: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="b4416-128">Test Device: Create New or Edit Existing</span></span>](ms.lync.lscp.ClientDeviceTestEdit.md)

[<span data-ttu-id="b4416-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="b4416-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="b4416-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="b4416-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="b4416-131">Exibir atualizações de software para dispositivos em sua organização</span><span class="sxs-lookup"><span data-stu-id="b4416-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
