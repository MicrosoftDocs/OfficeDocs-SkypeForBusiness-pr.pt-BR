---
title: Atualização de Dispositivo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: A Microsoft periodicamente lança um novo conjunto de atualizações de firmware do dispositivo para o Skype for Business Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. Você pode obter o conjunto mais recente de regras de atualização de dispositivos indo para a página Ajuda e Suporte no site da Microsoft e procurando porPhone Edition.Baixe o pacote de atualização mais recente e extraia os arquivos para uma pasta no computador onde as atualizações devem ser carregadas. Após a extração dos arquivos, você poderá usar o cmdlet Import-CsDeviceUpdate para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab). Para obter detalhes, consulte Import-CsDeviceUpdate.
ms.openlocfilehash: 375069d5812d5aa13ebd63dd02eaa3cdd6151cc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811051"
---
# <a name="device-update"></a><span data-ttu-id="12798-106">Atualização de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="12798-106">Device Update</span></span>

<span data-ttu-id="12798-107">A Microsoft periodicamente lança um novo conjunto de atualizações de firmware do dispositivo para o Skype for Business Phone Edition, que você pode importar para seus servidores e distribuir aos usuários.</span><span class="sxs-lookup"><span data-stu-id="12798-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="12798-108">É possível obter o conjunto mais recente de regras de atualização de dispositivo acessando a página Ajuda e Suporte no site da Microsoft e pesquisando por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="12798-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="12798-109">Baixe o pacote de atualizações mais recente e extraia os arquivos para uma pasta no computador onde as atualizações deverão ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="12798-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="12798-110">Após a extração dos arquivos, você poderá usar o cmdlet **Import-CsDeviceUpdate** para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="12798-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="12798-111">Para obter detalhes, [consulte Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="12798-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="12798-112">Depois que as regras de atualização de  dispositivos foram importadas, você pode usar a página Atualização de Dispositivo para exibir e gerenciar essas regras para os dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="12798-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="12798-113">É possível testar as atualizações de firmware e, supondo que os testes foram bem-sucedidos, disponibilizar as atualizações a todos os dispositivos relevantes usados na organização.</span><span class="sxs-lookup"><span data-stu-id="12798-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="12798-114">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="12798-114">Tasks you can perform</span></span>

<span data-ttu-id="12798-115">É possível executar as seguintes tarefas na página **Atualização de Dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="12798-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="12798-116">Aprovar as atualizações de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="12798-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="12798-117">Cancelar ou restaurar atualizações de dispositivo pendentes.</span><span class="sxs-lookup"><span data-stu-id="12798-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="12798-118">Excluir atualizações de dispositivo da lista.</span><span class="sxs-lookup"><span data-stu-id="12798-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="12798-119">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="12798-119">UI Reference</span></span>

<span data-ttu-id="12798-120">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="12798-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="12798-121">**Editar** Você pode usar essa opção para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12798-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="12798-122">**Selecionar Tudo** Essa opção seleciona todas as atualizações de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="12798-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="12798-123">**Excluir** Essa opção exclui todas as atualizações de dispositivo selecionadas.</span><span class="sxs-lookup"><span data-stu-id="12798-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="12798-124">**Ação** Você pode selecionar uma ou mais atualizações na lista e tomar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="12798-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="12798-125">**Cancelar atualizações pendentes** Essa opção impede que a atualização selecionada seja implantada nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="12798-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="12798-126">**Aprovar** Essa opção permite que a atualização selecionada seja implantada nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="12798-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="12798-127">**Restaurar** Essa opção permite que uma atualização aprovada anteriormente seja implantada nos dispositivos da sua organização</span><span class="sxs-lookup"><span data-stu-id="12798-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="12798-128">**Atualizar** Você pode atualizar a lista para verificar o status de todas as atualizações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12798-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="12798-129">Para obter detalhes sobre o serviço Device Update Web, consulte [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="12798-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="12798-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="12798-130">See also</span></span>

[<span data-ttu-id="12798-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="12798-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
