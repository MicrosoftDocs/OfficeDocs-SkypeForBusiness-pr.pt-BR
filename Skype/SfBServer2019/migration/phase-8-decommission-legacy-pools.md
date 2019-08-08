---
title: Fase 8 descomissionar pools herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: O tópico a seguir fornece uma orientação para atualizar entradas DNS, mover o servidor de gerenciamento de conteúdo, descomissionar pools e desativar e remover servidores e pools de uma implantação herdada. Nem todos os procedimentos listados nesta seção são necessários. Leia a documentação e determine qual procedimento de descomissionamento usar.
ms.openlocfilehash: 5edad470bcd7bcf0340a311a890f73ef01645138
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236993"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="91386-105">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="91386-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="91386-106">O tópico a seguir fornece uma orientação para atualizar entradas DNS, mover o servidor de gerenciamento de conteúdo, descomissionar pools e desativar e remover servidores e pools de uma implantação herdada.</span><span class="sxs-lookup"><span data-stu-id="91386-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="91386-107">Nem todos os procedimentos listados nesta seção são necessários.</span><span class="sxs-lookup"><span data-stu-id="91386-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="91386-108">Leia a documentação e determine qual procedimento de descomissionamento usar.</span><span class="sxs-lookup"><span data-stu-id="91386-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="91386-109">Para obter um artigo mais atualizado sobre a remoção de servidores e funções de servidor e um guia passo a passo para encerrar uma implantação, baixe a [desinstalação do Microsoft Lync Server e a remoção de funções de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="91386-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="91386-110">Para obter informações sobre como migrar e atualizar aplicativos da API gerenciada do Microsoft Unified Communication (UCMA), antes de encerrar o ambiente herdado, consulte [aplicativos do UCMA: cenários de coexistência, migração e atualização](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="91386-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="91386-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="91386-111">In this section</span></span>

> [<span data-ttu-id="91386-112">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="91386-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="91386-113">Mover o servidor de gerenciamento central de instalação herdada para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="91386-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="91386-114">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="91386-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="91386-115">Remover a associação de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="91386-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="91386-116">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="91386-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="91386-117">Remover o servidor front-end do Enterprise Edition ou o servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="91386-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="91386-118">Remover instâncias SQL Server e bancos de dados no Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="91386-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

