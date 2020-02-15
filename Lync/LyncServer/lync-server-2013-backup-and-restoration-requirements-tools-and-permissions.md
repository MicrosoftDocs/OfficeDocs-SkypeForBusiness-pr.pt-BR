---
title: 'Lync Server 2013: requisitos de backup e restauração: ferramentas e permissões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86f283aae05985ea903a17dfb15dff83574c42f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="c80c6-102">Requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões</span><span class="sxs-lookup"><span data-stu-id="c80c6-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c80c6-103">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="c80c6-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="c80c6-104">Este tópico identifica as ferramentas que você pode usar para fazer o backup e restaurar o Lync Server 2013, as permissões necessárias e se é possível executar comandos remotamente ou localmente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="c80c6-105">Especificamente, este tópico se concentra nas ferramentas fornecidas com o Lync Server para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="c80c6-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="c80c6-106">Fazer</span><span class="sxs-lookup"><span data-stu-id="c80c6-106">Backups</span></span>

<span data-ttu-id="c80c6-107">Para fazer backup do Lync Server, use as ferramentas identificadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c80c6-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="c80c6-108">Todos os comandos de que você precisa para fazer o backup do Lync Server podem ser executados em script e podem ser executados remotamente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="c80c6-109">Ferramentas para backup do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c80c6-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c80c6-110">Para fazer o backup:</span><span class="sxs-lookup"><span data-stu-id="c80c6-110">To back up this:</span></span></th>
<th><span data-ttu-id="c80c6-111">Use esta ferramenta ou cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c80c6-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-112">Dados de configuração da topologia (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c80c6-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-114">Dados do serviço de informação da localização (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="c80c6-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-116">Dados da configuração do Grupo de Respostas (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c80c6-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-118">Dados de usuário persistente (banco de dados Rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="c80c6-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="c80c6-119">IDs de conferência</span><span class="sxs-lookup"><span data-stu-id="c80c6-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="c80c6-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="c80c6-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="c80c6-121">Banco de dados de arquivamento (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="c80c6-122">Banco de dados do registro de detalhes da chamada de monitoração (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="c80c6-123">Banco de dados de QoE de monitoração (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c80c6-124">Ferramenta de banco de dados do SQL Server, como o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c80c6-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-125">Banco de dados de chat persistente (MGC. MDF)</span><span class="sxs-lookup"><span data-stu-id="c80c6-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-126">Procedimentos de backup do SQL Server ou Export-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="c80c6-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="c80c6-127">Export-CsPersistentChatData exporta dados de chat persistente como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="c80c6-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-128">Todos os repositórios de arquivos: repositório de arquivos do Lync Server, repositório de arquivos de arquivamento</span><span class="sxs-lookup"><span data-stu-id="c80c6-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c80c6-129">Não faça o backup dos arquivos com o nome <STRONG>Meeting.Active</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="c80c6-130">Eles estão em uso e são bloqueados enquanto a reunião ocorre.</span><span class="sxs-lookup"><span data-stu-id="c80c6-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="c80c6-131">Ferramenta de gerenciamento de sistema de arquivos padrão, como o Robocopy.</span><span class="sxs-lookup"><span data-stu-id="c80c6-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="c80c6-132">Tentativas</span><span class="sxs-lookup"><span data-stu-id="c80c6-132">Restoration</span></span>

<span data-ttu-id="c80c6-133">Para restaurar o Lync Server, use as ferramentas da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c80c6-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="c80c6-134">Todos os comandos que você precisa para restaurar o Lync Server podem ser controlados.</span><span class="sxs-lookup"><span data-stu-id="c80c6-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="c80c6-135">Alguns podem ser executados remotamente, mas outros precisam ser executados localmente, conforme especificado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c80c6-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="c80c6-136">Ferramentas para restaurar o Lync Server</span><span class="sxs-lookup"><span data-stu-id="c80c6-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c80c6-137">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="c80c6-137">To do this:</span></span></th>
<th><span data-ttu-id="c80c6-138">Use esta ferramenta ou cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c80c6-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-139">Crie um computador novo ou limpo</span><span class="sxs-lookup"><span data-stu-id="c80c6-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c80c6-140">Software de instalação do sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="c80c6-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="c80c6-141">Software de instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c80c6-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="c80c6-142">Certifica o snap-in do Console de Gerenciamento Microsoft (MMC), se estiver restaurando certificados com uma chave privada exportável</span><span class="sxs-lookup"><span data-stu-id="c80c6-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-143">Restaure os dados do repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="c80c6-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="c80c6-144">Ferramenta padrão de gerenciamento de sistema de arquivos, como o Robocopy</span><span class="sxs-lookup"><span data-stu-id="c80c6-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-145">Recrie bancos de dados vazios e defina permissões para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c80c6-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c80c6-146">Repositório de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="c80c6-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="c80c6-147">Servidor de Back-End</span><span class="sxs-lookup"><span data-stu-id="c80c6-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="c80c6-148">Banco de dados de monitoração</span><span class="sxs-lookup"><span data-stu-id="c80c6-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="c80c6-149">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="c80c6-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c80c6-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="c80c6-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-151">Restaurar o ponteiro dos serviços de domínio do Active Directory para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="c80c6-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c80c6-152">Se você perder o ponto de conexão de serviço a qualquer momento, você pode executar este cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="c80c6-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c80c6-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-154">Importar a topologia, as políticas e as definições de configuração para o repositório de gerenciamento central (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="c80c6-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c80c6-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-156">Publicar e habilitar a topologia</span><span class="sxs-lookup"><span data-stu-id="c80c6-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="c80c6-157">Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="c80c6-157">Topology Builder</span></span></p>
<p><span data-ttu-id="c80c6-158">- ou -</span><span class="sxs-lookup"><span data-stu-id="c80c6-158">-or-</span></span></p>
<p><span data-ttu-id="c80c6-159">Publish-CsTopology e Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="c80c6-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-160">Ative a última topologia publicada</span><span class="sxs-lookup"><span data-stu-id="c80c6-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="c80c6-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="c80c6-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-162">Reinstalar componentes do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c80c6-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="c80c6-163">Instalação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c80c6-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c80c6-164">Localizado na pasta de instalação do Lync Server ou na mídia em \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="c80c6-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-165">Restaure os dados informação da localização (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="c80c6-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-167">Restaurar dados persistentes do usuário (Rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="c80c6-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="c80c6-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-169">Dados da configuração do Grupo de Respostas (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c80c6-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c80c6-171">Se a configuração estiver sendo restaurada em um pool recentemente implantado que não tenha dados de grupo de resposta no banco de dados, use a opção – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="c80c6-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="c80c6-172">Use essa opção mesmo se os dados que estão sendo restaurados estiverem em um pool com o mesmo FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="c80c6-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c80c6-173">Caso contrário, a importação não terá êxito, devido aos objetos de contato para os grupos de resposta já existentes no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c80c6-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80c6-174">Restaure os bancos de dados a seguir:</span><span class="sxs-lookup"><span data-stu-id="c80c6-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="c80c6-175">Banco de dados de arquivamento (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="c80c6-176">Bancos de dados de monitoração: banco de dados de registro de detalhes da chamada (LcsCDR.mdf) e banco de dados de QoE (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="c80c6-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c80c6-177">Ferramentas de gerenciamento de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c80c6-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80c6-178">Banco de dados de chat persistente (MGS. MDF)</span><span class="sxs-lookup"><span data-stu-id="c80c6-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c80c6-179">Procedimentos de restauração do SQL Server ou Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="c80c6-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="c80c6-180">Você pode usar Import-CsPersistentChatData com um arquivo criado por Export-CsPersistentChatData, e os dados serão importados para o banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="c80c6-181">Permissões exigidas</span><span class="sxs-lookup"><span data-stu-id="c80c6-181">Required Permissions</span></span>

<span data-ttu-id="c80c6-182">Os usuários devem ser membros do grupo **RTCUniversalServerAdmins** para executar todos os comandos descritos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c80c6-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="c80c6-183">A maioria dos comandos de backup e restauração não oferece suporte ao controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c80c6-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="c80c6-184">Duas exceções são os cmdlets de chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, que devem ser executados por um usuário que seja membro do grupo CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c80c6-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="c80c6-185">Para executar o assistente de implantação do Lync Server, um usuário também deve ser um membro do grupo de administradores locais.</span><span class="sxs-lookup"><span data-stu-id="c80c6-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

