---
title: 'Lync Server 2013: requisitos de backup e restauração: ferramentas e permissões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="70273-102">Requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões</span><span class="sxs-lookup"><span data-stu-id="70273-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70273-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="70273-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="70273-104">Este tópico identifica as ferramentas que você pode usar para fazer backup e restaurar o Lync Server 2013, as permissões necessárias e se pode executar comandos remotamente ou localmente.</span><span class="sxs-lookup"><span data-stu-id="70273-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="70273-105">Especificamente, este tópico se concentra em ferramentas fornecidas com o Lync Server para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="70273-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="70273-106">Fazer</span><span class="sxs-lookup"><span data-stu-id="70273-106">Backups</span></span>

<span data-ttu-id="70273-107">Para fazer backup do Lync Server, use as ferramentas identificadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="70273-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="70273-108">Todos os comandos de que você precisa para fazer backup do Lync Server podem ser executados em script e podem ser executados remotamente.</span><span class="sxs-lookup"><span data-stu-id="70273-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="70273-109">Ferramentas para fazer backup do Lync Server</span><span class="sxs-lookup"><span data-stu-id="70273-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70273-110">Para fazer backup do seguinte:</span><span class="sxs-lookup"><span data-stu-id="70273-110">To back up this:</span></span></th>
<th><span data-ttu-id="70273-111">Use esta ferramenta ou cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70273-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70273-112">Dados de configuração de topologia (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70273-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-114">Dados do serviço de informações de localização (E9-1-1) (LIS. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="70273-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-116">Dados de configuração de grupo de resposta (RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70273-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-118">Dados de usuário persistente (banco de dados Rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="70273-119">IDs de conferência</span><span class="sxs-lookup"><span data-stu-id="70273-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="70273-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="70273-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="70273-121">Banco de dados de arquivamento (LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="70273-122">Monitorando o banco de dados de registros de detalhes de chamadas (LcsCDR. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="70273-123">Monitorando o banco de dados de QoE (QoEMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="70273-124">Ferramenta de banco de dados do SQL Server, como o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70273-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-125">Banco de dados de chat persistente (MGC. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-126">Procedimentos de backup do SQL Server ou Export-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="70273-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="70273-127">Export-CsPersistentChatData exporta dados de chat persistente como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="70273-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-128">Todas as lojas de arquivos: repositório de arquivos do Lync Server, arquivando repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="70273-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70273-129">Arquivos chamados <STRONG>Meeting. Active</STRONG> não devem ser backups.</span><span class="sxs-lookup"><span data-stu-id="70273-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="70273-130">Esses arquivos estão em uso e são bloqueados durante o momento em que uma reunião ocorre.</span><span class="sxs-lookup"><span data-stu-id="70273-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="70273-131">Ferramenta padrão de gerenciamento do sistema de arquivos, como Robocopy.</span><span class="sxs-lookup"><span data-stu-id="70273-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="70273-132">Recuperação</span><span class="sxs-lookup"><span data-stu-id="70273-132">Restoration</span></span>

<span data-ttu-id="70273-133">Para restaurar o Lync Server, use as ferramentas da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="70273-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="70273-134">Todos os comandos que você precisa para restaurar o Lync Server podem ser script.</span><span class="sxs-lookup"><span data-stu-id="70273-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="70273-135">Alguns podem ser executados remotamente, mas outros precisam ser executados localmente, conforme especificado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="70273-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="70273-136">Ferramentas para restaurar o Lync Server</span><span class="sxs-lookup"><span data-stu-id="70273-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70273-137">Para fazer isto:</span><span class="sxs-lookup"><span data-stu-id="70273-137">To do this:</span></span></th>
<th><span data-ttu-id="70273-138">Use esta ferramenta ou cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70273-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70273-139">Criar um computador novo ou limpo</span><span class="sxs-lookup"><span data-stu-id="70273-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70273-140">Software de instalação do sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="70273-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="70273-141">Software de instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="70273-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="70273-142">Snap-in de certificados do console de gerenciamento Microsoft (MMC), se estiver restaurando certificados com uma chave privada exportável</span><span class="sxs-lookup"><span data-stu-id="70273-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-143">Restaurar dados de armazenamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="70273-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="70273-144">Ferramenta padrão de gerenciamento do sistema de arquivos, como Robocopy</span><span class="sxs-lookup"><span data-stu-id="70273-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-145">Recrie bancos de dados vazios e defina permissões para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="70273-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70273-146">Repositório de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="70273-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="70273-147">Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="70273-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="70273-148">Banco de dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="70273-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="70273-149">Banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="70273-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="70273-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="70273-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-151">Restaurar o ponteiro dos serviços de domínio Active Directory para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="70273-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70273-152">Se você perder o ponto de conexão do serviço a qualquer momento, poderá executar novamente esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70273-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="70273-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="70273-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-154">Importar as configurações de topologia, políticas e configuração para o repositório de gerenciamento central (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70273-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-156">Publicar e habilitar a topologia</span><span class="sxs-lookup"><span data-stu-id="70273-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="70273-157">Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="70273-157">Topology Builder</span></span></p>
<p><span data-ttu-id="70273-158">or</span><span class="sxs-lookup"><span data-stu-id="70273-158">-or-</span></span></p>
<p><span data-ttu-id="70273-159">Publicar-CsTopology e habilitar-CsTopology</span><span class="sxs-lookup"><span data-stu-id="70273-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-160">Habilitar a última topologia publicada</span><span class="sxs-lookup"><span data-stu-id="70273-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="70273-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="70273-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-162">Reinstalar componentes do Lync Server</span><span class="sxs-lookup"><span data-stu-id="70273-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="70273-163">Instalação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="70273-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70273-164">Localizado na pasta de instalação do Lync Server ou na mídia em \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="70273-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-165">Restaurar informações de localização (E9-1-1) dados (LIS. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="70273-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-167">Restaurar dados persistentes do usuário (Rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="70273-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-169">Restaurar dados de configuração de grupo de resposta (RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70273-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70273-171">Se a configuração estiver sendo restaurada em um pool recém implantado sem dados de grupo de resposta no banco de dados, você deve usar a opção – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="70273-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="70273-172">Use essa opção mesmo se os dados que estão sendo restaurados estiverem em um pool com o mesmo nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="70273-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="70273-173">Caso contrário, a importação não terá êxito, devido aos objetos de contato para os grupos de resposta já existentes no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70273-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70273-174">Restaure os seguintes bancos de dados:</span><span class="sxs-lookup"><span data-stu-id="70273-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="70273-175">Banco de dados de arquivamento (LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="70273-176">Monitorando bancos de dados: banco de dados de registros de detalhes de chamadas (LcsCDR. MDF) e banco de dados de QoE (QoEMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="70273-177">Ferramentas de gerenciamento de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="70273-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70273-178">Banco de dados de chat persistente (MGS. MDF)</span><span class="sxs-lookup"><span data-stu-id="70273-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70273-179">Procedimentos de restauração do SQL Server ou Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="70273-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="70273-180">Você pode usar Import-CsPersistentChatData com um arquivo criado por Export-CsPersistentChatData, e os dados serão importados para o banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="70273-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="70273-181">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="70273-181">Required Permissions</span></span>

<span data-ttu-id="70273-182">Os usuários devem ser membros do grupo **RTCUniversalServerAdmins** para executar todos os comandos descritos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="70273-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="70273-183">A maioria dos comandos de backup e restauração não oferece suporte ao controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="70273-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="70273-184">Duas exceções são os cmdlets de chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, que devem ser executados por um usuário que seja membro do grupo CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="70273-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="70273-185">Para executar o assistente de implantação do Lync Server, um usuário também deve ser um membro do grupo Administradores locais.</span><span class="sxs-lookup"><span data-stu-id="70273-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

