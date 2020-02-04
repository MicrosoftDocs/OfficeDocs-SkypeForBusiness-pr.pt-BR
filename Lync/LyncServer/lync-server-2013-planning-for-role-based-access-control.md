---
title: 'Lync Server 2013: Planejamento de controle de acesso baseado em função'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89e4bdc075783d33bebcfb85398b1b627e1bf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="0250e-102">Planejamento de controle de acesso baseado em função no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0250e-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0250e-103">_**Tópico da última modificação:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="0250e-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="0250e-104">Para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança, o Lync Server 2013 oferece controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0250e-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="0250e-105">Com o RBAC, o privilégio administrativo é concedido por meio da atribuição de usuários a funções administrativas.</span><span class="sxs-lookup"><span data-stu-id="0250e-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="0250e-106">O Lync Server 2013 inclui um conjunto rico de funções administrativas internas e também permite que você crie novas funções e especifique uma lista personalizada de cmdlets para cada nova função.</span><span class="sxs-lookup"><span data-stu-id="0250e-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="0250e-107">Você também pode adicionar scripts de cmdlets às tarefas permitidas de funções RBAC predefinidas e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0250e-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="0250e-108">Melhor segurança e centralização do servidor</span><span class="sxs-lookup"><span data-stu-id="0250e-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="0250e-109">Com o RBAC, o acesso e a autorização são baseados precisamente na função do Lync Server de um usuário.</span><span class="sxs-lookup"><span data-stu-id="0250e-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="0250e-110">Isso permite o uso da prática de segurança de "privilégio mínimo", concedendo aos administradores e usuários somente os direitos necessários para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0250e-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0250e-111">As restrições RBAC funcionam apenas em administradores que trabalham remotamente, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0250e-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="0250e-112">Um usuário em um servidor que executa o Lync Server não é restrito pelo RBAC.</span><span class="sxs-lookup"><span data-stu-id="0250e-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="0250e-113">Portanto, a segurança física do Lync Server é importante para preservar as restrições de RBAC.</span><span class="sxs-lookup"><span data-stu-id="0250e-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="0250e-114">Funções e escopo</span><span class="sxs-lookup"><span data-stu-id="0250e-114">Roles and Scope</span></span>

