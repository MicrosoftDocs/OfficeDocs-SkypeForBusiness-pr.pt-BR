---
title: Associar relatórios de monitoramento a um banco de dados de espelho em Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumo: Saiba como associar relatórios de monitoramento de um banco de dados de espelho usado pelo Skype para Business Server 2015.'
ms.openlocfilehash: 246f16fd54133e2a6cf1e26a8126d0ec546bd686
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server-2015"></a><span data-ttu-id="0bee2-103">Associar relatórios de monitoramento a um banco de dados de espelho em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0bee2-103">Associate Monitoring Reports with a mirror database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0bee2-104">**Resumo:** Saiba como associar relatórios de monitoramento de um banco de dados de espelho usado pelo Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0bee2-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server 2015.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="0bee2-105">Monitoramento de relatórios com um banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="0bee2-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="0bee2-106">Se você configurar um espelho para o seu banco de dados de monitoramento, esse banco de dados espelho assumirá a função de banco de dados primário em caso de failover.</span><span class="sxs-lookup"><span data-stu-id="0bee2-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="0bee2-107">No entanto, se você usar o Skype para relatórios de monitoramento de servidor de negócios e ocorre um failover, você pode achar que seus relatórios de monitoramento não estiver se conectando ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="0bee2-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="0bee2-108">Isso ocorre porque quando você instala os Relatórios de Monitoramento, apenas o local do banco de dados primário é especificado; você não especifica o local do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="0bee2-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="0bee2-p102">Para que o failover dos Relatórios de Monitoramento seja executado automaticamente no banco de dados espelho, adicione esse banco de dados como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe das Chamadas e o outro para dados de Qualidade da Experiência (QoE)). (Observe que essa etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações de parceiro de failover editando manualmente os valores da cadeia de conexão usados por esses dois bancos de dados. Para fazer isso, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="0bee2-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="0bee2-p103">Use o Internet Explorer para abrir a home page do **SQL Server Reporting Services**. A URL dessa home page inclui:</span><span class="sxs-lookup"><span data-stu-id="0bee2-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="0bee2-114">O prefixo **http:**.</span><span class="sxs-lookup"><span data-stu-id="0bee2-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="0bee2-115">O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="0bee2-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="0bee2-116">A cadeia de caracteres **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="0bee2-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="0bee2-117">O nome da instância de banco de dados em que os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="0bee2-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="0bee2-118">Por exemplo, se o SQL Server Reporting Services for instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem a instância de banco de dados archinst, a URL da home page será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="0bee2-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="0bee2-119">Depois que você acessar a home page do Reporting Services, clique em **ServerReports** e em **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="0bee2-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="0bee2-120">Isso levará você à página **Reports_Content** para o Skype para relatórios de monitoramento de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0bee2-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="0bee2-121">Na página **Reports_Content**, clique na fonte de dados **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="0bee2-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="0bee2-p105">Na página **CDRDB**, na guia **Propriedades**, procure a caixa de texto chamada **Cadeia de conexão**. A cadeia de conexão atual será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="0bee2-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="0bee2-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="0bee2-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="0bee2-p106">Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados do banco de dados espelho. Por exemplo, se o servidor se chamar atl-mirror-001 e o banco de dados espelho estiver na instância archinst, será necessário especificar o banco de dados espelho usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="0bee2-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="0bee2-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="0bee2-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="0bee2-128">A cadeia de conexão editada será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="0bee2-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="0bee2-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="0bee2-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="0bee2-130">Após a atualização da cadeia de conexão, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0bee2-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="0bee2-p107">Na página **CDRDB**, clique no link **Reports_Content**. Clique na fonte de dados **QMSDB** e edite a cadeia de conexão do banco de dados de QoE. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bee2-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="0bee2-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="0bee2-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="0bee2-135">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0bee2-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0bee2-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0bee2-136">See also</span></span>

#### 

[<span data-ttu-id="0bee2-137">Instalar o monitoramento de relatórios no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0bee2-137">Install Monitoring Reports in Skype for Business Server 2015</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="0bee2-138">Usando relatórios do Skype de monitoramento para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0bee2-138">Using Monitoring Reports in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)

