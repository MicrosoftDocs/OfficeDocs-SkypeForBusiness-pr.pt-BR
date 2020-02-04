---
title: 'Lync Server 2013: alterações feitas pela preparação da floresta'
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
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="b85c4-102">Alterações feitas pela preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b85c4-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b85c4-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b85c4-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b85c4-104">Esta seção descreve as configurações globais e os objetos, e o serviço universal e os grupos de administração criados pela etapa de preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="b85c4-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="b85c4-105">Objetos e configurações globais do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b85c4-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="b85c4-106">Se você armazenar configurações globais no contêiner de configuração (como é o caso de todas as novas implantações do Lync Server 2013), a preparação da floresta usará o contêiner de serviços existentes e adicionará um objeto de **serviço RTC** no objeto de serviços de configuração\\.</span><span class="sxs-lookup"><span data-stu-id="b85c4-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="b85c4-107">No objeto de serviço RTC, a preparação da floresta adiciona um objeto de **configurações globais** do tipo MsRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="b85c4-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="b85c4-108">O objeto de configurações globais armazena todas as configurações que se aplicam à implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="b85c4-109">Se você armazenar configurações globais no contêiner do sistema, a preparação da floresta usará um contêiner da Microsoft no contêiner do sistema do domínio raiz e um objeto\\de serviço RTC sob o objeto do sistema Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b85c4-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="b85c4-110">A preparação da floresta também adiciona um novo objeto **msRTCSIP-Domain** para o domínio raiz no qual o procedimento é executado.</span><span class="sxs-lookup"><span data-stu-id="b85c4-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="b85c4-111">Grupos de administração e serviço universal do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b85c4-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="b85c4-112">A preparação da floresta cria grupos universais baseados no domínio que você especifica e adiciona entradas de controle de acesso (ACEs) a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="b85c4-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="b85c4-113">Esta etapa cria os grupos universais nos contêineres de usuários do domínio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="b85c4-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="b85c4-114">Os grupos universais permitem que os administradores acessem e gerenciem serviços e configurações globais.</span><span class="sxs-lookup"><span data-stu-id="b85c4-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="b85c4-115">A preparação da floresta adiciona os seguintes tipos de grupos universais:</span><span class="sxs-lookup"><span data-stu-id="b85c4-115">Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="b85c4-116">**Grupos administrativos esses**   grupos definem funções de administrador para uma rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="b85c4-117">**Grupos de infraestrutura**   esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="b85c4-118">Elas funcionam como componentes de grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="b85c4-118">They function as components of administrative groups.</span></span> <span data-ttu-id="b85c4-119">Você não deve modificar esses grupos ou adicionar usuários diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="b85c4-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="b85c4-120">**Grupos de serviços**   esses grupos são contas de serviço que são necessárias para acessar vários serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="b85c4-121">A tabela a seguir descreve os grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="b85c4-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="b85c4-122">Grupos administrativos criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="b85c4-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b85c4-123">Grupo administrativo</span><span class="sxs-lookup"><span data-stu-id="b85c4-123">Administrative group</span></span></th>
<th><span data-ttu-id="b85c4-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="b85c4-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b85c4-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b85c4-126">Permite que os membros gerenciem as configurações do servidor e do pool, incluindo todas as funções do servidor, configurações globais e usuários.</span><span class="sxs-lookup"><span data-stu-id="b85c4-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85c4-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b85c4-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b85c4-128">Permite que os membros gerenciem as configurações do usuário e movam os usuários de um servidor ou pool para outro.</span><span class="sxs-lookup"><span data-stu-id="b85c4-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="b85c4-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="b85c4-130">Permite que os membros leiam configurações de servidor, pool e usuário.</span><span class="sxs-lookup"><span data-stu-id="b85c4-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b85c4-131">A tabela a seguir descreve os grupos de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="b85c4-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="b85c4-132">Grupos de infraestrutura criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="b85c4-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b85c4-133">Grupo de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="b85c4-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="b85c4-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="b85c4-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="b85c4-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="b85c4-136">Concede acesso de gravação a objetos de configuração global do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85c4-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b85c4-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b85c4-138">Concede acesso somente leitura aos objetos de configuração global do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b85c4-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b85c4-140">Concede acesso somente leitura às configurações de usuário do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85c4-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b85c4-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b85c4-142">Concede acesso somente leitura às configurações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="b85c4-143">Esse grupo não tem acesso às configurações do nível do pool, somente para configurações específicas de um servidor individual.</span><span class="sxs-lookup"><span data-stu-id="b85c4-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="b85c4-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="b85c4-145">Concede acesso somente leitura à configuração do Lync Server e é colocado no grupo Administradores local dos aparelhos de ramificação sobreviventes durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="b85c4-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b85c4-146">A tabela a seguir descreve os grupos de serviços.</span><span class="sxs-lookup"><span data-stu-id="b85c4-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="b85c4-147">Grupos de serviço criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="b85c4-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b85c4-148">Grupo de serviços</span><span class="sxs-lookup"><span data-stu-id="b85c4-148">Service group</span></span></th>
<th><span data-ttu-id="b85c4-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="b85c4-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b85c4-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b85c4-151">Inclui contas de serviço usadas para executar servidores front-end Server e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b85c4-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="b85c4-152">Esse grupo permite que os servidores tenham acesso de leitura/gravação para configurações globais do Lync Server e objetos de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b85c4-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85c4-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b85c4-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b85c4-154">Inclui contas de serviço usadas para executar servidores de conferência A/V, serviços Web, servidor de mediação, servidor de arquivamento e Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b85c4-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b85c4-156">Inclui contas de serviço usadas para executar servidores do Lync Server Edge.</span><span class="sxs-lookup"><span data-stu-id="b85c4-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85c4-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="b85c4-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="b85c4-158">Inclui servidores que podem participar da replicação do repositório de gerenciamento central do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b85c4-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b85c4-160">Concede acesso somente leitura às configurações do Lync Server, mas permite a configuração de um servidor de ramificação para a instalação de um servidor de ramificação sobreviventes e a implantação de dispositivos em filiais sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="b85c4-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b85c4-161">A preparação da floresta adiciona grupos de serviços e de administração aos grupos de infraestrutura apropriados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b85c4-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="b85c4-162">RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="b85c4-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="b85c4-163">RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="b85c4-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="b85c4-164">RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="b85c4-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="b85c4-165">A preparação da floresta também cria os seguintes grupos de controle de acesso baseado na função (RBAC):</span><span class="sxs-lookup"><span data-stu-id="b85c4-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="b85c4-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-166">CSAdministrator</span></span>

  - <span data-ttu-id="b85c4-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="b85c4-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b85c4-168">CSHelpDesk</span></span>

  - <span data-ttu-id="b85c4-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="b85c4-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="b85c4-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="b85c4-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="b85c4-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="b85c4-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b85c4-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="b85c4-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="b85c4-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="b85c4-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b85c4-176">CsResponseGroupManager</span></span>