<span data-ttu-id="0250e-115">No RBAC, uma *função* é habilitada para usar uma lista de cmdlets, projetada para ser útil para um determinado tipo de administrador ou técnico.</span><span class="sxs-lookup"><span data-stu-id="0250e-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="0250e-116">Um *escopo* é o conjunto de objetos que os cmdlets definidos em uma função podem operar.</span><span class="sxs-lookup"><span data-stu-id="0250e-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="0250e-117">Os objetos que afetam o escopo podem ser contas de usuário (agrupadas por unidade organizacional) ou servidores (agrupados por site).</span><span class="sxs-lookup"><span data-stu-id="0250e-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="0250e-118">A tabela a seguir lista as funções predefinidas no Lync Server e fornece uma visão geral dos tipos de tarefas que cada uma pode fazer.</span><span class="sxs-lookup"><span data-stu-id="0250e-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="0250e-119">A quarta coluna mostra a função do Microsoft Exchange Server semelhante para cada função do Lync Server, se houver uma.</span><span class="sxs-lookup"><span data-stu-id="0250e-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="0250e-120">Funções administrativas predefinidas</span><span class="sxs-lookup"><span data-stu-id="0250e-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0250e-121">Função</span><span class="sxs-lookup"><span data-stu-id="0250e-121">Role</span></span></th>
<th><span data-ttu-id="0250e-122">Tarefas permitidas</span><span class="sxs-lookup"><span data-stu-id="0250e-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="0250e-123">Grupo subjacente do Active Directory</span><span class="sxs-lookup"><span data-stu-id="0250e-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="0250e-124">Equivalente do Exchange</span><span class="sxs-lookup"><span data-stu-id="0250e-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0250e-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-126">Pode executar todas as tarefas administrativas e modificar todas as configurações, incluindo a criação de funções e a atribuição de usuários a funções.</span><span class="sxs-lookup"><span data-stu-id="0250e-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="0250e-127">Pode expandir uma implantação adicionando novos sites, pools e serviços.</span><span class="sxs-lookup"><span data-stu-id="0250e-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="0250e-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-129">Gerenciamento de organização</span><span class="sxs-lookup"><span data-stu-id="0250e-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0250e-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-131">Pode habilitar e desabilitar usuários do Lync Server, mover usuários e atribuir políticas existentes para os usuários.</span><span class="sxs-lookup"><span data-stu-id="0250e-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="0250e-132">Não é possível modificar políticas.</span><span class="sxs-lookup"><span data-stu-id="0250e-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="0250e-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-134">Destinatários do email</span><span class="sxs-lookup"><span data-stu-id="0250e-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0250e-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-136">Pode criar, configurar e gerenciar configurações e políticas relacionadas à voz.</span><span class="sxs-lookup"><span data-stu-id="0250e-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="0250e-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-138">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0250e-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0250e-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-140">Pode gerenciar, monitorar e solucionar problemas de servidores e serviços.</span><span class="sxs-lookup"><span data-stu-id="0250e-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="0250e-141">Pode impedir novas conexões com os servidores, interromper e iniciar serviços e aplicar atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="0250e-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="0250e-142">Não é possível fazer alterações com o impacto de configuração global.</span><span class="sxs-lookup"><span data-stu-id="0250e-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="0250e-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-144">Gerenciamento de servidor</span><span class="sxs-lookup"><span data-stu-id="0250e-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0250e-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-146">Pode exibir a implantação, incluindo informações de usuário e do servidor, para monitorar a integridade da implantação.</span><span class="sxs-lookup"><span data-stu-id="0250e-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="0250e-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-148">Gerenciamento de organização somente para exibição</span><span class="sxs-lookup"><span data-stu-id="0250e-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0250e-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="0250e-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="0250e-150">Pode exibir a implantação, incluindo propriedades e políticas do usuário.</span><span class="sxs-lookup"><span data-stu-id="0250e-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="0250e-151">Pode executar tarefas específicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="0250e-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="0250e-152">Não é possível alterar propriedades ou políticas do usuário, configuração do servidor ou serviços.</span><span class="sxs-lookup"><span data-stu-id="0250e-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="0250e-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="0250e-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="0250e-154">Assistência técnica</span><span class="sxs-lookup"><span data-stu-id="0250e-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0250e-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-156">Pode modificar a configuração e as políticas de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0250e-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="0250e-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-158">Gerenciamento de retenção, controle legal</span><span class="sxs-lookup"><span data-stu-id="0250e-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0250e-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-160">Pode gerenciar a configuração do aplicativo de grupo de resposta em um site.</span><span class="sxs-lookup"><span data-stu-id="0250e-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="0250e-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-162">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0250e-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0250e-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-164">Nível mais baixo de direitos para gerenciamento aprimorado de 9-1-1 (E9-1-1), incluindo a criação de locais E9-1-1 e identificadores de rede e associação entre eles.</span><span class="sxs-lookup"><span data-stu-id="0250e-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="0250e-165">Esta função é sempre atribuída com um escopo global.</span><span class="sxs-lookup"><span data-stu-id="0250e-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="0250e-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-167">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0250e-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0250e-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0250e-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="0250e-169">Pode gerenciar grupos de resposta específicos.</span><span class="sxs-lookup"><span data-stu-id="0250e-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="0250e-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0250e-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="0250e-171">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0250e-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0250e-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-173">Pode gerenciar o recurso de chat persistente e salas de chat persistentes específicas.</span><span class="sxs-lookup"><span data-stu-id="0250e-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="0250e-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="0250e-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0250e-175">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0250e-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0250e-176">Todas as funções predefinidas fornecidas no Lync Server têm um escopo global.</span><span class="sxs-lookup"><span data-stu-id="0250e-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="0250e-177">Para acompanhar as práticas de privilégio mínimo, você não deve atribuir usuários às funções com escopo global se eles vão administrar apenas um conjunto limitado de servidores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="0250e-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="0250e-178">Para fazer isso, você pode criar funções com base em uma função existente, mas com um escopo mais limitado.</span><span class="sxs-lookup"><span data-stu-id="0250e-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="0250e-179">Criando uma função com escopo</span><span class="sxs-lookup"><span data-stu-id="0250e-179">Creating a Scoped Role</span></span>

