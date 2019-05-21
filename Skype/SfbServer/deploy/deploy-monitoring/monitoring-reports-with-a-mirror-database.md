---
title: Associar relatórios de monitoramento a um banco de dados espelho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumo: saiba como associar relatórios de monitoramento a um banco de dados espelho usado pelo Skype for Business Server.'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273963"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="d218e-103">Associar relatórios de monitoramento a um banco de dados espelho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d218e-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="d218e-104">**Resumo:** Saiba como associar relatórios de monitoramento a um banco de dados espelho usado pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d218e-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="d218e-105">Monitoramento de relatórios com um banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="d218e-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="d218e-106">Se você configurar um espelho para o seu banco de dados de monitoramento, esse banco de dados espelho assumirá a função de banco de dados primário em caso de failover.</span><span class="sxs-lookup"><span data-stu-id="d218e-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="d218e-107">No entanto, se você usar os relatórios de monitoramento do Skype for Business Server e ocorrer um failover, pode ser que seus relatórios de monitoramento não estejam se conectando ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="d218e-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="d218e-108">Isso ocorre porque quando você instala os Relatórios de Monitoramento, apenas o local do banco de dados primário é especificado; você não especifica o local do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="d218e-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="d218e-p102">Para que o failover dos Relatórios de Monitoramento seja executado automaticamente no banco de dados espelho, adicione esse banco de dados como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe das Chamadas e o outro para dados de Qualidade da Experiência (QoE)). (Observe que essa etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações de parceiro de failover editando manualmente os valores da cadeia de conexão usados por esses dois bancos de dados. Para fazer isso, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="d218e-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="d218e-p103">Use o Internet Explorer para abrir a home page do **SQL Server Reporting Services**. A URL dessa home page inclui:</span><span class="sxs-lookup"><span data-stu-id="d218e-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="d218e-114">O prefixo **http:**.</span><span class="sxs-lookup"><span data-stu-id="d218e-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="d218e-115">O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="d218e-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="d218e-116">A cadeia de caracteres **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="d218e-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="d218e-117">O nome da instância de banco de dados em que os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="d218e-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="d218e-118">Por exemplo, se o SQL Server Reporting Services for instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem a instância de banco de dados archinst, a URL da home page será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="d218e-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="d218e-119">Depois que você acessar a home page do Reporting Services, clique em **ServerReports** e em **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="d218e-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="d218e-120">Isso o levará até a página **Reports_Content** para os relatórios de monitoramento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d218e-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="d218e-121">Na página **Reports_Content**, clique na fonte de dados **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="d218e-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="d218e-p105">Na página **CDRDB**, na guia **Propriedades**, procure a caixa de texto chamada **Cadeia de conexão**. A cadeia de conexão atual será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="d218e-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="d218e-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="d218e-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="d218e-p106">Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados do banco de dados espelho. Por exemplo, se o servidor se chamar atl-mirror-001 e o banco de dados espelho estiver na instância archinst, será necessário especificar o banco de dados espelho usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d218e-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="d218e-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="d218e-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="d218e-128">A cadeia de conexão editada será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="d218e-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="d218e-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="d218e-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="d218e-130">Após a atualização da cadeia de conexão, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d218e-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="d218e-p107">Na página **CDRDB**, clique no link **Reports_Content**. Clique na fonte de dados **QMSDB** e edite a cadeia de conexão do banco de dados de QoE. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d218e-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="d218e-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="d218e-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="d218e-135">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d218e-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d218e-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="d218e-136">See also</span></span>

[<span data-ttu-id="d218e-137">Instalar relatórios de monitoramento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d218e-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="d218e-138">Usando relatórios de monitoramento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d218e-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
