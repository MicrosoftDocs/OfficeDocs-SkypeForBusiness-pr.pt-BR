---
title: 'Lync Server 2013: planejamento para controle de acesso baseado em função'
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
ms.openlocfilehash: 65f6411023c80a527cff31c389a8283d090dfc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528028"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="dc69e-102">Planejando o controle de acesso baseado em função no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc69e-102">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc69e-103">_**Última modificação do tópico:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="dc69e-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="dc69e-104">Para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança, o Lync Server 2013 oferece controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="dc69e-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="dc69e-105">Com o RBAC, o privilégio administrativo é concedido pela atribuição de usuários a funções administrativas.</span><span class="sxs-lookup"><span data-stu-id="dc69e-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="dc69e-106">O Lync Server 2013 inclui um conjunto avançado de funções administrativas internas e também permite que você crie novas funções e especifique uma lista personalizada de cmdlets para cada nova função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="dc69e-107">Você pode também adicionar scripts de cmdlets às tarefas permitidas para ambas as funções personalizadas e predefinidas do RBAC.</span><span class="sxs-lookup"><span data-stu-id="dc69e-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="dc69e-108">Melhor segurança e centralização do servidor</span><span class="sxs-lookup"><span data-stu-id="dc69e-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="dc69e-109">Com o RBAC, o acesso e a autorização são baseados precisamente na função do Lync Server do usuário.</span><span class="sxs-lookup"><span data-stu-id="dc69e-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="dc69e-110">Isso permite uso adequado da prática de segurança de "privilégio mínimo", concedendo a administradores e usuários somente os direitos necessários para seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="dc69e-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dc69e-111">As restrições RBAC funcionam somente nos administradores que trabalham remotamente, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc69e-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="dc69e-112">Um usuário em um servidor executando o Lync Server não é restrito pelo RBAC.</span><span class="sxs-lookup"><span data-stu-id="dc69e-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="dc69e-113">Portanto, a segurança física do Lync Server é importante para preservar as restrições de RBAC.</span><span class="sxs-lookup"><span data-stu-id="dc69e-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="dc69e-114">Funções e escopo</span><span class="sxs-lookup"><span data-stu-id="dc69e-114">Roles and Scope</span></span>

