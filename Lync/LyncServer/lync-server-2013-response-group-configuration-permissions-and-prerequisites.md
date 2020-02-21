---
title: 'Lync Server 2013: permissões e pré-requisitos de configuração de grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e27d3495ce2152dee67a5f176c4a0d9f7e7f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="17fac-102">Permissões e pré-requisitos de configuração de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17fac-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17fac-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="17fac-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="17fac-p101">O Grupo de Resposta é um recurso de gerenciamento de chamadas do Enterprise Voice. Este tópico descreve o que é preciso ter para que você possa configurar o Grupo de Resposta, bem como as credenciais administrativas e as permissões necessárias para a execução de tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="17fac-p101">Response Group is an Enterprise Voice call management feature. This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="17fac-106">Esta seção supõe que você leu a documentação de planejamento relacionada ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="17fac-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="17fac-107">Para obter detalhes, consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="17fac-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="17fac-108">Ferramentas de configuração e funções administrativas</span><span class="sxs-lookup"><span data-stu-id="17fac-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="17fac-109">É possível usar as seguintes ferramentas administrativas para configurar o Grupo de Resposta:</span><span class="sxs-lookup"><span data-stu-id="17fac-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="17fac-110">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="17fac-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="17fac-111">Ferramenta de configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="17fac-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="17fac-112">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="17fac-112">Lync Server Management Shell</span></span>

<span data-ttu-id="17fac-113">Para configurar grupos de resposta, você deve ser membro de pelo menos uma das funções administrativas a seguir:</span><span class="sxs-lookup"><span data-stu-id="17fac-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17fac-114"><strong>Grupo de segurança do Diretório Ativo(1)</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="17fac-115">Criar fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="17fac-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="17fac-116">Atribuir gerente</span><span class="sxs-lookup"><span data-stu-id="17fac-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="17fac-117">Criar/atribuir agentes, filas</span><span class="sxs-lookup"><span data-stu-id="17fac-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="17fac-118">Criar/gerenciar horas extras e de feriado</span><span class="sxs-lookup"><span data-stu-id="17fac-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="17fac-119">Ativar/Desativar fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="17fac-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="17fac-120">Configurar fluxo de trabalho (IVR ou Grupo de busca)</span><span class="sxs-lookup"><span data-stu-id="17fac-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17fac-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="17fac-122">√</span><span class="sxs-lookup"><span data-stu-id="17fac-122">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-123">√</span><span class="sxs-lookup"><span data-stu-id="17fac-123">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-124">√</span><span class="sxs-lookup"><span data-stu-id="17fac-124">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-125">√</span><span class="sxs-lookup"><span data-stu-id="17fac-125">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-126">√</span><span class="sxs-lookup"><span data-stu-id="17fac-126">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-127">√</span><span class="sxs-lookup"><span data-stu-id="17fac-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17fac-128"><strong>À csresponsegroupmanager</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="17fac-129">√ (2)</span><span class="sxs-lookup"><span data-stu-id="17fac-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="17fac-130">√ (3)</span><span class="sxs-lookup"><span data-stu-id="17fac-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="17fac-131">√ (3)</span><span class="sxs-lookup"><span data-stu-id="17fac-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="17fac-132">√ (3)</span><span class="sxs-lookup"><span data-stu-id="17fac-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="17fac-133">√ (3)</span><span class="sxs-lookup"><span data-stu-id="17fac-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17fac-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="17fac-135">√</span><span class="sxs-lookup"><span data-stu-id="17fac-135">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-136">√</span><span class="sxs-lookup"><span data-stu-id="17fac-136">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-137">√</span><span class="sxs-lookup"><span data-stu-id="17fac-137">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-138">√</span><span class="sxs-lookup"><span data-stu-id="17fac-138">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-139">√</span><span class="sxs-lookup"><span data-stu-id="17fac-139">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-140">√</span><span class="sxs-lookup"><span data-stu-id="17fac-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17fac-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="17fac-142">√</span><span class="sxs-lookup"><span data-stu-id="17fac-142">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-143">√</span><span class="sxs-lookup"><span data-stu-id="17fac-143">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-144">√</span><span class="sxs-lookup"><span data-stu-id="17fac-144">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-145">√</span><span class="sxs-lookup"><span data-stu-id="17fac-145">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-146">√</span><span class="sxs-lookup"><span data-stu-id="17fac-146">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-147">√</span><span class="sxs-lookup"><span data-stu-id="17fac-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17fac-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="17fac-149">√</span><span class="sxs-lookup"><span data-stu-id="17fac-149">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-150">√</span><span class="sxs-lookup"><span data-stu-id="17fac-150">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-151">√</span><span class="sxs-lookup"><span data-stu-id="17fac-151">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-152">√</span><span class="sxs-lookup"><span data-stu-id="17fac-152">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-153">√</span><span class="sxs-lookup"><span data-stu-id="17fac-153">√</span></span></p></td>
<td><p><span data-ttu-id="17fac-154">√</span><span class="sxs-lookup"><span data-stu-id="17fac-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17fac-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="17fac-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="17fac-156">√ (4)</span><span class="sxs-lookup"><span data-stu-id="17fac-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="17fac-157">√ (4)</span><span class="sxs-lookup"><span data-stu-id="17fac-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="17fac-158">√ (4)</span><span class="sxs-lookup"><span data-stu-id="17fac-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="17fac-159">√ (4)</span><span class="sxs-lookup"><span data-stu-id="17fac-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="17fac-160">√ (4)</span><span class="sxs-lookup"><span data-stu-id="17fac-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="17fac-161">√ (4)</span><span class="sxs-lookup"><span data-stu-id="17fac-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="17fac-162"><STRONG>(1)</STRONG> um objeto de usuário dos serviços de domínio Active Directory deve ser um membro do grupo de segurança do Active Directory especificado listado.</span><span class="sxs-lookup"><span data-stu-id="17fac-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="17fac-163">Um administrador ou outro membro do grupo do Active Directory delegado com as permissões apropriadas para adicionar usuários a um grupo de segurança (por exemplo, administrador, operadores de conta) deve adicionar um objeto user ao grupo ou grupo de segurança listado para que o usuário possa Execute as funções listadas.</span><span class="sxs-lookup"><span data-stu-id="17fac-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="17fac-164"><STRONG>(2)</STRONG> somente para fluxos de trabalho que o CsResponseGroupAdministrator atribuiu ao à csresponsegroupmanager.</span><span class="sxs-lookup"><span data-stu-id="17fac-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="17fac-165"><STRONG>(3)</STRONG> um gerente de grupo de resposta pode atribuir outro membro de à csresponsegroupmanager a um fluxo de trabalho que o gerente atual já gerencia.</span><span class="sxs-lookup"><span data-stu-id="17fac-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="17fac-166"><STRONG>(4)</STRONG> o CsViewOnlyAdministrator pode executar apenas o verbo "Get" do Lync Server Management Shell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="17fac-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="17fac-167">Pré-requisitos da configuração do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="17fac-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="17fac-168">O Grupo de Resposta requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="17fac-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="17fac-169">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="17fac-169">Application service</span></span>

  - <span data-ttu-id="17fac-170">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="17fac-170">Response Group application</span></span>

  - <span data-ttu-id="17fac-171">Pacotes de idiomas</span><span class="sxs-lookup"><span data-stu-id="17fac-171">Language packs</span></span>

  - <span data-ttu-id="17fac-172">Repositório de arquivos (para armazenar arquivos de áudio)</span><span class="sxs-lookup"><span data-stu-id="17fac-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="17fac-173">Serviços Web (inclui a ferramenta de configuração de grupo de resposta e o console de entrada e saída dos agentes)</span><span class="sxs-lookup"><span data-stu-id="17fac-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="17fac-174">Todos estes componentes são instalados por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="17fac-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="17fac-175">Talvez seja necessário executar as seguintes tarefas antes de configurar o grupo de resposta:</span><span class="sxs-lookup"><span data-stu-id="17fac-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="17fac-176">Habilitar usuários para o Lync Server 2013 e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="17fac-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="17fac-177">Modificar um arquivo de configuração para ser compatível com o FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="17fac-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="17fac-178">Modificar o agrupamento de banco de dados para oferecer suporte a caracteres Yi, Meng e Zang para nomes de fila e nomes de grupo de agente.</span><span class="sxs-lookup"><span data-stu-id="17fac-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="17fac-179">Permitir usuários</span><span class="sxs-lookup"><span data-stu-id="17fac-179">Enabling Users</span></span>

