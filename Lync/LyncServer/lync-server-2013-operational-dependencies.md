---
title: 'Lync Server 2013: dependências operacionais'
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
ms.openlocfilehash: d2403fde7387c1ef5af7d402ad9bc859aa95fe6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="64f92-102">Dependências operacionais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f92-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64f92-103">_**Última modificação do tópico:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="64f92-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="64f92-104">A arquitetura de referência discutida neste documento ajudará a garantir que você tenha uma implantação do Lync Server 2013 que não só seja dimensionada para os requisitos da organização, mas seja arquitetada de acordo com as práticas recomendadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64f92-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="64f92-105">Seja que, como pode ser a implementação do Lync Server 2013 é um serviço dinâmico e como qualquer outro serviço na empresa ainda requer o monitoramento e o gerenciamento proativo para manter alto nível de disponibilidade de serviço e qualidade de serviço para a empresa.</span><span class="sxs-lookup"><span data-stu-id="64f92-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="64f92-106">À medida que o Lync Server 2013 se torna muito ingerido na empresa diária da organização, é importante que o serviço seja gerenciado pelo gerenciamento de nível de serviço preciso e tangível.</span><span class="sxs-lookup"><span data-stu-id="64f92-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="64f92-107">A arquitetura do sistema do Lync pode se tornar complexa e muito integrada e, para manter o gerenciamento de nível de serviço efetivo e estabelecer SLAs para o Lync Server 2013, torna-se essencial entender as dependências do sistema em outras plataformas e servidores.</span><span class="sxs-lookup"><span data-stu-id="64f92-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="64f92-108">Igualmente importante é observar quais serviços comerciais, como os aplicativos integrados de voz e UC, são dependentes do Lync.</span><span class="sxs-lookup"><span data-stu-id="64f92-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="64f92-109">O Lync Server 2013 deve ser estabelecido observando todas as dependências mencionadas.</span><span class="sxs-lookup"><span data-stu-id="64f92-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="64f92-110">O mapa de serviços permitirá que você formule um SLA entre o Lync e seu serviço dependente e forneça um local inicial para negociação de SLA.</span><span class="sxs-lookup"><span data-stu-id="64f92-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="64f92-111">A tabela a seguir lista os serviços de dependência típicos para uma infraestrutura do Lync.</span><span class="sxs-lookup"><span data-stu-id="64f92-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="64f92-112">Cada uma dessas tecnologias deve ter seu próprio monitoramento proativo.</span><span class="sxs-lookup"><span data-stu-id="64f92-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="64f92-113">Serviços de dependência típicos</span><span class="sxs-lookup"><span data-stu-id="64f92-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f92-114">Serviço de dependência</span><span class="sxs-lookup"><span data-stu-id="64f92-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f92-115">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="64f92-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-116">Hardware do servidor</span><span class="sxs-lookup"><span data-stu-id="64f92-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="64f92-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-118">Infraestrutura de chave pública</span><span class="sxs-lookup"><span data-stu-id="64f92-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-119">Serviço de nomes de domínio</span><span class="sxs-lookup"><span data-stu-id="64f92-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-120">Serviços de banco de dados</span><span class="sxs-lookup"><span data-stu-id="64f92-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-121">Serviços de armazenamento</span><span class="sxs-lookup"><span data-stu-id="64f92-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-122">Gerenciamento do sistema – monitoramento e distribuição</span><span class="sxs-lookup"><span data-stu-id="64f92-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-123">Serviços de segurança-antivírus</span><span class="sxs-lookup"><span data-stu-id="64f92-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-124">Infraestrutura de rede-Internet</span><span class="sxs-lookup"><span data-stu-id="64f92-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-125">Infraestrutura de rede – interna (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="64f92-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-126">Infraestrutura de telefonia – IP-PBX e gateways</span><span class="sxs-lookup"><span data-stu-id="64f92-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-127">Serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="64f92-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="64f92-128">Presume-se que a organização seja operacionalmente desenvolvida em exercer funções básicas de gerenciamento de nível de serviço, como alteração, incidentes e gerenciamento de versão, conforme prescrito pelo MOF.</span><span class="sxs-lookup"><span data-stu-id="64f92-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="64f92-129">A solução Lync deve ser adotada por essas funções e se tornar sujeita aos mesmos processos de gerenciamento operacional.</span><span class="sxs-lookup"><span data-stu-id="64f92-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="64f92-130">A criação das informações obtidas acima agora tem uma compreensão maior sobre o que pode impactar o serviço Lync na empresa.</span><span class="sxs-lookup"><span data-stu-id="64f92-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="64f92-131">Para ajudar a garantir a disponibilidade e a qualidade do serviço do Lync Server 2013, as seguintes ferramentas de monitoramento devem acompanhar a implantação da arquitetura de referência:</span><span class="sxs-lookup"><span data-stu-id="64f92-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="64f92-132">Ferramentas de monitoramento</span><span class="sxs-lookup"><span data-stu-id="64f92-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f92-133">Componente</span><span class="sxs-lookup"><span data-stu-id="64f92-133">Component</span></span></th>
<th><span data-ttu-id="64f92-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="64f92-134">Description</span></span></th>
<th><span data-ttu-id="64f92-135">Site aplicável</span><span class="sxs-lookup"><span data-stu-id="64f92-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f92-136">Lync Server 2013 Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="64f92-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="64f92-137">Implante pelo menos uma função de servidor de monitoramento do Lync Server 2013 por site central e configure o pacote de relatórios de QoE (qualidade da experiência).</span><span class="sxs-lookup"><span data-stu-id="64f92-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="64f92-138">Consulte a documentação de implantação do Lync Server 2013 para obter mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="64f92-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="64f92-139"><a href="lync-server-2013-deploying-monitoring.md">Implantando o monitoramento no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="64f92-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="64f92-140">Sites centrais</span><span class="sxs-lookup"><span data-stu-id="64f92-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="64f92-141">Compartilhamento de Internet de cada pool para sua instância mais próxima da função de servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="64f92-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="64f92-142">Sites centrais</span><span class="sxs-lookup"><span data-stu-id="64f92-142">Central sites</span></span></p>
<p><span data-ttu-id="64f92-143">Sites de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="64f92-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="64f92-145">System Center Operations Manager 2012 com o pacote de gerenciamento do Microsoft Lync Server 2013 (MP) importado.</span><span class="sxs-lookup"><span data-stu-id="64f92-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="64f92-146">O pacote de gerenciamento implementa o log de eventos tradicional e a instrumentação baseada em contador de desempenho é utilizada, além de habilitar a instrumentação recentemente disponível no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64f92-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="64f92-147">Sites centrais</span><span class="sxs-lookup"><span data-stu-id="64f92-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="64f92-148">Certifique-se de que a descoberta central para a descoberta de funções e componentes que precisam ser monitoradas seja automaticamente concluída com base em um script de descoberta central que lê o documento de topologia publicado no banco de dados de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="64f92-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="64f92-149">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-149">Central Site</span></span></p>
<p><span data-ttu-id="64f92-150">Site de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-150">Branch Site</span></span></p>
<p><span data-ttu-id="64f92-151">Site de borda</span><span class="sxs-lookup"><span data-stu-id="64f92-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="64f92-152">Implantar agentes do System Centre Operations Manager 2007 em todos os servidores implantados que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64f92-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="64f92-153">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-153">Central Site</span></span></p>
<p><span data-ttu-id="64f92-154">Site de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-154">Branch Site</span></span></p>
<p><span data-ttu-id="64f92-155">Site de borda</span><span class="sxs-lookup"><span data-stu-id="64f92-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="64f92-156">Certifique-se de que os alertas priorizados estão configurados para notificação:</span><span class="sxs-lookup"><span data-stu-id="64f92-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="64f92-157">Alertas de alta prioridade</span><span class="sxs-lookup"><span data-stu-id="64f92-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="64f92-158">Alertas de prioridade média</span><span class="sxs-lookup"><span data-stu-id="64f92-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="64f92-159">Outros alertas.</span><span class="sxs-lookup"><span data-stu-id="64f92-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="64f92-160">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-160">Central Site</span></span></p>
<p><span data-ttu-id="64f92-161">Site de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-161">Branch Site</span></span></p>
<p><span data-ttu-id="64f92-162">Site de borda</span><span class="sxs-lookup"><span data-stu-id="64f92-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="64f92-163">Configure o monitoramento de porta para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="64f92-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="64f92-164">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-164">Central Site</span></span></p>
<p><span data-ttu-id="64f92-165">Site de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-165">Branch Site</span></span></p>
<p><span data-ttu-id="64f92-166">Site de borda</span><span class="sxs-lookup"><span data-stu-id="64f92-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="64f92-167">Configurar o monitoramento de URL para sua implantação</span><span class="sxs-lookup"><span data-stu-id="64f92-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="64f92-168">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-169">Integração do Lync e do System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="64f92-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="64f92-170">Implantar a confiabilidade das chamadas e a qualidade da mídia MonitoringCall confiabilidade e monitoramento de qualidade de mídia use o computador do Monitoring Server como o nó do inspetor para monitorar a confiabilidade da chamada e a qualidade de mídia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64f92-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="64f92-171">Esses dois recursos consultam os bancos de dados do Monitoring Server para fazer a análise.</span><span class="sxs-lookup"><span data-stu-id="64f92-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="64f92-172">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-172">Central Site</span></span></p>
<p><span data-ttu-id="64f92-173">Site de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="64f92-174">Garantir que os limites de aviso de qualidade de mídia estejam configurados com precisão.</span><span class="sxs-lookup"><span data-stu-id="64f92-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="64f92-175">A tabela a seguir indica a pontuação máxima média de opinião da rede por codec.</span><span class="sxs-lookup"><span data-stu-id="64f92-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="64f92-176">Em produção, essas pontuações devem ser monitoradas por um período definido e os limites aceitáveis devem ser estabelecidos com base nas pontuações específicas da organização NMOS.</span><span class="sxs-lookup"><span data-stu-id="64f92-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="64f92-177">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-177">Central Site</span></span></p>
<p><span data-ttu-id="64f92-178">Site de filial</span><span class="sxs-lookup"><span data-stu-id="64f92-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-179">Inspetor de transações sintéticas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f92-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="64f92-180">Implantar um Lync Server dedicado para ser um inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="64f92-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="64f92-181">As transações sintéticas são cmdlets do Windows PowerShell do Lync Server 2013 que são automaticamente disparados pelo pacote de gerenciamento em um intervalo predefinido.</span><span class="sxs-lookup"><span data-stu-id="64f92-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="64f92-182">Eles são executados em um nó de Inspetor de transação sintética que é um servidor designado pelo administrador responsável pela descoberta e execução de STs para cada pool.</span><span class="sxs-lookup"><span data-stu-id="64f92-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="64f92-183">Não recomendamos o uso de um servidor do Microsoft Lync Server 2013 existente como um nó do Inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="64f92-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="64f92-184">Isso se deve aos altos requisitos de uso de CPU/memória para executar o STs.</span><span class="sxs-lookup"><span data-stu-id="64f92-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="64f92-185">Use um novo computador servidor (ou um servidor virtual) para o nó do Inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="64f92-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="64f92-186">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="64f92-187">Implantando o nó Inspetor de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="64f92-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="64f92-188">Consulte o documento MonitoringCS_withSCOM. docx na documentação do UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="64f92-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="64f92-189">Site central</span><span class="sxs-lookup"><span data-stu-id="64f92-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="64f92-190">Pontuação máxima de MOS de rede por codec</span><span class="sxs-lookup"><span data-stu-id="64f92-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f92-191">Cenário</span><span class="sxs-lookup"><span data-stu-id="64f92-191">Scenario</span></span></th>
<th><span data-ttu-id="64f92-192">Codec</span><span class="sxs-lookup"><span data-stu-id="64f92-192">Codec</span></span></th>
<th><span data-ttu-id="64f92-193">NMOS máximo</span><span class="sxs-lookup"><span data-stu-id="64f92-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f92-194">UC-chamada UC</span><span class="sxs-lookup"><span data-stu-id="64f92-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="64f92-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="64f92-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="64f92-196">4.10</span><span class="sxs-lookup"><span data-stu-id="64f92-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-197">UC-chamada UC</span><span class="sxs-lookup"><span data-stu-id="64f92-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="64f92-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="64f92-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="64f92-199">2,95</span><span class="sxs-lookup"><span data-stu-id="64f92-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-200">Chamada de conferência</span><span class="sxs-lookup"><span data-stu-id="64f92-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="64f92-201">Siren</span><span class="sxs-lookup"><span data-stu-id="64f92-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="64f92-202">3,72</span><span class="sxs-lookup"><span data-stu-id="64f92-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f92-203">UC-chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="64f92-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="64f92-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="64f92-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="64f92-205">2,95</span><span class="sxs-lookup"><span data-stu-id="64f92-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f92-206">UC-chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="64f92-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="64f92-207">G-711</span><span class="sxs-lookup"><span data-stu-id="64f92-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="64f92-208">3,61</span><span class="sxs-lookup"><span data-stu-id="64f92-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="64f92-209">Acima e acima das atividades anteriores de monitoramento do Pro-active, as tarefas de manutenção devem ser executadas para sites centrais, de borda e de filial, de forma diária, semanal e mensal, conforme definido no guia de operações do Lync RA.</span><span class="sxs-lookup"><span data-stu-id="64f92-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

