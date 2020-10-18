---
title: 'Lync Server 2013: topologias do Active Directory com suporte'
description: 'Lync Server 2013: topologias do Active Directory com suporte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575307"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="6478e-103">Topologias do Active Directory com suporte no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6478e-103">Supported Active Directory topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6478e-104">_**Última modificação do tópico:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="6478e-104">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="6478e-105">O Lync Server 2013 oferece suporte às mesmas topologias de serviços de domínio do Active Directory que o Microsoft Lync Server 2010 e o Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6478e-105">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6478e-106">s topologias abaixo têm suporte:</span><span class="sxs-lookup"><span data-stu-id="6478e-106">The following topologies are supported:</span></span>

  - <span data-ttu-id="6478e-107">Floresta única com domínio único</span><span class="sxs-lookup"><span data-stu-id="6478e-107">Single forest with single domain</span></span>

  - <span data-ttu-id="6478e-108">Floresta única com uma única árvore e vários domínios</span><span class="sxs-lookup"><span data-stu-id="6478e-108">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="6478e-109">Floresta única com várias árvores e namespaces não contíguos</span><span class="sxs-lookup"><span data-stu-id="6478e-109">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="6478e-110">Várias florestas em uma topologia de floresta central</span><span class="sxs-lookup"><span data-stu-id="6478e-110">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="6478e-111">Várias florestas em uma topologia de floresta de recursos</span><span class="sxs-lookup"><span data-stu-id="6478e-111">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="6478e-112">Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6478e-112">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="6478e-113">A figura a seguir identifica os ícones usados nas ilustrações desta seção.</span><span class="sxs-lookup"><span data-stu-id="6478e-113">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="6478e-114">**Chave para ilustrações de topologia**</span><span class="sxs-lookup"><span data-stu-id="6478e-114">**Key to topology illustrations**</span></span>

