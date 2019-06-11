---
title: 'Lync Server 2013: Topologias do Active Directory suportadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="facf8-102">Topologias do Active Directory suportadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="facf8-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="facf8-103">_**Tópico da última modificação:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="facf8-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="facf8-104">O Lync Server 2013 oferece suporte às mesmas topologias de serviços de domínio Active Directory que o Microsoft Lync Server 2010 e o Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="facf8-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="facf8-105">Há suporte para as seguintes topologias:</span><span class="sxs-lookup"><span data-stu-id="facf8-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="facf8-106">Floresta única com domínio único</span><span class="sxs-lookup"><span data-stu-id="facf8-106">Single forest with single domain</span></span>

  - <span data-ttu-id="facf8-107">Floresta única com uma única árvore e vários domínios</span><span class="sxs-lookup"><span data-stu-id="facf8-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="facf8-108">Floresta única com várias árvores e namespaces não contíguos</span><span class="sxs-lookup"><span data-stu-id="facf8-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="facf8-109">Várias florestas em uma topologia de floresta central</span><span class="sxs-lookup"><span data-stu-id="facf8-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="facf8-110">Várias florestas em uma topologia de floresta de recursos</span><span class="sxs-lookup"><span data-stu-id="facf8-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="facf8-111">Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="facf8-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="facf8-112">A figura a seguir identifica os ícones usados nas ilustrações desta seção.</span><span class="sxs-lookup"><span data-stu-id="facf8-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="facf8-113">**Chave para ilustrações de topologia**</span><span class="sxs-lookup"><span data-stu-id="facf8-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="facf8-114">![Chave para ilustrações de topologia] (images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Chave para ilustrações de topologia")</span><span class="sxs-lookup"><span data-stu-id="facf8-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="facf8-115">Única floresta, único domínio</span><span class="sxs-lookup"><span data-stu-id="facf8-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="facf8-116">A topologia do Active Directory mais simples compatível com o Lync Server, uma floresta de domínio único, é uma topologia comum.</span><span class="sxs-lookup"><span data-stu-id="facf8-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="facf8-117">A figura a seguir ilustra uma implantação do Lync Server em uma única topologia de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="facf8-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="facf8-118">**Topologia de domínio único**</span><span class="sxs-lookup"><span data-stu-id="facf8-118">**Single domain topology**</span></span>

