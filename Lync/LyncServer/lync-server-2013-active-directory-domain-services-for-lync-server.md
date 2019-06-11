---
title: 'Lync Server 2013: serviços de domínio do Active Directory para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="b8294-102">Serviços de domínio do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8294-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8294-103">_**Tópico da última modificação:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="b8294-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="b8294-104">O serviços de domínio Active Directory funciona como o serviço de diretório para redes Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b8294-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="b8294-105">Os serviços de domínio Active Directory também servem como a base na qual a infraestrutura de segurança do Microsoft Lync Server 2013 é criada.</span><span class="sxs-lookup"><span data-stu-id="b8294-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="b8294-106">A finalidade desta seção é descrever como o Lync Server 2013 usa os serviços de domínio do Active Directory para criar um ambiente confiável para mensagens instantâneas, conferência na Web, mídia e voz.</span><span class="sxs-lookup"><span data-stu-id="b8294-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="b8294-107">Para obter detalhes sobre as extensões do Lync Server para os serviços de domínio do Active Directory e sobre como preparar seu ambiente para os serviços de domínio Active Directory, consulte [preparando os serviços de domínio Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na implantação documentação.</span><span class="sxs-lookup"><span data-stu-id="b8294-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="b8294-108">Para obter detalhes sobre a função dos serviços de domínio do Active Directory nas redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.</span><span class="sxs-lookup"><span data-stu-id="b8294-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="b8294-109">O Lync Server 2013 usa os serviços de domínio do Active Directory para armazenar:</span><span class="sxs-lookup"><span data-stu-id="b8294-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="b8294-110">Configurações globais que são necessárias para todos os servidores que executam o Lync Server 2013 em uma floresta.</span><span class="sxs-lookup"><span data-stu-id="b8294-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="b8294-111">Informações do serviço que identificam as funções de todos os servidores que executam o Lync Server 2013 em uma floresta.</span><span class="sxs-lookup"><span data-stu-id="b8294-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="b8294-112">Algumas configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="b8294-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="b8294-113">Infraestrutura do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8294-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="b8294-114">Os requisitos de infraestrutura do Active Directory incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8294-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="b8294-115">Requisitos do sistema operacional para controladores de domínio</span><span class="sxs-lookup"><span data-stu-id="b8294-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="b8294-116">Requisitos de níveis funcionais de domínio e de floresta</span><span class="sxs-lookup"><span data-stu-id="b8294-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="b8294-117">Requisitos de domínio do catálogo global</span><span class="sxs-lookup"><span data-stu-id="b8294-117">Global catalog domain requirements</span></span>