<span data-ttu-id="17fac-180">A primeira etapa da configuração do grupo de resposta é criar grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="17fac-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="17fac-181">Antes de poder criar um grupo de agentes, você deve habilitar os usuários que serão agentes para o grupo de resposta do Lync Server 2013 e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="17fac-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="17fac-182">Habilitar usuários para o Lync Server 2013 normalmente é uma etapa na implantação do servidor Enterprise Edition ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="17fac-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="17fac-183">Para obter detalhes sobre como habilitar usuários para o Lync Server 2013, confira [desabilitar ou reabilitar a conta de usuário do Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="17fac-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="17fac-184">Habilitar usuários para Enterprise Voice geralmente é uma etapa na implantação de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="17fac-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="17fac-185">Para obter detalhes, consulte [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="17fac-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="17fac-186">Conformidade com os requisitos FIPS</span><span class="sxs-lookup"><span data-stu-id="17fac-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="17fac-187">Esta seção somente se aplica a você sea  sua organização precisa cumprir com o FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="17fac-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="17fac-188">Para ser compatível com o FIPS, você precisará modificar o arquivo Web.config de nível de aplicativo para usar um algoritmo de criptografia diferente depois de instalar os serviços da Web.</span><span class="sxs-lookup"><span data-stu-id="17fac-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="17fac-189">Você precisa especificar que o ASP.NET usa o algoritmo Triple Data Encryption Standard (3DES) para processar os dados de estado de exibição.</span><span class="sxs-lookup"><span data-stu-id="17fac-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="17fac-190">Para o aplicativo grupo de resposta, esse requisito se aplica à ferramenta de configuração de grupo de resposta e ao console de entrada e saída do agente.</span><span class="sxs-lookup"><span data-stu-id="17fac-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="17fac-191">Para obter detalhes sobre esse requisito, consulte o artigo 911722 da base de dados de conhecimento da Microsoft, "você pode receber uma mensagem de erro ao acessar as páginas da Web do ASP.NET que possuem ViewState habilitado após a atualização [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)do ASP.NET 1,1 para o ASP.NET 2,0" em.</span><span class="sxs-lookup"><span data-stu-id="17fac-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="17fac-192">Para modificar o arquivo Web.config, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="17fac-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="17fac-193">Em um editor de texto como o Notepad, abra o arquivo Web.config de nível de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="17fac-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="17fac-194">No arquivo Web. config, localize a `<system.web>` seção.</span><span class="sxs-lookup"><span data-stu-id="17fac-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="17fac-195">Adicione a seguinte `<machineKey>` seção na `<system.web>` seção:</span><span class="sxs-lookup"><span data-stu-id="17fac-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="17fac-196">Salve o arquivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="17fac-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="17fac-197">Reinicie o serviço serviços de informações da Internet (IIS) executando o seguinte comando em um prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="17fac-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="17fac-198">Suporte aos caracteres Yi, Meng e Zang</span><span class="sxs-lookup"><span data-stu-id="17fac-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="17fac-199">Esta seção se aplica a você somente se a sua organização precisa oferecer suporte a caracteres Yi, Meng ou Zang.</span><span class="sxs-lookup"><span data-stu-id="17fac-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17fac-200">Para obter informações sobre o que os caracteres Yi, Meng e Zang são e por que eles podem ser importantes para sua implantação, consulte as informações nos conjuntos <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>de caracteres do GB18030.</span><span class="sxs-lookup"><span data-stu-id="17fac-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="17fac-p106">Para oferecer suporte a caracteres Yi, Meng ou Zang, você precisará modificar o agrupamento para o banco de dados Rgsconfig. Altere o agrupamento da coluna **Nome** nas seguintes tabelas em cada banco de dados Rgsconfig:</span><span class="sxs-lookup"><span data-stu-id="17fac-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="17fac-203">dbo. AgentGroups</span><span class="sxs-lookup"><span data-stu-id="17fac-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="17fac-204">dbo. BusinessHours</span><span class="sxs-lookup"><span data-stu-id="17fac-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="17fac-205">dbo. HolidaySets</span><span class="sxs-lookup"><span data-stu-id="17fac-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="17fac-206">dbo. Filas</span><span class="sxs-lookup"><span data-stu-id="17fac-206">dbo.Queues</span></span>

  - <span data-ttu-id="17fac-207">dbo. Fluxos</span><span class="sxs-lookup"><span data-stu-id="17fac-207">dbo.Workflows</span></span>

