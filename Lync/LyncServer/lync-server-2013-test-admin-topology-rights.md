---
title: 'Lync Server 2013: testar direitos de topologia de administração'
description: 'Lync Server 2013: testar direitos de topologia de administração.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d713297d0e944c7acbc5efcb11b21ea1b26639
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568557"
---
# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="9a4d7-103">Testar os direitos de topologia de administração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a4d7-103">Test admin topology rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a4d7-104">_**Última modificação do tópico:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="9a4d7-104">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a4d7-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="9a4d7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9a4d7-106">Após a implantação inicial do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="9a4d7-107">Conforme necessário se surgirem problemas relacionados à permissão.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a4d7-108">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="9a4d7-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9a4d7-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a4d7-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a4d7-110">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="9a4d7-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9a4d7-111">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9a4d7-112">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="9a4d7-113">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a4d7-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9a4d7-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9a4d7-114">Description</span></span>

<span data-ttu-id="9a4d7-115">Por padrão, somente os administradores de domínio podem habilitar uma topologia do Lync Server e fazer grandes alterações na infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-115">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="9a4d7-116">Isso não será um problema, contanto que seus administradores de domínio e seus administradores do Lync Server sejam os mesmos. Em muitas organizações, os administradores do Lync Server não retêm direitos administrativos em todo o domínio.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-116">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="9a4d7-117">Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer alterações de topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-117">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="9a4d7-118">Para dar aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações de topologia, você deve atribuir as permissões do Active Directory necessárias usando o cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="9a4d7-118">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="9a4d7-119">O cmdlet Test-CsSetupPermission verifica se as permissões necessárias necessárias para instalar o Lync Server ou um de seus componentes estão configuradas no contêiner do Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-119">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="9a4d7-120">Se as permissões não forem atribuídas, você poderá executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-120">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a4d7-121">Para obter uma lista detalhada de permissões atribuídas pelo Grant-CsSetupPermission, consulte o blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission e Grant-CsOUPermission</A>.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-121">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9a4d7-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="9a4d7-122">Running the test</span></span>

<span data-ttu-id="9a4d7-123">Para determinar se as permissões de configuração são atribuídas a um contêiner do Active Directory, chame o cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="9a4d7-124">Especifique o nome distinto do contêiner a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="9a4d7-125">Por exemplo, este comando verifica as permissões de instalação no contêiner ou = CsServers, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="9a4d7-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="9a4d7-126">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="9a4d7-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9a4d7-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="9a4d7-127">Determining success or failure</span></span>

<span data-ttu-id="9a4d7-128">Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor true:</span><span class="sxs-lookup"><span data-stu-id="9a4d7-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="9a4d7-129">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-129">True</span></span>

<span data-ttu-id="9a4d7-130">Se as permissões não forem definidas, Test-CsSetupPermission retornará o valor false.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="9a4d7-131">Observe que esse valor normalmente será incluído em várias mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="9a4d7-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a4d7-132">For example:</span></span>

<span data-ttu-id="9a4d7-133">Aviso: entrada de controle de acesso (ACE) ATL-cs-001 \\ RTCUniversalServerAdmins; Permitiu ExtendedRight; Nenhum Nenhum 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="9a4d7-133">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="9a4d7-134">Aviso: as entradas de controle de acesso (ACEs) no objeto "CN = computadores, DC = litwareinc, DC = com" não estão prontas.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="9a4d7-135">Falso</span><span class="sxs-lookup"><span data-stu-id="9a4d7-135">False</span></span>

<span data-ttu-id="9a4d7-136">Aviso: o processamento de "Test-CsSetupPermission" foi concluído com avisos.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="9a4d7-137">os avisos "2" foram registrados durante esta execução.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-137">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="9a4d7-138">Aviso: resultados detalhados podem ser encontrados em "C \\ : \\ usuários \\ admin \\ \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.htmlocal \\</span><span class="sxs-lookup"><span data-stu-id="9a4d7-138">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9a4d7-139">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="9a4d7-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="9a4d7-140">Embora haja raras exceções, se Test-CsSetupPermission falhar, isso normalmente significa que as permissões de configuração não são atribuídas para o contêiner do Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="9a4d7-141">Essas permissões podem ser atribuídas usando o cmdlet Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="9a4d7-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="9a4d7-142">Por exemplo, esse comando concede permissões de configuração para o contêiner de computadores no domínio litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="9a4d7-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="9a4d7-143">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="9a4d7-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

