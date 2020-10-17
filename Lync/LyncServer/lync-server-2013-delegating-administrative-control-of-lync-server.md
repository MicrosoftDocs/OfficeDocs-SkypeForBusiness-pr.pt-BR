---
title: 'Lync Server 2013: delegando o controle administrativo do Lync Server'
description: 'Lync Server 2013: delegando o controle administrativo do Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567487"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="db306-103">Delegando o controle administrativo do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db306-103">Delegating administrative control of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db306-104">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="db306-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="db306-105">No Lync Server 2013, as tarefas administrativas são delegadas aos usuários usando o novo recurso de controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="db306-105">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="db306-106">Quando você instala o Lync Server, várias funções do RBAC são criadas para você.</span><span class="sxs-lookup"><span data-stu-id="db306-106">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="db306-107">Essas funções correspondem a grupos de segurança universais nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db306-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="db306-108">Por exemplo, a função RBAC CsHelpDesk corresponde ao grupo CsHelpDesk encontrado no contêiner usuários nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db306-108">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="db306-109">Além disso, cada função RBAC é associada a um conjunto de cmdlets do Windows PowerShell do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db306-109">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="db306-110">Esses cmdlets representam as tarefas que podem ser executadas por usuários aos quais a função RBAC determinada foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="db306-110">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="db306-111">Por exemplo, a função CsHelpDesk foi atribuída aos cmdlets Lock-CsClientPin e UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="db306-111">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="db306-112">Isso significa que os usuários que receberam a função CsHelpDesk podem bloquear e desbloquear números de PIN do usuário.</span><span class="sxs-lookup"><span data-stu-id="db306-112">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="db306-113">No entanto, a função CsHelpDesk não recebeu a atribuição do cmdlet New-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="db306-113">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="db306-114">Isso significa que os usuários que receberam a função CsHelpDesk não podem criar novas políticas de voz.</span><span class="sxs-lookup"><span data-stu-id="db306-114">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="db306-115">Exibindo informações sobre as funções RBAC</span><span class="sxs-lookup"><span data-stu-id="db306-115">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="db306-116">Você pode recuperar informações básicas sobre suas funções RBAC executando o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="db306-116">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="db306-117">Tenha em mente que a identidade da função RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança encontrado no contêiner usuários nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db306-117">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="db306-118">Para visualizar uma lista de cmdlets que foram designados a uma função, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="db306-118">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="db306-119">Atribuindo uma função RBAC a um usuário</span><span class="sxs-lookup"><span data-stu-id="db306-119">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="db306-120">Para atribuir uma função RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança apropriado do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db306-120">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="db306-121">Por exemplo, para atribuir a função CsLocationAdministrator a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="db306-121">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="db306-122">Isso pode ser feito executando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="db306-122">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="db306-123">**Para atribuir um usuário a um grupo de segurança**</span><span class="sxs-lookup"><span data-stu-id="db306-123">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="db306-124">Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.</span><span class="sxs-lookup"><span data-stu-id="db306-124">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="db306-125">Clique em **Iniciar**, clique em **Todos os Programas**, clique em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="db306-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="db306-126">Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="db306-126">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="db306-127">Clique com o botão direito no grupo de segurança **CsLocationAdministrator** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="db306-127">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="db306-128">Na caixa de diálogo **Propriedades**, na guia **Membros**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="db306-128">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="db306-129">Na caixa de diálogo **Selecionar Usuários, Computadores, Contatos ou Grupos**, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, **Ken Myer**) na caixa **Inserir os nomes de objeto a selecionar** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="db306-129">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="db306-130">Na caixa de diálogo **Propriedades**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="db306-130">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="db306-131">Para verificar se a função RBAC foi atribuída, use o cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , passando o cmdlet para o sAMAccountName (nome de logon do Active Directory) do usuário.</span><span class="sxs-lookup"><span data-stu-id="db306-131">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="db306-132">Por exemplo, execute este comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="db306-132">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

