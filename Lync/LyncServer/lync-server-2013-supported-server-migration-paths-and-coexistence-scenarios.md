---
title: 'Lync Server 2013: caminhos de migração de servidor suportados e cenários de coexistência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 168cea4e41b7ff51e03132e300c2085a82f8bc66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="6a4f4-102">Caminhos de migração de servidor suportados e cenários de coexistência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4f4-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a4f4-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="6a4f4-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6a4f4-104">O Lync Server 2013 oferece suporte à migração de um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6a4f4-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="6a4f4-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6a4f4-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="6a4f4-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6a4f4-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="6a4f4-107">A migração de um ambiente executando ambas as versões anteriores não é suportada.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="6a4f4-108">A migração de versões anteriores, como o Microsoft Office Communications Server 2007 ou o Live Communications Server 2005, não é suportada.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="6a4f4-109">Se sua implantação anterior incluiu o chat de grupo, você deve migrá-lo separadamente.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="6a4f4-110">Métodos de migração</span><span class="sxs-lookup"><span data-stu-id="6a4f4-110">Migration Methods</span></span>

<span data-ttu-id="6a4f4-111">Há suporte para a migração de todas as topologias do Lync Server e funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="6a4f4-112">É possível migrar de uma topologia para uma topologia diferente, incluindo do servidor Standard Edition para o servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="6a4f4-113">O Lync Server 2013 suporta apenas o seguinte método de migração:</span><span class="sxs-lookup"><span data-stu-id="6a4f4-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="6a4f4-114">**Migração lado a lado.**</span><span class="sxs-lookup"><span data-stu-id="6a4f4-114">**Side-by-side migration.**</span></span> <span data-ttu-id="6a4f4-115">Na migração lado a lado, o Lync Server 2013 é implantado junto com uma implantação existente do Microsoft Lync Server 2010 ou do Office Communications Server 2007 R2 e, em seguida, transfere operações para os novos servidores e move os usuários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="6a4f4-116">Esse método exige plataformas de servidor adicionais, incluindo hardware e software, durante a migração, e nomes de sistema e de pool são diferentes na nova configuração.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="6a4f4-117">Se for necessário reverter para a versão anterior, você poderá retornar as operações para os servidores anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="6a4f4-118">Não há suporte para a migração entre florestas de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="6a4f4-p104">O caminho de migração recomendado é uma abordagem de base. Para obter detalhes sobre a migração de uma versão anterior, incluindo a fase adequada da implantação de componente, consulte os seguintes tópicos na documentação de Migração:</span><span class="sxs-lookup"><span data-stu-id="6a4f4-p104">The recommended migration path is a phased approach. For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="6a4f4-121">Migração do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4f4-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="6a4f4-122">Migração do Office Communications Server 2007 R2 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4f4-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="6a4f4-123">Migração do Lync Server 2010, Chat em Grupo ou Office Communications Server 2007 R2 Group Chat para Lync Server 2013, Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="6a4f4-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="6a4f4-124">Cenários de coexistência</span><span class="sxs-lookup"><span data-stu-id="6a4f4-124">Coexistence Scenarios</span></span>

<span data-ttu-id="6a4f4-125">O Lync Server 2013 pode coexistir com componentes de uma implantação do Lync Server 2010 ou uma implantação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="6a4f4-126">A implantação simultânea do Lync Server 2013 com o Lync Server 2010 e o Office Communications Server 2007 R2 (implantação simultânea de todas as três versões) não é suportada.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="6a4f4-127">Durante uma migração em fases na qual uma implantação anterior do Lync Server 2010 ou do Office Communications Server 2007 R2 coexiste temporariamente com a nova implantação do Lync Server 2013, o suporte para roteamento de versão mista é limitado.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="6a4f4-128">Para obter detalhes, consulte a documentação Migração.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="6a4f4-129">Você deve usar computadores separados e distintos que executam o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para suas instâncias de banco de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="6a4f4-130">Não é possível usar a mesma instância do SQL Server para um pool de front-ends do Lync Server 2013 que você usa para um pool de front-ends do Lync Server 2010 ou do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="6a4f4-131">Se você definir e configurar o Lync Server 2013 no construtor de topologias para uma implantação que já tem o Lync Server 2010 ou o Office Communications Server 2007 R2 implantado, o construtor de topologias não permitirá que você defina uma instância de um Lync Server 2013 que já está em uso no a topologia.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="6a4f4-132">O construtor de topologia exibirá a seguinte mensagem para informá-lo sobre esse problema \[: "o FQDN\] do SQL Server do servidor já contém uma instância do SQL que hospeda a função" repositório do usuário ".</span><span class="sxs-lookup"><span data-stu-id="6a4f4-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a4f4-133">Se você pretende implantar funções de servidor que são novas na sua implantação do Lync Server 2013, deve primeiro atualizar sua implantação existente conforme descrito na documentação de migração e a documentação de implantação e, em seguida, implantar as novas funções de servidor, conforme descrito em a documentação de planejamento e a documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="6a4f4-134">Se você estiver migrando uma versão anterior do chat de grupo, migre-a por último, após concluir o processo de migração de todos os outros componentes do Lync Server 2010 ou do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="6a4f4-135">Para obter requisitos específicos de coexistência e outros detalhes sobre a coexistência e a migração de componentes do Lync Server 2010 ou do Office Communications Server 2007 R2 e do Lync Server 2013, consulte [migração do Lync server 2010 para o Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) e [migração do Office communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) na documentação de migração.</span><span class="sxs-lookup"><span data-stu-id="6a4f4-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="6a4f4-136">Para obter detalhes sobre o suporte de versão mista para clientes, consulte [clientes com suporte de implantações anteriores no Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="6a4f4-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