<span data-ttu-id="b8294-118">Para obter detalhes, consulte [requisitos de infraestrutura do Active Directory para o Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="b8294-119">Preparação dos serviços de domínio Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8294-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8294-120">Recomendamos que você implante as configurações globais no contêiner de configuração, em vez do contêiner do sistema.</span><span class="sxs-lookup"><span data-stu-id="b8294-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="b8294-121">Isso não melhora a segurança, mas pode resultar em melhorias de escalabilidade para algumas topologias de serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8294-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="b8294-122">Se estiver migrando do Microsoft Office Communications Server 2007 e tiver usado o contêiner do sistema, mas planejar o uso do contêiner de configuração, você deverá mover as configurações no contêiner do sistema antes de fazer os preparativos de atualização.</span><span class="sxs-lookup"><span data-stu-id="b8294-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="b8294-123">Para migrar as configurações do contêiner do sistema para o contêiner de configuração, confira a ferramenta de migração <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>de configurações globais do Office Communications Server 2007 em.</span><span class="sxs-lookup"><span data-stu-id="b8294-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="b8294-124">Ao implantar o Lync Server 2013, a primeira etapa é preparar os serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8294-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="b8294-125">A preparação dos serviços de domínio Active Directory para o Lync Server 2013 consiste nas três etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="b8294-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="b8294-126">**Preparar o esquema**.</span><span class="sxs-lookup"><span data-stu-id="b8294-126">**Prepare Schema**.</span></span> <span data-ttu-id="b8294-127">Essa tarefa estende o esquema nos serviços de domínio Active Directory para incluir classes e atributos específicos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8294-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="b8294-128">Para obter detalhes sobre como preparar o esquema, consulte [executando a preparação do esquema do Active Directory no Lync Server 2013](lync-server-2013-running-schema-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="b8294-129">Para obter mais informações, consulte [migrar do Office Communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="b8294-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="b8294-130">**Preparar a floresta**.</span><span class="sxs-lookup"><span data-stu-id="b8294-130">**Prepare Forest**.</span></span> <span data-ttu-id="b8294-131">Essa tarefa cria configurações e objetos globais no domínio raiz da floresta, juntamente com o serviço universal e os grupos administrativos que controlam o acesso a essas configurações e objetos.</span><span class="sxs-lookup"><span data-stu-id="b8294-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="b8294-132">Para obter detalhes sobre como preparar a floresta, consulte [executando a preparação da floresta para o Lync Server 2013](lync-server-2013-running-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="b8294-133">**Prepare o domínio**.</span><span class="sxs-lookup"><span data-stu-id="b8294-133">**Prepare Domain**.</span></span> <span data-ttu-id="b8294-134">Essa tarefa adiciona as entradas de controle de acesso (ACEs) necessárias a grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio.</span><span class="sxs-lookup"><span data-stu-id="b8294-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="b8294-135">Essa tarefa deve ser concluída em todos os domínios em que você deseja implantar servidores que executam o Lync Server 2013 e qualquer domínio onde os usuários do Lync Server estejam.</span><span class="sxs-lookup"><span data-stu-id="b8294-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="b8294-136">Para obter detalhes sobre como preparar o domínio, consulte [executando a preparação do domínio para o Lync Server 2013](lync-server-2013-running-domain-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b8294-137">Para obter uma visão geral do processo completo de preparação do Active Directory e dos direitos e permissões necessários para executar cada etapa, consulte [requisitos de infraestrutura do Active Directory para o Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="b8294-138">Grupos Universais</span><span class="sxs-lookup"><span data-stu-id="b8294-138">Universal Groups</span></span>

<span data-ttu-id="b8294-139">Durante a preparação da floresta, o Lync Server 2013 cria vários grupos universais dentro dos serviços de domínio do Active Directory que têm permissão para acessar e gerenciar configurações e serviços globais.</span><span class="sxs-lookup"><span data-stu-id="b8294-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="b8294-140">Esses grupos universais incluem:</span><span class="sxs-lookup"><span data-stu-id="b8294-140">These universal groups include:</span></span>

  - <span data-ttu-id="b8294-141">**Grupos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="b8294-141">**Administrative groups**.</span></span> <span data-ttu-id="b8294-142">Esses grupos definem as funções de administrador fundamentais para uma rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8294-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="b8294-143">Durante a preparação da floresta, esses grupos de administradores são adicionados aos grupos de infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8294-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="b8294-144">**Grupos de Serviços**.</span><span class="sxs-lookup"><span data-stu-id="b8294-144">**Service groups**.</span></span> <span data-ttu-id="b8294-145">Esses grupos são contas de serviço que são necessárias para acessar vários serviços fornecidos pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8294-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="b8294-146">**Grupos de infraestrutura**.</span><span class="sxs-lookup"><span data-stu-id="b8294-146">**Infrastructure groups**.</span></span> <span data-ttu-id="b8294-147">Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8294-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="b8294-148">Eles funcionam como componentes dos grupos administrativos e você não deve modificá-los nem adicionar usuários diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="b8294-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="b8294-149">Durante a preparação da floresta, grupos de serviços e de administração específicos são adicionados aos grupos de infraestrutura adequados.</span><span class="sxs-lookup"><span data-stu-id="b8294-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="b8294-150">Para obter detalhes sobre os grupos universais específicos criados ao preparar o AD para o Lync Server, bem como os grupos de serviços e administração que são adicionados aos grupos de infraestrutura, consulte [alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na Documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8294-151">O Lync Server 2013 dá suporte a grupos universais no Windows Server 2012 para servidores que executam o Lync Server 2013, bem como sistemas operacionais Windows Server 2003 para controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="b8294-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="b8294-152">Os membros dos grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínio e podem receber permissões em qualquer domínio na árvore ou floresta de domínio.</span><span class="sxs-lookup"><span data-stu-id="b8294-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="b8294-153">O suporte a grupos universais, combinado com delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8294-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="b8294-154">Por exemplo, não é necessário adicionar um domínio a outro para permitir que um administrador os gerencie.</span><span class="sxs-lookup"><span data-stu-id="b8294-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="b8294-155">Controle de Acesso Baseado em Função</span><span class="sxs-lookup"><span data-stu-id="b8294-155">Role-Based Access Control</span></span>

<span data-ttu-id="b8294-156">Além de criar grupos de serviços e administração universais e de adicionar grupos de serviços e de administração aos grupos universais adequados, a preparação da floresta também cria grupos de Controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b8294-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="b8294-157">Para obter detalhes sobre os grupos de RBAC específicos criados pela preparação da floresta, consulte [alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="b8294-158">Para obter mais informações sobre grupos RBAC, consulte [controle de acesso baseado em função (RBAC) para o Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="b8294-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="b8294-159">Entradas de controle de acesso (ACEs) e Herança</span><span class="sxs-lookup"><span data-stu-id="b8294-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="b8294-160">A preparação da floresta cria ACEs privadas e públicas, adicionando ACEs nos grupos universais criados.</span><span class="sxs-lookup"><span data-stu-id="b8294-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="b8294-161">Ele cria ACEs privadas específicas no contêiner de configurações globais usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8294-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="b8294-162">Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner do sistema do domínio raiz, dependendo de onde você armazenou as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="b8294-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="b8294-p114">A etapa de preparação do domínio adiciona entradas de controle de acesso (ACEs) necessárias aos grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio. A preparação do domínio cria ACEs no domínio raiz e três contêiners integrados: Usuário, Computadores e Controladores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="b8294-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="b8294-165">Para obter detalhes sobre os ases públicos criados e adicionados pela preparação da floresta e pela preparação do domínio, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [alterações feitas por preparação do domínio no Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) na implantação documentação.</span><span class="sxs-lookup"><span data-stu-id="b8294-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b8294-166">Geralmente, as organizações bloqueiam os serviços de domínio Active Directory (AD DS) para ajudar a reduzir os riscos de segurança.</span><span class="sxs-lookup"><span data-stu-id="b8294-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="b8294-167">No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8294-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="b8294-168">Isso inclui remover ACEs dos contêineres e OUs e desabilitar a herança de permissões nos objetos de Usuário, Contato, InetOrgPerson ou Computador.</span><span class="sxs-lookup"><span data-stu-id="b8294-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="b8294-169">Em um ambiente bloqueado do Active Directory, as permissões devem ser definidas manualmente em contêineres e UOs que exigem.</span><span class="sxs-lookup"><span data-stu-id="b8294-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="b8294-170">Para obter detalhes, consulte [preparando os serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8294-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="b8294-171">Informações do servidor</span><span class="sxs-lookup"><span data-stu-id="b8294-171">Server Information</span></span>

<span data-ttu-id="b8294-172">Durante a ativação, o Lync Server 2013 publica as informações do servidor nos três seguintes locais nos serviços de domínio Active Directory:</span><span class="sxs-lookup"><span data-stu-id="b8294-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="b8294-173">Um SCP (ponto de conexão de serviço) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="b8294-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="b8294-174">Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.</span><span class="sxs-lookup"><span data-stu-id="b8294-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="b8294-175">Servidores confiáveis especificados no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b8294-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="b8294-176">Pontos de conexão de serviço</span><span class="sxs-lookup"><span data-stu-id="b8294-176">Service Connection Points</span></span>

<span data-ttu-id="b8294-177">Cada objeto do Lync Server 2013 nos serviços de domínio Active Directory tem um SCP chamado serviços RTC, que, por sua vez, contém vários atributos que identificam cada computador e especificam os serviços que ele fornece.</span><span class="sxs-lookup"><span data-stu-id="b8294-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="b8294-178">Dentre os atributos SCP mais importantes estão *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* e *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="b8294-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="b8294-179">Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando esses e outros atributos SCP.</span><span class="sxs-lookup"><span data-stu-id="b8294-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="b8294-180">Objetos de servidor do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8294-180">Active Directory Server Objects</span></span>

<span data-ttu-id="b8294-181">Cada função de servidor do Lync Server 2013 tem um objeto do Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função.</span><span class="sxs-lookup"><span data-stu-id="b8294-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="b8294-182">Além disso, quando um servidor de edição padrão é ativado ou quando um pool da Enterprise Edition é criado, o Lync Server 2013 cria um novo objeto **msRTCSIP-pool** no contêiner **msRTCSIP-Pools** .</span><span class="sxs-lookup"><span data-stu-id="b8294-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="b8294-183">A classe **msRTCSIP-Pool** especifica o nome de domínio totalmente qualificado (FQDN) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool.</span><span class="sxs-lookup"><span data-stu-id="b8294-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="b8294-184">(Um servidor Standard Edition é considerado um pool lógico cujas extremidades dianteiras e posteriores são posicionadas em um único computador.)</span><span class="sxs-lookup"><span data-stu-id="b8294-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="b8294-185">Servidores confiáveis</span><span class="sxs-lookup"><span data-stu-id="b8294-185">Trusted Servers</span></span>

<span data-ttu-id="b8294-186">No Lync Server 2013, os servidores confiáveis são aqueles especificados quando você executa o construtor de topologias e publica sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b8294-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="b8294-187">A topologia publicada, incluindo todas informações de servidor, é armazenada no Repositório de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="b8294-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="b8294-188">Apenas servidores definidos no Repositório de Gerenciamento Central são confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b8294-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="b8294-189">No Lync Server 2013, um servidor confiável é aquele que atende aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="b8294-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="b8294-190">O FQDN do servidor é apresentado na topologia armazenada no Repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="b8294-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="b8294-191">O servidor apresenta um certificado válido de uma CA confiável.</span><span class="sxs-lookup"><span data-stu-id="b8294-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="b8294-192">Para obter detalhes, consulte [requisitos de infraestrutura de certificado para o Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8294-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="b8294-p120">Se algum desses critérios não for cumprido, o servidor não é confiável e a conexão será recusada. Este requisito duplo impede um possível, mesmo se improvável, ataque em que um servidor não autorizado tenta assumir um FQDN de um servidor válido.</span><span class="sxs-lookup"><span data-stu-id="b8294-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="b8294-195">Além disso, para habilitar implantações do Microsoft Office Communications Server 2007 R2 e do Microsoft Office Communications Server 2007 para se comunicar com servidores do Lync Server 2013, o Lync Server 2013 cria contêineres durante a preparação da floresta para listas de servidores confiáveis para versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b8294-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="b8294-196">A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implantações anteriores.</span><span class="sxs-lookup"><span data-stu-id="b8294-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="b8294-197">Listas de servidores confiáveis e seus contêineres do Active Directory para compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="b8294-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8294-198">Lista de servidor confiável</span><span class="sxs-lookup"><span data-stu-id="b8294-198">Trusted server list</span></span></th>
<th><span data-ttu-id="b8294-199">Contêiner do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8294-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8294-200">Servidor Standard Edition e Servidor Front-End do Pool Enterprise</span><span class="sxs-lookup"><span data-stu-id="b8294-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b8294-201">Configurações globais/Serviço RTC</span><span class="sxs-lookup"><span data-stu-id="b8294-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8294-202">Servidores de Conferência</span><span class="sxs-lookup"><span data-stu-id="b8294-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="b8294-203">Serviço RTC/MCUs Confiáveis</span><span class="sxs-lookup"><span data-stu-id="b8294-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8294-204">Servidores de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="b8294-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="b8294-205">Serviço RTC/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="b8294-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8294-206">Servidor de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativo, Registrador do QoE, Serviço de Conferência A/V (também servidores SIP de terceiros)</span><span class="sxs-lookup"><span data-stu-id="b8294-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="b8294-207">Serviço RTC/Serviços confiáveis</span><span class="sxs-lookup"><span data-stu-id="b8294-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8294-208">Servidores proxy</span><span class="sxs-lookup"><span data-stu-id="b8294-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="b8294-209">O Lync Server 2013 não é compatível com a compatibilidade com versões anteriores para servidores proxy</span><span class="sxs-lookup"><span data-stu-id="b8294-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b8294-210">Para dar suporte a servidores confiáveis de versões anteriores, você deve executar a ferramenta Analisador de práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="b8294-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="b8294-211">Para obter detalhes sobre como executar o analisador de [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)práticas recomendadas, consulte.</span><span class="sxs-lookup"><span data-stu-id="b8294-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

