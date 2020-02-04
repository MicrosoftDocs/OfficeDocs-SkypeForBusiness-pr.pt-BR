---
title: 'Lync Server 2013: contas de usuário habilitadas para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="90848-102">Contas de usuário habilitadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90848-103">_**Tópico da última modificação:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="90848-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="90848-104">Os tópicos desta seção fornecem procedimentos passo a passo para configurar as configurações do usuário que você pode executar usando o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90848-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="90848-105">Você não pode usar o painel de controle do Lync Server para gerenciar os usuários que são membros do grupo Administradores de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90848-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="90848-106">Para usuários de administradores de domínio, você pode usar o painel de controle do Lync Server somente para realizar operações de pesquisa somente leitura.</span><span class="sxs-lookup"><span data-stu-id="90848-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="90848-107">Para realizar operações de gravação em usuários de administradores de domínio (por exemplo, habilitar ou desabilitar o painel de controle do Lync Server, alterar as atribuições de grupo ou política, configurações de telefonia, endereço SIP), você deve usar cmdlets do Windows PowerShell enquanto estiver conectado como um usuário administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="90848-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="90848-108">Para obter detalhes sobre como usar cmdlets do Windows PowerShell para gerenciar usuários, consulte <A href="lync-server-2013-lync-server-management-shell.md">Shell de gerenciamento do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="90848-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="90848-109">Quando você executa qualquer tarefa administrativa do Lync Server 2013 que envolve a pesquisa de um usuário ou filtragem dos resultados da pesquisa de usuário, há algumas propriedades de usuário que existem como atributos nos serviços de domínio Active Directory, mas que não são replicadas para o catálogo global até que o Microsoft Exchange Server seja implantado.</span><span class="sxs-lookup"><span data-stu-id="90848-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="90848-110">Microsoft Exchange, não Lync Server, marca os seguintes atributos de replicação para o catálogo global quando ele é instalado:</span><span class="sxs-lookup"><span data-stu-id="90848-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90848-111">Informações do usuário</span><span class="sxs-lookup"><span data-stu-id="90848-111">User Information</span></span></th>
<th><span data-ttu-id="90848-112">Endereço e telefone</span><span class="sxs-lookup"><span data-stu-id="90848-112">Address and Phone</span></span></th>
<th><span data-ttu-id="90848-113">Organização</span><span class="sxs-lookup"><span data-stu-id="90848-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90848-114">Iniciais</span><span class="sxs-lookup"><span data-stu-id="90848-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="90848-115">Endereço da rua</span><span class="sxs-lookup"><span data-stu-id="90848-115">Street address</span></span></p>
<p><span data-ttu-id="90848-116">País/Região</span><span class="sxs-lookup"><span data-stu-id="90848-116">Country/region</span></span></p>
<p><span data-ttu-id="90848-117">Page</span><span class="sxs-lookup"><span data-stu-id="90848-117">Pager</span></span></p>
<p><span data-ttu-id="90848-118">Fax</span><span class="sxs-lookup"><span data-stu-id="90848-118">Fax</span></span></p>
<p><span data-ttu-id="90848-119">Mobile</span><span class="sxs-lookup"><span data-stu-id="90848-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="90848-120">Título</span><span class="sxs-lookup"><span data-stu-id="90848-120">Title</span></span></p>
<p><span data-ttu-id="90848-121">Empresa</span><span class="sxs-lookup"><span data-stu-id="90848-121">Company</span></span></p>
<p><span data-ttu-id="90848-122">Partamentais</span><span class="sxs-lookup"><span data-stu-id="90848-122">Department</span></span></p>
<p><span data-ttu-id="90848-123">Office</span><span class="sxs-lookup"><span data-stu-id="90848-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="90848-124">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="90848-124">In This Section</span></span>

  - [<span data-ttu-id="90848-125">Exibir informações sobre contas de usuário habilitadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="90848-126">Habilitando e desabilitando usuários do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="90848-127">Gerenciando o Enterprise Voice para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="90848-128">Modificando Propriedades de conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="90848-129">Gerenciar política de acesso externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="90848-130">Como atribuir políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90848-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="90848-131">See Also</span></span>


[<span data-ttu-id="90848-132">Cmdlets de gerenciamento de usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="90848-133">Gerenciando usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90848-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

