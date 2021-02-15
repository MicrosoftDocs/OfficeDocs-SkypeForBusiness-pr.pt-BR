---
title: Alterações feitas pela preparação da floresta no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831911"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="f302c-103">Alterações feitas pela preparação da floresta no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f302c-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="f302c-104">Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.</span><span class="sxs-lookup"><span data-stu-id="f302c-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="f302c-105">Objetos e configurações globais do Active Directory</span><span class="sxs-lookup"><span data-stu-id="f302c-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="f302c-106">Se você armazenar configurações globais no contêiner Configuração (como é o caso de todas as novas implantações do Skype for Business Server), a preparação da floresta usará o contêiner de Serviços existente e adiciona um objeto de Serviço **RTC** sob o objeto Configuration\Services.</span><span class="sxs-lookup"><span data-stu-id="f302c-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="f302c-107">Sob a implantação do Serviço de RTC, a preparação da floresta adiciona um objeto **Configurações Globais** do tipo msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="f302c-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="f302c-108">O objeto de configurações globais contém todas as configurações que se aplicam à implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="f302c-109">Se você armazenar as configurações globais no contêiner Sistema, a preparação da floresta usará um contêiner Microsoft sob o contêiner Sistema do domínio raiz e um objeto Serviço de RTC sob o objeto Sistema\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f302c-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="f302c-110">A preparação de floresta também adiciona um novo objeto **msRTCSIP-Domain** ao domínio raiz no qual o procedimento é executado.</span><span class="sxs-lookup"><span data-stu-id="f302c-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="f302c-111">Grupos universais de serviço e administração do Active Directory</span><span class="sxs-lookup"><span data-stu-id="f302c-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="f302c-p102">A preparação de floresta cria grupos universais com base no domínio especificado e adiciona entradas de controle de acesso (ACEs) para esses grupos. Essa etapa cria os grupos universais nos contêineres Usuário do domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="f302c-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="f302c-p103">Os grupos universais permitem que os administradores acessem e gerenciem as configurações e serviços globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:</span><span class="sxs-lookup"><span data-stu-id="f302c-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="f302c-116">**Grupos administrativos** Esses grupos definem funções de administrador para uma rede do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="f302c-117">**Grupos de infraestrutura** Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="f302c-118">Eles funcionam como componentes dos grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="f302c-118">They function as components of administrative groups.</span></span> <span data-ttu-id="f302c-119">Não modifique esses grupos ou adicione usuários diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="f302c-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="f302c-120">**Grupos de serviços** Esses grupos são contas de serviço necessárias para acessar vários serviços do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="f302c-121">A tabela seguir descreve os grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="f302c-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="f302c-122">**Grupos administrativos criados durante a preparação da floresta**</span><span class="sxs-lookup"><span data-stu-id="f302c-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="f302c-123">**Grupo administrativo**</span><span class="sxs-lookup"><span data-stu-id="f302c-123">**Administrative group**</span></span>|<span data-ttu-id="f302c-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f302c-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f302c-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f302c-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="f302c-126">Permite que os membros gerenciem as configurações de servidor e de pool, incluindo todas as funções de servidor, configurações globais e usuários.</span><span class="sxs-lookup"><span data-stu-id="f302c-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="f302c-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f302c-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="f302c-128">Permite que os membros gerenciem configurações de usuário e movam usuários de um servidor ou pool para outro.</span><span class="sxs-lookup"><span data-stu-id="f302c-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="f302c-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="f302c-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="f302c-130">Permite que os membros leiam configurações de servidor, pool e usuário.</span><span class="sxs-lookup"><span data-stu-id="f302c-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="f302c-131">A tabela seguir descreve os grupos de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="f302c-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="f302c-132">**Grupos de infraestrutura criados durante a preparação da floresta**</span><span class="sxs-lookup"><span data-stu-id="f302c-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="f302c-133">**Grupo de infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="f302c-133">**Infrastructure group**</span></span>|<span data-ttu-id="f302c-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f302c-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f302c-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="f302c-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="f302c-136">Concede acesso de gravação aos objetos de configuração global do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="f302c-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f302c-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="f302c-138">Concede acesso somente leitura aos objetos de configuração global do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="f302c-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f302c-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="f302c-140">Concede acesso somente leitura às configurações de usuário do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="f302c-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f302c-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="f302c-142">Concede acesso somente leitura às configurações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="f302c-143">Este grupo não tem acesso às configurações no nível do pool, mas apenas às configurações específicas de um servidor individual.</span><span class="sxs-lookup"><span data-stu-id="f302c-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="f302c-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="f302c-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="f302c-145">Concede acesso somente leitura à configuração do Skype for Business Server e é colocado no grupo Administradores Locais dos aparelhos de filial que podem servivíveis durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="f302c-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="f302c-146">A tabela seguir descreve os grupos de serviço.</span><span class="sxs-lookup"><span data-stu-id="f302c-146">The following table describes the service groups.</span></span>