<span data-ttu-id="dc69e-115">No RBAC, uma *função* é habilitada para usar uma lista de cmdlets, projetadas para ser útil para um determinado tipo de administrador ou técnico.</span><span class="sxs-lookup"><span data-stu-id="dc69e-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="dc69e-116">Um *escopo* é o conjunto de objetos que os cmdlets definidos em uma função podem operar.</span><span class="sxs-lookup"><span data-stu-id="dc69e-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="dc69e-117">Os objetos que o escopo afeta podem ser contas de usuário (agrupadas por unidade organizacional) ou servidores (agrupados por site).</span><span class="sxs-lookup"><span data-stu-id="dc69e-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="dc69e-118">A tabela a seguir lista as funções predefinidas no Lync Server e fornece uma visão geral dos tipos de tarefas que cada uma pode fazer.</span><span class="sxs-lookup"><span data-stu-id="dc69e-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="dc69e-119">A quarta coluna mostra a função de servidor do Microsoft Exchange semelhante para cada função de servidor do Lync, se houver uma.</span><span class="sxs-lookup"><span data-stu-id="dc69e-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="dc69e-120">Funções administrativas predefinidas</span><span class="sxs-lookup"><span data-stu-id="dc69e-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc69e-121">Role</span><span class="sxs-lookup"><span data-stu-id="dc69e-121">Role</span></span></th>
<th><span data-ttu-id="dc69e-122">Tarefas permitidas</span><span class="sxs-lookup"><span data-stu-id="dc69e-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="dc69e-123">Grupo subjacente do Diretório Ativo</span><span class="sxs-lookup"><span data-stu-id="dc69e-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="dc69e-124">Equivalente do Exchange</span><span class="sxs-lookup"><span data-stu-id="dc69e-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc69e-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-p106">Pode executar todas as tarefas administrativas e modificar todas as configurações, incluindo a criação de funções e a atribuição de usuários a funções. Pode expandir uma implantação adicionando novos sites, pools e serviços.</span><span class="sxs-lookup"><span data-stu-id="dc69e-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-129">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="dc69e-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc69e-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-131">Pode habilitar e desabilitar usuários para o Lync Server, mover usuários e atribuir políticas existentes aos usuários.</span><span class="sxs-lookup"><span data-stu-id="dc69e-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="dc69e-132">Não é possível modificar as políticas.</span><span class="sxs-lookup"><span data-stu-id="dc69e-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-134">Destinatários de Email</span><span class="sxs-lookup"><span data-stu-id="dc69e-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc69e-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-136">Pode criar, configurar e gerenciar políticas e configurações relacionadas à voz.</span><span class="sxs-lookup"><span data-stu-id="dc69e-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-138">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc69e-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc69e-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-p108">Pode gerenciar, monitorar e solucionar problemas de servidores e serviços. Pode impedir novas conexões com servidores, parar e iniciar serviços e aplicar atualizações de software. Não é possível fazer alterações com impacto de configuração global.</span><span class="sxs-lookup"><span data-stu-id="dc69e-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-144">Gerenciamento de Servidor</span><span class="sxs-lookup"><span data-stu-id="dc69e-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc69e-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-146">Pode exibir a implantação, incluindo informações de usuário e servidor, para monitorar a integridade da implantação.</span><span class="sxs-lookup"><span data-stu-id="dc69e-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-148">Gerenciamento da Organização Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="dc69e-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc69e-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="dc69e-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="dc69e-p109">Pode exibir a implantação, incluindo propriedades e políticas do usuário. Pode executar tarefas específicas de solução de problemas. Não é possível alterar propriedades ou políticas do usuário, configuração do servidor ou serviços.</span><span class="sxs-lookup"><span data-stu-id="dc69e-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="dc69e-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="dc69e-154">Comunique</span><span class="sxs-lookup"><span data-stu-id="dc69e-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc69e-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-156">Pode modificar a configuração e as políticas de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="dc69e-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-158">Gerenciamento de Retenção, Bloqueio Legal</span><span class="sxs-lookup"><span data-stu-id="dc69e-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc69e-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-160">Pode gerenciar a configuração do aplicativo Grupo de Resposta em um site.</span><span class="sxs-lookup"><span data-stu-id="dc69e-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-162">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc69e-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc69e-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-p110">Nível mais baixo de direitos de gerenciamento de E9-1-1 (9-1-1 Avançado), incluindo a criação de locais e identificadores de rede E9-1-1 e associando uns com os outros. Esta função é sempre atribuída com um escopo global.</span><span class="sxs-lookup"><span data-stu-id="dc69e-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-167">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc69e-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc69e-168">À csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="dc69e-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="dc69e-169">Pode gerenciar grupos de resposta específicos.</span><span class="sxs-lookup"><span data-stu-id="dc69e-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-170">À csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="dc69e-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="dc69e-171">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc69e-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc69e-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-173">Pode gerenciar o recurso de Bate-papo Persistente e salas de Bate-papo Persistente específicas.</span><span class="sxs-lookup"><span data-stu-id="dc69e-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="dc69e-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="dc69e-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dc69e-175">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc69e-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc69e-176">Todas as funções predefinidas fornecidas no Lync Server têm um escopo global.</span><span class="sxs-lookup"><span data-stu-id="dc69e-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="dc69e-177">Para seguir ao menos as práticas de privilégio, você não deve atribuir usuários a funções com escopo global se eles forem administrar apenas um conjunto limitado de servidores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="dc69e-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="dc69e-178">Para tal, você pode criar funções que são baseadas em uma função existente, mas com escopo mais limitado.</span><span class="sxs-lookup"><span data-stu-id="dc69e-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="dc69e-179">Criando uma Função com escopo</span><span class="sxs-lookup"><span data-stu-id="dc69e-179">Creating a Scoped Role</span></span>

