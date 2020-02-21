---
title: 'Lync Server 2013: planilhas de restauração e backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="8a350-102">Planilhas de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a350-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a350-103">_**Última modificação do tópico:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="8a350-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="8a350-104">O plano de backup e restauração da sua organização deve conter detalhes sobre como e quando você faz backup de dados e configurações.</span><span class="sxs-lookup"><span data-stu-id="8a350-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="8a350-105">Você pode usar as planilhas apresentadas aqui para ajudá-lo a documentar essas informações para sua implantação específica e para os requisitos de backup e restauração da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a350-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="8a350-106">Use as planilhas a seguir para registrar as informações necessárias para fazer backup e restaurar o banco de dados, o repositório de arquivos e as informações de configurações de um pool do Lync Server ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8a350-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="8a350-107">Mantenha uma ou mais cópias dessas planilhas em um local seguro para que elas fiquem prontamente acessíveis se você precisar restaurar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a350-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a350-108">As planilhas desta seção abrangem apenas as informações necessárias para restaurar os dados e as configurações dos bancos de dados e servidores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a350-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="8a350-109">Se você precisar documentar outras informações de restauração, como as informações para reinstalação de sistemas operacionais e outros softwares, use os planos de implantação e os planos de backup e restauração da sua organização para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="8a350-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="8a350-110">Planilha de backup e restauração de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8a350-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="8a350-111">Use a tabela a seguir para registrar as informações necessárias para fazer backup e restaurar os bancos de dados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a350-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="8a350-112">Informações de banco de dados para backup e restauração</span><span class="sxs-lookup"><span data-stu-id="8a350-112">Database Information for Backup and Restoration</span></span>

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
<thead>
<tr class="header">
<th><span data-ttu-id="8a350-113">Banco de dados</span><span class="sxs-lookup"><span data-stu-id="8a350-113">Database</span></span></th>
<th><span data-ttu-id="8a350-114">Nome do servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="8a350-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="8a350-115">Agendamento de backup</span><span class="sxs-lookup"><span data-stu-id="8a350-115">Backup schedule</span></span></th>
<th><span data-ttu-id="8a350-116">Ferramenta de backup do banco de dados</span><span class="sxs-lookup"><span data-stu-id="8a350-116">Database backup tool</span></span></th>
<th><span data-ttu-id="8a350-117">Conjunto de backup</span><span class="sxs-lookup"><span data-stu-id="8a350-117">Backup set</span></span></th>
<th><span data-ttu-id="8a350-118">Destino do backup</span><span class="sxs-lookup"><span data-stu-id="8a350-118">Backup destination</span></span></th>
<th><span data-ttu-id="8a350-119">Observações</span><span class="sxs-lookup"><span data-stu-id="8a350-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a350-120">Banco de dados RTC no servidor back-end para dados de usuário</span><span class="sxs-lookup"><span data-stu-id="8a350-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="8a350-121">Cmdlet <strong>Export-CsUserData</strong></span><span class="sxs-lookup"><span data-stu-id="8a350-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="8a350-122">Tdomínio</span><span class="sxs-lookup"><span data-stu-id="8a350-122">Name:</span></span></p>
<p><span data-ttu-id="8a350-123">Validade</span><span class="sxs-lookup"><span data-stu-id="8a350-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a350-124">LcsLog (nome padrão) banco de dados no servidor de banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="8a350-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8a350-125">Ferramenta de gerenciamento do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a350-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="8a350-126">Tdomínio</span><span class="sxs-lookup"><span data-stu-id="8a350-126">Name:</span></span></p>
<p><span data-ttu-id="8a350-127">Validade</span><span class="sxs-lookup"><span data-stu-id="8a350-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a350-128">Banco de dados LcsCdr no servidor do banco de dados de monitoramento para registros de detalhes de chamada (CDRs)</span><span class="sxs-lookup"><span data-stu-id="8a350-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8a350-129">Ferramenta de gerenciamento do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a350-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="8a350-130">Tdomínio</span><span class="sxs-lookup"><span data-stu-id="8a350-130">Name:</span></span></p>
<p><span data-ttu-id="8a350-131">Validade</span><span class="sxs-lookup"><span data-stu-id="8a350-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a350-132">Banco de dados do QoEMetrics no Monitoring Database Server para dados de qualidade da experiência (QoE)</span><span class="sxs-lookup"><span data-stu-id="8a350-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8a350-133">Ferramenta de gerenciamento do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a350-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="8a350-134">Tdomínio</span><span class="sxs-lookup"><span data-stu-id="8a350-134">Name:</span></span></p>
<p><span data-ttu-id="8a350-135">Validade</span><span class="sxs-lookup"><span data-stu-id="8a350-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a350-136">Banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="8a350-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8a350-137">Ferramenta de gerenciamento do SQL Server ou cmdlet <strong>Export-CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="8a350-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="8a350-138">Tdomínio</span><span class="sxs-lookup"><span data-stu-id="8a350-138">Name:</span></span></p>
<p><span data-ttu-id="8a350-139">Validade</span><span class="sxs-lookup"><span data-stu-id="8a350-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a350-140">Não é necessário backup ou restauração dos seguintes bancos de dados:</span><span class="sxs-lookup"><span data-stu-id="8a350-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="8a350-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="8a350-141">Rtcdyn.</span></span> <span data-ttu-id="8a350-142">Os dados do usuário transitório neste banco de dados não são necessários para a restauração do serviço.</span><span class="sxs-lookup"><span data-stu-id="8a350-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="8a350-143">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="8a350-143">Rtcab.</span></span> <span data-ttu-id="8a350-144">O banco de dados do catálogo de endereços é automaticamente recriado a partir da lista de endereços global (GAL) nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8a350-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="8a350-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="8a350-145">Rgsdyn.</span></span> <span data-ttu-id="8a350-146">Os dados do serviço do grupo de resposta transitória neste banco de dados não são necessários para a restauração do serviço.</span><span class="sxs-lookup"><span data-stu-id="8a350-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="8a350-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="8a350-147">Cpsdyn.</span></span> <span data-ttu-id="8a350-148">As informações dinâmicas para o aplicativo de estacionamento de chamadas não são necessárias para a restauração do serviço.</span><span class="sxs-lookup"><span data-stu-id="8a350-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="8a350-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="8a350-149">MgcComp.</span></span> <span data-ttu-id="8a350-150">O banco de dados de conformidade para chat persistente não é necessário para a restauração do serviço.</span><span class="sxs-lookup"><span data-stu-id="8a350-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="8a350-151">Planilha de backup e restauração do repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="8a350-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="8a350-152">Use a tabela a seguir para registrar as informações necessárias para fazer backup e restaurar os repositórios de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8a350-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="8a350-153">Repositórios de arquivos contêm dados como metadados de conteúdo de reunião, reunião de logs de conformidade, logs de atualização para atualizações de dispositivo e arquivos de áudio para o grupo de resposta, estacionamento de chamada e aplicativos de anúncio.</span><span class="sxs-lookup"><span data-stu-id="8a350-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="8a350-154">Informações do repositório de arquivos para backup e restauração</span><span class="sxs-lookup"><span data-stu-id="8a350-154">File Store Information for Backup and Restoration</span></span>

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
<thead>
<tr class="header">
<th><span data-ttu-id="8a350-155">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="8a350-155">Content</span></span></th>
<th><span data-ttu-id="8a350-156">Nome do servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="8a350-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="8a350-157">Agendamento de backup</span><span class="sxs-lookup"><span data-stu-id="8a350-157">Backup schedule</span></span></th>
<th><span data-ttu-id="8a350-158">Ferramenta de backup do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="8a350-158">File system backup tool</span></span></th>
<th><span data-ttu-id="8a350-159">Compartilhamento de arquivos para backup \*</span><span class="sxs-lookup"><span data-stu-id="8a350-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="8a350-160">Destino do backup</span><span class="sxs-lookup"><span data-stu-id="8a350-160">Backup destination</span></span></th>
<th><span data-ttu-id="8a350-161">Observações</span><span class="sxs-lookup"><span data-stu-id="8a350-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a350-162">Repositório de arquivos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8a350-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8a350-163">Ferramenta de backup padrão, como Robocopy</span><span class="sxs-lookup"><span data-stu-id="8a350-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="8a350-164">No servidor de arquivos para Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8a350-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="8a350-165">No Standard Edition por padrão, para a implantação do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8a350-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="8a350-166">Normalmente, um por site.</span><span class="sxs-lookup"><span data-stu-id="8a350-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8a350-167">Não faça o backup dos arquivos com o nome <strong>Meeting.Active</strong>.</span><span class="sxs-lookup"><span data-stu-id="8a350-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="8a350-168">Esses arquivos estão em uso e são bloqueados durante o andamento da reunião.</span><span class="sxs-lookup"><span data-stu-id="8a350-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="8a350-169">Planilha de backup e restauração de configurações</span><span class="sxs-lookup"><span data-stu-id="8a350-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="8a350-170">Use a tabela a seguir para registrar as informações necessárias para fazer backup e restaurar as configurações.</span><span class="sxs-lookup"><span data-stu-id="8a350-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="8a350-171">Informações de configuração para backup e restauração</span><span class="sxs-lookup"><span data-stu-id="8a350-171">Settings Information for Backup and Restoration</span></span>

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
<thead>
<tr class="header">
<th><span data-ttu-id="8a350-172">Banco de dados</span><span class="sxs-lookup"><span data-stu-id="8a350-172">Database</span></span></th>
<th><span data-ttu-id="8a350-173">Nome do servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="8a350-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="8a350-174">Agendamento de backup</span><span class="sxs-lookup"><span data-stu-id="8a350-174">Backup schedule</span></span></th>
<th><span data-ttu-id="8a350-175">Ferramenta de backup</span><span class="sxs-lookup"><span data-stu-id="8a350-175">Backup tool</span></span></th>
<th><span data-ttu-id="8a350-176">Nome do arquivo de configuração (. xml)</span><span class="sxs-lookup"><span data-stu-id="8a350-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="8a350-177">Localização do backup</span><span class="sxs-lookup"><span data-stu-id="8a350-177">Backup location</span></span></th>
<th><span data-ttu-id="8a350-178">Observações</span><span class="sxs-lookup"><span data-stu-id="8a350-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a350-179">Banco de dados XDS no repositório de gerenciamento central para configuração de topologia (global)</span><span class="sxs-lookup"><span data-stu-id="8a350-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="8a350-180">Cmdlet <strong>Export-CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8a350-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a350-181">Lis o banco de dados no repositório de gerenciamento central para informações de local de E9-1-1 (global)</span><span class="sxs-lookup"><span data-stu-id="8a350-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8a350-182">Cmdlet <strong>Export-CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8a350-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a350-183">Banco de dados do RgsConfig no servidor back-end para configuração de grupo de resposta (pool)</span><span class="sxs-lookup"><span data-stu-id="8a350-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8a350-184">Cmdlet <strong>Export-CsRgsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8a350-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