<span data-ttu-id="6478e-115">![Chave para ilustrações de topologia](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Chave para ilustrações de topologia")</span><span class="sxs-lookup"><span data-stu-id="6478e-115">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="6478e-116">Floresta única, domínio único</span><span class="sxs-lookup"><span data-stu-id="6478e-116">Single Forest, Single Domain</span></span>

<span data-ttu-id="6478e-117">A topologia mais simples do Active Directory com suporte no Lync Server, uma floresta de domínio único, é uma topologia comum.</span><span class="sxs-lookup"><span data-stu-id="6478e-117">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="6478e-118">A figura a seguir ilustra uma implantação do Lync Server em uma única topologia de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6478e-118">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="6478e-119">**Topologia de domínio único**</span><span class="sxs-lookup"><span data-stu-id="6478e-119">**Single domain topology**</span></span>

<span data-ttu-id="6478e-120">![Topologia de domínio único](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologia de domínio único")</span><span class="sxs-lookup"><span data-stu-id="6478e-120">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="6478e-121">Floresta única, vários domínios</span><span class="sxs-lookup"><span data-stu-id="6478e-121">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="6478e-122">Outra topologia do Active Directory com suporte no Lync Server é uma única floresta que consiste em um domínio raiz e um ou mais domínios filho.</span><span class="sxs-lookup"><span data-stu-id="6478e-122">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="6478e-123">Nesse tipo de topologia do Active Directory, o domínio em que você cria usuários pode ser diferente do domínio no qual você está implantando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6478e-123">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="6478e-124">Porém, se você implantar um pool de Front-Ends, você deve implantar todos os Servidores de Front-Ends no pool com um único domínio.</span><span class="sxs-lookup"><span data-stu-id="6478e-124">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="6478e-125">O suporte do Lync Server para grupos de administradores universais do Windows permite a administração entre domínios.</span><span class="sxs-lookup"><span data-stu-id="6478e-125">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="6478e-126">A figura a seguir ilustra uma implantação em uma floresta única com vários domínios.</span><span class="sxs-lookup"><span data-stu-id="6478e-126">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="6478e-127">Nesta figura, um ícone de usuário mostra o domínio no qual a conta de usuário está hospedada e a seta aponta para o domínio onde reside o pool do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6478e-127">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="6478e-128">As contas de usuário incluem:</span><span class="sxs-lookup"><span data-stu-id="6478e-128">User accounts include the following:</span></span>

  - <span data-ttu-id="6478e-129">Contas de usuário no mesmo domínio que o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6478e-129">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="6478e-130">Contas de usuário em um domínio diferente do pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6478e-130">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="6478e-131">Contas de usuário em um domínio filho do domínio com o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6478e-131">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="6478e-132">**Floresta única com vários domínios**</span><span class="sxs-lookup"><span data-stu-id="6478e-132">**Single forest with multiple domains**</span></span>

<span data-ttu-id="6478e-133">![Floresta única com vários domínios](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Floresta única com vários domínios")</span><span class="sxs-lookup"><span data-stu-id="6478e-133">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="6478e-134">Floresta única, várias árvores</span><span class="sxs-lookup"><span data-stu-id="6478e-134">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="6478e-135">Uma topologia de floresta com várias árvores consiste em dois ou mais domínios que definem estruturas de árvore independentes e namespaces do Active Directory separados.</span><span class="sxs-lookup"><span data-stu-id="6478e-135">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="6478e-136">A figura a seguir ilustra uma floresta única com várias árvores.</span><span class="sxs-lookup"><span data-stu-id="6478e-136">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="6478e-137">Nesta figura, um ícone de usuário mostra o domínio no qual a conta de usuário está hospedada, uma linha sólida aponta para um pool do Lync Server que reside no mesmo domínio ou em um domínio diferente, e uma linha tracejada aponta para o pool do Lync Server que reside em uma árvore diferente.</span><span class="sxs-lookup"><span data-stu-id="6478e-137">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="6478e-138">As contas de usuário incluem:</span><span class="sxs-lookup"><span data-stu-id="6478e-138">User accounts include the following:</span></span>

  - <span data-ttu-id="6478e-139">Contas de usuário no mesmo domínio que o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6478e-139">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="6478e-140">Contas de usuário em um domínio diferente de (mas a mesma árvore que) o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6478e-140">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="6478e-141">Contas de usuário em uma árvore diferente do pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6478e-141">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="6478e-142">**Floresta única com várias árvores**</span><span class="sxs-lookup"><span data-stu-id="6478e-142">**Single forest with multiple trees**</span></span>

<span data-ttu-id="6478e-143">![Floresta única com várias árvores](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Floresta única com várias árvores")</span><span class="sxs-lookup"><span data-stu-id="6478e-143">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="6478e-144">Várias florestas, floresta central</span><span class="sxs-lookup"><span data-stu-id="6478e-144">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="6478e-145">O Lync Server oferece suporte a várias florestas configuradas em uma topologia de floresta central.</span><span class="sxs-lookup"><span data-stu-id="6478e-145">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="6478e-146">Topologias de floresta central usam objetos de contato na floresta central para representar os usuários nas outras florestas.</span><span class="sxs-lookup"><span data-stu-id="6478e-146">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="6478e-147">A floresta central também hospeda contas de usuário para os usuários dessa floresta.</span><span class="sxs-lookup"><span data-stu-id="6478e-147">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="6478e-148">Um produto da sincronização do diretório, como um Microsoft Identity Integration Server (MIIS), um Microsoft Forefront Identity Manager (FIM) 2010 ou um Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário dentro da organização: quando um novo usuário é criado em uma das florestas ou quando uma conta de usuário é excluída de uma floresta, o produto de sincronização do diretório sincroniza o contato correspondente na floresta central.</span><span class="sxs-lookup"><span data-stu-id="6478e-148">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="6478e-149">Uma floresta central tem as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="6478e-149">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="6478e-150">Os servidores que executam o Lync Server são centralizados em uma única floresta.</span><span class="sxs-lookup"><span data-stu-id="6478e-150">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="6478e-151">Os usuários podem procurar outros usuários em qualquer floresta e se comunicar com eles.</span><span class="sxs-lookup"><span data-stu-id="6478e-151">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="6478e-152">Os usuários podem visualizar a presença de outros usuários em qualquer floresta.</span><span class="sxs-lookup"><span data-stu-id="6478e-152">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="6478e-153">O produto da sincronização do diretório automatiza a adição e a exclusão de objetos de contato na floresta central à medida que as contas de usuários são criadas ou removidas.</span><span class="sxs-lookup"><span data-stu-id="6478e-153">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="6478e-154">A figura a seguir ilustra a topologia de floresta central.</span><span class="sxs-lookup"><span data-stu-id="6478e-154">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="6478e-155">Nesta figura, há relações de confiança de duas vias entre o domínio que hospeda o Lync Server, que está na floresta central e cada domínio somente usuário, que está em uma floresta separada.</span><span class="sxs-lookup"><span data-stu-id="6478e-155">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="6478e-156">O esquema nas florestas de usuários separadas não precisa ser estendido.</span><span class="sxs-lookup"><span data-stu-id="6478e-156">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="6478e-157">**Topologia de floresta central**</span><span class="sxs-lookup"><span data-stu-id="6478e-157">**Central forest topology**</span></span>

<span data-ttu-id="6478e-158">![Topologia de floresta central](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologia de floresta central")</span><span class="sxs-lookup"><span data-stu-id="6478e-158">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="6478e-159">Várias florestas, floresta de recursos</span><span class="sxs-lookup"><span data-stu-id="6478e-159">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="6478e-160">Em uma topologia de floresta de recursos, uma floresta é dedicada à execução de aplicativos de servidor, como o Microsoft Exchange Server e o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6478e-160">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="6478e-161">A floresta de recursos hospeda os aplicativos de servidor e uma representação sincronizada do objeto de usuário ativo, mas não inclui contas de usuário habilitadas para logon.</span><span class="sxs-lookup"><span data-stu-id="6478e-161">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="6478e-162">A floresta de recursos atua como um ambiente de serviços compartilhado para as outras florestas em que os objetos de usuário residem.</span><span class="sxs-lookup"><span data-stu-id="6478e-162">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="6478e-163">As florestas de usuários têm uma relação de confiança no nível de floresta com a floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6478e-163">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="6478e-164">Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuários.</span><span class="sxs-lookup"><span data-stu-id="6478e-164">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="6478e-165">Se o Microsoft Exchange já estiver implantado na floresta de recursos, talvez as contas de usuário desabilitadas já existam.</span><span class="sxs-lookup"><span data-stu-id="6478e-165">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="6478e-166">Um produto de sincronização do diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="6478e-166">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="6478e-167">Quando uma nova conta de usuário é criada em uma das florestas do usuário ou quando uma conta de usuário é excluída de uma floresta, o produto de sincronização do diretório sincroniza a representação do usuário correspondente na floresta de recurso.</span><span class="sxs-lookup"><span data-stu-id="6478e-167">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="6478e-p108">Essa topologia pode ser usada para fornecer uma infraestrutura compartilhada para os serviços nas organizações que gerenciam várias florestas ou para separar a administração de objetos do Active Directory de outros tipos de administração. As empresas que precisam isolar a administração do Active Directory por motivos de segurança escolhem essa topologia com frequência.</span><span class="sxs-lookup"><span data-stu-id="6478e-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="6478e-170">Essa topologia proporciona a vantagem de limitar a necessidade de estender o esquema do Active Directory a uma única floresta (a saber, a floresta de recursos).</span><span class="sxs-lookup"><span data-stu-id="6478e-170">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="6478e-171">O diagrama a seguir ilustra uma topologia de floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6478e-171">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="6478e-172">**Topologia da floresta de recursos**</span><span class="sxs-lookup"><span data-stu-id="6478e-172">**Resource forest topology**</span></span>

<span data-ttu-id="6478e-173">![Topologia de floresta de recursos do Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologia de floresta de recursos do Active Directory")</span><span class="sxs-lookup"><span data-stu-id="6478e-173">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="6478e-174">Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6478e-174">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="6478e-175">Nesta topologia, uma ou mais florestas estão localizadas no local e são dedicadas à Hospedagem de contas de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6478e-175">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="6478e-176">A floresta de recursos está localizada fora do local e é mantida por um provedor de Hospedagem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="6478e-176">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="6478e-177">A floresta de recursos contém apenas a implantação do Lync Server e uma replicação sincronizada das contas de usuário da (s) floresta (s) contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="6478e-177">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="6478e-178">Ele não contém contas de usuário habilitadas para logon.</span><span class="sxs-lookup"><span data-stu-id="6478e-178">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="6478e-179">O Exchange é implantado na (s) floresta (s) de contas de usuário local integrada junto com o Exchange Online (híbrido) ou os serviços de email para as contas de usuário locais são fornecidos exclusivamente pelo Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6478e-179">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="6478e-180">A floresta de recursos atua como um ambiente de serviços compartilhados para a (s) floresta (s) do Active Directory local onde os objetos de usuário residem.</span><span class="sxs-lookup"><span data-stu-id="6478e-180">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="6478e-181">As florestas de contas de usuário têm uma relação de confiança de nível de floresta unidirecional com a floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6478e-181">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="6478e-182">Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuários.</span><span class="sxs-lookup"><span data-stu-id="6478e-182">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="6478e-183">Um produto de sincronização do diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="6478e-183">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="6478e-184">Quando uma nova conta de usuário é criada em uma das florestas do usuário ou quando uma conta de usuário é excluída de uma floresta, o produto de sincronização do diretório sincroniza a representação do usuário correspondente na floresta de recurso.</span><span class="sxs-lookup"><span data-stu-id="6478e-184">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="6478e-185">Para obter mais informações sobre como configurar uma implantação de várias florestas, consulte [Deploying Lync in a multi-Forest Architecture (Lync Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="6478e-185">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

