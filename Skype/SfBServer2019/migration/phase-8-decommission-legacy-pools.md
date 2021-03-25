---
title: Fase 8 Demission legacy pools
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
description: O tópico a seguir fornece orientações para atualizar entradas DNS, mover o Servidor de Gerenciamento de Conteúdo, desativar pools e desativar e remover servidores e pools de uma implantação herdda. Nem todos os procedimentos listados nesta seção são obrigatórios. Leia a documentação e determine qual procedimento de descomissionamento usar.
ms.openlocfilehash: b1080c68e3b4075ce92aaef497854855135dc47d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113237"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="2620f-105">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="2620f-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="2620f-106">O tópico a seguir fornece orientações para atualizar entradas DNS, mover o Servidor de Gerenciamento de Conteúdo, desativar pools e desativar e remover servidores e pools de uma implantação herdda.</span><span class="sxs-lookup"><span data-stu-id="2620f-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="2620f-107">Nem todos os procedimentos listados nesta seção são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="2620f-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="2620f-108">Leia a documentação e determine qual procedimento de descomissionamento usar.</span><span class="sxs-lookup"><span data-stu-id="2620f-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="2620f-109">Para um artigo datado, porém exaustivo, sobre a remoção de servidores e funções de servidor e um guia passo a passo para descontinuar uma implantação, baixe Desinstalar o [Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkId=246227)e Remover Funções do Servidor.</span><span class="sxs-lookup"><span data-stu-id="2620f-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2620f-110">Para obter informações sobre como migrar e atualizar aplicativos UCMA (Microsoft Unified Communications Managed API), antes de desmantelar seu ambiente herdado, consulte [aplicativos UCMA: Coexistência,](/previous-versions/office/jj728782(v=office.15))migração e cenários de atualização.</span><span class="sxs-lookup"><span data-stu-id="2620f-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](/previous-versions/office/jj728782(v=office.15)).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2620f-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2620f-111">In this section</span></span>

> [<span data-ttu-id="2620f-112">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="2620f-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="2620f-113">Mover o Servidor de Gerenciamento Central de instalação herdada para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="2620f-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="2620f-114">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="2620f-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="2620f-115">Remover a associação de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="2620f-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="2620f-116">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="2620f-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="2620f-117">Remover o Servidor front-end enterprise edition ou o servidor front-end standard edition</span><span class="sxs-lookup"><span data-stu-id="2620f-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="2620f-118">Remover instâncias SQL Server e bancos de dados no Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="2620f-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
