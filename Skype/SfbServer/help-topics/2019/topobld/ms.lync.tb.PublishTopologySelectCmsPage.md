---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publicar a topologia que você configurou usando o construtor de topologia. Será solicitado que você selecione em uma lista na qual pool de Front-End ou de servidor Front-End assumirá a função de reter o repositório de gerenciamento Central. Somente um pool de Front-End ou de servidor Front-End pode conter esta função em um determinado momento.
ms.openlocfilehash: 0c80fa30721fe47fc3bc4725ca4f50f8a75f7009
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873826"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="7b8d9-105">Publicar Página CMS de Seleção de Topologia</span><span class="sxs-lookup"><span data-stu-id="7b8d9-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="7b8d9-106">Publicar a topologia que você configurou usando o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="7b8d9-107">Será solicitado que você selecione em uma lista na qual pool de Front-End ou de servidor Front-End assumirá a função de reter o repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="7b8d9-108">Somente um pool de Front-End ou de servidor Front-End pode conter esta função em um determinado momento.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="7b8d9-109">Sobre o servidor de gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="7b8d9-109">About the Central Management Server</span></span>
<span data-ttu-id="7b8d9-110">O servidor de gerenciamento Central é um sistema de única réplica mestre/múltiplo, onde a cópia de leitura/gravação do banco de dados é mantida por servidor Front-End que contém o servidor de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="7b8d9-111">Cada computador na topologia, incluindo o servidor Front-End que contém o servidor de gerenciamento Central, tem uma cópia somente leitura dos dados do repositório de gerenciamento Central em dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="7b8d9-112">O banco de dados local recebe atualizações de réplica por meio de agente replicador de réplica de servidor do Lync que é executado como um serviço em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="7b8d9-113">O nome do banco de dados real no servidor de gerenciamento Central e da réplica local é XDS, que é composta dos arquivos XDS. mdf e xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="7b8d9-114">O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="7b8d9-115">Todas as ferramentas que usam o servidor de gerenciamento Central para gerenciar e configurar o Lync Server usam o SCP para localizar o repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="7b8d9-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b8d9-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b8d9-116">See also</span></span>

[<span data-ttu-id="7b8d9-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="7b8d9-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
