---
title: 'Lync Server 2013: a herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson'
description: 'Lync Server 2013: a herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545157"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="26924-103">A herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26924-103">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26924-104">_**Última modificação do tópico:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="26924-104">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="26924-105">Em um serviço de domínio do Active Directory bloqueado, os usuários e os objetos de computador costumam ser colocados em unidades organizacionais (UOs) específicas com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de GPOs (objetos de política de grupo) para impor políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="26924-105">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="26924-106">A preparação do domínio e a ativação do servidor definem as entradas de controle de acesso (ACEs) exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26924-106">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="26924-107">Quando a herança de permissões está desabilitada, os grupos de segurança do Lync Server não podem herdar essas ACEs.</span><span class="sxs-lookup"><span data-stu-id="26924-107">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="26924-108">Quando essas permissões não são herdadas, os grupos de segurança do Lync Server não podem acessar as configurações e os dois problemas a seguir surgem:</span><span class="sxs-lookup"><span data-stu-id="26924-108">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="26924-109">Para administrar usuários, InetOrgPersons e contatos, e para operar servidores, os grupos de segurança do Lync Server exigem ACEs definidas pelo procedimento de preparação do domínio em conjuntos de propriedades de cada usuário, comunicação em tempo real (RTC), pesquisa de usuário RTC e informações públicas.</span><span class="sxs-lookup"><span data-stu-id="26924-109">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="26924-110">Quando a herança de permissões está desabilitada, os grupos de segurança não herdam essas ACEs e não podem gerenciar servidores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="26924-110">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="26924-111">Para descobrir servidores e pools, os servidores que executam o Lync Server dependem de ACEs definidas pela ativação em objetos relacionados ao computador, incluindo o contêiner da Microsoft e o objeto Server.</span><span class="sxs-lookup"><span data-stu-id="26924-111">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="26924-112">Quando a herança de permissões está desabilitada, os grupos de segurança, servidores e pools não herdam essas ACEs e não podem beneficiar-se delas.</span><span class="sxs-lookup"><span data-stu-id="26924-112">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="26924-113">Para resolver esses problemas, o Lync Server fornece o cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="26924-113">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="26924-114">Este cmdlet define ACEs do Lync Server necessárias diretamente em um contêiner especificado e unidades organizacionais e os objetos dentro do contêiner ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="26924-114">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="26924-115">Definir permissões para os objetos Usuário, InetOrgPerson e Contato após executar a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="26924-115">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="26924-116">Em um ambiente bloqueado do Active Directory onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou unidades organizacionais que possuem os objetos Usuários ou InetOrgPerson dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="26924-116">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="26924-117">Nessa situação, é necessário executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que possua objetos Usuário ou InetOrgPerson para os quais a herança de permissões está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="26924-117">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="26924-118">Se você tiver uma topologia de floresta central, também deverá realizar esse procedimento nos contêineres ou UOs que possuem os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="26924-118">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="26924-119">Para obter detalhes sobre as topologias de floresta central, consulte [supported Active Directory topologias in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="26924-119">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="26924-120">O parâmetro ObjectType especifica o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="26924-120">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="26924-121">O parâmetro OU especifica a unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="26924-121">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="26924-122">Esse cmdlet adiciona as ACEs necessárias diretamente nos contêineres ou UO especificadas e nos objetos Usuário ou InetOrgPerson dentro do contêiner.</span><span class="sxs-lookup"><span data-stu-id="26924-122">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="26924-123">Se a OU em que esse comando é executado tiver UOs filhas com objetos User ou InetOrgPerson, as permissões não serão aplicadas nesses.</span><span class="sxs-lookup"><span data-stu-id="26924-123">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="26924-124">Você precisará executar o comando em cada OU filho individualmente.</span><span class="sxs-lookup"><span data-stu-id="26924-124">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="26924-125">Este é um cenário comum com implantações de hospedagem do Lync por exemplo, OU pai = locatários OCS, DC = CONTOSO, DC = LOCAL e filho OU = Tenant1, OU = locatários do OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="26924-125">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="26924-126">Você precisa de direitos de usuário equivalentes à associação de grupo de administradores de domínio para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="26924-126">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="26924-127">Se as ACEs de usuário autenticado também tiverem sido removidas no ambiente bloqueado, você deverá conceder a essa conta as ACEs de leitura de acesso aos contêineres ou UOs relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="26924-127">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="26924-128">**Para definir as ACEs necessárias para os objetos Usuário, InetOrgPerson e Contato**</span><span class="sxs-lookup"><span data-stu-id="26924-128">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="26924-129">Faça logon em um computador associado ao domínio com uma conta que seja membro do grupo Admins. do Domínio ou que possua direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="26924-129">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="26924-130">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="26924-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26924-131">Sejam</span><span class="sxs-lookup"><span data-stu-id="26924-131">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="26924-132">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="26924-132">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="26924-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26924-133">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="26924-134">No arquivo de log, procure **\<Success\>** o resultado de execução no final de cada tarefa para verificar se as permissões foram definidas e, em seguida, feche a janela log.</span><span class="sxs-lookup"><span data-stu-id="26924-134">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="26924-135">Uma alternativa é executar o seguinte comando para determinar se as permissões foram definidas:</span><span class="sxs-lookup"><span data-stu-id="26924-135">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="26924-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26924-136">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="26924-137">Definir permissões para os objetos Computador após executar a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="26924-137">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="26924-138">Em um ambiente bloqueado do Active Directory no qual a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou UOs com objetos Computador dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="26924-138">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="26924-139">Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner OU unidade organizacional que tenha computadores que executam o Lync Server onde a herança de permissões está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="26924-139">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="26924-140">O parâmetro ObjectType especifica o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="26924-140">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="26924-141">Esse procedimento adiciona as ACEs necessárias diretamente nos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="26924-141">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="26924-142">Você precisa de direitos de usuário equivalentes à associação de grupo de administradores de domínio para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="26924-142">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="26924-143">Se as ACEs de usuário autenticado também tiverem sido removidas, você deverá conceder a essa conta ACEs de acesso de leitura nos contêineres relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="26924-143">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="26924-144">**Para definir as ACEs necessárias aos objetos de computador**</span><span class="sxs-lookup"><span data-stu-id="26924-144">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="26924-145">Faça logon no computador do domínio com uma conta que seja membro do grupo Admins. do Domínio ou que possua direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="26924-145">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="26924-146">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="26924-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26924-147">Sejam</span><span class="sxs-lookup"><span data-stu-id="26924-147">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="26924-148">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="26924-148">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="26924-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26924-149">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="26924-150">No exemplo de arquivo de log C: \\ Logs \\OUPermissions.xml, você procuraria o **\<Success\>** resultado da execução no final de cada tarefa e verificará se não há erros e, em seguida, feche o log.</span><span class="sxs-lookup"><span data-stu-id="26924-150">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="26924-151">É possível executar o seguinte cmdlet para testar as permissões:</span><span class="sxs-lookup"><span data-stu-id="26924-151">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="26924-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26924-152">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26924-153">Se você executar a preparação de domínio no domínio raiz da floresta em um ambiente do Active Directory bloqueado, lembre-se de que o Lync Server requer acesso ao esquema do Active Directory e aos contêineres de configuração.</span><span class="sxs-lookup"><span data-stu-id="26924-153">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="26924-154">Se a permissão de usuário autenticado padrão for removida do esquema ou dos contêineres de configuração no AD &nbsp; DS, somente os membros do grupo Administradores de esquema (para o contêiner de esquema) ou administradores corporativos (para o contêiner de configuração) terão permissão para acessar o contêiner fornecido.</span><span class="sxs-lookup"><span data-stu-id="26924-154">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="26924-155">Como Setup.exe, os cmdlets do Shell de gerenciamento do Lync Server e o painel de controle do Lync Server exigem acesso a esses contêineres, a instalação e a instalação das ferramentas administrativas falharão, a menos que o usuário que estiver executando a instalação tenha direitos de usuário equivalentes aos membros do grupo Administradores de esquema e administradores corporativos.</span><span class="sxs-lookup"><span data-stu-id="26924-155">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="26924-156">Para corrigir essa situação, é necessário conceder ao grupo RTCUniversalGlobalWriteGroup acesso de Leitura e Gravação nos contêineres Esquema e Configuração.</span><span class="sxs-lookup"><span data-stu-id="26924-156">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

