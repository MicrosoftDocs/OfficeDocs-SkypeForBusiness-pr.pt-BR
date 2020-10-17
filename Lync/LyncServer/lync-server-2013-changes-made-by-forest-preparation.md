---
title: 'Lync Server 2013: alterações feitas pela preparação da floresta'
description: 'Lync Server 2013: alterações feitas pela preparação da floresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543647"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="7b074-103">Alterações feitas pela preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b074-103">Changes made by forest preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b074-104">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="7b074-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7b074-105">Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.</span><span class="sxs-lookup"><span data-stu-id="7b074-105">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="7b074-106">Objetos e configurações globais do Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b074-106">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="7b074-107">Se você armazenar as configurações globais no contêiner de configuração (como é o caso de todas as novas implantações do Lync Server 2013), a preparação da floresta usará o contêiner de serviços existente e adicionará um objeto de **serviço RTC** sob o objeto de serviços de configuração \\ .</span><span class="sxs-lookup"><span data-stu-id="7b074-107">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="7b074-108">Sob a implantação do Serviço de RTC, a preparação da floresta adiciona um objeto **Configurações Globais** do tipo msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="7b074-108">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="7b074-109">O objeto de configurações globais contém todas as configurações que se aplicam à implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-109">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="7b074-110">Se você armazenar as configurações globais no contêiner do sistema, a preparação da floresta usará um contêiner da Microsoft no contêiner do sistema de domínio raiz e um objeto de serviço RTC no objeto do sistema \\ Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7b074-110">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="7b074-111">A preparação de floresta também adiciona um novo objeto **msRTCSIP-Domain** ao domínio raiz no qual o procedimento é executado.</span><span class="sxs-lookup"><span data-stu-id="7b074-111">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="7b074-112">Grupos universais de serviço e administração do Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b074-112">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="7b074-p102">A preparação de floresta cria grupos universais com base no domínio especificado e adiciona entradas de controle de acesso (ACEs) para esses grupos. Essa etapa cria os grupos universais nos contêineres Usuário do domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="7b074-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="7b074-p103">Os grupos universais permitem que os administradores acessem e gerenciem as configurações e serviços globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:</span><span class="sxs-lookup"><span data-stu-id="7b074-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="7b074-117">**Grupos administrativos**     Esses grupos definem as funções de administrador para uma rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-117">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="7b074-118">**Grupos**     de infraestrutura Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-118">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="7b074-119">Eles funcionam como componentes dos grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="7b074-119">They function as components of administrative groups.</span></span> <span data-ttu-id="7b074-120">Não modifique esses grupos ou adicione usuários diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="7b074-120">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="7b074-121">**Grupos**     de serviço Esses grupos são contas de serviço necessárias para acessar vários serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-121">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="7b074-122">A tabela seguir descreve os grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="7b074-122">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="7b074-123">Grupos administrativos criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="7b074-123">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b074-124">Grupo administrativo</span><span class="sxs-lookup"><span data-stu-id="7b074-124">Administrative group</span></span></th>
<th><span data-ttu-id="7b074-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="7b074-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b074-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7b074-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7b074-127">Permite que os membros gerenciem as configurações de servidor e de pool, incluindo todas as funções de servidor, configurações globais e usuários.</span><span class="sxs-lookup"><span data-stu-id="7b074-127">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b074-128">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7b074-128">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7b074-129">Permite que os membros gerenciem configurações de usuário e movam usuários de um servidor ou pool para outro.</span><span class="sxs-lookup"><span data-stu-id="7b074-129">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b074-130">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="7b074-130">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="7b074-131">Permite que os membros leiam configurações de servidor, pool e usuário.</span><span class="sxs-lookup"><span data-stu-id="7b074-131">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b074-132">A tabela seguir descreve os grupos de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="7b074-132">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="7b074-133">Grupos de infraestrutura criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="7b074-133">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b074-134">Grupo de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="7b074-134">Infrastructure group</span></span></th>
<th><span data-ttu-id="7b074-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="7b074-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b074-136">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="7b074-136">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="7b074-137">Concede acesso de gravação aos objetos de configuração global para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-137">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b074-138">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7b074-138">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7b074-139">Concede acesso somente leitura aos objetos de configuração global para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-139">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b074-140">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7b074-140">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7b074-141">Concede acesso somente leitura às configurações de usuário do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-141">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b074-142">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7b074-142">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7b074-143">Concede acesso somente leitura às configurações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-143">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="7b074-144">Este grupo não tem acesso às configurações no nível do pool, mas apenas às configurações específicas de um servidor individual.</span><span class="sxs-lookup"><span data-stu-id="7b074-144">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b074-145">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="7b074-145">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="7b074-146">Concede acesso somente leitura à configuração do Lync Server e é colocado no grupo local de administradores dos aparelhos de filial persistentes durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="7b074-146">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b074-147">A tabela seguir descreve os grupos de serviço.</span><span class="sxs-lookup"><span data-stu-id="7b074-147">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="7b074-148">Grupos de serviço criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="7b074-148">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b074-149">Grupo de serviço</span><span class="sxs-lookup"><span data-stu-id="7b074-149">Service group</span></span></th>
<th><span data-ttu-id="7b074-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="7b074-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b074-151">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7b074-151">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7b074-152">Inclui contas de serviço usadas para executar servidores front-end Server e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7b074-152">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="7b074-153">Esse grupo permite que os servidores tenham acesso de leitura/gravação às configurações globais do Lync Server e aos objetos de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7b074-153">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b074-154">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7b074-154">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7b074-155">Inclui contas de serviço usadas para executar servidores de conferência A/V, serviços Web, servidor de mediação, servidor de arquivamento e servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="7b074-155">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b074-156">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7b074-156">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7b074-157">Inclui contas de serviço usadas para executar servidores de borda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-157">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b074-158">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="7b074-158">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="7b074-159">Inclui servidores que podem participar da replicação do repositório de gerenciamento central do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-159">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b074-160">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7b074-160">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7b074-161">Concede acesso somente leitura às configurações do Lync Server, mas permite a configuração da instalação de um servidor de filial persistente e implantação de aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="7b074-161">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b074-162">Em seguida, a preparação de floresta adiciona os grupos de serviço e administração aos grupos de infraestrutura apropriados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7b074-162">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="7b074-163">RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="7b074-163">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="7b074-164">RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="7b074-164">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="7b074-165">RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="7b074-165">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="7b074-166">A preparação da floresta também cria os seguintes grupos RBAC (controle de acesso baseado na função):</span><span class="sxs-lookup"><span data-stu-id="7b074-166">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="7b074-167">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-167">CSAdministrator</span></span>

  - <span data-ttu-id="7b074-168">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-168">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="7b074-169">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="7b074-169">CSHelpDesk</span></span>

  - <span data-ttu-id="7b074-170">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-170">CSLocationAdministrator</span></span>

  - <span data-ttu-id="7b074-171">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-171">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="7b074-172">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-172">CSServerAdministrator</span></span>

  - <span data-ttu-id="7b074-173">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-173">CSUserAdministrator</span></span>

  - <span data-ttu-id="7b074-174">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-174">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="7b074-175">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b074-175">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="7b074-176">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="7b074-176">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="7b074-177">À csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="7b074-177">CsResponseGroupManager</span></span>

