---
title: 'Lync Server 2013: requisitos de backup e restauração: dados'
description: 'Lync Server 2013: requisitos de backup e restauração: Data.'
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
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563177"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="4bc3f-103">Requisitos de backup e restauração no Lync Server 2013: data</span><span class="sxs-lookup"><span data-stu-id="4bc3f-103">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bc3f-104">_**Última modificação do tópico:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="4bc3f-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="4bc3f-105">O Lync Server usa configurações e informações de configuração que são armazenadas em bancos de dados e dados armazenados em bancos de dados e repositórios de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-105">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="4bc3f-106">Este tópico descreve os dados dos quais você precisa fazer backup para poder restaurar o serviço se sua organização tiver uma falha ou uma interrupção, e também identificar os dados e os componentes usados pelo Lync Server para os quais você precisa fazer backup separadamente.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-106">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="4bc3f-107">Configurações e requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="4bc3f-107">Settings and Configuration Requirements</span></span>

<span data-ttu-id="4bc3f-108">Este tópico inclui procedimentos para fazer backup e restaurar as configurações e as informações de configuração necessárias para a recuperação do serviço do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-108">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="4bc3f-109">As informações de configuração estão localizadas no repositório de gerenciamento central ou em outro banco de dados de back-end ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-109">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="4bc3f-110">A tabela a seguir identifica as configurações e as informações de configuração necessárias para fazer backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-110">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="4bc3f-111">Definições e dados de configuração</span><span class="sxs-lookup"><span data-stu-id="4bc3f-111">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bc3f-112">Tipos de dados</span><span class="sxs-lookup"><span data-stu-id="4bc3f-112">Type of data</span></span></th>
<th><span data-ttu-id="4bc3f-113">Onde armazenado</span><span class="sxs-lookup"><span data-stu-id="4bc3f-113">Where stored</span></span></th>
<th><span data-ttu-id="4bc3f-114">Descrição/quando fazer backup</span><span class="sxs-lookup"><span data-stu-id="4bc3f-114">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bc3f-115">Informações de configuração de topologia</span><span class="sxs-lookup"><span data-stu-id="4bc3f-115">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-116">Repositório de gerenciamento central (banco de dados: XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-116">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-117">Configurações de topologia, política e configuração.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-117">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="4bc3f-118">Faça o backup com seus backups regulares e depois de usar o painel de controle ou cmdlets do Lync Server para modificar sua configuração ou políticas.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-118">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bc3f-119">Informações de local</span><span class="sxs-lookup"><span data-stu-id="4bc3f-119">Location information</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-120">Repositório de gerenciamento central (banco de dados: Lis. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-120">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-121">Informações de configuração do Enterprise Voice Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-121">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="4bc3f-122">Geralmente, essas informações são estáticas.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-122">This information is generally static.</span></span></p>
<p><span data-ttu-id="4bc3f-123">Faça o backup com seus backups regulares.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-123">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bc3f-124">Informações de configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="4bc3f-124">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-125">Servidor back-end ou servidor Standard Edition (banco de dados: RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-125">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-126">Grupos de agente de grupo de resposta, filas e fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-126">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="4bc3f-127">Faça o backup com seus backups regulares e depois de adicionar ou alterar grupos de agentes, filas ou fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-127">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="4bc3f-128">Requisitos de dados</span><span class="sxs-lookup"><span data-stu-id="4bc3f-128">Data Requirements</span></span>

<span data-ttu-id="4bc3f-129">Veja a seguir uma lista dos dados do Lync Server que você precisa fazer o backup para que possa restaurar o serviço do Lync Server em caso de falha.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-129">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="4bc3f-130">Observe que alguns tipos de dados não são necessários para a recuperação.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-130">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="4bc3f-131">Este tópico não contém procedimentos para fazer backup desses tipos de dados, que incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4bc3f-131">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="4bc3f-132">Dados de usuários transitórios, como pontos de extremidade e assinaturas, servidores de conferência ativos e Estados de conferência transitórias (banco de dados: RtcDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-132">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="4bc3f-133">Dados do catálogo de endereços (bancos de dados: RTCAb. MDF e Rtcab1. MDF).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-133">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="4bc3f-134">O banco de dados do catálogo de endereços é regenerado automaticamente de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-134">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="4bc3f-135">Informações dinâmicas para o aplicativo de estacionamento de chamada (banco de dados: CpsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-135">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="4bc3f-136">Dados de grupo de resposta transitório, como o estado de entrada de agentes e informações de chamada em espera (banco de dados: RgsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-136">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="4bc3f-137">O banco de dados de conformidade para chat persistente (banco de dados: MgcComp. MDF).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-137">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="4bc3f-138">Se você tiver a conformidade de chat persistente habilitada, as informações no banco de dados de conformidade de chat persistente serão temporárias, contanto que você tenha um adaptador configurado para ler informações do banco de dados e convertê-lo em um formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-138">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="4bc3f-139">Portanto, o banco de dados de conformidade para chat persistente é considerado temporário.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-139">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="4bc3f-140">Lync Server 2013 persistent chat Server é fornecido com um adaptador XML.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-140">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="4bc3f-141">Você também pode instalar adaptadores personalizados que usam esses dados e movê-los para outras fontes, como arquivos mortos hospedados do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-141">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="4bc3f-142">A tabela a seguir identifica os dados necessários para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-142">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="4bc3f-143">Dados armazenados em bancos de dados</span><span class="sxs-lookup"><span data-stu-id="4bc3f-143">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bc3f-144">Tipos de dados</span><span class="sxs-lookup"><span data-stu-id="4bc3f-144">Type of data</span></span></th>
<th><span data-ttu-id="4bc3f-145">Onde armazenado</span><span class="sxs-lookup"><span data-stu-id="4bc3f-145">Where stored</span></span></th>
<th><span data-ttu-id="4bc3f-146">Descrição/quando fazer backup</span><span class="sxs-lookup"><span data-stu-id="4bc3f-146">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bc3f-147">Dados de usuário persistente</span><span class="sxs-lookup"><span data-stu-id="4bc3f-147">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-148">Servidor back-end ou servidor Standard Edition (banco de dados: RTCXDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-148">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-149">Direitos de usuário, listas de contatos do usuário, dados de servidor ou pool, conferências agendadas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-149">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="4bc3f-150">Estes dados de usuário não incluem conteúdo carregado em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-150">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="4bc3f-151">Faça o backup com seus backups regulares.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-151">Back up with your regular backups.</span></span> <span data-ttu-id="4bc3f-152">Essas informações são dinâmicas, mas a perda de atualizações não é catastrófica no Lync Server se você precisar restaurar para o último backup regular.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-152">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="4bc3f-153">Se as listas de contatos forem fundamentais para sua organização, você pode fazer o backup desses dados com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-153">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bc3f-154">Arquivamento de dados</span><span class="sxs-lookup"><span data-stu-id="4bc3f-154">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-155">Banco de dados de arquivamento (banco de dados: LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-155">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="4bc3f-156">Esses dados podem ser armazenados no Exchange 2013, se você tiver habilitado a opção de integração do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-156">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="4bc3f-157">Caso contrário, esses dados são mantidos em um banco de dados de arquivamento do Lync Server, que pode ser colocado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-157">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-158">Mensagens instantâneas (IM) e conteúdo da reunião.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-158">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="4bc3f-159">Esses dados não são críticos para o Lync Server, mas podem ser fundamentais para sua organização para fins normativos.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-159">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="4bc3f-160">Determine o backup agendado de acordo.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-160">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bc3f-161">Dados de monitoramento</span><span class="sxs-lookup"><span data-stu-id="4bc3f-161">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-162">Bancos de dados de monitoramento (LcsCDR. MDF e QoeMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="4bc3f-162">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="4bc3f-163">Esses bancos de dados podem ser colocados com outro banco de dados do Lync Server ou autônomos em um servidor de banco de dados separado.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-163">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-164">Registros de detalhes da chamada (LcsCDR. MDF) e métricas de QoE (qualidade da experiência) (QoeMetrics. MDF).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-164">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="4bc3f-165">Os registros de detalhes das chamadas são dinâmicos e podem ser fundamentais para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-165">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="4bc3f-166">Determine sua agenda de backup, considerando se você precisa desses registros por razões regulamentares.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-166">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="4bc3f-167">As informações de qualidade da experiência são dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-167">Quality of experience information is dynamic.</span></span> <span data-ttu-id="4bc3f-168">A perda de dados de QoE não é essencial para a operação do Lync Server, mas pode ser crucial para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-168">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="4bc3f-169">Determine sua agenda de backup com base em quão crítica essas informações estão à sua organização.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-169">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bc3f-170">Dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4bc3f-170">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-171">Banco de dados de chat persistente (gerenciadas. MDF).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-171">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="4bc3f-172">Este banco de dados pode ser colocado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-172">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-173">Dados de chat persistente são o conteúdo de chat real que está sendo lançado em salas de chat.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-173">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="4bc3f-174">Esses dados costumam ser críticos para os negócios.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-174">This data is often business critical.</span></span></p>
<p><span data-ttu-id="4bc3f-175">Você pode optar por usar o backup do SQL Server ou exportar o banco de dados usando o cmdlet <strong>Export-CsPersistentChatData</strong> fornecido no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-175">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="4bc3f-176">Para recuperação dos dados, você pode importar e restaurar o banco de dados para o ponto do último backup completo, o que significa que não é possível restaurar o banco de dados para o ponto de falha.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-176">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="4bc3f-177">Requisitos de dados do repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="4bc3f-177">File Store Data Requirements</span></span>

<span data-ttu-id="4bc3f-178">Em uma implantação Enterprise Edition, o repositório de arquivos do Lync Server normalmente está localizado em um servidor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-178">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="4bc3f-179">Em uma implantação do Standard Edition, o repositório de arquivos do Lync Server está localizado por padrão no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-179">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="4bc3f-180">Normalmente, há um repositório de arquivos do Lync Server que é compartilhado para um site.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-180">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="4bc3f-181">O repositório de arquivos de chat persistente usa o mesmo compartilhamento de arquivo que o repositório de arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-181">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="4bc3f-182">Os locais do repositório de arquivos são identificados como o \\ \\ nome do compartilhamento do servidor \\ .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-182">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="4bc3f-183">Para localizar os locais específicos dos repositórios de arquivos, abra o construtor de topologias e examine o nó **repositórios de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-183">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="4bc3f-184">A tabela a seguir identifica os repositórios de arquivos necessários para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-184">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="4bc3f-185">Repositórios de Arquivo</span><span class="sxs-lookup"><span data-stu-id="4bc3f-185">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bc3f-186">Tipos de dados</span><span class="sxs-lookup"><span data-stu-id="4bc3f-186">Type of data</span></span></th>
<th><span data-ttu-id="4bc3f-187">Onde armazenado</span><span class="sxs-lookup"><span data-stu-id="4bc3f-187">Where stored</span></span></th>
<th><span data-ttu-id="4bc3f-188">Descrição/quando fazer backup</span><span class="sxs-lookup"><span data-stu-id="4bc3f-188">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bc3f-189">Repositório de arquivos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="4bc3f-189">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-190">Normalmente em um servidor de arquivos, um cluster de arquivos ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4bc3f-190">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="4bc3f-191">Conteúdo de reunião, metadados de conteúdo de reunião, logs de conformidade, arquivos de dados de aplicativo, arquivos de atualização para atualizações de dispositivo, arquivos de áudio para grupo de resposta, estacionamento de chamada e aplicativos de anúncio e arquivos publicados em salas de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-191">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="4bc3f-192">Faça o backup com seus backups regulares.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-192">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="4bc3f-193">Requisitos adicionais de backup</span><span class="sxs-lookup"><span data-stu-id="4bc3f-193">Additional Backup Requirements</span></span>

<span data-ttu-id="4bc3f-194">Para ajudar a garantir a capacidade de restaurar os serviços do Lync Server em caso de falha, você deve fazer o backup de alguns componentes necessários que não fazem parte do Lync Server propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-194">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="4bc3f-195">Os seguintes componentes não são armazenados ou restaurados como parte do processo de backup e restauração do Lync Server descrito neste documento:</span><span class="sxs-lookup"><span data-stu-id="4bc3f-195">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="4bc3f-196">Serviços de domínio **do Active Directory**     Você precisa fazer backup do AD DS usando as ferramentas do Active Directory ao mesmo tempo em que faz backup do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-196">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="4bc3f-197">É importante manter o AD DS sincronizado com o Lync Server para evitar problemas que podem ocorrer quando o Lync Server espera objetos de contato que não correspondem àqueles no AD DS.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-197">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="4bc3f-198">O AD DS armazena as seguintes configurações que são usadas pelo Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4bc3f-198">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="4bc3f-199">URI do SIP do usuário e outras configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-199">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="4bc3f-200">Objetos de contato para aplicativos como o grupo de resposta e o atendedor de conferência.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-200">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="4bc3f-201">Um ponteiro para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-201">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="4bc3f-202">Conta de autenticação Kerberos (um objeto de computador opcional) e grupos de segurança do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-202">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="4bc3f-203">Para obter detalhes sobre como fazer backup e restaurar o AD DS no Windows Server 2008, consulte "guia passo a passo de backup e recuperação do AD DS" em [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-203">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="4bc3f-204">**Autoridade de certificação e certificados**     Use a política da sua organização para fazer o backup da autoridade de certificação (CA) e dos certificados.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-204">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="4bc3f-205">Se você usar chaves privadas exportáveis, será possível fazer backup do certificado e da chave privada e exportá-los se usar os procedimentos neste documento para restaurar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-205">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="4bc3f-206">Se você usar uma autoridade de certificação interna, poderá reinscrever se precisar restaurar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-206">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="4bc3f-207">É importante que você mantenha a chave privada em um local seguro, onde estará disponível se um computador falhar.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-207">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="4bc3f-208">**System Center Operations Manager**     Se você usar o Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager) para monitorar sua implantação do Lync Server, é possível fazer o backup dos dados que ele cria enquanto está monitorando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-208">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="4bc3f-209">Use o processo de backup padrão do SQL Server para fazer backup dos arquivos do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-209">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="4bc3f-210">Esses arquivos não são restaurados durante a recuperação.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-210">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="4bc3f-211">**Configuração de gateway PSTN (rede telefônica pública comutada)**     Se você usar aparelhos de filial persistente ou Enterprise Voice, precisará fazer backup da configuração de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-211">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="4bc3f-212">Consulte seu fornecedor para obter detalhes sobre o backup e a restauração de configurações de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-212">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="4bc3f-213">**Versões coexistentes do Lync Server ou do Office Communications Server**     Se a implantação do Lync Server 2013 coexistir com o Lync Server 2010 ou uma versão anterior do Office Communications Server, você não poderá usar os procedimentos neste documento para fazer o backup ou a restauração da versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-213">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="4bc3f-214">Em vez disso, você deve usar os procedimentos de backup e restauração documentados especificamente para sua versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-214">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="4bc3f-215">Para obter detalhes sobre como fazer backup e restaurar o Lync Server 2010, consulte [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-215">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="4bc3f-216">Para obter detalhes sobre como fazer backup e restaurar o Microsoft Office Communications Server 2007 R2, consulte [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-216">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="4bc3f-217">**Informações**     de infraestrutura Você precisa fazer backup das informações sobre sua infraestrutura, como a configuração do seu firewall, a configuração de balanceamento de carga, a configuração dos serviços de informações da Internet (IIS), os registros e endereços IP do sistema de nomes de domínio (DNS) e a configuração do protocolo de configuração dinâmica de hosts (DHCP).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-217">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="4bc3f-218">Para obter detalhes sobre como fazer backup desses componentes, verifique com seus respectivos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-218">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="4bc3f-219">**Unificação de mensagens (um) do Microsoft Exchange e do Exchange**     Faça backup e restaure o Microsoft Exchange e o UM do Exchange conforme descrito na documentação do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-219">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="4bc3f-220">Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2013, consulte [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-220">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="4bc3f-221">Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2010, consulte [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .</span><span class="sxs-lookup"><span data-stu-id="4bc3f-221">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="4bc3f-222">Observe que o Lync Server 2013 introduz a capacidade de ter listas de contatos de usuário, fotos de usuário de alta definição e dados de arquivamento armazenados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-222">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="4bc3f-223">Consulte a lista a seguir para ver como fazer backup desses tipos de dados:</span><span class="sxs-lookup"><span data-stu-id="4bc3f-223">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="4bc3f-224">Há backup de **fotos de alta definição** como parte do backup do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-224">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="4bc3f-225">O **repositório unificado de contatos** é apresentado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-225">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="4bc3f-226">O repositório unificado de contatos permite que os usuários mantenham todas as informações de contato no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-226">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="4bc3f-227">Você deve verificar se os backups estão atualizados para os usuários em termos de que seus contatos de usuário estejam armazenados no repositório unificado de contatos ou no servidor back-end do Lync.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-227">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="4bc3f-228">Os cenários a seguir ilustram onde a migração de contatos do usuário para o repositório unificado de contatos pode causar problemas para o processo de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-228">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="4bc3f-229">**Cenário 1:** Os contatos do usuário são migrados para o repositório unificado de contatos e uma restauração é realizada de um backup do Lync Server realizado antes da migração dos contatos do usuário.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-229">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="4bc3f-230">Neste cenário, o usuário terá um estado de contatos desatualizados para até um dia até a tarefa de migração do Lync Server começar a migrar contatos de usuário para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-230">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="4bc3f-231">(Observe que, como os contatos do usuário foram anteriormente migrados para o repositório unificado de contatos, as informações de contato do Exchange serão usadas).</span><span class="sxs-lookup"><span data-stu-id="4bc3f-231">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="4bc3f-232">Nenhuma intervenção do administrador é necessária neste cenário.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-232">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="4bc3f-233">**Cenário 2:** Os contatos do usuário foram armazenados anteriormente no repositório unificado de contatos, mas revertidos.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-233">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="4bc3f-234">Uma restauração é realizada de um backup do Lync Server feito quando os contatos do usuário foram armazenados no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-234">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="4bc3f-235">Neste cenário, uma mensagem de erro `Error: Incorrect Exchange Version` nos logs do servidor cliente ou do Lyss pode indicar isso como um problema.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-235">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="4bc3f-236">O usuário poderá acessar a lista de contatos no Lync 2013 diretamente do Exchange, mas o estado do cliente não corresponderá ao estado do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-236">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="4bc3f-237">Para corrigir isso, um administrador precisará executar os cmdlets **Invoke-CsUCSRollback** para os usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-237">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="4bc3f-238">**Os dados de arquivamento** podem ser armazenados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-238">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="4bc3f-239">Esses dados não são críticos para o Lync Server, mas podem ser fundamentais para sua organização para fins normativos.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-239">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="4bc3f-240">Se os dados de arquivamento estiverem armazenados no Exchange e forem fundamentais para sua organização, siga os procedimentos de backup e restauração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-240">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="4bc3f-241">Observe que os dados de arquivamento armazenados no Exchange não podem ser movidos de volta para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-241">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="4bc3f-242">Além disso, não há como mover dados já armazenados no banco de dados de arquivamento do Lync para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bc3f-242">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

