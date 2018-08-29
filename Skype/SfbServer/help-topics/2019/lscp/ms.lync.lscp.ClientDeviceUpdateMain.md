---
title: Atualização de Dispositivos
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: A Microsoft lança periodicamente um novo conjunto de atualizações de firmware do dispositivo para Skype para negócios Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. Você pode obter o mais recente conjunto de regras de atualização de dispositivo, indo para a página de Ajuda e suporte no site da Microsoft e pesquisando forPhone Edition.Download o pacote de atualização mais recente e extraia os arquivos para uma pasta no computador onde as atualizações devem ser carregadas. Após a extração dos arquivos, você poderá usar o cmdlet Import-CsDeviceUpdate para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab). Para obter detalhes, consulte Import-CsDeviceUpdate.
ms.openlocfilehash: 997570ffa8dfbf8422577784086efb8f0e4dc20a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261718"
---
# <a name="device-update"></a><span data-ttu-id="8b45d-106">Atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8b45d-106">Device Update</span></span>

<span data-ttu-id="8b45d-107">A Microsoft lança periodicamente um novo conjunto de atualizações de firmware do dispositivo para Skype para negócios Phone Edition, que você pode importar para seus servidores e distribuir aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8b45d-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="8b45d-108">É possível obter o conjunto mais recente de regras de atualização de dispositivo acessando a página Ajuda e Suporte no site da Microsoft e pesquisando por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="8b45d-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="8b45d-109">Baixe o pacote de atualizações mais recente e extraia os arquivos para uma pasta no computador onde as atualizações deverão ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="8b45d-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="8b45d-110">Após a extração dos arquivos, você poderá usar o cmdlet **Import-CsDeviceUpdate** para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="8b45d-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="8b45d-111">Para obter detalhes, consulte [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8b45d-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="8b45d-112">Depois que as regras de atualização de dispositivo tenham sido importadas, você pode usar a página **Atualização do dispositivo** para exibir e gerenciar essas regras para os dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b45d-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="8b45d-113">É possível testar as atualizações de firmware e, supondo que os testes foram bem-sucedidos, disponibilizar as atualizações a todos os dispositivos relevantes usados na organização.</span><span class="sxs-lookup"><span data-stu-id="8b45d-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="8b45d-114">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="8b45d-114">Tasks you can perform</span></span>

<span data-ttu-id="8b45d-115">É possível executar as seguintes tarefas na página  **Atualização de Dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="8b45d-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="8b45d-116">Aprovar as atualizações de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="8b45d-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="8b45d-117">Cancelar ou restaurar atualizações de dispositivo pendentes.</span><span class="sxs-lookup"><span data-stu-id="8b45d-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="8b45d-118">Excluir atualizações de dispositivo da lista.</span><span class="sxs-lookup"><span data-stu-id="8b45d-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8b45d-119">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="8b45d-119">UI Reference</span></span>

<span data-ttu-id="8b45d-120">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="8b45d-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="8b45d-121">**Editar** Você pode usar essa opção para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b45d-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="8b45d-122">**Selecionar tudo** Essa opção seleciona todas as atualizações de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="8b45d-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="8b45d-123">**Excluir** Essa opção exclui todas as atualizações do dispositivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8b45d-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="8b45d-124">**Ação** Você pode selecionar uma ou mais atualizações na lista e execute as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="8b45d-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="8b45d-125">**Cancelar atualizações pendentes** Essa opção impede que a atualização selecionada sendo implantada nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b45d-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="8b45d-126">**Aprovar** Essa opção permite a atualização selecionada para serem implantados nos dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b45d-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="8b45d-127">**Restaurar** Essa opção permite que uma atualização aprovada anteriormente a serem implantados nos dispositivos da sua organização</span><span class="sxs-lookup"><span data-stu-id="8b45d-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="8b45d-128">**Atualizar** É possível atualizar a lista para verificar o status de todas as atualizações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b45d-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="8b45d-129">Para obter detalhes sobre o serviço Web de atualização de dispositivo, consulte [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8b45d-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="8b45d-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8b45d-130">See also</span></span>

[<span data-ttu-id="8b45d-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="8b45d-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)