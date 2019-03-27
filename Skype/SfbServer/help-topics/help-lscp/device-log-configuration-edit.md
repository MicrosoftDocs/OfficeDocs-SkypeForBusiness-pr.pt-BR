---
title: Edição de configuração de Log de dispositivo
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Você pode adicionar uma configuração de log de dispositivo para a página Editar configuração de Log que determina o tamanho de cache máximo do log, tamanho do arquivo de log máximo ou período de tempo que um arquivo de log é mantido antes de ele será limpo. Você pode alterar essas configurações de acordo com requisitos da sua organização.
ms.openlocfilehash: 09d0bc24ad61be98864fd1f37964c01f1fba84ba
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888263"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="8b2e8-104">Configuração de Log de Dispositivo: Editar</span><span class="sxs-lookup"><span data-stu-id="8b2e8-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="8b2e8-105">Você pode adicionar uma configuração de log de dispositivo para a página **Editar configuração de Log** que determina o tamanho de cache máximo do log, tamanho do arquivo de log máximo ou período de tempo que um arquivo de log é mantido antes de ele será limpo.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="8b2e8-106">Você pode alterar essas configurações de acordo com requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8b2e8-107">A exclusão remove permanentemente os arquivos do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-107">Purging files permanently removes them from the file system.</span></span> <span data-ttu-id="8b2e8-108">Depois de excluir um arquivo, ele não poderá ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-108">After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="8b2e8-109">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="8b2e8-109">Tasks you can perform</span></span>

<span data-ttu-id="8b2e8-110">Você pode executar as seguintes tarefas na página **Editar configuração de Log** :</span><span class="sxs-lookup"><span data-stu-id="8b2e8-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="8b2e8-111">Adicione uma configuração de log de dispositivo globalmente ou para um site específico.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="8b2e8-112">Modificar as opções de um log de configuração de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="8b2e8-113">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="8b2e8-113">UI Reference</span></span>

<span data-ttu-id="8b2e8-114">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="8b2e8-115">**Escopo** Identifica o escopo (Global ou Site) da configuração de log de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="8b2e8-116">**Nome** É possível adicionar ou modificar o nome da configuração de log de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="8b2e8-117">**Tamanho máximo do arquivo (bytes)** Você pode especificar o tamanho máximo de que um arquivo de log pode se tornar antes que ele será limpo.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="8b2e8-118">O padrão é 1.024.000 bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="8b2e8-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="8b2e8-119">**Tamanho de cache máximo (bytes)** Você pode especificar a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache deve estar desmarcada e os dados são gravados em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="8b2e8-120">O padrão é 512,000 bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="8b2e8-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="8b2e8-121">**Minutos para liberar o cache (1-60)** Você pode especificar com que frequência informações armazenadas no cache de arquivos de log são gravadas no arquivo de log atual.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="8b2e8-122">Depois que os dados são registrados, o cache está desmarcado.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="8b2e8-123">O padrão é cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="8b2e8-124">**Dias para manter os arquivos de log (1-365)** Você pode especificar o número de dias que os arquivos de log são mantidos antes de serem expurgados.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="8b2e8-125">O padrão é 10 dias.</span><span class="sxs-lookup"><span data-stu-id="8b2e8-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8b2e8-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b2e8-126">See also</span></span>

[<span data-ttu-id="8b2e8-127">Configuração do Log de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="8b2e8-127">Device Log Configuration</span></span>](device-log-configuration.md)