<span data-ttu-id="b85c4-177">Para obter detalhes sobre as funções RBAC e as tarefas permitidas para cada uma, consulte [planejando o controle de acesso baseado em função no Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b85c4-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="b85c4-178">A preparação da floresta cria ACEs públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="b85c4-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="b85c4-179">Ele cria ACEs privadas no contêiner de configurações globais usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b85c4-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="b85c4-180">Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner do sistema do domínio raiz, dependendo de onde você armazenou as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="b85c4-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="b85c4-181">As ACEs públicas criadas pela preparação da floresta são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b85c4-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="b85c4-182">ACEs públicas criadas pela preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="b85c4-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b85c4-183">ACE</span><span class="sxs-lookup"><span data-stu-id="b85c4-183">ACE</span></span></th>
<th><span data-ttu-id="b85c4-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b85c4-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b85c4-185">Ler contêiner do sistema de domínio raiz (não herdado)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="b85c4-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="b85c4-186">X</span><span class="sxs-lookup"><span data-stu-id="b85c4-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85c4-187">Ler o contêiner DisplaySpecifiers da configuração (não herdado)</span><span class="sxs-lookup"><span data-stu-id="b85c4-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="b85c4-188">X</span><span class="sxs-lookup"><span data-stu-id="b85c4-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b85c4-189"><STRONG>\*</STRONG>As ACEs que não são herdadas não concedem acesso a objetos filho sob esses contêineres.</span><span class="sxs-lookup"><span data-stu-id="b85c4-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="b85c4-190">ACEs que são herdadas conceder acesso a objetos filho sob esses contêineres.</span><span class="sxs-lookup"><span data-stu-id="b85c4-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="b85c4-191">No contêiner de configuração, no contexto de nomenclatura de configuração, a preparação da floresta executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b85c4-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="b85c4-192">Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página de **Propriedades RTC** nos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e inetOrgPersons (por exemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="b85c4-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="b85c4-193">Adiciona um objeto **RTCPropertySet** do tipo **ControlAccessRight** em **direitos estendidos** que se aplicam às classes de usuário e de contato.</span><span class="sxs-lookup"><span data-stu-id="b85c4-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="b85c4-194">Adiciona um objeto **RTCUserSearchPropertySet** do tipo **ControlAccessRight** em **direitos estendidos** que se aplicam às classes usuário, contato, UO e DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="b85c4-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="b85c4-195">Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** de cada especificador de exibição de unidade organizacional (ou) de idioma (por exemplo, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN = Default-display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="b85c4-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="b85c4-196">Adiciona atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** de cada especificador de exibição de idioma para os objetos usuários, contatos e INETORGPERSON (por exemplo, em inglês: CN = usuário-exibição, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="b85c4-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

