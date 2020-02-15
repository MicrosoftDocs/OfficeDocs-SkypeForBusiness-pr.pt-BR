---
title: 'Lync Server 2013: serviços de domínio do Active Directory para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b53b878d7f41a5eb83eb67d98fc69d68709a603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="ff22d-102">Serviços de domínio do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff22d-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff22d-103">_**Última modificação do tópico:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="ff22d-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="ff22d-104">O serviços de domínio do Active Directory funciona como o serviço de diretório para redes Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="ff22d-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="ff22d-105">Os serviços de domínio do Active Directory também servem como a base na qual a infraestrutura de segurança do Microsoft Lync Server 2013 é criada.</span><span class="sxs-lookup"><span data-stu-id="ff22d-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="ff22d-106">O objetivo desta seção é descrever como o Lync Server 2013 usa os serviços de domínio do Active Directory para criar um ambiente confiável para mensagens instantâneas, conferências da Web, mídia e voz.</span><span class="sxs-lookup"><span data-stu-id="ff22d-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="ff22d-107">Para obter detalhes sobre as extensões do Lync Server para os serviços de domínio do Active Directory e sobre como preparar seu ambiente para os serviços de domínio do Active Directory, consulte [preparação de serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="ff22d-108">Para obter detalhes sobre a função dos Serviços de Domínio Active Directory em redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.</span><span class="sxs-lookup"><span data-stu-id="ff22d-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="ff22d-109">O Lync Server 2013 usa os serviços de domínio do Active Directory para armazenar:</span><span class="sxs-lookup"><span data-stu-id="ff22d-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="ff22d-110">Configurações globais que todos os servidores que executam o Lync Server 2013 em uma floresta exigem.</span><span class="sxs-lookup"><span data-stu-id="ff22d-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="ff22d-111">Informações de serviço que identificam as funções de todos os servidores que executam o Lync Server 2013 em uma floresta.</span><span class="sxs-lookup"><span data-stu-id="ff22d-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="ff22d-112">Algumas configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="ff22d-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="ff22d-113">Infraestrutura do Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff22d-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="ff22d-114">Os requisitos de infraestrutura do Active Directory incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ff22d-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="ff22d-115">Requisitos do sistema operacional para controladores de domínio</span><span class="sxs-lookup"><span data-stu-id="ff22d-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="ff22d-116">Requisitos de nível funcional de floresta e domínio</span><span class="sxs-lookup"><span data-stu-id="ff22d-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="ff22d-117">Requisitos de domínio do catálogo global</span><span class="sxs-lookup"><span data-stu-id="ff22d-117">Global catalog domain requirements</span></span>

