---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Você publica a topologia configurada usando o Construtor de Topologias. Você é solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o armazenamento de Gerenciamento Central. Somente um servidor front-end ou pool de front-end pode manter essa função a qualquer momento.
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096877"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="a5177-105">Publicar Página CMS de Seleção de Topologia</span><span class="sxs-lookup"><span data-stu-id="a5177-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="a5177-106">Você publica a topologia configurada usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="a5177-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="a5177-107">Você é solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="a5177-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="a5177-108">Somente um servidor front-end ou pool de front-end pode manter essa função a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="a5177-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="a5177-109">Sobre o Servidor de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="a5177-109">About the Central Management Server</span></span>
<span data-ttu-id="a5177-110">O Servidor de Gerenciamento Central é um único sistema mestre/réplica múltipla, onde a cópia de leitura/gravação do banco de dados é mantida pelo Servidor de Front-End que contém o Servidor de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="a5177-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="a5177-111">Cada computador na topologia, incluindo o Servidor front-end que contém o Servidor de Gerenciamento Central, tem uma cópia somente leitura dos dados do armazenamento de Gerenciamento Central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação.</span><span class="sxs-lookup"><span data-stu-id="a5177-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="a5177-112">O banco de dados local recebe atualizações de réplica por meio do Agente replicador de réplica do Lync Server que é executado como um serviço em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="a5177-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="a5177-113">O nome do banco de dados real no Servidor de Gerenciamento Central e a réplica local é XDS, que é feito dos arquivos xds.mdf e xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="a5177-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="a5177-114">O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5177-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="a5177-115">Todas as ferramentas que usam o Servidor de Gerenciamento Central para gerenciar e configurar o Lync Server usam o SCP para localizar o armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="a5177-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5177-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5177-116">See also</span></span>

[<span data-ttu-id="a5177-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="a5177-117">Move-CsManagementServer</span></span>](/powershell/module/skype/move-csmanagementserver?view=skype-ps)