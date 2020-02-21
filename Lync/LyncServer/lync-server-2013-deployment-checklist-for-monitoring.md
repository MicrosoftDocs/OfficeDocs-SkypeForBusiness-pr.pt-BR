---
title: 'Lync Server 2013: lista de verificação de implantação para monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca72cf23ea3cb761dd652efae63ef086cae2e198
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="d7f0e-102">Lista de verificação de implantação para monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7f0e-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7f0e-103">_**Última modificação do tópico:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="d7f0e-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="d7f0e-104">Embora o monitoramento já esteja instalado e ativado em cada servidor de front-end, ainda há várias etapas que você deve realizar antes de realmente coletar dados de monitoramento do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d7f0e-105">Essas etapas são descritas na seguinte lista de verificação:</span><span class="sxs-lookup"><span data-stu-id="d7f0e-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7f0e-106">Fase</span><span class="sxs-lookup"><span data-stu-id="d7f0e-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-107">Etapas</span><span class="sxs-lookup"><span data-stu-id="d7f0e-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-108">Associação de grupo e função</span><span class="sxs-lookup"><span data-stu-id="d7f0e-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-109">Documentação</span><span class="sxs-lookup"><span data-stu-id="d7f0e-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0e-110"><strong>Instale o pré-requisito de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0e-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0e-111">Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados backend do monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-112">Usuário do domínio que também é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-113"><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> no guia de suporte</span><span class="sxs-lookup"><span data-stu-id="d7f0e-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="d7f0e-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> no guia de suporte</span><span class="sxs-lookup"><span data-stu-id="d7f0e-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0e-115"><strong>Criar a topologia interna apropriada para dar suporte ao monitoramento</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0e-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0e-116">Use o construtor de topologias do Lync Server 2013 para adicionar bancos de dados de monitoramento à topologia e, em seguida, publique a topologia atualizada.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-117">Para definir uma topologia, um usuário que seja membro do grupo local de usuários.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="d7f0e-118">Para publicar a topologia, um usuário que seja membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associando um repositório de monitoramento a um pool de front-ends no Lync Server 2013</a> no guia de implantação</span><span class="sxs-lookup"><span data-stu-id="d7f0e-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0e-120"><strong>Habilitar a configuração de monitoramento apropriada</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0e-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0e-121">Habilitar registro de detalhes das chamadas (CDR) e/ou o monitoramento da Qualidade da Experiência (QoE) no escopo global e/ou do site.</span><span class="sxs-lookup"><span data-stu-id="d7f0e-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-122">Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration .</span><span class="sxs-lookup"><span data-stu-id="d7f0e-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="d7f0e-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurando a gravação de detalhes da chamada e as configurações de qualidade da experiência no Lync Server 2013</a> no guia de operações</span><span class="sxs-lookup"><span data-stu-id="d7f0e-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

