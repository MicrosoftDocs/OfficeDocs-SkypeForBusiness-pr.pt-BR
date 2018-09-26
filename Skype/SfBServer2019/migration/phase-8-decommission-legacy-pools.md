---
title: Fase 8 descomissionamento os pools herdados
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: O tópico a seguir fornece orientações para atualizar as entradas DNS, movendo o servidor de gerenciamento de conteúdo, encerrando pools e desativando e removendo servidores e pools de uma implantação herdada. Nem todos os procedimentos listados nesta seção são necessários. Leia a documentação e determine qual descomissionamento procedimento para usar.
ms.openlocfilehash: ddad3714f18b79b5db6efd9421b46e481df81319
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029885"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="88ce8-105">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="88ce8-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="88ce8-106">O tópico a seguir fornece orientações para atualizar as entradas DNS, movendo o servidor de gerenciamento de conteúdo, encerrando pools e desativando e removendo servidores e pools de uma implantação herdada.</span><span class="sxs-lookup"><span data-stu-id="88ce8-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="88ce8-107">Nem todos os procedimentos listados nesta seção são necessários.</span><span class="sxs-lookup"><span data-stu-id="88ce8-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="88ce8-108">Leia a documentação e determine qual descomissionamento procedimento para usar.</span><span class="sxs-lookup"><span data-stu-id="88ce8-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="88ce8-109">Para um artigo sobre como remover servidores e funções de servidor e um guia passo a passo para encerrar uma implantação desatualizado mas exaustiva, baixe a [desinstalação do Microsoft Lync Server e Removendo funções de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="88ce8-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="88ce8-110">Para obter informações sobre a migração e atualização de aplicativos de certificação Microsoft Unified Communications Managed API (UCMA), antes de descomissionar seu ambiente herdado, consulte [aplicativos UCMA: cenários de atualização, migração e coexistência](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="88ce8-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="88ce8-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="88ce8-111">In this section</span></span>

> [<span data-ttu-id="88ce8-112">Atualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="88ce8-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
    
> [<span data-ttu-id="88ce8-113">Mover a herdado instalar servidor de gerenciamento Central para Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="88ce8-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
    
> [<span data-ttu-id="88ce8-114">Mover Diretórios de Conferência</span><span class="sxs-lookup"><span data-stu-id="88ce8-114">Move Conference Directories</span></span>](move-conference-directories.md)
    
> [<span data-ttu-id="88ce8-115">Remover a associação do servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="88ce8-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
    
> [<span data-ttu-id="88ce8-116">Remover a associação do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="88ce8-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
    
> [<span data-ttu-id="88ce8-117">Remover o servidor de Front-End do Enterprise Edition ou o servidor de Front-End Standard Edition</span><span class="sxs-lookup"><span data-stu-id="88ce8-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
    
> [<span data-ttu-id="88ce8-118">Remover instâncias do SQL Server e os bancos de dados do servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="88ce8-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