<span data-ttu-id="17fac-208">Para o SQL Server 2008 R2 e o SQL Server 2012, use\_o\_agrupamento latim geral 100 (diferenciação de ênfase).</span><span class="sxs-lookup"><span data-stu-id="17fac-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="17fac-209">Se você usar esse agrupamento, todos os nomes de objeto não se diferenciarão entre maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="17fac-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="17fac-210">Você pode alterar o agrupamento usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="17fac-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="17fac-211">Para obter detalhes sobre como usar essa ferramenta, consulte "usando o SQL Server Management [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)Studio" em.</span><span class="sxs-lookup"><span data-stu-id="17fac-211">For details about using this tool, see "Using SQL Server Management Studio" at [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="17fac-212">Siga essas etapas para alterar o agrupamento:</span><span class="sxs-lookup"><span data-stu-id="17fac-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="17fac-213">Certifique-se de que o SQL Server Management Studio está configurado para permitir alterações que precisam que as tabelas sejam recriadas.</span><span class="sxs-lookup"><span data-stu-id="17fac-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="17fac-214">Para obter detalhes, consulte "caixa de diálogo Salvar (não permitido) [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186)" em.</span><span class="sxs-lookup"><span data-stu-id="17fac-214">For details, see "Save (Not Permitted) Dialog Box" at [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="17fac-215">Para obter detalhes sobre como configurar um agrupamento de colunas, consulte "como definir o agrupamento de colunas (Visual Database Tools [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185))" em.</span><span class="sxs-lookup"><span data-stu-id="17fac-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="17fac-216">Usando o Microsoft SQL Server Management Studio, conecte-se com o banco de dados Rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="17fac-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="17fac-217">Encontre a tabela que você deseja alterar no banco de dados Rgsconfig, clique com o botão direito na tabela e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="17fac-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="17fac-218">Altere o agrupamento da coluna **Nome** e salve a tabela.</span><span class="sxs-lookup"><span data-stu-id="17fac-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

