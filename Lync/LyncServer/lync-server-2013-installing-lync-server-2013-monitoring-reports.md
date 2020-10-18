---
title: 'Lync Server 2013: instalando relatórios de monitoramento do Lync Server 2013'
description: 'Lync Server 2013: instalando relatórios de monitoramento do Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573927"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="979e4-103">Instalando Relatórios de Monitoramento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="979e4-103">Installing Lync Server 2013 Monitoring Reports</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="979e4-104">_**Última modificação do tópico:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="979e4-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="979e4-105">Os relatórios de monitoramento do Microsoft Lync Server 2013 oferecem uma ampla gama de informações sobre a qualidade e a quantidade das sessões de comunicação que ocorrem na organização.</span><span class="sxs-lookup"><span data-stu-id="979e4-105">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="979e4-106">No entanto, os relatórios de monitoramento não são instalados automaticamente quando você instala o Lync Server 2013; em vez disso, você deve instalar os relatórios de monitoramento separadamente e somente depois que o Lync Server tiver sido instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="979e4-106">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="979e4-p102">Recomenda-se a instalação dos relatórios de monitoramento no mesmo computador em que o banco de dados de monitoramento está instalado. Isso simplifica o processo de atribuição de permissões para acessar os relatórios: a com a instalação dos relatórios de monitoramento no computador que hospeda o repositório de monitoramento, você não precisará configurar permissões que permitam que um banco de dados em um computador interaja com os Reporting Services em execução em outro computador.</span><span class="sxs-lookup"><span data-stu-id="979e4-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="979e4-109">Os relatórios de monitoramento do Lync Server incluem mais de 30 relatórios projetados para fornecer informações detalhadas sobre conferências, sessões de IM ponto a ponto, registros de usuário, aplicativo de grupo de resposta e muito mais.</span><span class="sxs-lookup"><span data-stu-id="979e4-109">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="979e4-110">Para a versão 2013, os relatórios de monitoramento do Lync Server incluem vários aprimoramentos:</span><span class="sxs-lookup"><span data-stu-id="979e4-110">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="979e4-111">**Novos relatórios de qualidade de voz**.</span><span class="sxs-lookup"><span data-stu-id="979e4-111">**New voice quality reports**.</span></span> <span data-ttu-id="979e4-112">Esses novos relatórios incluem o [relatório de comparação de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), que compara a qualidade entre diferentes tipos de chamadas (por exemplo, entre chamadas com fio e chamadas sem fio); e o [relatório de tempo de ingresso em conferência no Lync Server 2013](lync-server-2013-conference-join-time-report.md), que fornece informações sobre a quantidade de tempo necessária para que os usuários ingressem em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="979e4-112">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="979e4-113">**Relatórios aprimorados para analisar e solucionar problemas de sessões de vídeo e compartilhamento de aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="979e4-113">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="979e4-114">O [relatório de Resumo de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-summary-report.md) oferece uma maneira de analisar as chamadas de compartilhamento de vídeo e aplicativos, enquanto o [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) detalha o desempenho dos servidores que geram essas chamadas.</span><span class="sxs-lookup"><span data-stu-id="979e4-114">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="979e4-115">As métricas de compartilhamento de vídeo e aplicativos agora também são relatadas pelo [relatório de detalhes de sessão ponto a ponto no Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) e no [relatório de detalhes de conferência no Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="979e4-115">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="979e4-p106">**Desempenho de relatórios aprimorado**. Inclui tempos menores de resposta e recuperação de dados, bem como navegação mais rápida e fácil pelos relatórios.</span><span class="sxs-lookup"><span data-stu-id="979e4-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="979e4-118">Encontre mais informações sobre os relatórios individuais na documentação dos relatórios de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="979e4-118">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="979e4-119">Há outro novo relatório – subrelatório de detalhes de chamadas de QoE – incluído no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="979e4-119">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="979e4-120">Porém, seu uso é principalmente interno e o acesso a ele não pode ser feito diretamente.</span><span class="sxs-lookup"><span data-stu-id="979e4-120">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="979e4-121">Há duas maneiras de instalar os relatórios de monitoramento do Lync Server: você pode usar o assistente de implantação do Lync Server ou você pode usar um script do Windows PowerShell incluído nos arquivos de instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="979e4-121">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="979e4-122">Independente do método usado para instalar os relatórios, primeiro você deve certificar-se de:</span><span class="sxs-lookup"><span data-stu-id="979e4-122">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="979e4-123">Ter o direito de adicionar uma função de banco de dados a uma conta de usuário no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="979e4-123">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="979e4-p109">Possuir a função Gerenciador de Conteúdo no SQL Server Reporting Services. Essa função concede o direito de implantar relatórios no SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="979e4-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="979e4-126">Para instalar os relatórios de monitoramento usando o Assistente de Implantação, siga as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="979e4-126">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="979e4-127">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="979e4-127">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="979e4-128">No Assistente de Implantação, clique em **Implantar Relatórios de Monitoramento** para iniciar o assistente Implantar Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="979e4-128">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="979e4-p110">No assistente Implantar Relatórios de Monitoramento, na página **Especificar Banco de Dados de Monitoramento**, certifique-se de que o nome de domínio totalmente qualificado do computador que hospeda o repositório de monitoramento apareça na lista suspensa **Banco de dados de monitoramento** (caso tenha vários repositórios de monitoramento, será necessário selecionar o servidor correto na lista suspensa). Verifique se a instância correta do SQL Server aparece na caixa **Instância do SSRS (SQL Server Reporting Services)** (por exemplo, **atl-sql-001.litwareinc.com/archinst**) e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="979e4-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="979e4-131">Na página **especificar credenciais** , na caixa **nome de usuário** , digite o nome de domínio e o nome de usuário da conta a ser usada ao acessar os relatórios de monitoramento (por exemplo, **litwareinc \\ kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="979e4-131">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="979e4-132">Se você não usar esse formato (nome de \\ usuário do domínio), ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="979e4-132">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="979e4-133">Digite a senha da conta de usuário na caixa **Senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="979e4-133">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="979e4-134">Observe que nenhum direito especial é necessário para esta conta.</span><span class="sxs-lookup"><span data-stu-id="979e4-134">Note that no special rights are required for this account.</span></span> <span data-ttu-id="979e4-135">A conta receberá automaticamente as permissões de logon e banco de dados necessárias quando a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="979e4-135">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="979e4-p113">Na página **Especificar Grupo Somente Leitura**, informe o nome de um grupo de segurança ao qual será concedido acesso somente leitura ao SQL Server Reporting Services na caixa Grupo de usuários. Por exemplo, para conceder aos administradores acesso somente leitura aos relatórios, digite **RTCUniversalReadOnlyAdmins**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="979e4-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="979e4-139">Na página **Executando Comandos**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="979e4-139">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="979e4-140">Os relatórios de monitoramento também podem ser instalados do Shell de gerenciamento do Lync Server executando o script DeployReports.ps1; Este script do Windows PowerShell pode ser encontrado na mídia de instalação do Lync Server \\ na \\ pasta Setup ReportingSetup</span><span class="sxs-lookup"><span data-stu-id="979e4-140">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="979e4-141">Para instalar os relatórios de monitoramento usando DeployReports.ps1, digite um comando semelhante a este no prompt do Shell de Gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="979e4-141">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="979e4-142">Os parâmetros usados no comando anterior são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="979e4-142">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="979e4-143">Nome do parâmetro</span><span class="sxs-lookup"><span data-stu-id="979e4-143">Parameter Name</span></span></th>
<th><span data-ttu-id="979e4-144">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="979e4-144">Required</span></span></th>
<th><span data-ttu-id="979e4-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="979e4-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="979e4-146">storedUserName</span><span class="sxs-lookup"><span data-stu-id="979e4-146">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="979e4-147">Sim</span><span class="sxs-lookup"><span data-stu-id="979e4-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="979e4-148">Conta de usuário (no formato domínio\nome_de_usuário) usada para acessar o repositório de monitoramento; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="979e4-148">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="979e4-149">Essa conta deve ter permissões do SQL Server e SQL Server Reporting Services especificadas previamente. Caso contrário, o script falhará.</span><span class="sxs-lookup"><span data-stu-id="979e4-149">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="979e4-150">storedPassword</span><span class="sxs-lookup"><span data-stu-id="979e4-150">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="979e4-151">Sim</span><span class="sxs-lookup"><span data-stu-id="979e4-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="979e4-152">Senha da conta de usuário usada para acessar o repositório de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="979e4-152">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="979e4-153">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="979e4-153">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="979e4-154">Não</span><span class="sxs-lookup"><span data-stu-id="979e4-154">No</span></span></p></td>
<td><p><span data-ttu-id="979e4-155">Grupo de segurança local ou domínio cujos membros receberão acesso somente leitura aos relatórios de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="979e4-155">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="979e4-156">Observe que o script falhará se o grupo especificado não existir.</span><span class="sxs-lookup"><span data-stu-id="979e4-156">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="979e4-157">Caso decida revogar as permissões posteriormente ou se decidir conceder permissão de acesso a outros usuários ou grupos, faça isso usando o gerenciador de relatórios do SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="979e4-157">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="979e4-158">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="979e4-158">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="979e4-159">Não</span><span class="sxs-lookup"><span data-stu-id="979e4-159">No</span></span></p></td>
<td><p><span data-ttu-id="979e4-p116">Instância do SQL Server que hospeda o Reporting Service. A instância de relatório deve ser especificada usando o nome de domínio totalmente qualificado do servidor de relatório. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="979e4-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="979e4-162">Se este parâmetro não for incluído, o script partirá do pressuposto de que o Reporting Services é hospedado pela mesma instância do SQL Server que hospeda o banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="979e4-162">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="979e4-163">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="979e4-163">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="979e4-164">Não</span><span class="sxs-lookup"><span data-stu-id="979e4-164">No</span></span></p></td>
<td><p><span data-ttu-id="979e4-p117">Identidade de serviço do banco de dados de monitoramento. Você pode retornar as identidades dos bancos de dados de monitoramento executando este comando:</span><span class="sxs-lookup"><span data-stu-id="979e4-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="979e4-167">Após a instalação do relatórios de monitoramento, você deve usar o cmdlet Set-CsReportingConfiguration para configurar o URL usado para acessar esses relatórios.</span><span class="sxs-lookup"><span data-stu-id="979e4-167">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="979e4-168">Essa tarefa pode ser realizada no Shell de gerenciamento do Lync Server, executando o seguinte comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="979e4-168">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="979e4-169">Observe que, apesar de recomendado, não é obrigatório usar o protocolo HTTPS ao configurar o URL do relatório:</span><span class="sxs-lookup"><span data-stu-id="979e4-169">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="979e4-p119">No comando anterior, a propriedade ReportingUrl deve ser definida como o URL do Gerenciador de Relatórios usado pelo  SQL Server 2008 R2 Reporting Services. Você pode determinar o URL do Gerenciador de Relatórios concluindo as etapas a seguir no computador onde o  SQL Server Reporting Services foi instalado:</span><span class="sxs-lookup"><span data-stu-id="979e4-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="979e4-172">Clique em Iniciar, Todos os Programas,  Microsoft SQL Server 2008 R2, Ferramentas de Configuração e Gerenciador de Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="979e4-172">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="979e4-p120">Na caixa de diálogo Conexão de Configuração do Reporting Services, certifique-se de que o nome do computador do Reporting Services apareça na caixa Nome do Servidor. Selecione a instância do SQL Server na lista suspensa Instância do Servidor de Relatório e clique em Conectar.</span><span class="sxs-lookup"><span data-stu-id="979e4-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="979e4-p121">no Gerenciador de Configuração do Reporting Services, clique em URL do Gerenciador de Relatório. Um ou mais URLs devem aparecer no painel URL do Gerenciador de Relatório. Todos esses URLs podem ser usados como URL de relatório, embora, mais uma vez, seja recomendado que ReportingUrl use o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="979e4-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="979e4-178">Se você configurou um banco de dados espelho para seu banco de dados de monitoramento, você também deve associar os relatórios de monitoramento com o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="979e4-178">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="979e4-179">Confira o artigo [associando relatórios de monitoramento a um banco de dados espelho no Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="979e4-179">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