<span data-ttu-id="7b074-178">Para obter detalhes sobre as funções RBAC e as tarefas permitidas para cada uma, consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7b074-178">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="7b074-179">A preparação de floresta cria ACEs particulares e públicas.</span><span class="sxs-lookup"><span data-stu-id="7b074-179">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="7b074-180">Ele cria ACEs privadas no contêiner de configurações globais usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b074-180">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="7b074-181">Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner de sistema no domínio raiz, dependendo de onde você armazena as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="7b074-181">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="7b074-182">As ACEs públicas criadas pela preparação de floresta estão listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7b074-182">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="7b074-183">ACEs públicas criadas pela preparação de floresta</span><span class="sxs-lookup"><span data-stu-id="7b074-183">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b074-184">ACE</span><span class="sxs-lookup"><span data-stu-id="7b074-184">ACE</span></span></th>
<th><span data-ttu-id="7b074-185">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7b074-185">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b074-186">Ler o contêiner Sistema do domínio raiz (não herdado)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="7b074-186">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="7b074-187">X</span><span class="sxs-lookup"><span data-stu-id="7b074-187">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b074-188">Ler o contêiner DisplaySpecifiers de Configuração (não herdado)</span><span class="sxs-lookup"><span data-stu-id="7b074-188">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="7b074-189">X</span><span class="sxs-lookup"><span data-stu-id="7b074-189">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7b074-190"><STRONG>\*</STRONG>As ACEs que não são herdadas não concedem acesso a objetos filho sob esses contêineres.</span><span class="sxs-lookup"><span data-stu-id="7b074-190"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="7b074-191">As ACEs que são herdadas concedem acesso aos objetos filho desses contêineres.</span><span class="sxs-lookup"><span data-stu-id="7b074-191">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="7b074-192">No contêiner Configuração, no contexto de nomenclatura de configuração, a preparação de floresta executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="7b074-192">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="7b074-193">Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página **Propriedade RTC** dos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e InetOrgPersons (por exemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="7b074-193">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="7b074-194">Adiciona um objeto **RTCPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário e Contato.</span><span class="sxs-lookup"><span data-stu-id="7b074-194">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="7b074-195">Adiciona um objeto **RTCUserSearchPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário, Contato, UO e DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="7b074-195">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="7b074-196">Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** do especificador de exibição da UO (unidade organizacional) de cada idioma (por exemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="7b074-196">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="7b074-197">Adiciona os atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** do especificador de exibição de cada idioma para os objetos Usuários, Contatos e InetOrgPerson (por exemplo, em inglês: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="7b074-197">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

