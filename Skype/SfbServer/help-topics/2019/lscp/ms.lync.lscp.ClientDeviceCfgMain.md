---
title: Configuração do Log de Dispositivos
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: O Serviço Web de Atualização de Dispositivo cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, convém definir limites sobre o tamanho do cache de dados de log, tamanho do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ele será limpo. Você pode alterar essas configurações de acordo com requisitos da sua organização. Se você não quiser que o Serviço Web de Atualização de Dispositivo exclua os arquivos de log automaticamente, será possível excluí-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
ms.openlocfilehash: 68e5e7d569f3a0436f80bb081b0785e5278bcb0d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892389"
---
# <a name="device-log-configuration"></a><span data-ttu-id="213d6-107">Configuração do Log de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="213d6-107">Device Log Configuration</span></span>

<span data-ttu-id="213d6-108">O Serviço Web de Atualização de Dispositivo cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="213d6-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="213d6-109">Como parte da estratégia de gerenciamento de dados da sua organização, convém definir limites sobre o tamanho do cache de dados de log, tamanho do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ele será limpo.</span><span class="sxs-lookup"><span data-stu-id="213d6-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="213d6-110">Você pode alterar essas configurações de acordo com requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="213d6-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="213d6-111">Se você não quiser que o Serviço Web de Atualização de Dispositivo exclua os arquivos de log automaticamente, será possível excluí-los manualmente, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="213d6-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="213d6-112">As configurações de log podem ser alteradas globalmente ou de acordo com o site.</span><span class="sxs-lookup"><span data-stu-id="213d6-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="213d6-113">Também é possível configurar um horário do dia em que você deseja que o Serviço Web de Atualização de Dispositivo exclua automaticamente os arquivos de log mais antigos do que o número de dias configurado (por padrão, são os arquivos de log com mais de 10 dias).</span><span class="sxs-lookup"><span data-stu-id="213d6-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="213d6-114">Essa configuração não pode ser modificada usando Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="213d6-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="213d6-115">Em vez disso, você deve usar Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="213d6-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="213d6-116">Para especificar a hora do dia para excluir arquivos de log expirados, use o cmdlet **New-CsDeviceUpdateConfiguration** com o parâmetro - LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="213d6-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="213d6-117">Para obter detalhes, consulte [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="213d6-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="213d6-118">A exclusão remove permanentemente os arquivos do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="213d6-118">Purging files permanently removes them from the file system.</span></span> <span data-ttu-id="213d6-119">Depois de excluir um arquivo, ele não poderá ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="213d6-119">After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="213d6-120">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="213d6-120">Tasks you can perform</span></span>

<span data-ttu-id="213d6-121">É possível executar as seguintes tarefas na página  **Configuração do Log do Dispositivos**:</span><span class="sxs-lookup"><span data-stu-id="213d6-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="213d6-122">Adicionar uma configuração de log de dispositivo globalmente ou para um site ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="213d6-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="213d6-123">Modificar as opções de um log de configuração de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="213d6-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="213d6-124">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="213d6-124">UI Reference</span></span>

<span data-ttu-id="213d6-125">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="213d6-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="213d6-126">**Novo** Você pode adicionar uma nova configuração de log de dispositivo com o seguinte escopo:</span><span class="sxs-lookup"><span data-stu-id="213d6-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="213d6-127">Global</span><span class="sxs-lookup"><span data-stu-id="213d6-127">Global</span></span>

  - <span data-ttu-id="213d6-128">Site</span><span class="sxs-lookup"><span data-stu-id="213d6-128">Site</span></span>

- <span data-ttu-id="213d6-129">**Editar** Você pode alterar as opções de uma configuração de log de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="213d6-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="213d6-130">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="213d6-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="213d6-131">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma configuração de log de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="213d6-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="213d6-132">**Selecionar tudo** Essa opção seleciona todas as configuração de log de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="213d6-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="213d6-133">**Excluir** Essa opção exclui todas as configuração de log do dispositivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="213d6-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="213d6-134">**Atualizar** É possível atualizar a lista de configuração de log de dispositivo para verificar o status das opções de configuração de log de todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="213d6-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="213d6-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="213d6-135">See also</span></span>

[<span data-ttu-id="213d6-136">Modificar as configurações para os arquivos de Log da atividade de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="213d6-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
