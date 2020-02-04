---
title: 'Lync Server 2013: Tarefas semanais'
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
ms.openlocfilehash: b973d5d69e6e4609a1dff3029b0ad0b05ec3a936
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="fb582-102">Tarefas semanais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb582-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb582-103">_**Tópico da última modificação:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="fb582-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="fb582-104">As tarefas semanais geralmente estão relacionadas à coleta e análise de logs e relatórios.</span><span class="sxs-lookup"><span data-stu-id="fb582-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="fb582-105">Arquivar logs de eventos</span><span class="sxs-lookup"><span data-stu-id="fb582-105">Archive event logs</span></span>

<span data-ttu-id="fb582-106">Se os logs de eventos não estiverem configurados para substituir eventos conforme necessário, eles deverão ser arquivados e excluídos regularmente.</span><span class="sxs-lookup"><span data-stu-id="fb582-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="fb582-107">Essa ação é especialmente importante para logs de segurança, que podem ser necessários quando a investigação tentava violações de segurança.</span><span class="sxs-lookup"><span data-stu-id="fb582-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="fb582-108">Sua organização precisará definir políticas e procedimentos para o arquivamento de logs.</span><span class="sxs-lookup"><span data-stu-id="fb582-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="fb582-109">Criar relatórios</span><span class="sxs-lookup"><span data-stu-id="fb582-109">Create reports</span></span>

<span data-ttu-id="fb582-110">Crie relatórios de status para ajudar com o planejamento da capacidade, análises de SLA e análise de desempenho.</span><span class="sxs-lookup"><span data-stu-id="fb582-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="fb582-111">Use dados diários do log de eventos e do monitor do sistema para criar relatórios sobre o disco, a memória e o uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="fb582-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="fb582-112">Use o System Center Operations Manager para gerar relatórios de tempo de atividade e disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fb582-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="fb582-113">Sua organização precisará definir políticas e procedimentos para relatórios de status.</span><span class="sxs-lookup"><span data-stu-id="fb582-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="fb582-114">Relatórios de incidentes</span><span class="sxs-lookup"><span data-stu-id="fb582-114">Incident reports</span></span>

<span data-ttu-id="fb582-115">Realize uma auditoria semanal dos relatórios de incidentes da sua organização relacionados ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb582-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="fb582-116">Essa auditoria deve incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb582-116">This audit should include the following:</span></span>

  - <span data-ttu-id="fb582-117">Os incidentes de alta geração, resolvidos e pendentes.</span><span class="sxs-lookup"><span data-stu-id="fb582-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="fb582-118">Soluções para incidentes não resolvidos.</span><span class="sxs-lookup"><span data-stu-id="fb582-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="fb582-119">Atualizando relatórios para incluir novos tickets de problemas.</span><span class="sxs-lookup"><span data-stu-id="fb582-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="fb582-120">Atualizar um repositório de documentos para obter guias de solução de problemas e postar mortes sobre interrupções.</span><span class="sxs-lookup"><span data-stu-id="fb582-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="fb582-121">Como o sistema de rastreamento de incidentes da sua organização é uma opção independente do Lync Server, instruções específicas ou ponteiros não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fb582-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="fb582-122">Consulte a documentação do sistema que sua organização escolheu.</span><span class="sxs-lookup"><span data-stu-id="fb582-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="fb582-123">Verificar os logs e o desempenho do IIS</span><span class="sxs-lookup"><span data-stu-id="fb582-123">Check IIS logs and performance</span></span>

<span data-ttu-id="fb582-124">Realize uma revisão semanal dos logs e do desempenho dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="fb582-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="fb582-125">Para obter mais informações sobre como monitorar os logs e o desempenho do IIS, consulte [visão geral do log de eventos dos serviços de informações da Internet (IIS) do Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="fb582-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="fb582-126">A revisão deve incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb582-126">The review should include the following:</span></span>

  - <span data-ttu-id="fb582-127">Contadores de cache do serviço Web para monitorar o cache do serviço WWW.</span><span class="sxs-lookup"><span data-stu-id="fb582-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="fb582-128">Contadores ASPs (Active Server Pages) para monitorar aplicativos que são executados como ASPs.</span><span class="sxs-lookup"><span data-stu-id="fb582-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="fb582-129">Gerar relatórios de banco de dados</span><span class="sxs-lookup"><span data-stu-id="fb582-129">Generate database reports</span></span>

