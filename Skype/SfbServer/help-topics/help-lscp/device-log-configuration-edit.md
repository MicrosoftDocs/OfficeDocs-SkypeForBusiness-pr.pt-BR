---
title: Editar configuração de log de dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Você pode adicionar uma configuração de log de dispositivo à página Editar configuração do log que determina o tamanho máximo do cache de log, o tamanho máximo do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização.
ms.openlocfilehash: 3ea368c0f3bccd7655d1bca3cb93a98a86b99c47
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822904"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="d166e-104">Configuração de Log de Dispositivo: Editar</span><span class="sxs-lookup"><span data-stu-id="d166e-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="d166e-105">Você pode adicionar uma configuração de log de dispositivo à página **Editar configuração do log** que determina o tamanho máximo do cache de log, o tamanho máximo do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ser limpo.</span><span class="sxs-lookup"><span data-stu-id="d166e-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="d166e-106">Você pode alterar essas configurações de acordo com os requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d166e-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d166e-107">A exclusão remove permanentemente os arquivos do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d166e-107">Purging files permanently removes them from the file system.</span></span> <span data-ttu-id="d166e-108">Depois de excluir um arquivo, ele não poderá ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="d166e-108">After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="d166e-109">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="d166e-109">Tasks you can perform</span></span>

<span data-ttu-id="d166e-110">Você pode executar as seguintes tarefas na página **Editar configuração do log** :</span><span class="sxs-lookup"><span data-stu-id="d166e-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="d166e-111">Adicione uma configuração de log de dispositivo globalmente ou para um site específico.</span><span class="sxs-lookup"><span data-stu-id="d166e-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="d166e-112">Modificar as opções de um log de configuração de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="d166e-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="d166e-113">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="d166e-113">UI Reference</span></span>

<span data-ttu-id="d166e-114">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="d166e-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="d166e-115">**Escopo** Identifica o escopo (global ou site) da configuração de log do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d166e-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="d166e-116">**Nome** Você pode adicionar ou modificar o nome da configuração do log do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d166e-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="d166e-117">**Tamanho máximo de arquivo (bytes)** Você pode especificar o tamanho máximo que um arquivo de log pode ficar antes de ser limpo.</span><span class="sxs-lookup"><span data-stu-id="d166e-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="d166e-118">O padrão é 1.024.000 bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="d166e-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="d166e-119">**Tamanho máximo do cache (bytes)** Você pode especificar a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache deva ser limpo e os dados sejam gravados em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="d166e-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="d166e-120">O padrão é 512.000 bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="d166e-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="d166e-121">**Minutos para liberar o cache (1-60)** Você pode especificar com que frequência as informações armazenadas no cache do arquivo de log são gravadas no arquivo de log real.</span><span class="sxs-lookup"><span data-stu-id="d166e-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="d166e-122">Depois que os dados são registrados, o cache é limpo.</span><span class="sxs-lookup"><span data-stu-id="d166e-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="d166e-123">O padrão é cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d166e-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="d166e-124">**Dias para manter os arquivos de log (1-365)** Você pode especificar o número de dias durante os quais os arquivos de log serão mantidos antes de serem limpos.</span><span class="sxs-lookup"><span data-stu-id="d166e-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="d166e-125">O padrão é 10 dias.</span><span class="sxs-lookup"><span data-stu-id="d166e-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d166e-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="d166e-126">See also</span></span>

[<span data-ttu-id="d166e-127">Configuração do Log de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="d166e-127">Device Log Configuration</span></span>](device-log-configuration.md)