<span data-ttu-id="0250e-180">Quando você cria uma função com escopo limitado (uma função com escopo), especifica o escopo, juntamente com a função existente na qual ele é baseado e o grupo do Active Directory ao qual a função deve ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="0250e-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="0250e-181">O grupo do Active Directory que você especificar já deve ter sido criado.</span><span class="sxs-lookup"><span data-stu-id="0250e-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="0250e-182">O cmdlet a seguir é um exemplo de criação de uma função que tem os privilégios de uma das funções administrativas predefinidas, mas com escopo limitado.</span><span class="sxs-lookup"><span data-stu-id="0250e-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="0250e-183">Ele cria uma nova função chamada `Site01 Server Administrators`.</span><span class="sxs-lookup"><span data-stu-id="0250e-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="0250e-184">A função tem as habilidades da função CsServerAdministrator predefinida, mas somente para os servidores localizados no site do Site01.</span><span class="sxs-lookup"><span data-stu-id="0250e-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="0250e-185">Para que esse cmdlet funcione, o site do Site01 já deve estar definido, e um grupo de segurança `Site01 Server Administrators` universal chamado já deve existir.</span><span class="sxs-lookup"><span data-stu-id="0250e-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="0250e-186">Após a execução do cmdlet, todos os usuários que são membros `Site01 Server Administrators` do grupo terão privilégios de administrador do servidor para os servidores no Site01.</span><span class="sxs-lookup"><span data-stu-id="0250e-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="0250e-187">Além disso, todos os usuários adicionados posteriormente a esse grupo de segurança universal também obterão os privilégios dessa função.</span><span class="sxs-lookup"><span data-stu-id="0250e-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="0250e-188">Observe que a função em si e o grupo de segurança universal ao qual ele está atribuído são `Site01 Server Administrators`chamados.</span><span class="sxs-lookup"><span data-stu-id="0250e-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="0250e-189">O exemplo a seguir limita o escopo do usuário em vez do escopo do servidor.</span><span class="sxs-lookup"><span data-stu-id="0250e-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="0250e-190">Ele cria uma `Sales Users Administrator` função para administrar as contas de usuário na unidade organizacional Sales.</span><span class="sxs-lookup"><span data-stu-id="0250e-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="0250e-191">O grupo de segurança universal SalesUsersAdministrator deve já ter sido criado para que esse cmdlet funcione.</span><span class="sxs-lookup"><span data-stu-id="0250e-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="0250e-192">Criando uma nova função</span><span class="sxs-lookup"><span data-stu-id="0250e-192">Creating a New Role</span></span>

<span data-ttu-id="0250e-193">Para criar uma função que tenha acesso a um conjunto de cmdlets que não estão em uma das funções predefinidas ou a um conjunto de scripts ou módulos, comece novamente usando uma das funções predefinidas como um modelo.</span><span class="sxs-lookup"><span data-stu-id="0250e-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="0250e-194">Observe que os scripts e os módulos que as funções devem ser capazes de executar devem estar armazenados nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="0250e-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="0250e-195">O caminho do módulo do Lync, que é por padrão\\C:\\arquivos de\\programas arquivos comuns do\\Microsoft\\Lync Server 2013 Lync</span><span class="sxs-lookup"><span data-stu-id="0250e-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="0250e-196">O caminho do script de usuário, que, por padrão\\, C\\: arquivos\\de programas comuns Microsoft\\Lync Server 2013 AdminScripts</span><span class="sxs-lookup"><span data-stu-id="0250e-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="0250e-197">Para fazer uma nova função, use o cmdlet **New-CsAdminRole** .</span><span class="sxs-lookup"><span data-stu-id="0250e-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="0250e-198">Antes de executar **New-CsAdminRole**, primeiro você deve criar o grupo de segurança universal subjacente que será associado a essa função.</span><span class="sxs-lookup"><span data-stu-id="0250e-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="0250e-199">Os cmdlets a seguir servem como um exemplo de criação de uma nova função.</span><span class="sxs-lookup"><span data-stu-id="0250e-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="0250e-200">Eles criam um novo tipo de função `MyHelpDeskScriptRole`chamado.</span><span class="sxs-lookup"><span data-stu-id="0250e-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="0250e-201">A nova função tem as habilidades da função CsHelpDesk predefinida e, além disso, pode executar as funções em um script chamado "TestScript".</span><span class="sxs-lookup"><span data-stu-id="0250e-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="0250e-202">Para que esse cmdlet funcione, primeiro você deve ter criado o grupo de segurança universal MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="0250e-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="0250e-203">Depois que esse cmdlet é executado, você pode atribuir usuários diretamente a essa função (nesse caso, eles têm escopo global) ou criar uma função de escopo com base nessa função, conforme explicado em criando uma função de escopo, anteriormente neste documento.</span><span class="sxs-lookup"><span data-stu-id="0250e-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="0250e-204">Atribuindo funções a usuários</span><span class="sxs-lookup"><span data-stu-id="0250e-204">Assigning Roles to Users</span></span>