<span data-ttu-id="fb582-130">**Para gerar relatórios no banco de dados SQL**</span><span class="sxs-lookup"><span data-stu-id="fb582-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="fb582-131">Abra o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb582-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="fb582-132">Na árvore do console, expanda o nó da floresta, expanda **pools corporativos**e clique no pool para o qual você deseja gerar um relatório de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb582-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="fb582-133">No painel detalhes, clique na guia **banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="fb582-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="fb582-134">Na guia **banco de dados** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb582-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="fb582-135">Para exibir o nome do banco de dados, expanda **configurações gerais**e exiba o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb582-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="fb582-136">Para recuperar as estatísticas de resumo do usuário atual do pool, expanda **relatórios de resumo do usuário**, clique em **ir**e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="fb582-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="fb582-137">Para recuperar os dados atuais por usuário para um único usuário do pool, expanda **relatórios por usuário**, digite o URI SIP do usuário, clique em **ir**e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="fb582-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="fb582-138">Para recuperar as estatísticas de Resumo de conferência atuais do pool, expanda **relatórios de resumo da conferência**, clique em **ir**e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="fb582-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="fb582-139">Verificar se há atualizações de segurança e do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fb582-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="fb582-140">Identifique qualquer novo Service Pack, hotfixes ou atualizações.</span><span class="sxs-lookup"><span data-stu-id="fb582-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="fb582-141">Se for apropriado, teste isso em um laboratório de teste e use os procedimentos de controle de alteração para organizar a implantação nos servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="fb582-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="fb582-142">Além disso, as atualizações de componentes do Lync Server agora estão disponíveis como parte do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="fb582-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="fb582-143">Todas as atualizações de componentes do Lync Server devem ser atualizadas ao mesmo tempo em todos os servidores que estão executando o Lync Server para os quais as atualizações são aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="fb582-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="fb582-144">Executar o analisador de práticas recomendadas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb582-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="fb582-145">A ferramenta do analisador de práticas recomendadas do Lync Server 2013 é uma ferramenta de diagnóstico que coleta informações de configuração e determina se a configuração é definida de acordo com as práticas recomendadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb582-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="fb582-146">A documentação para essa ferramenta se encontra no [analisador de práticas recomendadas do Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="fb582-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="fb582-147">A ferramenta compara os dados de configuração da sua implantação com um conjunto de regras predefinidas para o Lync Server e relata possíveis problemas.</span><span class="sxs-lookup"><span data-stu-id="fb582-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="fb582-148">Para cada problema relatado, a ferramenta fornece a configuração atual no ambiente do Lync Server e a configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="fb582-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="fb582-149">Com o acesso à rede correto, a ferramenta pode examinar o AD DS e os servidores que executam o Lync Server 2013 para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb582-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="fb582-150">Realize verificações de integridade de forma proativa, verificando se a configuração está definida de acordo com as práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="fb582-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="fb582-151">Gerar uma lista de problemas, como configurações de configuração otimizadas ou opções não aceitas ou não recomendadas</span><span class="sxs-lookup"><span data-stu-id="fb582-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="fb582-152">Julgar a integridade geral de um sistema</span><span class="sxs-lookup"><span data-stu-id="fb582-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="fb582-153">Ajudar a solucionar problemas específicos</span><span class="sxs-lookup"><span data-stu-id="fb582-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="fb582-154">Solicitar o download de atualizações se elas estiverem disponíveis</span><span class="sxs-lookup"><span data-stu-id="fb582-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="fb582-155">Fornecer documentação online e local sobre problemas relatados e incluir dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="fb582-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="fb582-156">Gerar informações de configuração que podem ser capturadas para revisão posterior</span><span class="sxs-lookup"><span data-stu-id="fb582-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="fb582-157">Verifique se o RTCBPA. msi está instalado em todos os servidores do Lync Server 2013 e gere um relatório semanal de verificação de integridade.</span><span class="sxs-lookup"><span data-stu-id="fb582-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="fb582-158">Observe os resultados e corrija, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fb582-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="fb582-159">Analisar os valores de desempenho do SLA</span><span class="sxs-lookup"><span data-stu-id="fb582-159">Review SLA performance figures</span></span>