<span data-ttu-id="dc69e-180">Ao criar uma função com escopo limitado (função com escopo), você especifica o escopo junto com a função existente a qual é baseada e o grupo de Diretório Ativo a ser atribuído à função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="dc69e-181">O grupo do Diretório Ativo especificado já deve ter sido criado.</span><span class="sxs-lookup"><span data-stu-id="dc69e-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="dc69e-182">O cmdlet a seguir é um exemplo de uma criação de função a qual possui os privilégios de uma das funções administrativas, mas com escopo limitado.</span><span class="sxs-lookup"><span data-stu-id="dc69e-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="dc69e-183">Ele cria uma nova função chamada `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="dc69e-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="dc69e-184">A função possui as capacidades da função CsServerAdministrator predefinida, mas apenas servidores localizados no local do Site01.</span><span class="sxs-lookup"><span data-stu-id="dc69e-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="dc69e-185">Para que este cmdlet funcione, o site do Site01 já deve estar definido, e um grupo de segurança universal chamado `Site01 Server Administrators` já deve existir.</span><span class="sxs-lookup"><span data-stu-id="dc69e-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="dc69e-186">Após a execução do cmdlet, todos os usuários que são membros do `Site01 Server Administrators` grupo terão privilégios de administrador do servidor para os servidores no Site01.</span><span class="sxs-lookup"><span data-stu-id="dc69e-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="dc69e-187">Além disso, qualquer usuário que posteriormente adicionado a esse grupo de segurança universal também obterá os privilégios dessa função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="dc69e-188">Observe que a função em si e o grupo de segurança universal ao qual é atribuído são chamados `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="dc69e-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="dc69e-189">O exemplo a seguir limita o escopo de usuário, em vez do escopo do servidor.</span><span class="sxs-lookup"><span data-stu-id="dc69e-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="dc69e-190">Ele cria uma `Sales Users Administrator` função para administrar as contas de usuário na unidade organizacional Sales.</span><span class="sxs-lookup"><span data-stu-id="dc69e-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="dc69e-191">O grupo de segurança universal do SalesUsersAdministrator já deve ser criado para que esse cmdlet funcione.</span><span class="sxs-lookup"><span data-stu-id="dc69e-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="dc69e-192">Criando uma nova função</span><span class="sxs-lookup"><span data-stu-id="dc69e-192">Creating a New Role</span></span>

<span data-ttu-id="dc69e-p115">Para criar uma função que possui acesso a um conjunto de cmdlets que não estão em uma das funções predefinidas ou para um conjunto de scripts ou módulos, você pode começar utilizando uma das funções predefinidas como modelo. Observe que os scripts e módulos com a função que devem estar aptos a ser executados devem ser armazenados nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="dc69e-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="dc69e-195">O caminho do módulo do Lync, que é por padrão C: Arquivos de \\ programa arquivos \\ comuns \\ do Microsoft Lync Server 2013 \\ \\ Lync</span><span class="sxs-lookup"><span data-stu-id="dc69e-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="dc69e-196">O caminho do script de usuário, que é por padrão C: Arquivos de \\ programas \\ comuns \\ Microsoft Lync Server 2013 \\ AdminScripts</span><span class="sxs-lookup"><span data-stu-id="dc69e-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="dc69e-197">Para criar uma nova função, utilize o cmdlet **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="dc69e-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="dc69e-198">Antes de executar o **New-CsAdminRole**, você deve primeiro criar o grupo de segurança universal subjacente que será associado a essa função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="dc69e-199">Os seguintes cmdlets servem como um exemplo de criação de nova função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="dc69e-200">Eles criam um novo tipo de função chamado `MyHelpDeskScriptRole` .</span><span class="sxs-lookup"><span data-stu-id="dc69e-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="dc69e-201">A nova função possui as capacidades da função CsHelpDesk predefinida e pode, adicionalmente, executar funções em um script chamado “testscript”.</span><span class="sxs-lookup"><span data-stu-id="dc69e-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="dc69e-202">Para que este cmdlet funcione, você deve ter criado primeiro o grupo de segurança universal MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="dc69e-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="dc69e-203">Depois que esse cmdlet é executado, você pode atribuir usuários diretamente a essa função (neste caso, eles possuem escopo global) ou criar uma função com escopo com base nessa função, como explicado em Criando uma função com escopo, anteriormente neste documento.</span><span class="sxs-lookup"><span data-stu-id="dc69e-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="dc69e-204">Atribuindo funções a usuários</span><span class="sxs-lookup"><span data-stu-id="dc69e-204">Assigning Roles to Users</span></span>

