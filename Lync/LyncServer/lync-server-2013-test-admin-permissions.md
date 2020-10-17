---
title: 'Lync Server 2013: testar permissões de administrador'
description: 'Lync Server 2013: testar permissões de administrador.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568517"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="618b0-103">Testar permissões de administrador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="618b0-103">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="618b0-104">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="618b0-104">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="618b0-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="618b0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="618b0-106">Após a implantação inicial do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="618b0-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="618b0-107">Conforme necessário se surgirem problemas relacionados à permissão.</span><span class="sxs-lookup"><span data-stu-id="618b0-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="618b0-108">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="618b0-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="618b0-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="618b0-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="618b0-110">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="618b0-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="618b0-111">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="618b0-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="618b0-112">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="618b0-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="618b0-113">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="618b0-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="618b0-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="618b0-114">Description</span></span>

<span data-ttu-id="618b0-115">Quando você instala o Lync Server 2013 1 das tarefas que foram realizadas pelo programa de instalação fornece ao grupo RTCUniversalUserAdmins permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativos e pessoas do InetOrg.</span><span class="sxs-lookup"><span data-stu-id="618b0-115">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="618b0-116">Se você desabilitou a herança de permissão na configuração do Active Directory, não será possível atribuir essas permissões.</span><span class="sxs-lookup"><span data-stu-id="618b0-116">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="618b0-117">Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar entidades do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="618b0-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="618b0-118">Esses privilégios de gerenciamento só estarão disponíveis para os administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="618b0-118">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="618b0-119">O cmdlet Test-CsOUPermission verifica se as permissões necessárias necessárias para gerenciar usuários, computadores e outros objetos estão definidas em um contêiner do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="618b0-119">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="618b0-120">Se essas permissões não estiverem definidas, você poderá resolver esse problema executando o cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="618b0-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="618b0-121">Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="618b0-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="618b0-122">Você não pode usar este cmdlet para conceder permissões a um usuário ou grupo arbitrário.</span><span class="sxs-lookup"><span data-stu-id="618b0-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="618b0-123">Se quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, você deve adicionar esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="618b0-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="618b0-124">Para obter mais informações sobre permissões de OU, confira o artigo a [herança de permissões está desabilitada em computadores, usuários ou contêiners inetOrgPerson no Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="618b0-124">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="618b0-125">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="618b0-125">Running the test</span></span>

<span data-ttu-id="618b0-126">Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome distinto do contêiner e pelo tipo de permissões que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="618b0-126">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="618b0-127">Por exemplo, este comando verifica se as permissões do usuário estão definidas na OU ou = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="618b0-127">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="618b0-128">Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e, em seguida, separe-os usando vírgulas.</span><span class="sxs-lookup"><span data-stu-id="618b0-128">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="618b0-129">Por exemplo, este comando verifica as permissões de usuário, computador e contato:</span><span class="sxs-lookup"><span data-stu-id="618b0-129">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="618b0-130">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="618b0-130">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="618b0-131">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="618b0-131">Determining success or failure</span></span>

<span data-ttu-id="618b0-132">Se as permissões necessárias já tiverem sido definidas, Test-CsOUPermission retornará uma resposta de um Word:</span><span class="sxs-lookup"><span data-stu-id="618b0-132">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="618b0-133">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="618b0-133">True</span></span>

<span data-ttu-id="618b0-134">Se as permissões necessárias não estiverem definidas, Test-CsOUPermission retornará o valor false.</span><span class="sxs-lookup"><span data-stu-id="618b0-134">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="618b0-135">Talvez seja necessário pesquisar por um momento para encontrar esse valor.</span><span class="sxs-lookup"><span data-stu-id="618b0-135">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="618b0-136">Normalmente, ele será incorporado dentro de vários avisos de acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="618b0-136">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="618b0-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="618b0-137">For example:</span></span>

<span data-ttu-id="618b0-138">Aviso: entrada de controle de acesso (ACE) ATL-cs-001 \\ RTCUniversalUserReadOnlyGroup; permitir; ReadProperty ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="618b0-138">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="618b0-139">Aviso: as entradas de controle de acesso (ACEs) no objeto "OU = América, DC = ATL-cs-001 \\ DC = litwareinc, DC = com" não estão prontas.</span><span class="sxs-lookup"><span data-stu-id="618b0-139">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="618b0-140">Falso</span><span class="sxs-lookup"><span data-stu-id="618b0-140">False</span></span>

<span data-ttu-id="618b0-141">Aviso: o processamento de "Test-CsOUPermission" foi concluído com avisos.</span><span class="sxs-lookup"><span data-stu-id="618b0-141">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="618b0-142">os avisos "2" foram registrados durante esta execução.</span><span class="sxs-lookup"><span data-stu-id="618b0-142">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="618b0-143">Aviso: resultados detalhados podem ser encontrados em "C \\ : \\ usuários \\ admin \\ \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.htmlocal \\</span><span class="sxs-lookup"><span data-stu-id="618b0-143">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="618b0-144">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="618b0-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="618b0-145">Se Test-CsOUPermission falhar, normalmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="618b0-145">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="618b0-146">Você pode resolver esse problema e atribuir as permissões necessárias, usando o cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="618b0-146">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="618b0-147">Por exemplo, este comando concede permissões de OU para usuários, contatos e inetOrgPersons ao grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="618b0-147">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="618b0-148">Para obter mais informações, consulte o tópico de ajuda para o cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="618b0-148">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

