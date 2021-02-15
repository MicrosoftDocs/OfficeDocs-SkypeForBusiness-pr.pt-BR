---
title: Configuração do Log de Dispositivos
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
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: O serviço Device Update Web cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados de log, no tamanho do arquivo de log ou no período de tempo que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o serviço Device Update Web exclua os arquivos de log automaticamente, será possível exclui-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
ms.openlocfilehash: 27b4382c84d6aa12a642f191a6167e99ac10565c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829481"
---
# <a name="device-log-configuration"></a><span data-ttu-id="14c0c-107">Configuração do Log de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="14c0c-107">Device Log Configuration</span></span>

<span data-ttu-id="14c0c-108">O serviço Device Update Web cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14c0c-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="14c0c-109">Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados de log, no tamanho do arquivo de log ou no período de tempo que um arquivo de log é mantido antes de ser limpo.</span><span class="sxs-lookup"><span data-stu-id="14c0c-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="14c0c-110">Você pode alterar essas configurações de acordo com os requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="14c0c-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="14c0c-111">Se você não quiser que o serviço Device Update Web exclua os arquivos de log automaticamente, será possível exclui-los manualmente, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="14c0c-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="14c0c-112">As configurações de log podem ser alteradas globalmente ou de acordo com o site.</span><span class="sxs-lookup"><span data-stu-id="14c0c-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="14c0c-113">Também é possível configurar um momento do dia em que você deseja que o serviço Device Update Web exclua automaticamente os arquivos de log mais antigos do que o número de dias configurado (por padrão, são os arquivos de log com mais de 10 dias).</span><span class="sxs-lookup"><span data-stu-id="14c0c-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="14c0c-114">Essa configuração não pode ser modificada usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="14c0c-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="14c0c-115">Em vez disso, você deve usar o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="14c0c-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="14c0c-116">Para especificar a hora do dia para excluir arquivos de log expirados, use o cmdlet **New-CsDeviceUpdateConfiguration** com o parâmetro -LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="14c0c-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="14c0c-117">Para obter detalhes, [consulte New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14c0c-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="14c0c-p104">A exclusão permanente dos arquivos os remove do sistema de arquivos. Depois de excluir um arquivo, ele não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="14c0c-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="14c0c-120">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="14c0c-120">Tasks you can perform</span></span>

<span data-ttu-id="14c0c-121">É possível executar as seguintes tarefas na página **Configuração do Log do Dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="14c0c-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="14c0c-122">Adicionar uma configuração de log de dispositivo globalmente ou para um site ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="14c0c-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="14c0c-123">Modificar as opções de um log de configuração de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="14c0c-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="14c0c-124">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="14c0c-124">UI Reference</span></span>

<span data-ttu-id="14c0c-125">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="14c0c-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="14c0c-126">**Novo** Você pode adicionar uma nova configuração de log de dispositivo com o seguinte escopo:</span><span class="sxs-lookup"><span data-stu-id="14c0c-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="14c0c-127">Global</span><span class="sxs-lookup"><span data-stu-id="14c0c-127">Global</span></span>

  - <span data-ttu-id="14c0c-128">Site</span><span class="sxs-lookup"><span data-stu-id="14c0c-128">Site</span></span>

- <span data-ttu-id="14c0c-129">**Editar** Você pode alterar as opções de uma configuração de log de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="14c0c-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="14c0c-130">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="14c0c-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="14c0c-131">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma configuração de log de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14c0c-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="14c0c-132">**Selecionar Tudo** Essa opção seleciona todas as configurações de log de dispositivo na lista.</span><span class="sxs-lookup"><span data-stu-id="14c0c-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="14c0c-133">**Excluir** Essa opção exclui todas as configurações de log de dispositivo selecionadas.</span><span class="sxs-lookup"><span data-stu-id="14c0c-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="14c0c-134">**Atualizar** Você pode atualizar a lista de configurações de log de dispositivos para verificar o status das opções de todas as configurações de log de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14c0c-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="14c0c-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="14c0c-135">See also</span></span>

[<span data-ttu-id="14c0c-136">Modificar configurações de arquivos de log da atividade de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="14c0c-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
