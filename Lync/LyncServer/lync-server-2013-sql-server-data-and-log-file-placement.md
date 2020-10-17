---
title: 'Lync Server 2013: posicionamento de arquivos de log e dados do SQL Server'
description: 'Lync Server 2013: posicionamento de arquivos de log e dados do SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558277"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="fa093-103">Posicionamento de arquivos de log e dados do SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa093-103">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa093-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fa093-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fa093-105">Durante o planejamento e a implantação do Microsoft SQL Server 2012 ou do Microsoft SQL Server 2008 R2 SP1 para seu pool de front-ends do Lync Server 2013, uma consideração importante é o posicionamento de dados e arquivos de log em discos rígidos físicos para desempenho.</span><span class="sxs-lookup"><span data-stu-id="fa093-105">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="fa093-106">A configuração de disco recomendada é implementar um conjunto de RAID 1 + 0 usando 6 eixos.</span><span class="sxs-lookup"><span data-stu-id="fa093-106">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="fa093-107">Colocar todos os arquivos de banco de dados e de log usados pelo pool de front-ends e os serviços e funções de servidor associadas (ou seja, o servidor de arquivamento e monitoramento, o serviço de grupo de resposta do Lync Server, o serviço de estacionamento de chamadas do Lync Server) para o conjunto de drives RAID usando o assistente de implantação do Lync</span><span class="sxs-lookup"><span data-stu-id="fa093-107">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="fa093-108">Os arquivos de banco de dados e suas responsabilidades são detalhados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa093-108">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa093-109">Se suas políticas e configurações do SQL Server exigem uma instalação mais especializada, o banco de dados e os arquivos de log podem ser instalados em qualquer local predefinido usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa093-109">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="fa093-110">Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013</A> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="fa093-110">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="fa093-111">Arquivos de dados e de log para o Repositório de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="fa093-111">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa093-112">Arquivos de banco de dados do repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="fa093-112">Central Management store database files</span></span></th>
<th><span data-ttu-id="fa093-113">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="fa093-113">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa093-114">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-114">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-115">Arquivo de log de transações para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="fa093-115">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-116">XDS. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-116">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-117">Mantém a configuração da topologia atual do Lync Server 2013, conforme definido e publicado pelo construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="fa093-117">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-118">Lis. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-118">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-119">Arquivo de dados do serviço de informações de local</span><span class="sxs-lookup"><span data-stu-id="fa093-119">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-120">Lis. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-120">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-121">Log de transações para o arquivo de dados do serviço de informações de local</span><span class="sxs-lookup"><span data-stu-id="fa093-121">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="fa093-122">Arquivos de dados e de log de Usuário, Conferência e Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="fa093-122">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa093-123">Principais arquivos do banco de dados do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa093-123">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="fa093-124">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="fa093-124">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa093-125">RTC. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-125">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-126">Dados persistentes do usuário (por exemplo, listas de controle de acesso (ACLs), contatos, conferências agendadas)</span><span class="sxs-lookup"><span data-stu-id="fa093-126">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-127">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-127">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-128">Log de transações para dados RTC</span><span class="sxs-lookup"><span data-stu-id="fa093-128">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-129">RTCDyn. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-129">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-130">Mantém dados de usuário temporários (dados de tempo de execução de presença)</span><span class="sxs-lookup"><span data-stu-id="fa093-130">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-131">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-131">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-132">Log de transações para dados de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="fa093-132">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-133">RTCAb. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-133">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-134">O banco de dados do catálogo de endereços RTC (comunicação em tempo real) é o repositório do SQL Server onde as informações do serviço de Catálogo de Endereços são armazenadas</span><span class="sxs-lookup"><span data-stu-id="fa093-134">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-135">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-135">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-136">Log de transação para o serviço Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="fa093-136">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-137">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="fa093-137">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="fa093-138">Hospeda o diretório de conferência</span><span class="sxs-lookup"><span data-stu-id="fa093-138">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-139">Rtcxds. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-139">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-140">Mantém o backup dos dados do usuário</span><span class="sxs-lookup"><span data-stu-id="fa093-140">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-141">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-141">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-142">Log de transações para dados de Rtcxds</span><span class="sxs-lookup"><span data-stu-id="fa093-142">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="fa093-143">Arquivos de dados e log para o Estacionamento de Chamada e o Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="fa093-143">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa093-144">Banco de dados de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fa093-144">Application database</span></span></th>
<th><span data-ttu-id="fa093-145">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="fa093-145">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa093-146">Cpsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-146">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-147">Banco de dados de informações dinâmicas para o aplicativo de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="fa093-147">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-148">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-148">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-149">Log de transações para o arquivo de dados de aplicativo de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="fa093-149">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-150">Rgsconfig. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-150">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-151">Arquivo de dados do serviço Grupo de Resposta do Lync Server para a configuração dos serviços</span><span class="sxs-lookup"><span data-stu-id="fa093-151">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-152">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-152">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-153">Arquivo de log de transações para a configuração do aplicativo de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fa093-153">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-154">Rgsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-154">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-155">Arquivo de dados do serviço Grupo de Resposta para operações de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="fa093-155">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-156">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-156">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-157">Log de transação do arquivo de dados de tempo de execuçã do serviço Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="fa093-157">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="fa093-158">Arquivos de dados e de log para o Servidor de Arquivamento e o Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="fa093-158">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa093-159">Arquivos de banco de dados de Arquivamento e Monitoramento</span><span class="sxs-lookup"><span data-stu-id="fa093-159">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="fa093-160">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="fa093-160">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa093-161">LcsCdr. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-161">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-162">Repositório de dados do processo de registro de detalhes das chamadas (CDR) do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="fa093-162">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-163">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-163">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-164">Log de transação dos dados CDR (registro de detalhes da chamada)</span><span class="sxs-lookup"><span data-stu-id="fa093-164">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-165">QoEMetrics. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-165">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-166">Arquivo de dados de qualidade da experiência armazenado do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="fa093-166">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-167">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-167">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-168">Log de transação dos dados de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="fa093-168">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa093-169">LcsLog. MDF</span><span class="sxs-lookup"><span data-stu-id="fa093-169">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="fa093-170">Arquivo de dados para a retenção de mensagens instantâneas e dados de conferência em um servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="fa093-170">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa093-171">LcsLog. ldf</span><span class="sxs-lookup"><span data-stu-id="fa093-171">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="fa093-172">Log de transação dos dados de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="fa093-172">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa093-p103">Neste tópico, são feitas referências ao disco e ao conjunto RAID. Observe que na configuração de recursos do SQL Server, referir-se a um disco significa um dispositivo de hardware único. Um disco rígido com duas partições, uma que mantém os arquivos de log e a outra partição que contém os arquivos de dados, não é o mesmo que dois discos, cada um dedicado a arquivos de log ou de dados.</span><span class="sxs-lookup"><span data-stu-id="fa093-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="fa093-176">Em referência aos conjuntos RAID, há diversas tecnologias RAID diferentes de vários fornecedores.</span><span class="sxs-lookup"><span data-stu-id="fa093-176">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="fa093-177">Além disso, com a proliferação de redes SAN, os conjuntos RAID dedicados a um único sistema estão mais raros.</span><span class="sxs-lookup"><span data-stu-id="fa093-177">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="fa093-178">Você deve consultar seu fornecedor de RAID ou SAN para determinar qual é a melhor configuração para o seu layout de disco ao configurar o desempenho do SQL Server com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa093-178">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="fa093-179">Observe também que nem todas as unidades de disco são criadas igualmente; algumas têm melhor desempenho melhor que outras.</span><span class="sxs-lookup"><span data-stu-id="fa093-179">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="fa093-180">Mesmo as unidades do mesmo fabricante podem variar em desempenho devido a velocidade de rotação, tamanho do cache de hardware e outros fatores.</span><span class="sxs-lookup"><span data-stu-id="fa093-180">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

