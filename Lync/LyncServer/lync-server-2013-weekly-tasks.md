---
title: 'Lync Server 2013: tarefas semanais'
description: 'Lync Server 2013: tarefas semanais.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d818e1140141a470bb57a1471bb04931f505a6bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546137"
---
# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="3907b-103">Tarefas semanais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3907b-103">Weekly tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3907b-104">_**Última modificação do tópico:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="3907b-104">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="3907b-105">Tarefas semanais geralmente estão relacionadas à coleta e análise de logs e relatórios.</span><span class="sxs-lookup"><span data-stu-id="3907b-105">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="3907b-106">Arquivar logs de eventos</span><span class="sxs-lookup"><span data-stu-id="3907b-106">Archive event logs</span></span>

<span data-ttu-id="3907b-107">Se os logs de eventos não estiverem configurados para substituir eventos conforme necessário, eles devem ser arquivados e excluídos regularmente.</span><span class="sxs-lookup"><span data-stu-id="3907b-107">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="3907b-108">Esta ação é especialmente importante para logs de segurança, que podem ser necessários ao investigar tentativas de violação de segurança.</span><span class="sxs-lookup"><span data-stu-id="3907b-108">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="3907b-109">Sua organização terá que definir políticas e procedimentos para o arquivamento de logs.</span><span class="sxs-lookup"><span data-stu-id="3907b-109">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="3907b-110">Criar relatórios</span><span class="sxs-lookup"><span data-stu-id="3907b-110">Create reports</span></span>

<span data-ttu-id="3907b-111">Criar relatórios de status para ajudar no planejamento de capacidade, análises de SLA e análise de desempenho.</span><span class="sxs-lookup"><span data-stu-id="3907b-111">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="3907b-112">Use dados diários do log de eventos e do monitor do sistema para criar relatórios sobre o disco, memória e uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="3907b-112">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="3907b-113">Use o System Center Operations Manager para gerar relatórios de disponibilidade e tempo de atividade.</span><span class="sxs-lookup"><span data-stu-id="3907b-113">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="3907b-114">Sua organização terá que definir políticas e procedimentos para relatórios de status.</span><span class="sxs-lookup"><span data-stu-id="3907b-114">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="3907b-115">Relatórios de incidentes</span><span class="sxs-lookup"><span data-stu-id="3907b-115">Incident reports</span></span>

<span data-ttu-id="3907b-116">Realize uma auditoria semanal dos relatórios de incidentes da sua organização relacionados ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3907b-116">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="3907b-117">Essa auditoria deve incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3907b-117">This audit should include the following:</span></span>

  - <span data-ttu-id="3907b-118">Os incidentes gerados acima, resolvidos e pendentes.</span><span class="sxs-lookup"><span data-stu-id="3907b-118">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="3907b-119">Soluções para incidentes não resolvidos.</span><span class="sxs-lookup"><span data-stu-id="3907b-119">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="3907b-120">Atualizando relatórios para incluir novos tíquetes de problema.</span><span class="sxs-lookup"><span data-stu-id="3907b-120">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="3907b-121">Atualização de um repositório de documentos para guias de solução de problemas e postagem de panes sobre interrupções.</span><span class="sxs-lookup"><span data-stu-id="3907b-121">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="3907b-122">Como o sistema de controle de incidentes da sua organização é uma opção independente do Lync Server, instruções específicas ou ponteiros não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3907b-122">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="3907b-123">Consulte a documentação do sistema que sua organização escolheu.</span><span class="sxs-lookup"><span data-stu-id="3907b-123">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="3907b-124">Verificar os logs e o desempenho do IIS</span><span class="sxs-lookup"><span data-stu-id="3907b-124">Check IIS logs and performance</span></span>

