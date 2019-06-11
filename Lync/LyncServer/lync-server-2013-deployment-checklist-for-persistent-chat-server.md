---
title: 'Lync Server 2013: Lista de verificação de implantação para o Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e539a1aa6883863228aaab19ddaa38300ae45591
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="13285-102">Lista de verificação de implantação para o Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13285-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13285-103">_**Tópico da última modificação:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="13285-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="13285-104">A implantação do Lync Server 2013, servidor de chat persistente exige que você o implante na sequência correta e conclua todas as etapas de implantação necessárias.</span><span class="sxs-lookup"><span data-stu-id="13285-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="13285-105">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="13285-105">Deployment Sequence</span></span>

<span data-ttu-id="13285-106">Você pode implantar o servidor de chat persistente após implantar a topologia inicial, incluindo pelo menos um Lync Server 2013, um pool de front-end ou um servidor do Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="13285-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="13285-107">Este tópico descreve como implantar o servidor de chat persistente adicionando-o a uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="13285-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="13285-108">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="13285-108">Deployment Process</span></span>

<span data-ttu-id="13285-109">A tabela a seguir lista as etapas básicas para implantar o servidor de chat persistente e fornece links para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="13285-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="13285-110">Processo de implantação do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="13285-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13285-111">Tarefa</span><span class="sxs-lookup"><span data-stu-id="13285-111">Task</span></span></th>
<th><span data-ttu-id="13285-112">Etapas</span><span class="sxs-lookup"><span data-stu-id="13285-112">Steps</span></span></th>
<th><span data-ttu-id="13285-113">Funções exigidas e associações em grupo</span><span class="sxs-lookup"><span data-stu-id="13285-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="13285-114">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="13285-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13285-115"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="13285-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="13285-116">No hardware que atender aos requisitos do sistema, instale o seguinte:</span><span class="sxs-lookup"><span data-stu-id="13285-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="13285-117">Nos servidores de front-end do servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="13285-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="13285-118">Um sistema operacional que atenda aos requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="13285-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="13285-119">Pré-requisitos de software para computadores que executam o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13285-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="13285-120">SQL Server no servidor que hospedará o banco de dados persistente do servidor de chat</span><span class="sxs-lookup"><span data-stu-id="13285-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="13285-121">Se for necessário conformidade com o servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="13285-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="13285-122">SQL Server no servidor que hospedará o banco de dados de conformidade do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="13285-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="13285-123">Qualquer usuário que seja membro do grupo Administradores locais.</span><span class="sxs-lookup"><span data-stu-id="13285-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="13285-124"><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="13285-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="13285-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="13285-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="13285-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determinando seus requisitos de sistema para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="13285-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="13285-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisitos técnicos para servidor de chat persistente no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="13285-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13285-128"><strong>Criar a topologia interna apropriada para dar suporte a servidor de chat persistente (e, opcionalmente, conformidade de chat persistente)</strong></span><span class="sxs-lookup"><span data-stu-id="13285-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="13285-129">Execute o construtor de topologias para adicionar um pool de servidores de chat persistentes à sua topologia:</span><span class="sxs-lookup"><span data-stu-id="13285-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="13285-130">Adicionar componentes persistentes do servidor de chat à topologia</span><span class="sxs-lookup"><span data-stu-id="13285-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="13285-131">Criar um banco de dados SQL Server para o repositório persistente do servidor de chat (e um SQL Server de backup para recuperação de desastres)</span><span class="sxs-lookup"><span data-stu-id="13285-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="13285-132">Definir um novo repositório de arquivos do Lync ou usar um repositório de arquivos existente do Lync para arquivos persistentes do servidor de chat</span><span class="sxs-lookup"><span data-stu-id="13285-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="13285-133">Associar o pool do Lync Server 2013 que pode rotear solicitações para este pool do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="13285-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="13285-134">Se a conformidade com Chat Persistente for necessária:</span><span class="sxs-lookup"><span data-stu-id="13285-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="13285-135">Adicionar repositório de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="13285-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="13285-136">Clique na caixa de seleção definição do pool de servidores de chat persistentes para habilitar a conformidade</span><span class="sxs-lookup"><span data-stu-id="13285-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="13285-137">Publicar a topologia</span><span class="sxs-lookup"><span data-stu-id="13285-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="13285-138">Se você instalar o servidor de chat persistente na edição Standard, o nome de domínio totalmente qualificado (FQDN) do pool do servidor de chat persistente deve coincidir com o servidor Standard Edition e os bancos de dados do SQL Server são posicionados na instância do SQL Server Express no padrão Servidor de edição</span><span class="sxs-lookup"><span data-stu-id="13285-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="13285-139">Para definir uma topologia, uma canta membro do grupo de usuários local.</span><span class="sxs-lookup"><span data-stu-id="13285-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="13285-140">Para publicar a topologia, uma conta que seja membro do grupo Domain admins e do grupo RTCUniversalServerAdmins e o usuário também deve ter permissões de controle total (ler/gravar/modificar) na repositório de arquivos do Lync para arquivos de servidor de chat persistente (para que a topologia O construtor pode configurar as DACLs obrigatórias).</span><span class="sxs-lookup"><span data-stu-id="13285-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="13285-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adicionar um servidor de chat persistente à sua implantação no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="13285-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13285-142"><strong>Implantar Servidor de Chat Persistente</strong></span><span class="sxs-lookup"><span data-stu-id="13285-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="13285-143">Execute a instalação do Lync Server em todos os computadores que executam o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="13285-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="13285-144">A configuração do servidor de chat persistente está integrada ao assistente de implantação do Lync Server 2013 que fornece as instruções a seguir:</span><span class="sxs-lookup"><span data-stu-id="13285-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="13285-145">Implantar repositório de gerenciamento local</span><span class="sxs-lookup"><span data-stu-id="13285-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="13285-146">Instalar serviços persistentes do servidor de chat</span><span class="sxs-lookup"><span data-stu-id="13285-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="13285-147">Solicitar e assinar certificados</span><span class="sxs-lookup"><span data-stu-id="13285-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="13285-148">Executar e iniciar os serviços</span><span class="sxs-lookup"><span data-stu-id="13285-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="13285-149">Qualquer usuário que seja membro do grupo Administradores locais.</span><span class="sxs-lookup"><span data-stu-id="13285-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="13285-150">Implantando o <a href="lync-server-2013-deploying-persistent-chat-server.md">servidor de chat persistente no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="13285-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13285-151"><strong>Criar um administrador de Chat Persistente</strong></span><span class="sxs-lookup"><span data-stu-id="13285-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="13285-152">Adicionar usuários ao grupo de segurança CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="13285-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="13285-153">Qualquer usuário que seja membro dos administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="13285-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="13285-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adicionar um administrador de chat persistente no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="13285-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13285-155"><strong>Configurar o Servidor de Chat Persistente</strong></span><span class="sxs-lookup"><span data-stu-id="13285-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="13285-156">Configurar usuários:</span><span class="sxs-lookup"><span data-stu-id="13285-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="13285-157">O usuário deve ser habilitado pela política para acessar o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="13285-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="13285-158">Por padrão, a política está desativada para todos os usuários e pode ser definida nos escopos global/site/pool/usuário.</span><span class="sxs-lookup"><span data-stu-id="13285-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="13285-159">Definir configurações</span><span class="sxs-lookup"><span data-stu-id="13285-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="13285-p104">O usuário deve ser membro do CsPersistentChatAdministrator. Para alterar a política, o usuário deve estar no CsUserAdministrator, no mínimo.</span><span class="sxs-lookup"><span data-stu-id="13285-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="13285-162">Configurando o <a href="lync-server-2013-configuring-persistent-chat-server.md">servidor de chat persistente no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="13285-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="13285-163">Você pode implantar um ou mais pools de servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="13285-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="13285-164">Oferecemos suporte a vários pools de servidores de chat persistentes por motivos regulatórios nos quais os dados gerados em determinada região são necessários para permanecer nessa região.</span><span class="sxs-lookup"><span data-stu-id="13285-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="13285-165">Por exemplo, se você implantar um pool de servidores de chat persistente em Chicago e outro em Zurique para ficar em conformidade com as normas de dados na Suíça, os usuários poderão se conectar a salas nos pools de servidores de chat persistentes, contanto que tenham acesso.</span><span class="sxs-lookup"><span data-stu-id="13285-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

