---
title: 'Lync Server 2013: a herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson'
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
ms.openlocfilehash: 1340c76209667d705908f5012a8182eaf1c7c4cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="86cde-102">A herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86cde-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86cde-103">_**Última modificação do tópico:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="86cde-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="86cde-104">Em um serviço de domínio do Active Directory bloqueado, os usuários e os objetos de computador costumam ser colocados em unidades organizacionais (UOs) específicas com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de GPOs (objetos de política de grupo) para impor políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="86cde-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="86cde-105">A preparação do domínio e a ativação do servidor definem as entradas de controle de acesso (ACEs) exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86cde-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="86cde-106">Quando a herança de permissões está desabilitada, os grupos de segurança do Lync Server não podem herdar essas ACEs.</span><span class="sxs-lookup"><span data-stu-id="86cde-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="86cde-107">Quando essas permissões não são herdadas, os grupos de segurança do Lync Server não podem acessar as configurações e os dois problemas a seguir surgem:</span><span class="sxs-lookup"><span data-stu-id="86cde-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="86cde-108">Para administrar usuários, InetOrgPersons e contatos, e para operar servidores, os grupos de segurança do Lync Server exigem ACEs definidas pelo procedimento de preparação do domínio nos conjuntos de propriedades de cada usuário, comunicação em tempo real (RTC), pesquisa de usuário RTC e informações públicas .</span><span class="sxs-lookup"><span data-stu-id="86cde-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="86cde-109">Quando a herança de permissões está desabilitada, os grupos de segurança não herdam essas ACEs e não podem gerenciar servidores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="86cde-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="86cde-110">Para descobrir servidores e pools, os servidores que executam o Lync Server dependem de ACEs definidas pela ativação em objetos relacionados ao computador, incluindo o contêiner da Microsoft e o objeto Server.</span><span class="sxs-lookup"><span data-stu-id="86cde-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="86cde-111">Quando a herança de permissões está desabilitada, os grupos de segurança, servidores e pools não herdam essas ACEs e não podem beneficiar-se delas.</span><span class="sxs-lookup"><span data-stu-id="86cde-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="86cde-112">Para resolver esses problemas, o Lync Server fornece o cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="86cde-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="86cde-113">Este cmdlet define ACEs do Lync Server necessárias diretamente em um contêiner especificado e unidades organizacionais e os objetos dentro do contêiner ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="86cde-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="86cde-114">Definir permissões para os objetos Usuário, InetOrgPerson e Contato após executar a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="86cde-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="86cde-115">Em um ambiente bloqueado do Active Directory onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou unidades organizacionais que possuem os objetos Usuários ou InetOrgPerson dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="86cde-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="86cde-116">Nessa situação, é necessário executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que possua objetos Usuário ou InetOrgPerson para os quais a herança de permissões está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="86cde-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="86cde-117">Se você tiver uma topologia de floresta central, também deverá realizar esse procedimento nos contêineres ou UOs que possuem os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="86cde-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="86cde-118">Para obter detalhes sobre as topologias de floresta central, consulte [supported Active Directory topologias in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="86cde-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="86cde-119">O parâmetro ObjectType especifica o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="86cde-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="86cde-120">O parâmetro OU especifica a unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="86cde-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="86cde-121">Esse cmdlet adiciona as ACEs necessárias diretamente nos contêineres ou UO especificadas e nos objetos Usuário ou InetOrgPerson dentro do contêiner.</span><span class="sxs-lookup"><span data-stu-id="86cde-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="86cde-122">Se a OU em que esse comando é executado tiver UOs filhas com objetos User ou InetOrgPerson, as permissões não serão aplicadas nesses.</span><span class="sxs-lookup"><span data-stu-id="86cde-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="86cde-123">Você precisará executar o comando em cada OU filho individualmente.</span><span class="sxs-lookup"><span data-stu-id="86cde-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="86cde-124">Este é um cenário comum com implantações de hospedagem do Lync por exemplo, OU pai = locatários OCS, DC = CONTOSO, DC = LOCAL e filho OU = Tenant1, OU = locatários do OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="86cde-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="86cde-125">Você precisa de direitos de usuário equivalentes à associação de grupo de administradores de domínio para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86cde-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="86cde-126">Se as ACEs de usuário autenticado também tiverem sido removidas no ambiente bloqueado, você deverá conceder a essa conta as ACEs de leitura de acesso aos contêineres ou UOs relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="86cde-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="86cde-127">**Para definir as ACEs necessárias para os objetos Usuário, InetOrgPerson e Contato**</span><span class="sxs-lookup"><span data-stu-id="86cde-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="86cde-128">Faça logon em um computador associado ao domínio com uma conta que seja membro do grupo Admins. do Domínio ou que possua direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="86cde-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="86cde-129">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86cde-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="86cde-130">Sejam</span><span class="sxs-lookup"><span data-stu-id="86cde-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="86cde-131">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="86cde-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="86cde-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86cde-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="86cde-133">No arquivo de log, procure o resultado de execução de \*\* \<êxito\> \*\* no final de cada tarefa para verificar se as permissões foram definidas e, em seguida, feche a janela log.</span><span class="sxs-lookup"><span data-stu-id="86cde-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="86cde-134">Uma alternativa é executar o seguinte comando para determinar se as permissões foram definidas:</span><span class="sxs-lookup"><span data-stu-id="86cde-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="86cde-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86cde-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="86cde-136">Definir permissões para os objetos Computador após executar a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="86cde-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="86cde-137">Em um ambiente bloqueado do Active Directory no qual a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou UOs com objetos Computador dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="86cde-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="86cde-138">Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner OU unidade organizacional que tenha computadores que executam o Lync Server onde a herança de permissões está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="86cde-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="86cde-139">O parâmetro ObjectType especifica o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="86cde-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="86cde-140">Esse procedimento adiciona as ACEs necessárias diretamente nos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="86cde-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="86cde-141">Você precisa de direitos de usuário equivalentes à associação de grupo de administradores de domínio para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86cde-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="86cde-142">Se as ACEs de usuário autenticado também tiverem sido removidas, você deverá conceder a essa conta ACEs de acesso de leitura nos contêineres relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="86cde-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="86cde-143">**Para definir as ACEs necessárias aos objetos de computador**</span><span class="sxs-lookup"><span data-stu-id="86cde-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="86cde-144">Faça logon no computador do domínio com uma conta que seja membro do grupo Admins. do Domínio ou que possua direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="86cde-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="86cde-145">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86cde-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="86cde-146">Sejam</span><span class="sxs-lookup"><span data-stu-id="86cde-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="86cde-147">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="86cde-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="86cde-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86cde-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="86cde-149">No exemplo de arquivo de log C\\:\\logs OUPermissions. xml, você procurará o resultado de execução de \*\* \<êxito\> \*\* no final de cada tarefa e verificará se não há erros e, em seguida, feche o log.</span><span class="sxs-lookup"><span data-stu-id="86cde-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="86cde-150">É possível executar o seguinte cmdlet para testar as permissões:</span><span class="sxs-lookup"><span data-stu-id="86cde-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="86cde-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86cde-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86cde-152">Se você executar a preparação de domínio no domínio raiz da floresta em um ambiente do Active Directory bloqueado, lembre-se de que o Lync Server requer acesso ao esquema do Active Directory e aos contêineres de configuração.</span><span class="sxs-lookup"><span data-stu-id="86cde-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="86cde-153">Se a permissão de usuário autenticado padrão for removida do esquema ou dos contêineres de&nbsp;configuração no AD DS, somente os membros do grupo Administradores de esquema (para o contêiner de esquema) ou administradores corporativos (para o contêiner de configuração) terão permissão para acessar o contêiner fornecido.</span><span class="sxs-lookup"><span data-stu-id="86cde-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="86cde-154">Como setup. exe, cmdlets do Shell de gerenciamento do Lync Server e o painel de controle do Lync Server exigem acesso a esses contêineres, a instalação e a instalação das ferramentas administrativas falharão, a menos que o usuário executando a instalação tenha direitos de usuário equivalentes ao esquema Associação de grupo Administradores e administradores corporativos.</span><span class="sxs-lookup"><span data-stu-id="86cde-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="86cde-155">Para corrigir essa situação, é necessário conceder ao grupo RTCUniversalGlobalWriteGroup acesso de Leitura e Gravação nos contêineres Esquema e Configuração.</span><span class="sxs-lookup"><span data-stu-id="86cde-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