<span data-ttu-id="dc69e-205">Cada função de servidor do Lync é associada a um grupo de segurança universal subjacente do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc69e-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="dc69e-206">Qualquer usuário adicionado ao grupo subjacente recebem as capacidades de tal função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="dc69e-207">Os exemplos nas seções anteriores criaram uma nova função e atribuiram um grupo de segurança universal existente à nova função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="dc69e-208">Para atribuir uma função existente a um ou mais usuários, adicione tais usuários ao grupo associado com tal função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="dc69e-209">Você pode adicionar usuários individuais e grupos de segurança universais a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="dc69e-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="dc69e-210">Por exemplo, a função **CsAdministrator** é automaticamente concedida ao grupo de segurança universal **Administradores de CS** no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc69e-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="dc69e-211">Esse grupo de segurança universal é criado no Active Directory quando você implanta o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc69e-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="dc69e-212">Para fornecer esse privilégio a um usuário ou grupo, você pode simplesmente adicioná-los ao grupo **Administradores CS**.</span><span class="sxs-lookup"><span data-stu-id="dc69e-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="dc69e-213">Um usuário pode receber várias funções do RBAC ao ser adicionado aos grupos subjacentes do Active Directory que correspondem a cada função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="dc69e-214">Observe que quando você cria uma função, os usuários que posteriormente são adicionados ao grupo subjacente do Active Directory ganham os recursos dessa função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="dc69e-215">Modificando as capacidades de uma função</span><span class="sxs-lookup"><span data-stu-id="dc69e-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="dc69e-p121">Você pode modificar a lista de cmdlets e scripts que uma função pode executar. Você pode modificar tanto os cmdlets quanto scripts que as funções personalizadas podem executar, mas pode apenas modificar os scripts para funções predefinidas. Cada cmdlet que você digita pode adicionar, remover ou substituir cmdlets ou scripts.</span><span class="sxs-lookup"><span data-stu-id="dc69e-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="dc69e-219">Para modificar uma função, utilize o cmdlet **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="dc69e-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="dc69e-220">O cmdlet a seguir remove um script da função.</span><span class="sxs-lookup"><span data-stu-id="dc69e-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="dc69e-221">Planejando o RBAC</span><span class="sxs-lookup"><span data-stu-id="dc69e-221">Planning for RBAC</span></span>

<span data-ttu-id="dc69e-222">Para cada pessoa que deverá receber qualquer tipo de direitos administrativos para sua implantação do Lync Server, considere exatamente quais tarefas precisam ser executadas e, em seguida, atribua-as às funções com o menor privilégio e escopo necessários para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc69e-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="dc69e-223">Se necessário, você pode usar o cmdlet **Set-CsAdminRole** para criar uma nova função com com apenas os cmdlets necessários para as tarefas dessa pessoa.</span><span class="sxs-lookup"><span data-stu-id="dc69e-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="dc69e-p124">Os usuários que têm a função CsAdministrator podem criar todos os tipos de funções, incluindo funções baseadas no CsAdministrator e atribuir usuários a elas. A melhor prática é atribuir a função CsAdministrator a um conjunto muito pequeno de usuários confiáveis.</span><span class="sxs-lookup"><span data-stu-id="dc69e-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

