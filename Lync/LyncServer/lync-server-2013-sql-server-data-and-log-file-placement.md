---
title: 'Lync Server 2013: posicionamento de arquivos de log e dados do SQL Server'
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
ms.openlocfilehash: fc1ae5f876986f6387ce4b1038f89115b746de49
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="0c88b-102">Posicionamento de arquivos de log e dados do SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c88b-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c88b-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0c88b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0c88b-104">Durante o planejamento e a implantação do Microsoft SQL Server 2012 ou do Microsoft SQL Server 2008 R2 SP1 para seu pool de front-ends do Lync Server 2013, uma consideração importante é o posicionamento de dados e arquivos de log em discos rígidos físicos para desempenho.</span><span class="sxs-lookup"><span data-stu-id="0c88b-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="0c88b-105">A configuração de disco recomendada é implementar um conjunto de RAID 1 + 0 usando 6 eixos.</span><span class="sxs-lookup"><span data-stu-id="0c88b-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="0c88b-106">Colocar todos os arquivos de banco de dados e de log usados pelo pool de front-ends e por funções e serviços associados do servidor (ou seja, servidor de arquivamento e monitoramento, serviço de grupo de resposta do Lync Server, serviço de estacionamento de chamadas do Lync Server) para o conjunto de drives RAID usando o Lync Server O assistente de implantação resultará em uma configuração que foi testada para um bom desempenho.</span><span class="sxs-lookup"><span data-stu-id="0c88b-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="0c88b-107">Os arquivos de banco de dados e suas responsabilidades são detalhados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0c88b-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c88b-108">Se suas políticas e configurações do SQL Server exigem uma instalação mais especializada, o banco de dados e os arquivos de log podem ser instalados em qualquer local predefinido usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0c88b-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="0c88b-109">Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013</A> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0c88b-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="0c88b-110">Arquivos de dados e de log para o Repositório de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="0c88b-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c88b-111">Arquivos de banco de dados do repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="0c88b-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="0c88b-112">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="0c88b-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-114">Arquivo de log de transações para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="0c88b-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-115">XDS. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-116">Mantém a configuração da topologia atual do Lync Server 2013, conforme definido e publicado pelo construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="0c88b-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-117">Lis. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-118">Arquivo de dados do serviço de informações de local</span><span class="sxs-lookup"><span data-stu-id="0c88b-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-119">Lis. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-120">Log de transações para o arquivo de dados do serviço de informações de local</span><span class="sxs-lookup"><span data-stu-id="0c88b-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="0c88b-121">Arquivos de dados e de log de Usuário, Conferência e Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="0c88b-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c88b-122">Principais arquivos do banco de dados do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c88b-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="0c88b-123">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="0c88b-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-124">RTC. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-125">Dados persistentes do usuário (por exemplo, listas de controle de acesso (ACLs), contatos, conferências agendadas)</span><span class="sxs-lookup"><span data-stu-id="0c88b-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-127">Log de transações para dados RTC</span><span class="sxs-lookup"><span data-stu-id="0c88b-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-128">RTCDyn. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-129">Mantém dados de usuário temporários (dados de tempo de execução de presença)</span><span class="sxs-lookup"><span data-stu-id="0c88b-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-131">Log de transações para dados de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="0c88b-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-132">RTCAb. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-133">O banco de dados do catálogo de endereços RTC (comunicação em tempo real) é o repositório do SQL Server onde as informações do serviço de Catálogo de Endereços são armazenadas</span><span class="sxs-lookup"><span data-stu-id="0c88b-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-134">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-135">Log de transação para o serviço Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="0c88b-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="0c88b-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="0c88b-137">Hospeda o diretório de conferência</span><span class="sxs-lookup"><span data-stu-id="0c88b-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-138">Rtcxds. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-139">Mantém o backup dos dados do usuário</span><span class="sxs-lookup"><span data-stu-id="0c88b-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-141">Log de transações para dados de Rtcxds</span><span class="sxs-lookup"><span data-stu-id="0c88b-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="0c88b-142">Arquivos de dados e log para o Estacionamento de Chamada e o Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="0c88b-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c88b-143">Banco de dados de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0c88b-143">Application database</span></span></th>
<th><span data-ttu-id="0c88b-144">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="0c88b-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-145">Cpsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-146">Banco de dados de informações dinâmicas para o aplicativo de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="0c88b-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-148">Log de transações para o arquivo de dados de aplicativo de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="0c88b-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-149">Rgsconfig. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-150">Arquivo de dados do serviço Grupo de Resposta do Lync Server para a configuração dos serviços</span><span class="sxs-lookup"><span data-stu-id="0c88b-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-152">Arquivo de log de transações para a configuração do aplicativo de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="0c88b-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-153">Rgsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-154">Arquivo de dados do serviço Grupo de Resposta para operações de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="0c88b-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-156">Log de transação do arquivo de dados de tempo de execuçã do serviço Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="0c88b-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="0c88b-157">Arquivos de dados e de log para o Servidor de Arquivamento e o Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="0c88b-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c88b-158">Arquivos de banco de dados de Arquivamento e Monitoramento</span><span class="sxs-lookup"><span data-stu-id="0c88b-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="0c88b-159">Objetivo do arquivo de dados ou log</span><span class="sxs-lookup"><span data-stu-id="0c88b-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-160">LcsCdr. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-161">Repositório de dados do processo de registro de detalhes das chamadas (CDR) do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="0c88b-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-163">Log de transação dos dados CDR (registro de detalhes da chamada)</span><span class="sxs-lookup"><span data-stu-id="0c88b-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-164">QoEMetrics. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-165">Arquivo de dados de qualidade da experiência armazenado do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="0c88b-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-167">Log de transação dos dados de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="0c88b-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c88b-168">LcsLog. MDF</span><span class="sxs-lookup"><span data-stu-id="0c88b-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-169">Arquivo de dados para a retenção de mensagens instantâneas e dados de conferência em um servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="0c88b-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c88b-170">LcsLog. ldf</span><span class="sxs-lookup"><span data-stu-id="0c88b-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="0c88b-171">Log de transação dos dados de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="0c88b-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0c88b-p103">Neste tópico, são feitas referências ao disco e ao conjunto RAID. Observe que na configuração de recursos do SQL Server, referir-se a um disco significa um dispositivo de hardware único. Um disco rígido com duas partições, uma que mantém os arquivos de log e a outra partição que contém os arquivos de dados, não é o mesmo que dois discos, cada um dedicado a arquivos de log ou de dados.</span><span class="sxs-lookup"><span data-stu-id="0c88b-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="0c88b-175">Em referência aos conjuntos RAID, há diversas tecnologias RAID diferentes de vários fornecedores.</span><span class="sxs-lookup"><span data-stu-id="0c88b-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="0c88b-176">Além disso, com a proliferação de redes SAN, os conjuntos RAID dedicados a um único sistema estão mais raros.</span><span class="sxs-lookup"><span data-stu-id="0c88b-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="0c88b-177">Você deve consultar seu fornecedor de RAID ou SAN para determinar qual é a melhor configuração para o seu layout de disco ao configurar o desempenho do SQL Server com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c88b-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="0c88b-178">Observe também que nem todas as unidades de disco são criadas igualmente; algumas têm melhor desempenho melhor que outras.</span><span class="sxs-lookup"><span data-stu-id="0c88b-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="0c88b-179">Mesmo as unidades do mesmo fabricante podem variar em desempenho devido a velocidade de rotação, tamanho do cache de hardware e outros fatores.</span><span class="sxs-lookup"><span data-stu-id="0c88b-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