<span data-ttu-id="f302c-147">**Grupos de serviço criados durante a preparação da floresta**</span><span class="sxs-lookup"><span data-stu-id="f302c-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="f302c-148">**Grupo de serviço**</span><span class="sxs-lookup"><span data-stu-id="f302c-148">**Service group**</span></span>|<span data-ttu-id="f302c-149">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f302c-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f302c-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f302c-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="f302c-151">Inclui contas de serviço usadas para executar servidores Front End e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f302c-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="f302c-152">Esse grupo permite aos servidores acesso de leitura/gravação às configurações globais do Skype for Business Server e aos objetos de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f302c-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="f302c-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f302c-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="f302c-154">Inclui contas de serviço usadas para executar Servidores de Conferência A/V, Serviços Web, Servidor de Mediação, Servidor de Arquivamento e Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="f302c-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f302c-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="f302c-156">Inclui contas de serviço usadas para executar os Servidores de Borda do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="f302c-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="f302c-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="f302c-158">Inclui servidores que podem participar da replicação do armazenamento de Gerenciamento Central do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="f302c-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f302c-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="f302c-160">Concede acesso somente leitura às configurações do Skype for Business Server, mas permite a configuração para a instalação de um servidor de filial e implantação de aparelho de filial resvivível.</span><span class="sxs-lookup"><span data-stu-id="f302c-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="f302c-161">Em seguida, a preparação de floresta adiciona os grupos de serviço e administração aos grupos de infraestrutura apropriados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f302c-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="f302c-162">RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="f302c-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="f302c-163">RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="f302c-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="f302c-164">RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="f302c-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="f302c-165">A preparação da floresta também cria os seguintes grupos RBAC (controle de acesso baseado na função):</span><span class="sxs-lookup"><span data-stu-id="f302c-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="f302c-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-166">CSAdministrator</span></span>

- <span data-ttu-id="f302c-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="f302c-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="f302c-168">CSHelpDesk</span></span>

- <span data-ttu-id="f302c-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="f302c-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="f302c-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-171">CSServerAdministrator</span></span>

- <span data-ttu-id="f302c-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-172">CSUserAdministrator</span></span>

- <span data-ttu-id="f302c-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="f302c-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f302c-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="f302c-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="f302c-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="f302c-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="f302c-176">CsResponseGroupManager</span></span>

<span data-ttu-id="f302c-177">Para obter detalhes sobre as funções de RBAC e as tarefas permitidas para cada, consulte [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="f302c-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="f302c-178">A preparação de floresta cria ACEs particulares e públicas.</span><span class="sxs-lookup"><span data-stu-id="f302c-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="f302c-179">Ele cria ACEs privadas no contêiner de configurações globais usado pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f302c-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="f302c-180">Esse contêiner é usado somente pelo Skype for Business Server e está localizado no contêiner Configuração ou no contêiner Sistema no domínio raiz, dependendo de onde você armazena as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="f302c-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="f302c-181">As ACEs públicas criadas pela preparação de floresta estão listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f302c-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="f302c-182">**ACEs públicas criadas pela preparação de floresta**</span><span class="sxs-lookup"><span data-stu-id="f302c-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="f302c-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="f302c-183">**ACE**</span></span>                                                                 | <span data-ttu-id="f302c-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="f302c-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="f302c-185">Ler contêiner do sistema de domínio raiz (não herdado) **\\**\*</span><span class="sxs-lookup"><span data-stu-id="f302c-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="f302c-186">X</span><span class="sxs-lookup"><span data-stu-id="f302c-186">X</span></span>  <br/>                            |
| <span data-ttu-id="f302c-187">Ler o contêiner DisplaySpecifiers da Configuração (não herdado)</span><span class="sxs-lookup"><span data-stu-id="f302c-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="f302c-188">X</span><span class="sxs-lookup"><span data-stu-id="f302c-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="f302c-189"><strong>\\</strong>\*AS ACEs que não são herdadas não concedem acesso a objetos filho nesses contêineres.</span><span class="sxs-lookup"><span data-stu-id="f302c-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="f302c-190">As ACEs que são herdadas concedem acesso aos objetos filho desses contêineres.</span><span class="sxs-lookup"><span data-stu-id="f302c-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="f302c-191">No contêiner Configuração, no contexto de nomenclatura de configuração, a preparação de floresta executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f302c-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="f302c-192">Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página **Propriedade RTC** dos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e InetOrgPersons (por exemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="f302c-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="f302c-193">Adiciona um objeto **RTCPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário e Contato.</span><span class="sxs-lookup"><span data-stu-id="f302c-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="f302c-194">Adiciona um objeto **RTCUserSearchPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário, Contato, UO e DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="f302c-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="f302c-195">Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** do especificador de exibição da UO (unidade organizacional) de cada idioma (por exemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="f302c-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="f302c-196">Adiciona os atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** do especificador de exibição de cada idioma para os objetos Usuários, Contatos e InetOrgPerson (por exemplo, em inglês: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="f302c-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


