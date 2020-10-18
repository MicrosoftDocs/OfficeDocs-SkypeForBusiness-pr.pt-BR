---
title: 'Lync Server 2013: dependências operacionais'
description: 'Lync Server 2013: dependências operacionais.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579187"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="d30d2-103">Dependências operacionais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d30d2-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d30d2-104">_**Última modificação do tópico:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="d30d2-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="d30d2-105">A arquitetura de referência discutida neste documento ajudará a garantir que você tenha uma implantação do Lync Server 2013 que não só seja dimensionada para os requisitos da organização, mas seja arquitetada de acordo com as práticas recomendadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d30d2-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="d30d2-106">Seja que, como pode ser a implementação do Lync Server 2013 é um serviço dinâmico e como qualquer outro serviço na empresa ainda requer o monitoramento e o gerenciamento proativo para manter alto nível de disponibilidade de serviço e qualidade de serviço para a empresa.</span><span class="sxs-lookup"><span data-stu-id="d30d2-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="d30d2-107">À medida que o Lync Server 2013 se torna muito ingerido na empresa diária da organização, é importante que o serviço seja gerenciado pelo gerenciamento de nível de serviço preciso e tangível.</span><span class="sxs-lookup"><span data-stu-id="d30d2-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="d30d2-108">A arquitetura do sistema do Lync pode se tornar complexa e muito integrada e, para manter o gerenciamento de nível de serviço efetivo e estabelecer SLAs para o Lync Server 2013, torna-se essencial entender as dependências do sistema em outras plataformas e servidores.</span><span class="sxs-lookup"><span data-stu-id="d30d2-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="d30d2-109">Igualmente importante é observar quais serviços comerciais, como os aplicativos integrados de voz e UC, são dependentes do Lync.</span><span class="sxs-lookup"><span data-stu-id="d30d2-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="d30d2-110">O Lync Server 2013 deve ser estabelecido observando todas as dependências mencionadas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="d30d2-111">O mapa de serviços permitirá que você formule um SLA entre o Lync e seu serviço dependente e forneça um local inicial para negociação de SLA.</span><span class="sxs-lookup"><span data-stu-id="d30d2-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="d30d2-112">A tabela a seguir lista os serviços de dependência típicos para uma infraestrutura do Lync.</span><span class="sxs-lookup"><span data-stu-id="d30d2-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="d30d2-113">Cada uma dessas tecnologias deve ter seu próprio monitoramento proativo.</span><span class="sxs-lookup"><span data-stu-id="d30d2-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="d30d2-114">Serviços de dependência típicos</span><span class="sxs-lookup"><span data-stu-id="d30d2-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d30d2-115">Serviço de dependência</span><span class="sxs-lookup"><span data-stu-id="d30d2-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-116">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="d30d2-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-117">Hardware do servidor</span><span class="sxs-lookup"><span data-stu-id="d30d2-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="d30d2-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-119">Infraestrutura de chave pública</span><span class="sxs-lookup"><span data-stu-id="d30d2-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-120">Serviço de nomes de domínio</span><span class="sxs-lookup"><span data-stu-id="d30d2-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-121">Serviços de banco de dados</span><span class="sxs-lookup"><span data-stu-id="d30d2-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-122">Serviços de armazenamento</span><span class="sxs-lookup"><span data-stu-id="d30d2-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-123">Gerenciamento do sistema – monitoramento e distribuição</span><span class="sxs-lookup"><span data-stu-id="d30d2-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-124">Serviços de segurança-antivírus</span><span class="sxs-lookup"><span data-stu-id="d30d2-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-125">Infraestrutura de rede-Internet</span><span class="sxs-lookup"><span data-stu-id="d30d2-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-126">Infraestrutura de rede – interna (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="d30d2-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-127">Infraestrutura de telefonia – IP-PBX e gateways</span><span class="sxs-lookup"><span data-stu-id="d30d2-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-128">Serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="d30d2-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d30d2-129">Presume-se que a organização seja operacionalmente desenvolvida em exercer funções básicas de gerenciamento de nível de serviço, como alteração, incidentes e gerenciamento de versão, conforme prescrito pelo MOF.</span><span class="sxs-lookup"><span data-stu-id="d30d2-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="d30d2-130">A solução Lync deve ser adotada por essas funções e se tornar sujeita aos mesmos processos de gerenciamento operacional.</span><span class="sxs-lookup"><span data-stu-id="d30d2-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="d30d2-131">A criação das informações obtidas acima agora tem uma compreensão maior sobre o que pode impactar o serviço Lync na empresa.</span><span class="sxs-lookup"><span data-stu-id="d30d2-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="d30d2-132">Para ajudar a garantir a disponibilidade e a qualidade do serviço do Lync Server 2013, as seguintes ferramentas de monitoramento devem acompanhar a implantação da arquitetura de referência:</span><span class="sxs-lookup"><span data-stu-id="d30d2-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="d30d2-133">Ferramentas de monitoramento</span><span class="sxs-lookup"><span data-stu-id="d30d2-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d30d2-134">Componente</span><span class="sxs-lookup"><span data-stu-id="d30d2-134">Component</span></span></th>
<th><span data-ttu-id="d30d2-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="d30d2-135">Description</span></span></th>
<th><span data-ttu-id="d30d2-136">Site aplicável</span><span class="sxs-lookup"><span data-stu-id="d30d2-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-137">Lync Server 2013 Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="d30d2-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="d30d2-138">Implante pelo menos uma função de servidor de monitoramento do Lync Server 2013 por site central e configure o pacote de relatórios de QoE (qualidade da experiência).</span><span class="sxs-lookup"><span data-stu-id="d30d2-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="d30d2-139">Consulte a documentação de implantação do Lync Server 2013 para obter mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="d30d2-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="d30d2-140"><a href="lync-server-2013-deploying-monitoring.md">Implantando o monitoramento no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d30d2-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d30d2-141">Sites centrais</span><span class="sxs-lookup"><span data-stu-id="d30d2-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d30d2-142">Compartilhamento de Internet de cada pool para sua instância mais próxima da função de servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d30d2-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-143">Sites centrais</span><span class="sxs-lookup"><span data-stu-id="d30d2-143">Central sites</span></span></p>
<p><span data-ttu-id="d30d2-144">Sites de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="d30d2-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="d30d2-146">System Center Operations Manager 2012 com o pacote de gerenciamento do Microsoft Lync Server 2013 (MP) importado.</span><span class="sxs-lookup"><span data-stu-id="d30d2-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="d30d2-147">O pacote de gerenciamento implementa o log de eventos tradicional e a instrumentação baseada em contador de desempenho é utilizada, além de habilitar a instrumentação recentemente disponível no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d30d2-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-148">Sites centrais</span><span class="sxs-lookup"><span data-stu-id="d30d2-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d30d2-149">Certifique-se de que a descoberta central para a descoberta de funções e componentes que precisam ser monitoradas seja automaticamente concluída com base em um script de descoberta central que lê o documento de topologia publicado no banco de dados de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="d30d2-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-150">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-150">Central Site</span></span></p>
<p><span data-ttu-id="d30d2-151">Site de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-151">Branch Site</span></span></p>
<p><span data-ttu-id="d30d2-152">Site de borda</span><span class="sxs-lookup"><span data-stu-id="d30d2-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d30d2-153">Implantar agentes do System Centre Operations Manager 2007 em todos os servidores implantados que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d30d2-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-154">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-154">Central Site</span></span></p>
<p><span data-ttu-id="d30d2-155">Site de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-155">Branch Site</span></span></p>
<p><span data-ttu-id="d30d2-156">Site de borda</span><span class="sxs-lookup"><span data-stu-id="d30d2-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d30d2-157">Certifique-se de que os alertas priorizados estão configurados para notificação:</span><span class="sxs-lookup"><span data-stu-id="d30d2-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="d30d2-158">Alertas de alta prioridade</span><span class="sxs-lookup"><span data-stu-id="d30d2-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="d30d2-159">Alertas de prioridade média</span><span class="sxs-lookup"><span data-stu-id="d30d2-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="d30d2-160">Outros alertas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-161">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-161">Central Site</span></span></p>
<p><span data-ttu-id="d30d2-162">Site de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-162">Branch Site</span></span></p>
<p><span data-ttu-id="d30d2-163">Site de borda</span><span class="sxs-lookup"><span data-stu-id="d30d2-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d30d2-164">Configure o monitoramento de porta para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d30d2-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-165">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-165">Central Site</span></span></p>
<p><span data-ttu-id="d30d2-166">Site de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-166">Branch Site</span></span></p>
<p><span data-ttu-id="d30d2-167">Site de borda</span><span class="sxs-lookup"><span data-stu-id="d30d2-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d30d2-168">Configurar o monitoramento de URL para sua implantação</span><span class="sxs-lookup"><span data-stu-id="d30d2-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="d30d2-169">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-170">Integração do Lync e do System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d30d2-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="d30d2-171">Implantar a confiabilidade das chamadas e a qualidade da mídia MonitoringCall confiabilidade e monitoramento de qualidade de mídia use o computador do Monitoring Server como o nó do inspetor para monitorar a confiabilidade da chamada e a qualidade de mídia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d30d2-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="d30d2-172">Esses dois recursos consultam os bancos de dados do Monitoring Server para fazer a análise.</span><span class="sxs-lookup"><span data-stu-id="d30d2-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-173">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-173">Central Site</span></span></p>
<p><span data-ttu-id="d30d2-174">Site de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d30d2-175">Garantir que os limites de aviso de qualidade de mídia estejam configurados com precisão.</span><span class="sxs-lookup"><span data-stu-id="d30d2-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="d30d2-176">A tabela a seguir indica a pontuação máxima média de opinião da rede por codec.</span><span class="sxs-lookup"><span data-stu-id="d30d2-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="d30d2-177">Em produção, essas pontuações devem ser monitoradas por um período definido e os limites aceitáveis devem ser estabelecidos com base nas pontuações específicas da organização NMOS.</span><span class="sxs-lookup"><span data-stu-id="d30d2-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-178">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-178">Central Site</span></span></p>
<p><span data-ttu-id="d30d2-179">Site de filial</span><span class="sxs-lookup"><span data-stu-id="d30d2-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-180">Inspetor de transações sintéticas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d30d2-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="d30d2-181">Implantar um Lync Server dedicado para ser um inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="d30d2-182">As transações sintéticas são cmdlets do Windows PowerShell do Lync Server 2013 que são automaticamente disparados pelo pacote de gerenciamento em um intervalo predefinido.</span><span class="sxs-lookup"><span data-stu-id="d30d2-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="d30d2-183">Eles são executados em um nó de Inspetor de transação sintética que é um servidor designado pelo administrador responsável pela descoberta e execução de STs para cada pool.</span><span class="sxs-lookup"><span data-stu-id="d30d2-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="d30d2-184">Não recomendamos o uso de um servidor do Microsoft Lync Server 2013 existente como um nó do Inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="d30d2-185">Isso se deve aos altos requisitos de uso de CPU/memória para executar o STs.</span><span class="sxs-lookup"><span data-stu-id="d30d2-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="d30d2-186">Use um novo computador servidor (ou um servidor virtual) para o nó do Inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-187">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d30d2-188">Implantando o nó Inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="d30d2-189">Consulte o documento de MonitoringCS_withSCOM.docx da documentação do UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="d30d2-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="d30d2-190">Site central</span><span class="sxs-lookup"><span data-stu-id="d30d2-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="d30d2-191">Pontuação máxima de MOS de rede por codec</span><span class="sxs-lookup"><span data-stu-id="d30d2-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d30d2-192">Cenário</span><span class="sxs-lookup"><span data-stu-id="d30d2-192">Scenario</span></span></th>
<th><span data-ttu-id="d30d2-193">Codec</span><span class="sxs-lookup"><span data-stu-id="d30d2-193">Codec</span></span></th>
<th><span data-ttu-id="d30d2-194">NMOS máximo</span><span class="sxs-lookup"><span data-stu-id="d30d2-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-195">UC-chamada UC</span><span class="sxs-lookup"><span data-stu-id="d30d2-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="d30d2-196">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="d30d2-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="d30d2-197">4.10</span><span class="sxs-lookup"><span data-stu-id="d30d2-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-198">UC-chamada UC</span><span class="sxs-lookup"><span data-stu-id="d30d2-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="d30d2-199">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="d30d2-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="d30d2-200">2,95</span><span class="sxs-lookup"><span data-stu-id="d30d2-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-201">Chamada de conferência</span><span class="sxs-lookup"><span data-stu-id="d30d2-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="d30d2-202">Siren</span><span class="sxs-lookup"><span data-stu-id="d30d2-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="d30d2-203">3,72</span><span class="sxs-lookup"><span data-stu-id="d30d2-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d30d2-204">UC-chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="d30d2-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="d30d2-205">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="d30d2-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="d30d2-206">2,95</span><span class="sxs-lookup"><span data-stu-id="d30d2-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d30d2-207">UC-chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="d30d2-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="d30d2-208">G-711</span><span class="sxs-lookup"><span data-stu-id="d30d2-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="d30d2-209">3,61</span><span class="sxs-lookup"><span data-stu-id="d30d2-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d30d2-210">Acima e acima das atividades anteriores de monitoramento do Pro-active, as tarefas de manutenção devem ser executadas para sites centrais, de borda e de filial, de forma diária, semanal e mensal, conforme definido no guia de operações do Lync RA.</span><span class="sxs-lookup"><span data-stu-id="d30d2-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

