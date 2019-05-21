---
title: Atualização de Dispositivos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: A Microsoft lança periodicamente um novo conjunto de atualizações de firmware de dispositivo para o Skype for Business Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. Você pode obter o conjunto mais recente de regras de atualização de dispositivos indo para a página de ajuda e suporte no site da Microsoft e pesquisando o forPhone Edition. Baixe o pacote de atualização mais recente e extraia os arquivos para uma pasta no computador onde as atualizações devem ser carregadas. Após a extração dos arquivos, você poderá usar o cmdlet Import-CsDeviceUpdate para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab). Para obter detalhes, consulte importar-CsDeviceUpdate.
ms.openlocfilehash: 19b0253dece8b010fc4de4fe3907cf8cff2a5bf9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300375"
---
# <a name="device-update"></a><span data-ttu-id="e9764-106">Atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9764-106">Device Update</span></span>

<span data-ttu-id="e9764-107">A Microsoft lança periodicamente um novo conjunto de atualizações de firmware de dispositivo para o Skype for Business Phone Edition, que você pode importar para seus servidores e distribuir aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e9764-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="e9764-108">É possível obter o conjunto mais recente de regras de atualização de dispositivo acessando a página Ajuda e Suporte no site da Microsoft e pesquisando por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="e9764-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="e9764-109">Baixe o pacote de atualizações mais recente e extraia os arquivos para uma pasta no computador onde as atualizações deverão ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="e9764-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="e9764-110">Após a extração dos arquivos, você poderá usar o cmdlet **Import-CsDeviceUpdate** para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="e9764-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="e9764-111">Para obter detalhes, consulte [importar-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e9764-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="e9764-112">Depois que as regras de atualização do dispositivo forem importadas, você poderá usar a página de **atualização do dispositivo** para exibir e gerenciar essas regras para os dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9764-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="e9764-113">É possível testar as atualizações de firmware e, supondo que os testes foram bem-sucedidos, disponibilizar as atualizações a todos os dispositivos relevantes usados na organização.</span><span class="sxs-lookup"><span data-stu-id="e9764-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e9764-114">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="e9764-114">Tasks you can perform</span></span>

<span data-ttu-id="e9764-115">É possível executar as seguintes tarefas na página  **Atualização de Dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="e9764-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="e9764-116">Aprovar as atualizações de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="e9764-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="e9764-117">Cancelar ou restaurar atualizações de dispositivo pendentes.</span><span class="sxs-lookup"><span data-stu-id="e9764-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="e9764-118">Excluir atualizações de dispositivo da lista.</span><span class="sxs-lookup"><span data-stu-id="e9764-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e9764-119">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="e9764-119">UI Reference</span></span>

<span data-ttu-id="e9764-120">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="e9764-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="e9764-121">**Editar** Você pode usar essa opção para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e9764-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="e9764-122">**Selecionar tudo** Essa opção seleciona todas as atualizações de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="e9764-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="e9764-123">**Excluir** Esta opção exclui todas as atualizações de dispositivos selecionadas.</span><span class="sxs-lookup"><span data-stu-id="e9764-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="e9764-124">**Ação** Você pode selecionar uma ou mais atualizações na lista e executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e9764-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="e9764-125">**Cancelar atualizações pendentes** Essa opção impede que a atualização selecionada seja implantada nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9764-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="e9764-126">**Aprovar** Essa opção permite que a atualização selecionada seja implantada nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9764-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="e9764-127">**Restaurar** Esta opção permite que uma atualização aprovada anteriormente seja implantada nos dispositivos da sua organização</span><span class="sxs-lookup"><span data-stu-id="e9764-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="e9764-128">**Atualização** Você pode atualizar a lista para verificar o status de todas as atualizações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9764-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="e9764-129">Para obter detalhes sobre o Serviço Web de Atualização de Dispositivo, consulte  [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="e9764-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="e9764-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="e9764-130">See also</span></span>

[<span data-ttu-id="e9764-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="e9764-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