<span data-ttu-id="3907b-125">Executar uma revisão semanal dos logs e desempenho dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="3907b-125">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="3907b-126">Para obter mais informações sobre como monitorar os logs e o desempenho do IIS, consulte [Windows Server 2003 serviços de informações da Internet (IIS) visão geral do log de eventos](https://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="3907b-126">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="3907b-127">A revisão deve incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3907b-127">The review should include the following:</span></span>

  - <span data-ttu-id="3907b-128">Contadores de cache de serviço Web para monitorar o cache de serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="3907b-128">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="3907b-129">Contadores ASPs (Active Server Pages) para monitorar aplicativos executados como ASPs.</span><span class="sxs-lookup"><span data-stu-id="3907b-129">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="3907b-130">Gerar relatórios de banco de dados</span><span class="sxs-lookup"><span data-stu-id="3907b-130">Generate database reports</span></span>

<span data-ttu-id="3907b-131">**Para gerar relatórios sobre o banco de dados SQL**</span><span class="sxs-lookup"><span data-stu-id="3907b-131">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="3907b-132">Abra o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3907b-132">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="3907b-133">Na árvore do console, expanda o nó floresta, expanda **pools corporativos**e clique no pool para o qual você deseja gerar um relatório de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3907b-133">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="3907b-134">No painel de detalhes, clique na guia **banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="3907b-134">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="3907b-135">Na guia **banco de dados** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3907b-135">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="3907b-136">Para exibir o nome do banco de dados, expanda **configurações gerais**e exiba o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3907b-136">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="3907b-137">Para recuperar as estatísticas de resumo do usuário atual do pool, expanda **relatórios de resumo do usuário**, clique em **ir**e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="3907b-137">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="3907b-138">Para recuperar os dados atuais por usuário para um único usuário do pool, expanda **relatórios por usuário**, digite o URI do SIP do usuário, clique em **ir**e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="3907b-138">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="3907b-139">Para recuperar as estatísticas atuais de Resumo de conferência para o pool, expanda **relatórios de Resumo de conferências**, clique em **ir**e exiba os resultados.</span><span class="sxs-lookup"><span data-stu-id="3907b-139">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="3907b-140">Verificar atualizações de segurança e Lync Server</span><span class="sxs-lookup"><span data-stu-id="3907b-140">Check for security and Lync Server updates</span></span>

<span data-ttu-id="3907b-141">Identificar quaisquer Service Packs, hotfixes ou atualizações novos.</span><span class="sxs-lookup"><span data-stu-id="3907b-141">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="3907b-142">Se apropriado, teste-os em um laboratório de teste e use os procedimentos de controle de alteração para organizar a implantação nos servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="3907b-142">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="3907b-143">Além disso, as atualizações de componentes do Lync Server agora estão disponíveis como parte do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="3907b-143">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="3907b-144">Todas as atualizações de componentes do Lync Server devem ser atualizadas ao mesmo tempo em todos os servidores que estão executando o Lync Server para o qual as atualizações são aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="3907b-144">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="3907b-145">Executar o analisador de práticas recomendadas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3907b-145">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="3907b-146">A ferramenta Analisador de práticas recomendadas do Lync Server 2013 é uma ferramenta de diagnóstico que coleta informações de configuração e determina se a configuração é definida de acordo com as práticas recomendadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3907b-146">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="3907b-147">A documentação da ferramenta é no [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="3907b-147">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="3907b-148">A ferramenta compara os dados de configuração da sua implantação com um conjunto de regras predefinidas para o Lync Server e relata possíveis problemas.</span><span class="sxs-lookup"><span data-stu-id="3907b-148">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="3907b-149">Para cada problema relatado, a ferramenta fornece a configuração atual no ambiente do Lync Server e a configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="3907b-149">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="3907b-150">Com o acesso à rede correto, a ferramenta pode examinar seu AD DS e servidores que estão executando o Lync Server 2013 para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3907b-150">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="3907b-151">Realize verificações de integridade de forma proativa, verificando se a configuração está definida de acordo com as práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="3907b-151">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="3907b-152">Gerar uma lista de problemas, como definições de configuração subótimas ou opções não suportadas ou não recomendadas</span><span class="sxs-lookup"><span data-stu-id="3907b-152">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="3907b-153">Avaliar a integridade geral de um sistema</span><span class="sxs-lookup"><span data-stu-id="3907b-153">Judge the general health of a system</span></span>

  - <span data-ttu-id="3907b-154">Ajudar a solucionar problemas específicos</span><span class="sxs-lookup"><span data-stu-id="3907b-154">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="3907b-155">Solicitar que você baixe as atualizações se elas estiverem disponíveis</span><span class="sxs-lookup"><span data-stu-id="3907b-155">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="3907b-156">Fornecer documentação online e local sobre problemas relatados e incluir dicas de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3907b-156">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="3907b-157">Gerar informações de configuração que possam ser capturadas para revisão posterior</span><span class="sxs-lookup"><span data-stu-id="3907b-157">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="3907b-158">Verifique se o RTCBPA.msi está instalado em todos os servidores do Lync Server 2013 e gere um relatório semanal de verificação de integridade.</span><span class="sxs-lookup"><span data-stu-id="3907b-158">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="3907b-159">Anote os resultados e corrija, se necessário.</span><span class="sxs-lookup"><span data-stu-id="3907b-159">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="3907b-160">Analisar os valores de desempenho do SLA</span><span class="sxs-lookup"><span data-stu-id="3907b-160">Review SLA performance figures</span></span>

<span data-ttu-id="3907b-161">Verifique os dados principais de desempenho da semana anterior.</span><span class="sxs-lookup"><span data-stu-id="3907b-161">Check the key performance data for the previous week.</span></span> <span data-ttu-id="3907b-162">Analise o desempenho em relação aos requisitos do SLA.</span><span class="sxs-lookup"><span data-stu-id="3907b-162">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="3907b-163">Identificar tendências e itens que não atingiram seus destinos.</span><span class="sxs-lookup"><span data-stu-id="3907b-163">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="3907b-164">Analisar o pacote de gerenciamento do System Center Operations Manager e os relatórios de qualidade da experiência</span><span class="sxs-lookup"><span data-stu-id="3907b-164">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="3907b-165">Obtenha e revise o pacote de gerenciamento do Lync Server 2013 e os relatórios de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="3907b-165">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="3907b-166">Geração e exibição de relatórios de banco de dados para pools corporativos</span><span class="sxs-lookup"><span data-stu-id="3907b-166">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="3907b-167">**Para gerar relatórios de pool**</span><span class="sxs-lookup"><span data-stu-id="3907b-167">**To generate pool reports**</span></span>

1.  <span data-ttu-id="3907b-168">Abra o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3907b-168">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="3907b-169">Na árvore do console, expanda o nó floresta, expanda **pools corporativos**e clique no pool para o qual você deseja gerar um relatório de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3907b-169">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="3907b-170">No painel de detalhes, clique na guia **banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="3907b-170">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="3907b-171">Na guia **banco de dados** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3907b-171">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="3907b-172">Para exibir o nome do banco de dados, expanda **configurações gerais**e exiba o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3907b-172">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="3907b-173">Para recuperar as estatísticas de resumo do usuário atual do pool, expanda **relatórios de resumo do usuário**, clique em **ir**e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="3907b-173">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="3907b-174">Para recuperar os dados atuais por usuário para um único usuário do pool, expanda **relatórios por usuário**, digite o URI do SIP do usuário, clique em **ir**e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="3907b-174">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="3907b-175">Para recuperar as estatísticas atuais de Resumo de conferência para o pool, expanda **relatórios de Resumo de conferências**, clique em **ir**e exiba os resultados.</span><span class="sxs-lookup"><span data-stu-id="3907b-175">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="3907b-176">Para cada pool de empresas, os administradores podem usar a guia **banco de dados** para exibir o nome do banco de dados e recuperar e exibir relatórios do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3907b-176">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="3907b-177">Relatórios e descrições de bancos de dados</span><span class="sxs-lookup"><span data-stu-id="3907b-177">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3907b-178">Seção</span><span class="sxs-lookup"><span data-stu-id="3907b-178">Section</span></span></th>
<th><span data-ttu-id="3907b-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="3907b-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3907b-180">Relatórios de resumo do usuário</span><span class="sxs-lookup"><span data-stu-id="3907b-180">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="3907b-181">Dbanalyze/v/Report: diag [/SqlServer: valor]</span><span class="sxs-lookup"><span data-stu-id="3907b-181">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3907b-182">Esta seção exibe informações de agregação sobre usuários em um pool, como o número de usuários habilitados, o número médio de contatos por usuário e o número de usuários para recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="3907b-182">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="3907b-183">Ao usar esses relatórios, as seguintes informações podem ser úteis:</span><span class="sxs-lookup"><span data-stu-id="3907b-183">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="3907b-184">Um usuário habilitado é um usuário habilitado para o Lync Server 2013 usando o snap-in usuários e computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3907b-184">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="3907b-185">Um usuário ativo é um usuário que fez logon ou está registrado.</span><span class="sxs-lookup"><span data-stu-id="3907b-185">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="3907b-186">Os relatórios de resumo também oferecem um conjunto de informações estatísticas sobre contatos.</span><span class="sxs-lookup"><span data-stu-id="3907b-186">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="3907b-187">Essas estatísticas são válidas apenas para a população de usuários que fizeram logon pelo menos uma vez e que têm pelo menos um contato.</span><span class="sxs-lookup"><span data-stu-id="3907b-187">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="3907b-188">Consequentemente, você normalmente não verá um número mínimo de contatos de 0.</span><span class="sxs-lookup"><span data-stu-id="3907b-188">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="3907b-189">Devido a esse comportamento, se um usuário não tiver contatos (mas estiver ativo, se o usuário tiver registrado), você poderá ver: &lt; vazio &gt; para alguns campos de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="3907b-189">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3907b-190">Relatórios de Per-User</span><span class="sxs-lookup"><span data-stu-id="3907b-190">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="3907b-191">Dbanalyze/v/Report: Disk [/SqlServer: value]</span><span class="sxs-lookup"><span data-stu-id="3907b-191">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3907b-192">Ao contrário dos relatórios de resumo, que são calculados sobre uma população de usuário, eles são relatórios sobre um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="3907b-192">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3907b-193">Relatórios de Resumo de conferências</span><span class="sxs-lookup"><span data-stu-id="3907b-193">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="3907b-194">Dbanalyze/v/Report: conf [/SqlServer: valor]</span><span class="sxs-lookup"><span data-stu-id="3907b-194">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3907b-195">Esta seção exibe informações de agregação sobre estatísticas de Resumo de conferência para o pool, como o número de conferências ativas e o número total de participantes.</span><span class="sxs-lookup"><span data-stu-id="3907b-195">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="3907b-196">Executando analisador de utilização de largura de banda</span><span class="sxs-lookup"><span data-stu-id="3907b-196">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3907b-197">O analisador de utilização de largura de banda é uma ferramenta que cria relatórios sobre vários modos de exibição de consumo de largura de banda pelos pontos de extremidade UC nos links WAN na rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="3907b-197">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="3907b-198">Esses relatórios podem ser usados para entender o padrão de consumo de largura de banda atual e para ajudar no planejamento da capacidade de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3907b-198">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="3907b-199">Ele também itera na capacidade de largura de banda atribuída a vários links.</span><span class="sxs-lookup"><span data-stu-id="3907b-199">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="3907b-200">Esta ferramenta faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3907b-200">This tool does the following:</span></span>

  - <span data-ttu-id="3907b-201">Gera relatórios específicos para o uso de áudio na rede</span><span class="sxs-lookup"><span data-stu-id="3907b-201">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="3907b-202">Ajuda no planejamento de capacidade mais eficaz e na iteração na capacidade de largura de banda atribuída a vários links</span><span class="sxs-lookup"><span data-stu-id="3907b-202">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3907b-203">O analisador de utilização de largura de banda pode gerar gráficos de capacidade de largura de banda e relatórios de uso.</span><span class="sxs-lookup"><span data-stu-id="3907b-203">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="3907b-204">Eles são:</span><span class="sxs-lookup"><span data-stu-id="3907b-204">They are as follows:</span></span>

  - <span data-ttu-id="3907b-205">Todos os links WAN na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="3907b-205">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="3907b-206">Filtrado por links WAN selecionados que foram escolhidos</span><span class="sxs-lookup"><span data-stu-id="3907b-206">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="3907b-207">Filtrado por links WAN que excederam a capacidade de link</span><span class="sxs-lookup"><span data-stu-id="3907b-207">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="3907b-208">Filtrado por links WAN que estavam usando a largura de banda provisionada</span><span class="sxs-lookup"><span data-stu-id="3907b-208">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="3907b-209">Filtrar por links WAN que atingiram níveis críticos (um uso de largura de banda maior que 90 por cento da capacidade de largura de banda do link WAN)</span><span class="sxs-lookup"><span data-stu-id="3907b-209">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="3907b-210">Filtrado por tipo de link WAN — links de site de rede, links entre regiões e links dentro de um site</span><span class="sxs-lookup"><span data-stu-id="3907b-210">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="3907b-211">Filtrado por região de rede</span><span class="sxs-lookup"><span data-stu-id="3907b-211">Filtered by network region</span></span>

<span data-ttu-id="3907b-212">A documentação da ferramenta está disponível na [documentação das ferramentas do Lync Server 2013 Resource Kit](https://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="3907b-212">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3907b-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="3907b-213">See Also</span></span>


[<span data-ttu-id="3907b-214">Lista de verificação de tarefas semanais</span><span class="sxs-lookup"><span data-stu-id="3907b-214">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

