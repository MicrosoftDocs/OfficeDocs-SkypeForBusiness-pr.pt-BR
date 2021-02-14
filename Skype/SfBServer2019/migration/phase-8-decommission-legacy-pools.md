---
title: Fase 8 Descomissionar pools herddos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: O tópico a seguir fornece orientações para atualizar entradas DNS, mover o Servidor de Gerenciamento de Conteúdo, desativar pools e desativar e remover servidores e pools de uma implantação herdados. Nem todos os procedimentos listados nesta seção são obrigatórios. Leia a documentação e determine qual procedimento de descomissionamento usar.
ms.openlocfilehash: 2406b25436bc13cafca8b09c92220a96e0635ae3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753689"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="3de75-105">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="3de75-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="3de75-106">O tópico a seguir fornece orientações para atualizar entradas DNS, mover o Servidor de Gerenciamento de Conteúdo, desativar pools e desativar e remover servidores e pools de uma implantação herdados.</span><span class="sxs-lookup"><span data-stu-id="3de75-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="3de75-107">Nem todos os procedimentos listados nesta seção são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="3de75-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="3de75-108">Leia a documentação e determine qual procedimento de descomissionamento usar.</span><span class="sxs-lookup"><span data-stu-id="3de75-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="3de75-109">Para um artigo completo sobre como remover servidores e funções de servidor e um guia passo a passo para descomissionar uma implantação, baixe a desinstalação do [Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkId=246227)e a remoção de funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="3de75-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3de75-110">Para obter informações sobre como migrar e atualizar aplicativos UCMA (Unified Communications Managed API), antes de desprogramar seu ambiente herdado, consulte [aplicativos UCMA: cenários de coexistência,](https://go.microsoft.com/fwlink/p/?LinkId=269555)migração e atualização.</span><span class="sxs-lookup"><span data-stu-id="3de75-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3de75-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3de75-111">In this section</span></span>

> [<span data-ttu-id="3de75-112">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="3de75-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="3de75-113">Mover o Servidor de Gerenciamento Central de instalação herdada para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3de75-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="3de75-114">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="3de75-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="3de75-115">Remover a associação de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="3de75-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="3de75-116">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="3de75-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="3de75-117">Remover o Servidor de Front End Enterprise Edition ou o Servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3de75-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="3de75-118">Remover instâncias SQL Server e bancos de dados no Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="3de75-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