<span data-ttu-id="0250e-205">Cada função do Lync Server está associada a um grupo de segurança universal subjacente do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0250e-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="0250e-206">Qualquer usuário que você adicionar ao grupo subjacente terá as habilidades dessa função.</span><span class="sxs-lookup"><span data-stu-id="0250e-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="0250e-207">Os exemplos nas seções anteriores criaram uma nova função e atribuí um grupo de segurança universal existente para a nova função.</span><span class="sxs-lookup"><span data-stu-id="0250e-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="0250e-208">Para atribuir uma função existente a um ou mais usuários, adicione esses usuários ao grupo associado à função.</span><span class="sxs-lookup"><span data-stu-id="0250e-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="0250e-209">Você pode adicionar usuários individuais e grupos de segurança universais a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="0250e-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="0250e-210">Por exemplo, a função **CsAdministrator** é automaticamente concedida ao grupo de segurança universal **Administradores do CS** no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0250e-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="0250e-211">Este grupo de segurança universal é criado no Active Directory quando você implanta o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0250e-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="0250e-212">Para conceder esse privilégio a um usuário ou grupo, basta adicioná-lo ao grupo de **Administradores do CS** .</span><span class="sxs-lookup"><span data-stu-id="0250e-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="0250e-213">Um usuário pode receber várias funções RBAC ao ser adicionado aos grupos subjacentes do Active Directory que correspondem a cada função.</span><span class="sxs-lookup"><span data-stu-id="0250e-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="0250e-214">Observe que, quando você cria uma função, os usuários adicionados posteriormente ao grupo subjacente do Active Directory ganham as habilidades dessa função.</span><span class="sxs-lookup"><span data-stu-id="0250e-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="0250e-215">Modificando as habilidades de uma função</span><span class="sxs-lookup"><span data-stu-id="0250e-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="0250e-216">Você pode modificar a lista de cmdlets e scripts que uma função pode executar.</span><span class="sxs-lookup"><span data-stu-id="0250e-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="0250e-217">Você pode modificar os cmdlets e scripts que as funções personalizadas podem executar, mas você pode modificar somente os scripts para funções predefinidas.</span><span class="sxs-lookup"><span data-stu-id="0250e-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="0250e-218">Cada cmdlet digitado pode adicionar, remover ou substituir cmdlets ou scripts.</span><span class="sxs-lookup"><span data-stu-id="0250e-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="0250e-219">Para modificar uma função, use o cmdlet **set-CsAdminRole** .</span><span class="sxs-lookup"><span data-stu-id="0250e-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="0250e-220">O cmdlet a seguir remove um script da função.</span><span class="sxs-lookup"><span data-stu-id="0250e-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="0250e-221">Planejando para RBAC</span><span class="sxs-lookup"><span data-stu-id="0250e-221">Planning for RBAC</span></span>

<span data-ttu-id="0250e-222">Para cada pessoa que deve receber qualquer tipo de direitos administrativos para a implantação do Lync Server, considere exatamente quais tarefas precisam executar e, em seguida, atribua-as às funções com o menor privilégio e escopo necessários para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0250e-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="0250e-223">Se necessário, você pode usar o cmdlet **set-CsAdminRole** para criar uma nova função apenas com os cmdlets necessários para as tarefas desta pessoa.</span><span class="sxs-lookup"><span data-stu-id="0250e-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="0250e-224">Os usuários que têm a função CsAdministrator podem criar todos os tipos de funções, incluindo as funções baseadas no CsAdministrator, e atribuir usuários a elas.</span><span class="sxs-lookup"><span data-stu-id="0250e-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="0250e-225">A prática recomendada é atribuir a função CsAdministrator a um conjunto muito pequeno de usuários confiáveis.</span><span class="sxs-lookup"><span data-stu-id="0250e-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

