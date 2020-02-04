---
title: 'Lync Server 2013: requisitos de backup e restauração: dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="06d5c-102">Requisitos de backup e restauração no Lync Server 2013: dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06d5c-103">_**Tópico da última modificação:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="06d5c-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="06d5c-104">O Lync Server usa configurações e informações de configuração que são armazenadas em bancos de dados e dados armazenados em bancos de dados e repositórios de arquivos.</span><span class="sxs-lookup"><span data-stu-id="06d5c-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="06d5c-105">Este tópico descreve os dados dos quais você precisa fazer backup para restaurar o serviço se a sua organização tiver uma falha ou uma interrupção, além de identificar os dados e os componentes usados pelo Lync Server dos quais você precisa fazer backup separadamente.</span><span class="sxs-lookup"><span data-stu-id="06d5c-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="06d5c-106">Configurações e requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="06d5c-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="06d5c-107">Este tópico inclui procedimentos para fazer o backup e a restauração das configurações e informações de configuração necessárias para a recuperação do serviço do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="06d5c-108">As informações de configuração estão localizadas no repositório de gerenciamento central ou em outro banco de dados back-end ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="06d5c-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="06d5c-109">A tabela a seguir identifica as configurações e informações de configuração das quais você precisa fazer backup e restaurar.</span><span class="sxs-lookup"><span data-stu-id="06d5c-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="06d5c-110">Configurações e dados de configuração</span><span class="sxs-lookup"><span data-stu-id="06d5c-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06d5c-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-111">Type of data</span></span></th>
<th><span data-ttu-id="06d5c-112">Onde armazenado</span><span class="sxs-lookup"><span data-stu-id="06d5c-112">Where stored</span></span></th>
<th><span data-ttu-id="06d5c-113">Descrição/quando fazer backup</span><span class="sxs-lookup"><span data-stu-id="06d5c-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06d5c-114">Informações de configuração de topologia</span><span class="sxs-lookup"><span data-stu-id="06d5c-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="06d5c-115">Repositório de gerenciamento central (banco de dados: XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="06d5c-116">Configurações de topologia, política e configuração.</span><span class="sxs-lookup"><span data-stu-id="06d5c-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="06d5c-117">Faça backup com seus backups regulares e depois de usar os cmdlets ou o painel de controle do Lync Server para modificar sua configuração ou políticas.</span><span class="sxs-lookup"><span data-stu-id="06d5c-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d5c-118">Informações de localização</span><span class="sxs-lookup"><span data-stu-id="06d5c-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="06d5c-119">Repositório de gerenciamento central (banco de dados: Lis. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="06d5c-120">Informações de configuração do 9-1-1 (E9-1-1) avançada do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="06d5c-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="06d5c-121">Geralmente, essas informações são estáticas.</span><span class="sxs-lookup"><span data-stu-id="06d5c-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="06d5c-122">Faça backup com seus backups regulares.</span><span class="sxs-lookup"><span data-stu-id="06d5c-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d5c-123">Informações de configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="06d5c-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="06d5c-124">Servidor back-end ou servidor Standard Edition (banco de dados: RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="06d5c-125">Grupo de resposta grupos, filas e fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="06d5c-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="06d5c-126">Faça backup com seus backups regulares e depois de adicionar ou alterar grupos de agente, filas ou fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="06d5c-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="06d5c-127">Requisitos de dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-127">Data Requirements</span></span>

<span data-ttu-id="06d5c-128">Aqui está uma lista dos dados do Lync Server dos quais você precisa fazer backup para que você possa restaurar o serviço do Lync Server em caso de falha.</span><span class="sxs-lookup"><span data-stu-id="06d5c-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="06d5c-129">Observe que alguns tipos de dados não são necessários para a recuperação.</span><span class="sxs-lookup"><span data-stu-id="06d5c-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="06d5c-130">Este tópico não contém procedimentos para fazer backup desses tipos de dados, que incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="06d5c-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="06d5c-131">Dados de usuários transitórios, como pontos de extremidade e assinaturas, servidores de conferência ativos e Estados de conferência transitória (banco de dados: RtcDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="06d5c-132">Dados de catálogo de endereços (bancos de dados: RTCAb. MDF e Rtcab1. MDF).</span><span class="sxs-lookup"><span data-stu-id="06d5c-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="06d5c-133">O banco de dados do catálogo de endereços é regenerado automaticamente dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06d5c-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="06d5c-134">Informações dinâmicas para o aplicativo parque de chamadas (banco de dados: CpsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="06d5c-135">Dados de grupo de resposta transitório, como estado de entrada do agente e informações de chamada em espera (banco de dados: RgsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="06d5c-136">O banco de dados de conformidade para chats persistentes (banco de dados: MgcComp. MDF).</span><span class="sxs-lookup"><span data-stu-id="06d5c-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="06d5c-137">Se a conformidade de chat persistente estiver habilitada, as informações no banco de dados de conformidade de chat persistente serão transitórias desde que você tenha um adaptador configurado para ler as informações do banco de dados e convertê-las em um formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="06d5c-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="06d5c-138">Portanto, o banco de dados de conformidade para chats persistentes é considerado transitório.</span><span class="sxs-lookup"><span data-stu-id="06d5c-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="06d5c-139">O servidor de chat persistente do Lync Server 2013 vem com um adaptador XML.</span><span class="sxs-lookup"><span data-stu-id="06d5c-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="06d5c-140">Você também pode instalar adaptadores personalizados que tomam esses dados e movê-los para outras fontes, como arquivos Exchange hospedados.</span><span class="sxs-lookup"><span data-stu-id="06d5c-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="06d5c-141">A tabela a seguir identifica os dados dos quais você precisa fazer backup e restaurar.</span><span class="sxs-lookup"><span data-stu-id="06d5c-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="06d5c-142">Dados armazenados em bancos de dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06d5c-143">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-143">Type of data</span></span></th>
<th><span data-ttu-id="06d5c-144">Onde armazenado</span><span class="sxs-lookup"><span data-stu-id="06d5c-144">Where stored</span></span></th>
<th><span data-ttu-id="06d5c-145">Descrição/quando fazer backup</span><span class="sxs-lookup"><span data-stu-id="06d5c-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06d5c-146">Dados persistentes do usuário</span><span class="sxs-lookup"><span data-stu-id="06d5c-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="06d5c-147">Servidor back-end ou servidor Standard Edition (banco de dados: RTCXDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="06d5c-148">Direitos de usuário, listas de contatos do usuário, dados de servidor ou pool, conferências programadas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="06d5c-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="06d5c-149">Estes dados do usuário não incluem o conteúdo carregado em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="06d5c-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="06d5c-150">Faça backup com seus backups regulares.</span><span class="sxs-lookup"><span data-stu-id="06d5c-150">Back up with your regular backups.</span></span> <span data-ttu-id="06d5c-151">Essas informações são dinâmicas, mas a perda de atualizações não é catastrófica no Lync Server, caso seja necessário restaurar o último backup regular.</span><span class="sxs-lookup"><span data-stu-id="06d5c-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="06d5c-152">Se as listas de contatos forem essenciais para a sua organização, você poderá fazer backup desses dados com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="06d5c-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d5c-153">Arquivar dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="06d5c-154">Banco de dados de arquivamento (banco de dados: LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="06d5c-155">Esses dados podem ser armazenados no Exchange 2013, se você tiver habilitado a opção de integração do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="06d5c-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="06d5c-156">Caso contrário, esses dados são mantidos em um banco de dados de arquivamento do Lync Server, que pode ser posicionado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</span><span class="sxs-lookup"><span data-stu-id="06d5c-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="06d5c-157">Mensagens instantâneas (IM) e conteúdo da reunião.</span><span class="sxs-lookup"><span data-stu-id="06d5c-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="06d5c-158">Esses dados não são críticos para o Lync Server, mas podem ser críticos para a sua organização para fins reguladores.</span><span class="sxs-lookup"><span data-stu-id="06d5c-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="06d5c-159">Determine o seu cronograma de backup de acordo.</span><span class="sxs-lookup"><span data-stu-id="06d5c-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d5c-160">Monitorando dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="06d5c-161">Bancos de dados de monitoramento (LcsCDR. MDF e QoeMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="06d5c-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="06d5c-162">Esses bancos de dados podem estar posicionados com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</span><span class="sxs-lookup"><span data-stu-id="06d5c-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="06d5c-163">Registros de detalhes da chamada (LcsCDR. MDF) e métricas de qualidade da experiência (QoE) (QoeMetrics. MDF).</span><span class="sxs-lookup"><span data-stu-id="06d5c-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="06d5c-164">Os registros de detalhes da chamada são dinâmicos e podem ser críticos para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="06d5c-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="06d5c-165">Determine o seu cronograma de backup, considerando se você precisa desses registros por motivos reguladores.</span><span class="sxs-lookup"><span data-stu-id="06d5c-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="06d5c-166">As informações de qualidade da experiência são dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="06d5c-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="06d5c-167">A perda de dados de QoE não é essencial para a operação do Lync Server, mas pode ser fundamental para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="06d5c-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="06d5c-168">Determine sua agenda de backup com base em quão críticas essas informações são para sua organização.</span><span class="sxs-lookup"><span data-stu-id="06d5c-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d5c-169">Dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="06d5c-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="06d5c-170">Banco de dados de chat persistente (MGD. MDF).</span><span class="sxs-lookup"><span data-stu-id="06d5c-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="06d5c-171">Esse banco de dados pode estar posicionado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</span><span class="sxs-lookup"><span data-stu-id="06d5c-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="06d5c-172">Dados de chat persistentes são postados pelo conteúdo real do chat em salas de chat.</span><span class="sxs-lookup"><span data-stu-id="06d5c-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="06d5c-173">Geralmente, esses dados são críticos para os negócios.</span><span class="sxs-lookup"><span data-stu-id="06d5c-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="06d5c-174">Você pode optar por usar o backup do SQL Server ou exportar o banco de dados usando o cmdlet <strong>Export-CsPersistentChatData</strong> fornecido no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="06d5c-175">Para a recuperação dos dados, você pode importar e restaurar o banco de dados para o ponto do último backup completo, o que significa que você não pode restaurar o banco de dados ao ponto de falha.</span><span class="sxs-lookup"><span data-stu-id="06d5c-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="06d5c-176">Requisitos de dados do repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="06d5c-176">File Store Data Requirements</span></span>

<span data-ttu-id="06d5c-177">Em uma implantação do Enterprise Edition, o armazenamento de arquivos do Lync Server geralmente está localizado em um servidor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="06d5c-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="06d5c-178">Em uma implantação de edição padrão, o repositório de arquivos do Lync Server está localizado por padrão no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="06d5c-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="06d5c-179">Geralmente, há um repositório de arquivos do Lync Server que é compartilhado para um site.</span><span class="sxs-lookup"><span data-stu-id="06d5c-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="06d5c-180">O repositório de arquivos de chat persistente usa o mesmo compartilhamento de arquivo que o repositório de arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="06d5c-181">Locais do repositório de arquivos são \\ \\identificados\\como nome do compartilhamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="06d5c-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="06d5c-182">Para localizar os locais específicos de seus armazenamentos de arquivos, abra o construtor de topologias e procure no nó **armazenamentos de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="06d5c-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="06d5c-183">A tabela a seguir identifica os armazenamentos de arquivos que você precisa fazer backup e restaurar.</span><span class="sxs-lookup"><span data-stu-id="06d5c-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="06d5c-184">Repositórios de arquivos</span><span class="sxs-lookup"><span data-stu-id="06d5c-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06d5c-185">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="06d5c-185">Type of data</span></span></th>
<th><span data-ttu-id="06d5c-186">Onde armazenado</span><span class="sxs-lookup"><span data-stu-id="06d5c-186">Where stored</span></span></th>
<th><span data-ttu-id="06d5c-187">Descrição/quando fazer backup</span><span class="sxs-lookup"><span data-stu-id="06d5c-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06d5c-188">Repositório de arquivos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="06d5c-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="06d5c-189">Geralmente em um servidor de arquivos, um cluster de arquivos ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="06d5c-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="06d5c-190">Conteúdo da reunião, metadados de conteúdo da reunião, logs de conformidade da reunião, arquivos de dados do aplicativo, arquivos de atualização para atualizações de dispositivo, arquivos de áudio para o grupo de resposta, estacionamento de chamadas e aplicativos de anúncio e arquivos postados em salas de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06d5c-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="06d5c-191">Faça backup com seus backups regulares.</span><span class="sxs-lookup"><span data-stu-id="06d5c-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="06d5c-192">Requisitos adicionais de backup</span><span class="sxs-lookup"><span data-stu-id="06d5c-192">Additional Backup Requirements</span></span>

<span data-ttu-id="06d5c-193">Para ajudar a garantir a capacidade de restaurar os serviços do Lync Server em caso de falha, você deve fazer backup de alguns componentes necessários que não fazem parte do Lync Server propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="06d5c-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="06d5c-194">Não é possível fazer backup ou restauração dos seguintes componentes, como parte do processo de backup e restauração do Lync Server descrito neste documento:</span><span class="sxs-lookup"><span data-stu-id="06d5c-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="06d5c-195">**Serviços de domínio do Active Directory**   você precisa fazer backup do AD DS usando as ferramentas do Active Directory ao mesmo tempo em que fizer backup do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="06d5c-196">É importante manter o AD DS sincronizado com o Lync Server para evitar problemas que podem ocorrer quando o Lync Server espera objetos de contato que não correspondem àqueles no AD DS.</span><span class="sxs-lookup"><span data-stu-id="06d5c-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="06d5c-197">O AD DS armazena as seguintes configurações que são usadas pelo Lync Server:</span><span class="sxs-lookup"><span data-stu-id="06d5c-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="06d5c-198">URI de SIP do usuário e outras configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="06d5c-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="06d5c-199">Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência.</span><span class="sxs-lookup"><span data-stu-id="06d5c-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="06d5c-200">Um ponteiro para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="06d5c-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="06d5c-201">Conta de autenticação Kerberos (um objeto de computador opcional) e grupos de segurança do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="06d5c-202">Para obter detalhes sobre como fazer backup e restaurar o AD DS no Windows Server 2008, consulte "guia passo a passo de backup e recuperação do AD DS [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)" em.</span><span class="sxs-lookup"><span data-stu-id="06d5c-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="06d5c-203">**A autoridade de certificação e os certificados**   usam a política da sua organização para fazer backup da autoridade de certificação e dos certificados.</span><span class="sxs-lookup"><span data-stu-id="06d5c-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="06d5c-204">Se você usar chaves privadas exportáveis, poderá fazer backup do certificado e da chave privada e exportá-los se usar os procedimentos deste documento para restaurar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="06d5c-205">Se você usar uma autoridade de certificação interna, poderá recadastrar se precisar restaurar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="06d5c-206">É importante manter a chave privada em um local seguro, onde estará disponível se um computador falhar.</span><span class="sxs-lookup"><span data-stu-id="06d5c-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="06d5c-207">**System Center Operations Manager**   se você usar o Microsoft System Center Operations Manager (antigo Microsoft Operations Manager) para monitorar a implantação do Lync Server, você pode, opcionalmente, fazer o backup dos dados que ele cria enquanto está monitorando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="06d5c-208">Use o processo de backup padrão do SQL Server para fazer backup dos arquivos do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="06d5c-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="06d5c-209">Esses arquivos não são restaurados durante a recuperação.</span><span class="sxs-lookup"><span data-stu-id="06d5c-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="06d5c-210">**Configuração de gateway da rede de telefonia pública comutada (PSTN)**   se você usar aparelhos de filial e filiais sobreviventes, será necessário fazer backup da configuração do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="06d5c-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="06d5c-211">Consulte o fornecedor para obter detalhes sobre como fazer backup e restaurar configurações de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="06d5c-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="06d5c-212">**Versões coexistentes do Lync Server ou do Office Communications Server**   se sua implantação do Lync Server 2013 existir no Lync Server 2010 ou em uma versão anterior do Office Communications Server, você não poderá usar os procedimentos deste documento para fazer backup ou restaurar a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="06d5c-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="06d5c-213">Em vez disso, você deve usar os procedimentos de backup e restauração documentados especificamente para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="06d5c-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="06d5c-214">Para obter detalhes sobre como fazer backup e restaurar o Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) , consulte.</span><span class="sxs-lookup"><span data-stu-id="06d5c-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="06d5c-215">Para obter detalhes sobre como fazer backup e restaurar o Microsoft Office Communications Server 2007 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)R2, consulte.</span><span class="sxs-lookup"><span data-stu-id="06d5c-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="06d5c-216">**Informações de infraestrutura**   você precisa fazer backup de informações sobre sua infraestrutura, como a configuração do seu firewall, a configuração de balanceamento de carga, a configuração dos serviços de informações da Internet (IIS), os registros DNS e os endereços IP e a configuração de DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="06d5c-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="06d5c-217">Para obter detalhes sobre como fazer backup desses componentes, consulte seus respectivos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="06d5c-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="06d5c-218">**Microsoft Exchange e Exchange Unified Messaging (um)**   backup e restauração do Microsoft Exchange e do Exchange um, conforme descrito na documentação do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="06d5c-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="06d5c-219">Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2013 [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384), consulte.</span><span class="sxs-lookup"><span data-stu-id="06d5c-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="06d5c-220">Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179), consulte.</span><span class="sxs-lookup"><span data-stu-id="06d5c-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="06d5c-221">Observe que o Lync Server 2013 introduz a capacidade de ter listas de contatos do usuário, fotos de usuários de alta definição e arquivar dados armazenados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="06d5c-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="06d5c-222">Veja a lista a seguir para ver como fazer backup desses tipos de dados:</span><span class="sxs-lookup"><span data-stu-id="06d5c-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="06d5c-223">**Fotos de alta definição** são cofeitas como parte do backup do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="06d5c-224">O **repositório de contatos unificado** é apresentado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06d5c-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="06d5c-225">O repositório de contatos unificado permite que os usuários mantenham todas as informações de contato no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="06d5c-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="06d5c-226">Você deve garantir que os backups sejam atualizados para os usuários em termos de se seus contatos do usuário estão armazenados no repositório de contatos unificado ou no servidor do Lync back-end.</span><span class="sxs-lookup"><span data-stu-id="06d5c-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="06d5c-227">Os cenários a seguir ilustram onde a migração de contatos do usuário para o repositório de contatos unificado pode causar problemas para o processo de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="06d5c-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="06d5c-228">**Cenário 1:** Os contatos do usuário são migrados para o repositório de contatos unificado, e uma restauração é realizada de um backup do Lync Server feito antes da migração dos contatos do usuário.</span><span class="sxs-lookup"><span data-stu-id="06d5c-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="06d5c-229">Nesse cenário, o usuário terá um estado de contatos desatualizados para até um dia até que a tarefa de migração do Lync Server comece a migrar contatos do usuário para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="06d5c-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="06d5c-230">(Observe que, como os contatos do usuário foram anteriormente migrados para o repositório de contatos unificado, as informações de contato do Exchange serão usadas).</span><span class="sxs-lookup"><span data-stu-id="06d5c-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="06d5c-231">Nesse cenário, nenhuma intervenção do administrador é necessária.</span><span class="sxs-lookup"><span data-stu-id="06d5c-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="06d5c-232">**Cenário 2:** Os contatos do usuário foram armazenados anteriormente no repositório de contatos unificado, mas depois revertidos.</span><span class="sxs-lookup"><span data-stu-id="06d5c-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="06d5c-233">Uma restauração é realizada de um backup do Lync Server realizada quando os contatos do usuário eram armazenados no repositório de contatos unificado.</span><span class="sxs-lookup"><span data-stu-id="06d5c-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="06d5c-234">Nesse cenário, uma mensagem de erro nos `Error: Incorrect Exchange Version` logs do servidor cliente ou Lyss pode indicar isso como um problema.</span><span class="sxs-lookup"><span data-stu-id="06d5c-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="06d5c-235">O usuário poderá acessar a lista de contatos no Lync 2013 diretamente do Exchange, mas o estado do cliente não será compatível com o estado do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="06d5c-236">Para corrigir isso, um administrador precisará executar os cmdlets **Invoke-CsUCSRollback** para os usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="06d5c-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="06d5c-237">O **arquivamento de dados** pode ser armazenado no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="06d5c-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="06d5c-238">Esses dados não são críticos para o Lync Server, mas podem ser críticos para a sua organização para fins reguladores.</span><span class="sxs-lookup"><span data-stu-id="06d5c-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="06d5c-239">Se o arquivamento de dados estiver armazenado no Exchange e for essencial para sua organização, siga os procedimentos de backup e restauração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="06d5c-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="06d5c-240">Observe que o arquivamento de dados armazenados no Exchange não pode ser retornado ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06d5c-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="06d5c-241">Além disso, não há nenhuma maneira de mover os dados já armazenados no banco de dados de arquivamento do Lync para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="06d5c-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