<span data-ttu-id="ff22d-118">Para obter detalhes, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="ff22d-119">Preparação dos Serviços de Domínio Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff22d-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff22d-120">Recomendamos que você implante as configurações globais no contêiner de Configuração em vez do contêiner do Sistema.</span><span class="sxs-lookup"><span data-stu-id="ff22d-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="ff22d-121">Isso não melhora a segurança, mas pode resultar em melhorias de escalabilidade para algumas topologias dos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff22d-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="ff22d-122">Se você estiver migrando do Microsoft Office Communications Server 2007 e tiver usado o contêiner de sistema, mas planejar usar o contêiner de configuração, você deve mover as configurações no contêiner do sistema antes de fazer preparativos de atualização.</span><span class="sxs-lookup"><span data-stu-id="ff22d-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="ff22d-123">Para migrar as configurações do contêiner de sistema para o contêiner de configuração, confira ferramenta de migração de <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>configurações globais do Office Communications Server 2007 em.</span><span class="sxs-lookup"><span data-stu-id="ff22d-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="ff22d-124">Ao implantar o Lync Server 2013, a primeira etapa é preparar os serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff22d-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="ff22d-125">Preparar os serviços de domínio do Active Directory para o Lync Server 2013 consiste nas seguintes três etapas:</span><span class="sxs-lookup"><span data-stu-id="ff22d-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="ff22d-126">**Preparar Esquema**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-126">**Prepare Schema**.</span></span> <span data-ttu-id="ff22d-127">Esta tarefa estende o esquema nos serviços de domínio do Active Directory para incluir classes e atributos específicos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff22d-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="ff22d-128">Para obter detalhes sobre como preparar o esquema, consulte [running Active Directory Schema Preparation no Lync Server 2013](lync-server-2013-running-schema-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="ff22d-129">Para obter mais informações, consulte [migração do Office Communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ff22d-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="ff22d-130">**Preparar a floresta**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-130">**Prepare Forest**.</span></span> <span data-ttu-id="ff22d-131">Esta tarefa cria objetos e configurações globais no domínio raiz da floresta, juntamente com os grupos universais administrativos e de serviços que regulam o acesso a esses objetos e configurações.</span><span class="sxs-lookup"><span data-stu-id="ff22d-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="ff22d-132">Para obter detalhes sobre como preparar a floresta, consulte [running Forest Preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ff22d-133">**Preparar Domínio**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-133">**Prepare Domain**.</span></span> <span data-ttu-id="ff22d-134">Esta tarefa adiciona as ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="ff22d-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="ff22d-135">Essa tarefa deve ser concluída em todos os domínios em que você deseja implantar servidores que executam o Lync Server 2013 e todos os domínios onde seus usuários do Lync Server residem.</span><span class="sxs-lookup"><span data-stu-id="ff22d-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="ff22d-136">Para obter detalhes sobre como preparar o domínio, consulte [running Domain Preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ff22d-137">Para obter uma visão geral do processo completo para preparar o Active Directory e os direitos e permissões necessários para executar cada etapa, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="ff22d-138">Grupos universais</span><span class="sxs-lookup"><span data-stu-id="ff22d-138">Universal Groups</span></span>

<span data-ttu-id="ff22d-139">Durante a preparação da floresta, o Lync Server 2013 cria vários grupos universais nos serviços de domínio do Active Directory que têm permissão para acessar e gerenciar configurações globais e serviços.</span><span class="sxs-lookup"><span data-stu-id="ff22d-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="ff22d-140">Esses grupos universais incluem:</span><span class="sxs-lookup"><span data-stu-id="ff22d-140">These universal groups include:</span></span>

  - <span data-ttu-id="ff22d-141">**Grupos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-141">**Administrative groups**.</span></span> <span data-ttu-id="ff22d-142">Esses grupos definem as funções de administrador fundamentais para uma rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff22d-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="ff22d-143">Durante a preparação da floresta, esses grupos de administradores são adicionados aos grupos de infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff22d-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="ff22d-144">**Grupos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-144">**Service groups**.</span></span> <span data-ttu-id="ff22d-145">Esses grupos são contas de serviço necessárias para acessar vários serviços fornecidos pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff22d-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="ff22d-146">**Grupos de infraestrutura**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-146">**Infrastructure groups**.</span></span> <span data-ttu-id="ff22d-147">Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff22d-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="ff22d-148">Eles funcionam como componentes de grupos administrativos e você não deve modificá-los ou adicionar usuários diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="ff22d-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="ff22d-149">Durante a preparação da floresta, os grupos de serviços e de administração específicos são adicionados aos grupos de infraestrutura apropriados.</span><span class="sxs-lookup"><span data-stu-id="ff22d-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="ff22d-150">Para obter detalhes sobre os grupos universais específicos criados ao preparar o AD para o Lync Server, bem como os grupos de serviço e administração que são adicionados aos grupos de infraestrutura, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff22d-151">O Lync Server 2013 oferece suporte aos grupos universais no Windows Server 2012 para servidores que executam o Lync Server 2013, bem como sistemas operacionais Windows Server 2003 para controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="ff22d-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="ff22d-152">Os membros de grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínios e podem receber permissões em qualquer domínio na árvore ou floresta de domínios.</span><span class="sxs-lookup"><span data-stu-id="ff22d-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="ff22d-153">O suporte a grupos universais, combinado com a delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff22d-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="ff22d-154">Por exemplo, não é necessário adicionar um domínio para outro para permitir que um administrador gerencie os dois.</span><span class="sxs-lookup"><span data-stu-id="ff22d-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="ff22d-155">Controle de Acesso Baseado em Função</span><span class="sxs-lookup"><span data-stu-id="ff22d-155">Role-Based Access Control</span></span>

<span data-ttu-id="ff22d-156">Além de criar grupos universais de serviço e de administração e de adicionar grupos de serviços e de administração aos grupos universais apropriados, a preparação da floresta também cria grupos RBAC (controle de acesso baseado em função).</span><span class="sxs-lookup"><span data-stu-id="ff22d-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="ff22d-157">Para obter detalhes sobre grupos de RBAC específicos criados pela preparação da floresta, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="ff22d-158">Para obter mais informações sobre grupos RBAC, consulte [controle de acesso baseado em função (RBAC) para o Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="ff22d-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="ff22d-159">Entradas de Controle de Acesso (ACEs) e herança</span><span class="sxs-lookup"><span data-stu-id="ff22d-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="ff22d-160">A preparação de floresta cria ACEs particulares e públicas e adiciona as ACEs aos grupos universais criados.</span><span class="sxs-lookup"><span data-stu-id="ff22d-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="ff22d-161">Ele cria ACEs privadas específicas no contêiner de configurações globais usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff22d-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="ff22d-162">Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner de sistema no domínio raiz, dependendo de onde você armazena as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="ff22d-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="ff22d-p114">A etapa de preparação do domínio adiciona ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio. A preparação de domínio cria ACEs na raiz do domínio e três contêineres internos: Usuários, Computadores e Controladores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="ff22d-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="ff22d-165">Para obter detalhes sobre as ACEs públicas criadas e adicionadas pela preparação da floresta e pela preparação do domínio, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [as alterações feitas pela preparação do domínio no Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ff22d-166">As organizações geralmente bloqueiam o AD DS (Serviços de Domínio Active Directory) para ajudar a atenuar os riscos de segurança.</span><span class="sxs-lookup"><span data-stu-id="ff22d-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="ff22d-167">No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff22d-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="ff22d-168">Isso pode incluir a remoção das ACEs de contêineres e OUs e a desabilitação da herança de permissões nos objetos User, Contact, InetOrgPerson ou Computer.</span><span class="sxs-lookup"><span data-stu-id="ff22d-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="ff22d-169">Em um ambiente bloqueado do Active Directory, as permissões devem ser definidas manualmente em contêineres e UOs que necessitam deles.</span><span class="sxs-lookup"><span data-stu-id="ff22d-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="ff22d-170">Para obter detalhes, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ff22d-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="ff22d-171">Informações do servidor</span><span class="sxs-lookup"><span data-stu-id="ff22d-171">Server Information</span></span>

<span data-ttu-id="ff22d-172">Durante a ativação, o Lync Server 2013 publica as informações do servidor nos três seguintes locais nos serviços de domínio do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="ff22d-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="ff22d-173">Um ponto de conexão de serviço (SCP) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="ff22d-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="ff22d-174">Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.</span><span class="sxs-lookup"><span data-stu-id="ff22d-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="ff22d-175">Servidores confiáveis especificados no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="ff22d-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="ff22d-176">Pontos de conexão de serviço</span><span class="sxs-lookup"><span data-stu-id="ff22d-176">Service Connection Points</span></span>

<span data-ttu-id="ff22d-177">Cada objeto do Lync Server 2013 nos serviços de domínio do Active Directory tem um SCP chamado serviços RTC, que por sua vez contém vários atributos que identificam cada computador e especificam os serviços que ele fornece.</span><span class="sxs-lookup"><span data-stu-id="ff22d-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="ff22d-178">Entre os atributos do SCP mais importantes estão *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* e *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="ff22d-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="ff22d-179">Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando nesses e em outros atributos do SCP.</span><span class="sxs-lookup"><span data-stu-id="ff22d-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="ff22d-180">Objetos de servidor do Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff22d-180">Active Directory Server Objects</span></span>

<span data-ttu-id="ff22d-181">Cada função de servidor do Lync Server 2013 tem um objeto Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função.</span><span class="sxs-lookup"><span data-stu-id="ff22d-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="ff22d-182">Além disso, quando um servidor Standard Edition é ativado ou quando um pool Enterprise Edition é criado, o Lync Server 2013 cria um novo objeto **msRTCSIP-pool** no contêiner **msRTCSIP-Pools** .</span><span class="sxs-lookup"><span data-stu-id="ff22d-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="ff22d-183">A classe **msRTCSIP-Pool** especifica o FQDN (nome de domínio totalmente qualificado) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool.</span><span class="sxs-lookup"><span data-stu-id="ff22d-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="ff22d-184">(Um servidor Standard Edition é considerado um pool lógico cujos front-end e back-end são colocados em um único computador.)</span><span class="sxs-lookup"><span data-stu-id="ff22d-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="ff22d-185">Servidores confiáveis</span><span class="sxs-lookup"><span data-stu-id="ff22d-185">Trusted Servers</span></span>

<span data-ttu-id="ff22d-186">No Lync Server 2013, os servidores confiáveis são aqueles especificados quando você executa o construtor de topologias e publica sua topologia.</span><span class="sxs-lookup"><span data-stu-id="ff22d-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="ff22d-187">A topologia publicada, incluindo todas as informações do servidor, é armazenada no repositório de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="ff22d-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="ff22d-188">Somente os servidores definidos no repositório de Gerenciamento Central são confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ff22d-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="ff22d-189">No Lync Server 2013, um servidor confiável é aquele que atende aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="ff22d-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="ff22d-190">O FQDN do servidor ocorre na topologia armazenada no repositório de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="ff22d-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="ff22d-191">O servidor apresenta um certificado válido de uma CA confiável.</span><span class="sxs-lookup"><span data-stu-id="ff22d-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="ff22d-192">Para obter detalhes, consulte [Certificate Infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff22d-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="ff22d-p120">Quando um dos seguintes critérios está ausente, o servidor não é confiável e a conexão com ele é recusada. Esse requisito duplo impede um possível ataque, embora improvável, em que um servidor não autorizado tenta assumir o FQDN do servidor válido.</span><span class="sxs-lookup"><span data-stu-id="ff22d-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="ff22d-195">Além disso, para habilitar o Microsoft Office Communications Server 2007 R2 e o Microsoft Office Communications Server 2007 implantações para se comunicar com os servidores do Lync Server 2013, o Lync Server 2013 cria contêineres durante a preparação da floresta para conter listas de servidores confiáveis para versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="ff22d-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="ff22d-196">A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implementações anteriores.</span><span class="sxs-lookup"><span data-stu-id="ff22d-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="ff22d-197">Listas de servidores confiáveis e seus contêineres do Active Directory para compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="ff22d-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff22d-198">Lista de servidores confiáveis</span><span class="sxs-lookup"><span data-stu-id="ff22d-198">Trusted server list</span></span></th>
<th><span data-ttu-id="ff22d-199">Contêiner do Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff22d-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff22d-200">Servidores Standard Edition e Servidores Fron-End do pool Enterprise</span><span class="sxs-lookup"><span data-stu-id="ff22d-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff22d-201">Serviço RTC/Configurações Globais</span><span class="sxs-lookup"><span data-stu-id="ff22d-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff22d-202">Servidores de Conferência</span><span class="sxs-lookup"><span data-stu-id="ff22d-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="ff22d-203">Serviço RTC/MCUs confiáveis</span><span class="sxs-lookup"><span data-stu-id="ff22d-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff22d-204">Servidores de Web Components</span><span class="sxs-lookup"><span data-stu-id="ff22d-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="ff22d-205">Serviço RTC/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="ff22d-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff22d-206">Servidores de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativos, Registrador com QoE, Serviço de Conferência A/V (além de servidores SIP de terceiros)</span><span class="sxs-lookup"><span data-stu-id="ff22d-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="ff22d-207">Serviço RTC/serviços confiáveis</span><span class="sxs-lookup"><span data-stu-id="ff22d-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff22d-208">Servidores Proxy</span><span class="sxs-lookup"><span data-stu-id="ff22d-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="ff22d-209">O Lync Server 2013 não dá suporte à compatibilidade com versões anteriores para servidores proxy</span><span class="sxs-lookup"><span data-stu-id="ff22d-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff22d-210">Para dar suporte a servidores confiáveis de versões anteriores, você deve executar a ferramenta Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="ff22d-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="ff22d-211">Para obter detalhes sobre como executar o analisador de [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)práticas recomendadas, consulte.</span><span class="sxs-lookup"><span data-stu-id="ff22d-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

