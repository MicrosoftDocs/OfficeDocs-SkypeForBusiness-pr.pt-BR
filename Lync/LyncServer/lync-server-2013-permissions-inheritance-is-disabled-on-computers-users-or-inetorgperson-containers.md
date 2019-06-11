---
title: 'Lync Server 2013: Herança de permissões está desabilitado em computadores, usuários ou contêiners InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="e54b8-102">Herança de permissões está desabilitado em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e54b8-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e54b8-103">_**Tópico da última modificação:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="e54b8-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="e54b8-104">Em um serviço de domínio do Active Directory bloqueado, usuários e objetos de computador geralmente são colocados em unidades organizacionais específicas (UOs) com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de objetos de política de grupo (GPOs) para impor políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="e54b8-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="e54b8-105">A preparação do domínio e a ativação do servidor definem as entradas de controle de acesso (ACEs) necessárias pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e54b8-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="e54b8-106">Quando a herança de permissões está desabilitada, os grupos de segurança do Lync Server não podem herdar esses ACEs.</span><span class="sxs-lookup"><span data-stu-id="e54b8-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="e54b8-107">Quando essas permissões não forem herdadas, os grupos de segurança do Lync Server não poderão acessar as configurações, e os dois problemas a seguir ocorrerão:</span><span class="sxs-lookup"><span data-stu-id="e54b8-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="e54b8-108">Para administrar usuários, InetOrgPersons e contatos, e para operar servidores, os grupos de segurança do Lync Server exigem ACEs definidas pelo procedimento de preparação do domínio em conjuntos de propriedades de cada usuário, comunicação em tempo real (RTC), pesquisa de usuário RTC e informações públicas .</span><span class="sxs-lookup"><span data-stu-id="e54b8-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="e54b8-109">Quando a herança de permissões está desabilitada, os grupos de segurança não herdam esses ases e não podem gerenciar servidores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="e54b8-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="e54b8-110">Para descobrir servidores e pools, os servidores que executam o Lync Server dependem de ACEs definidas pela ativação em objetos relacionados a computador, incluindo o contêiner da Microsoft e o objeto do servidor.</span><span class="sxs-lookup"><span data-stu-id="e54b8-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="e54b8-111">Quando a herança de permissões está desabilitada, os grupos de segurança, os servidores e os pools não herdam esses ases e não podem tirar proveito dessas ACEs.</span><span class="sxs-lookup"><span data-stu-id="e54b8-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="e54b8-112">Para resolver esses problemas, o Lync Server fornece o cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="e54b8-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="e54b8-113">Esse cmdlet define ACEs necessárias do Lync Server diretamente em um contêiner especificado e unidades organizacionais e os objetos dentro do contêiner ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="e54b8-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="e54b8-114">Definir permissões para usuários, InetOrgPerson e objetos de contato após a execução da preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="e54b8-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="e54b8-115">Em um ambiente do Active Directory bloqueado onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou unidades organizacionais que mantêm usuários ou objetos InetOrgPerson no domínio.</span><span class="sxs-lookup"><span data-stu-id="e54b8-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="e54b8-116">Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que tenha objetos de usuário ou inetOrgPerson para os quais a herança de permissões esteja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e54b8-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="e54b8-117">Se você tiver uma topologia de floresta central, também deverá executar esse procedimento nos recipientes ou nas UOs que mantêm objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="e54b8-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="e54b8-118">Para obter detalhes sobre as topologias de floresta central, consulte [topologias do Active Directory com suporte no Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="e54b8-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="e54b8-119">O parâmetro ObjectType especifica o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e54b8-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="e54b8-120">O parâmetro OU especifica a unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="e54b8-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="e54b8-121">Esse cmdlet adiciona as ACEs necessárias diretamente nos contêineres ou UOs especificados e nos objetos User ou InetOrgPerson dentro do contêiner.</span><span class="sxs-lookup"><span data-stu-id="e54b8-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="e54b8-122">Se a UO na qual esse comando for executado tiver UOs filho com objetos User ou InetOrgPerson, as permissões não serão aplicadas.</span><span class="sxs-lookup"><span data-stu-id="e54b8-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="e54b8-123">Será necessário executar o comando em cada UO filho individualmente.</span><span class="sxs-lookup"><span data-stu-id="e54b8-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="e54b8-124">Esse é um cenário comum com implantações de hospedagem do Lync, por exemplo, Parent OU = locatários do OCS, DC = CONTOSO, DC = LOCAL e filho OU = Tenant1, OU = locatários do OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="e54b8-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="e54b8-125">Você precisa de direitos de usuário equivalentes ao grupo de administradores de domínio para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e54b8-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="e54b8-126">Se as ACEs do usuário autenticado também tiverem sido removidas no ambiente bloqueado, você deverá conceder a essa conta ACEs de leitura de acesso nos recipientes ou UOs relevantes do domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou use uma conta que seja membro do grupo Administradores da empresa.</span><span class="sxs-lookup"><span data-stu-id="e54b8-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="e54b8-127">**Para definir ACEs necessárias para objetos de usuário, InetOrgPerson e contato**</span><span class="sxs-lookup"><span data-stu-id="e54b8-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="e54b8-128">Faça logon em um computador associado ao domínio com uma conta que seja membro do grupo Domain admins ou que tenha direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e54b8-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="e54b8-129">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e54b8-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e54b8-130">Execute:</span><span class="sxs-lookup"><span data-stu-id="e54b8-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e54b8-131">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="e54b8-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="e54b8-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e54b8-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="e54b8-133">No arquivo de log, procure o resultado de execução do \*\* \<sucesso\> \*\* no final de cada tarefa para verificar se as permissões foram definidas e, em seguida, feche a janela log.</span><span class="sxs-lookup"><span data-stu-id="e54b8-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="e54b8-134">Ou, você pode executar o seguinte comando para determinar se as permissões foram definidas:</span><span class="sxs-lookup"><span data-stu-id="e54b8-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="e54b8-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e54b8-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="e54b8-136">Definir permissões para objetos de computador após a execução da preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="e54b8-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="e54b8-137">Em um ambiente do Active Directory bloqueado onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou nas UOs que armazenam objetos do computador dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="e54b8-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="e54b8-138">Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que tenha computadores que executam o Lync Server onde a herança de permissões esteja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e54b8-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="e54b8-139">O parâmetro ObjectType especifica o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e54b8-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="e54b8-140">Esse procedimento adiciona as ACEs necessárias diretamente nos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="e54b8-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="e54b8-141">Você precisa de direitos de usuário equivalentes ao grupo de administradores de domínio para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e54b8-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="e54b8-142">Se as ACEs do usuário autenticado também tiverem sido removidas, você deverá conceder a essa conta as ACEs de leitura de acesso aos recipientes relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja um membro do grupo Administradores da empresa.</span><span class="sxs-lookup"><span data-stu-id="e54b8-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="e54b8-143">**Para definir ACEs necessárias para objetos de computador**</span><span class="sxs-lookup"><span data-stu-id="e54b8-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="e54b8-144">Faça logon no computador do domínio com uma conta que seja membro do grupo Domain admins ou que tenha direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e54b8-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="e54b8-145">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e54b8-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e54b8-146">Execute:</span><span class="sxs-lookup"><span data-stu-id="e54b8-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="e54b8-147">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="e54b8-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="e54b8-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e54b8-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="e54b8-149">No exemplo de arquivo de log C\\:\\registra OUPermissions. xml, você procura o resultado de execução do \*\* \<sucesso\> \*\* no final de cada tarefa e verifica se não há erros e, em seguida, feche o log.</span><span class="sxs-lookup"><span data-stu-id="e54b8-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="e54b8-150">Você pode executar o seguinte cmdlet para testar permissões:</span><span class="sxs-lookup"><span data-stu-id="e54b8-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e54b8-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e54b8-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e54b8-152">Se você executar a preparação do domínio no domínio raiz da floresta em um ambiente do Active Directory bloqueado, lembre-se de que o Lync Server exige acesso ao esquema e aos contêineres de configuração do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e54b8-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="e54b8-153">Se a permissão de usuário autenticado padrão for removida do esquema ou dos contêineres de&nbsp;configuração no AD DS, somente os membros do grupo Schema Admins (para contêiner de esquema) ou administradores de empresas (para contêiner de configuração) serão permitidos acessar o contêiner fornecido.</span><span class="sxs-lookup"><span data-stu-id="e54b8-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="e54b8-154">Como setup. exe, cmdlets do Shell de gerenciamento do Lync Server e o painel de controle do Lync Server exigem acesso a esses contêineres, a configuração e a instalação das ferramentas administrativas falham, a menos que o usuário executando a instalação tenha direitos de usuário equivalentes ao esquema Associação de grupo Administradores e administradores corporativos.</span><span class="sxs-lookup"><span data-stu-id="e54b8-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="e54b8-155">Para corrigir essa situação, você deve conceder ao grupo RTCUniversalGlobalWriteGroup o acesso de gravação, leitura para o esquema e os contêineres de configuração.</span><span class="sxs-lookup"><span data-stu-id="e54b8-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

