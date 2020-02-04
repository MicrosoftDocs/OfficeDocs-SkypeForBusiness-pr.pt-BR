---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Você publica a topologia que você configurou usando o construtor de topologias. Você será solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o repositório de gerenciamento central. Somente um servidor front-end ou um pool de front-end pode reter essa função a qualquer momento.
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701666"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="1a287-105">Publicar Página CMS de Seleção de Topologia</span><span class="sxs-lookup"><span data-stu-id="1a287-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="1a287-106">Você publica a topologia que você configurou usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1a287-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="1a287-107">Você será solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="1a287-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="1a287-108">Somente um servidor front-end ou um pool de front-end pode reter essa função a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="1a287-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="1a287-109">Sobre o servidor de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="1a287-109">About the Central Management Server</span></span>
<span data-ttu-id="1a287-110">O servidor de gerenciamento central é um único sistema de réplica mestra/múltipla, em que a cópia de leitura/gravação do banco de dados é mantida pelo servidor front-end que contém o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="1a287-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="1a287-111">Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura dos dados do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalados no computador durante a instalação e implementação.</span><span class="sxs-lookup"><span data-stu-id="1a287-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="1a287-112">O banco de dados local recebe atualizações de réplica por meio do agente duplicador de réplica do Lync Server que é executado como um serviço em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="1a287-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="1a287-113">O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="1a287-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="1a287-114">O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1a287-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="1a287-115">Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Lync Server usam o SCP para localizar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="1a287-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a287-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="1a287-116">See also</span></span>

[<span data-ttu-id="1a287-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="1a287-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