<span data-ttu-id="facf8-119">![Topologia de domínio único] (images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologia de domínio único")</span><span class="sxs-lookup"><span data-stu-id="facf8-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="facf8-120">Única floresta, vários domínios</span><span class="sxs-lookup"><span data-stu-id="facf8-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="facf8-121">Outra topologia do Active Directory compatível com o Lync Server é uma única floresta que consiste em um domínio raiz e um ou mais domínios filho.</span><span class="sxs-lookup"><span data-stu-id="facf8-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="facf8-122">Nesse tipo de topologia do Active Directory, o domínio em que você cria usuários pode ser diferente do domínio onde você implanta o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="facf8-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="facf8-123">No entanto, se você implantar um pool de front-end, deve implantar todos os servidores de front-end no pool dentro de um único domínio.</span><span class="sxs-lookup"><span data-stu-id="facf8-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="facf8-124">O suporte do Lync Server para grupos de administradores universais do Windows permite a administração entre domínios.</span><span class="sxs-lookup"><span data-stu-id="facf8-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="facf8-125">A figura a seguir ilustra uma implantação em uma única floresta com vários domínios.</span><span class="sxs-lookup"><span data-stu-id="facf8-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="facf8-126">Nesta figura, um ícone de usuário mostra o domínio no qual a conta de usuário é hospedada e a seta aponta para o domínio onde o pool do servidor do Lync reside.</span><span class="sxs-lookup"><span data-stu-id="facf8-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="facf8-127">As contas de usuário incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="facf8-127">User accounts include the following:</span></span>

  - <span data-ttu-id="facf8-128">Contas de usuário no mesmo domínio que o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="facf8-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="facf8-129">Contas de usuário em um domínio diferente do pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="facf8-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="facf8-130">Contas de usuário em um domínio filho do domínio com o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="facf8-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="facf8-131">**Floresta única com vários domínios**</span><span class="sxs-lookup"><span data-stu-id="facf8-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="facf8-132">![Floresta única com vários domínios] (images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Floresta única com vários domínios")</span><span class="sxs-lookup"><span data-stu-id="facf8-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="facf8-133">Única floresta, várias árvores</span><span class="sxs-lookup"><span data-stu-id="facf8-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="facf8-134">Uma topologia de floresta de várias árvores consiste em dois ou mais domínios que definem estruturas de árvore independentes e namespaces separados do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="facf8-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="facf8-135">A figura a seguir ilustra uma única floresta com várias árvores.</span><span class="sxs-lookup"><span data-stu-id="facf8-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="facf8-136">Nesta figura, um ícone de usuário mostra o domínio em que a conta de usuário é hospedada, uma linha sólida aponta para um pool do Lync Server que reside no mesmo domínio ou em um domínio diferente, e uma linha tracejada aponta para o pool do Lync Server que reside em uma árvore diferente.</span><span class="sxs-lookup"><span data-stu-id="facf8-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="facf8-137">As contas de usuário incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="facf8-137">User accounts include the following:</span></span>

  - <span data-ttu-id="facf8-138">Contas de usuário no mesmo domínio que o pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="facf8-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="facf8-139">Contas de usuário em um domínio diferente de (mas na mesma árvore que) o pool do servidor do Lync</span><span class="sxs-lookup"><span data-stu-id="facf8-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="facf8-140">Contas de usuário em uma árvore diferente do pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="facf8-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="facf8-141">**Floresta única com várias árvores**</span><span class="sxs-lookup"><span data-stu-id="facf8-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="facf8-142">![Floresta única com várias árvores] (images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Floresta única com várias árvores")</span><span class="sxs-lookup"><span data-stu-id="facf8-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="facf8-143">Várias florestas, floresta central</span><span class="sxs-lookup"><span data-stu-id="facf8-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="facf8-144">O Lync Server oferece suporte a várias florestas configuradas em uma topologia de floresta central.</span><span class="sxs-lookup"><span data-stu-id="facf8-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="facf8-145">Topologias de floresta central usam objetos de contato na floresta central para representar usuários em outras florestas.</span><span class="sxs-lookup"><span data-stu-id="facf8-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="facf8-146">A floresta central também hospeda contas de usuário para qualquer usuário dessa floresta.</span><span class="sxs-lookup"><span data-stu-id="facf8-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="facf8-147">Um produto de sincronização de diretório, como o Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida de contas de usuário em a organização: quando uma nova conta de usuário é criada em uma das florestas ou uma conta de usuário é excluída de uma floresta, o produto de sincronização de diretório sincroniza o contato correspondente na floresta central.</span><span class="sxs-lookup"><span data-stu-id="facf8-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="facf8-148">Uma floresta central tem as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="facf8-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="facf8-149">Os servidores que executam o Lync Server são centralizados em uma única floresta.</span><span class="sxs-lookup"><span data-stu-id="facf8-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="facf8-150">Os usuários podem pesquisar e se comunicar com outros usuários em qualquer floresta.</span><span class="sxs-lookup"><span data-stu-id="facf8-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="facf8-151">Os usuários podem ver a presença de outros usuários em qualquer floresta.</span><span class="sxs-lookup"><span data-stu-id="facf8-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="facf8-152">O produto de sincronização de diretório automatiza a adição e a exclusão de objetos de contato na floresta central, pois as contas de usuário são criadas ou removidas.</span><span class="sxs-lookup"><span data-stu-id="facf8-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="facf8-153">A figura a seguir ilustra uma topologia de floresta central.</span><span class="sxs-lookup"><span data-stu-id="facf8-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="facf8-154">Nesta figura, há relações de confiança bidirecionais entre o domínio que hospeda o Lync Server, que está na floresta central, e cada domínio somente de usuário, que está em uma floresta separada.</span><span class="sxs-lookup"><span data-stu-id="facf8-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="facf8-155">O esquema nas florestas de usuários separadas não precisa ser estendido.</span><span class="sxs-lookup"><span data-stu-id="facf8-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="facf8-156">**Topologia da floresta central**</span><span class="sxs-lookup"><span data-stu-id="facf8-156">**Central forest topology**</span></span>

<span data-ttu-id="facf8-157">![Topologia da floresta central] (images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologia da floresta central")</span><span class="sxs-lookup"><span data-stu-id="facf8-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="facf8-158">Várias florestas, floresta de recursos</span><span class="sxs-lookup"><span data-stu-id="facf8-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="facf8-159">Em uma topologia de floresta de recursos, uma floresta é dedicada à execução de aplicativos do servidor, como o Microsoft Exchange Server e o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="facf8-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="facf8-160">A floresta de recursos hospeda os aplicativos do servidor e uma representação sincronizada do objeto de usuário ativo, mas não contém contas de usuário habilitadas para logon.</span><span class="sxs-lookup"><span data-stu-id="facf8-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="facf8-161">A floresta de recursos age como um ambiente de serviços compartilhados para as outras florestas em que os objetos do usuário residem.</span><span class="sxs-lookup"><span data-stu-id="facf8-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="facf8-162">As florestas do usuário têm uma relação de confiança no nível da floresta com a floresta do recurso.</span><span class="sxs-lookup"><span data-stu-id="facf8-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="facf8-163">Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário.</span><span class="sxs-lookup"><span data-stu-id="facf8-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="facf8-164">Se o Microsoft Exchange já estiver implantado na floresta de recursos, talvez as contas de usuário desabilitadas já existam.</span><span class="sxs-lookup"><span data-stu-id="facf8-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="facf8-165">Um produto de sincronização de diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="facf8-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="facf8-166">Quando uma nova conta de usuário é criada em uma das florestas do usuário ou uma conta de usuário é excluída de uma floresta, o produto de sincronização de diretório sincroniza a representação de usuário correspondente na floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="facf8-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="facf8-167">Essa topologia pode ser usada para fornecer uma infraestrutura compartilhada para serviços nas organizações que gerenciam várias florestas ou para separar a administração de objetos do Active Directory de outras administração.</span><span class="sxs-lookup"><span data-stu-id="facf8-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="facf8-168">As empresas que precisam isolar a administração do Active Directory por motivos de segurança muitas vezes escolhem essa topologia.</span><span class="sxs-lookup"><span data-stu-id="facf8-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="facf8-169">Essa topologia fornece a vantagem de limitar a necessidade de estender o esquema do Active Directory para uma única floresta (ou seja, a floresta de recursos).</span><span class="sxs-lookup"><span data-stu-id="facf8-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="facf8-170">O diagrama a seguir ilustra uma topologia de floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="facf8-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="facf8-171">**Topologia da floresta de recursos**</span><span class="sxs-lookup"><span data-stu-id="facf8-171">**Resource forest topology**</span></span>

<span data-ttu-id="facf8-172">![Topologia da floresta de recursos do Active Directory] (images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologia da floresta de recursos do Active Directory")</span><span class="sxs-lookup"><span data-stu-id="facf8-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="facf8-173">Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="facf8-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="facf8-174">Nessa topologia, uma ou mais florestas estão localizadas no local e são dedicadas à Hospedagem de contas de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="facf8-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="facf8-175">A floresta de recursos está localizada fora do local e é mantida por um provedor de Hospedagem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="facf8-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="facf8-176">A floresta de recursos contém somente a implantação do Lync Server e uma replicação sincronizada das contas de usuário da (s) floresta (s) contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="facf8-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="facf8-177">Ele não contém contas de usuário habilitadas para logon.</span><span class="sxs-lookup"><span data-stu-id="facf8-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="facf8-178">O Exchange é implantado na (s) floresta (s) da conta de usuário local integrada ao Exchange Online (híbrido) ou os serviços de email das contas de usuário locais são fornecidos exclusivamente pelo Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="facf8-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="facf8-179">A floresta de recursos age como um ambiente de serviços compartilhados para a (s) floresta (s) do Active Directory local onde os objetos do usuário residem.</span><span class="sxs-lookup"><span data-stu-id="facf8-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="facf8-180">A (s) floresta (s) da conta do usuário tem uma relação de confiança unidirecional de nível de floresta com a floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="facf8-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="facf8-181">Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário.</span><span class="sxs-lookup"><span data-stu-id="facf8-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="facf8-182">Um produto de sincronização de diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="facf8-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="facf8-183">Quando uma nova conta de usuário é criada em uma das florestas do usuário ou uma conta de usuário é excluída de uma floresta, o produto de sincronização de diretório sincroniza a representação de usuário correspondente na floresta de recursos.</span><span class="sxs-lookup"><span data-stu-id="facf8-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="facf8-184">Para obter mais informações sobre como configurar uma implantação de várias florestas, consulte Implantando o [Lync em uma arquitetura de várias florestas (Lync hospedado pelo parceiro com Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="facf8-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