<span data-ttu-id="fb582-160">Verifique os dados de desempenho principais da semana anterior.</span><span class="sxs-lookup"><span data-stu-id="fb582-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="fb582-161">Revisar o desempenho com base nos requisitos do SLA.</span><span class="sxs-lookup"><span data-stu-id="fb582-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="fb582-162">Identifique tendências e itens que não atingiram seus alvos.</span><span class="sxs-lookup"><span data-stu-id="fb582-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="fb582-163">Examinar os relatórios do pacote de gerenciamento do System Center Operations Manager e do Quality of Experience</span><span class="sxs-lookup"><span data-stu-id="fb582-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="fb582-164">Obtenha e revise os relatórios do pacote de gerenciamento do Lync Server 2013 e qualidade de experiência.</span><span class="sxs-lookup"><span data-stu-id="fb582-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="fb582-165">Gerando e exibindo relatórios do banco de dados para pools corporativos</span><span class="sxs-lookup"><span data-stu-id="fb582-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="fb582-166">**Para gerar relatórios de pool**</span><span class="sxs-lookup"><span data-stu-id="fb582-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="fb582-167">Abra o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb582-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="fb582-168">Na árvore do console, expanda o nó da floresta, expanda **pools corporativos**e clique no pool para o qual você deseja gerar um relatório de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb582-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="fb582-169">No painel detalhes, clique na guia **banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="fb582-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="fb582-170">Na guia **banco de dados** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb582-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="fb582-171">Para exibir o nome do banco de dados, expanda **configurações gerais**e exiba o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb582-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="fb582-172">Para recuperar as estatísticas de resumo do usuário atual do pool, expanda **relatórios de resumo do usuário**, clique em **ir**e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="fb582-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="fb582-173">Para recuperar os dados atuais por usuário para um único usuário do pool, expanda **relatórios por usuário**, digite o URI SIP do usuário, clique em **ir**e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="fb582-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="fb582-174">Para recuperar as estatísticas de Resumo de conferência atuais do pool, expanda **relatórios de resumo da conferência**, clique em **ir**e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="fb582-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="fb582-175">Para cada pool de empresas, os administradores podem usar a guia **banco de dados** para exibir o nome do banco de dados e recuperar e exibir relatórios do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb582-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="fb582-176">Relatórios e descrições de banco de dados</span><span class="sxs-lookup"><span data-stu-id="fb582-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb582-177">Seção</span><span class="sxs-lookup"><span data-stu-id="fb582-177">Section</span></span></th>
<th><span data-ttu-id="fb582-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="fb582-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb582-179">Relatórios de resumo do usuário</span><span class="sxs-lookup"><span data-stu-id="fb582-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="fb582-180">Dbanalyze/v/Report: diag [/SqlServer: valor]</span><span class="sxs-lookup"><span data-stu-id="fb582-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="fb582-181">Esta seção exibe informações de agregação sobre os usuários em um pool, como o número de usuários habilitados, o número médio de contatos por usuário e o número de usuários para recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="fb582-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="fb582-182">Ao usar esses relatórios, as seguintes informações podem ser úteis:</span><span class="sxs-lookup"><span data-stu-id="fb582-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="fb582-183">Um usuário habilitado é um usuário habilitado para o Lync Server 2013 usando o snap-in usuários e computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb582-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="fb582-184">Um usuário ativo é um usuário que fez logon ou registrou.</span><span class="sxs-lookup"><span data-stu-id="fb582-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="fb582-185">Os relatórios de resumo também oferecem um conjunto de informações estatísticas sobre contatos.</span><span class="sxs-lookup"><span data-stu-id="fb582-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="fb582-186">Essas estatísticas são válidas apenas para o preenchimento de usuários que fizeram logon pelo menos uma vez e que têm pelo menos um contato.</span><span class="sxs-lookup"><span data-stu-id="fb582-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="fb582-187">Consequentemente, você normalmente não verá um número mínimo de contatos de 0.</span><span class="sxs-lookup"><span data-stu-id="fb582-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="fb582-188">Por causa desse comportamento, se um usuário não tiver contatos (mas estiver ativo, se o usuário tiver registrado), você poderá ver: &lt;vazio&gt; para alguns campos de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="fb582-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb582-189">Relatórios por usuário</span><span class="sxs-lookup"><span data-stu-id="fb582-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="fb582-190">Dbanalyze/v/Report: disco [/SqlServer: valor]</span><span class="sxs-lookup"><span data-stu-id="fb582-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="fb582-191">Ao contrário dos relatórios de resumo, que são calculados sobre uma população do usuário, são relatórios sobre um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="fb582-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb582-192">Relatórios de Resumo de conferências</span><span class="sxs-lookup"><span data-stu-id="fb582-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="fb582-193">Dbanalyze/v/Report: conf [/SqlServer: valor]</span><span class="sxs-lookup"><span data-stu-id="fb582-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="fb582-194">Esta seção exibe informações de agregação sobre as estatísticas de resumo da conferência para o pool, como o número de conferências ativas e o número total de participantes.</span><span class="sxs-lookup"><span data-stu-id="fb582-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="fb582-195">Sistema de utilização de largura de banda em execução</span><span class="sxs-lookup"><span data-stu-id="fb582-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="fb582-196">O Analisador de Utilização da Largura de Banda é uma ferramenta que cria relatórios sobre diversas exibições do consumo de largura de banda pelos pontos de extremidade de UC nos links WAN da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="fb582-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="fb582-197">Esses relatórios podem ser usados para compreender o padrão de consumo de largura de banda atual e para ajudar no planejamento da capacidade de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="fb582-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="fb582-198">Também itera na capacidade de largura de banda atribuída a diversos links.</span><span class="sxs-lookup"><span data-stu-id="fb582-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="fb582-199">Essa ferramenta faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb582-199">This tool does the following:</span></span>

  - <span data-ttu-id="fb582-200">Gera relatórios específicos para uso de áudio pela rede</span><span class="sxs-lookup"><span data-stu-id="fb582-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="fb582-201">Ajuda com um planejamento de capacidade mais eficaz e com a iteração na capacidade de largura de banda atribuída a vários links.</span><span class="sxs-lookup"><span data-stu-id="fb582-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="fb582-202">O analisador de utilização de largura de banda pode gerar plotagem gráficas da capacidade de largura de banda e dos relatórios</span><span class="sxs-lookup"><span data-stu-id="fb582-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="fb582-203">Elas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="fb582-203">They are as follows:</span></span>

  - <span data-ttu-id="fb582-204">Todos os links WAN na rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="fb582-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="fb582-205">Filtrado por links WAN selecionados que foram escolhidos</span><span class="sxs-lookup"><span data-stu-id="fb582-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="fb582-206">Filtradas pelos links WAN que excederam o limite de capacidade.</span><span class="sxs-lookup"><span data-stu-id="fb582-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="fb582-207">Filtrado por links WAN que estavam usando a largura de banda provisionada</span><span class="sxs-lookup"><span data-stu-id="fb582-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="fb582-208">Filtrar por links WAN que atingiram níveis críticos (um uso de largura de banda superior a 90% da capacidade de largura de banda do link de WAN)</span><span class="sxs-lookup"><span data-stu-id="fb582-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="fb582-209">Filtrado por tipo de link de WAN — links de site de rede, links interregional e links dentro de um site</span><span class="sxs-lookup"><span data-stu-id="fb582-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="fb582-210">Filtradas por região de rede.</span><span class="sxs-lookup"><span data-stu-id="fb582-210">Filtered by network region</span></span>

<span data-ttu-id="fb582-211">A documentação para esta ferramenta está disponível na [documentação de ferramentas do kit de recursos do Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="fb582-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb582-212">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb582-212">See Also</span></span>


[<span data-ttu-id="fb582-213">Lista de verificação semanal de tarefas</span><span class="sxs-lookup"><span data-stu-id="fb582-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

