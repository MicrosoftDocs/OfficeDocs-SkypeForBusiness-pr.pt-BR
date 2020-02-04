---
title: 'Lync Server 2013: associando relatórios de monitoramento a um banco de dados espelho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e5f10e3e4bd3c063cafcb2fd984098482ebf22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="6fa0c-102">Associando relatórios de monitoramento a um banco de dados espelho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fa0c-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fa0c-103">_**Tópico da última modificação:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="6fa0c-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="6fa0c-104">Se você configurar um espelho para o seu banco de dados de monitoramento, esse banco de dados espelho assumirá a função de banco de dados primário em caso de failover.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="6fa0c-105">No entanto, se você usar os relatórios de monitoramento do Lync Server e ocorrer um failover, pode ser que seus relatórios de monitoramento não estejam se conectando ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="6fa0c-106">Isso ocorre porque quando você instala os Relatórios de Monitoramento, apenas o local do banco de dados primário é especificado; você não especifica o local do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="6fa0c-p102">Para que o failover dos Relatórios de Monitoramento seja executado automaticamente no banco de dados espelho, adicione esse banco de dados como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe das Chamadas e o outro para dados de Qualidade da Experiência (QoE)). (Observe que essa etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações de parceiro de failover editando manualmente os valores da cadeia de conexão usados por esses dois bancos de dados. Para fazer isso, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="6fa0c-p103">Use o Internet Explorer para abrir a home page do **SQL Server Reporting Services**. A URL dessa home page inclui:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="6fa0c-112">O prefixo **http:**.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="6fa0c-113">O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="6fa0c-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="6fa0c-114">A cadeia de **caracteres\_/Reports**.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="6fa0c-115">O nome da instância de banco de dados em que os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="6fa0c-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="6fa0c-116">Por exemplo, se o SQL Server Reporting Services for instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem a instância de banco de dados archinst, a URL da home page será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="6fa0c-117">Depois de acessar a página inicial do Reporting Services, clique em **LyncServerReports**e, em seguida, clique em **relatórios\_de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="6fa0c-118">Isso o levará até a página de **conteúdo relatórios\_** dos relatórios de monitoramento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="6fa0c-119">Na página **relatórios\_de conteúdo** , clique na fonte de dados **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="6fa0c-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="6fa0c-p105">Na página **CDRDB**, na guia **Propriedades**, procure a caixa de texto chamada **Cadeia de conexão**. A cadeia de conexão atual será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="6fa0c-122">**Dados fonte = (local)\\archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="6fa0c-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="6fa0c-p106">Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados do banco de dados espelho. Por exemplo, se o servidor se chamar atl-mirror-001 e o banco de dados espelho estiver na instância archinst, será necessário especificar o banco de dados espelho usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="6fa0c-125">**Parceiro de failover = ATL-Mirror-\\001 archinst**</span><span class="sxs-lookup"><span data-stu-id="6fa0c-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="6fa0c-126">A cadeia de conexão editada será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="6fa0c-127">**Dados fonte = (local)\\archinst; Parceiro de failover = ATL-Mirror-\\001 archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="6fa0c-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="6fa0c-128">Após a atualização da cadeia de conexão, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="6fa0c-129">Na página **CDRDB** , clique no link **de\_conteúdo relatórios** .</span><span class="sxs-lookup"><span data-stu-id="6fa0c-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="6fa0c-130">Clique na fonte de dados **QMSDB** e edite a cadeia de conexão do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="6fa0c-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-131">For example:</span></span>
    
    <span data-ttu-id="6fa0c-132">**Dados fonte = (local)\\archinst; Parceiro de failover = ATL-Mirror-\\001 archinst; Initial Catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="6fa0c-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="6fa0c-133">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6fa0c-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="6fa0c-134">See Also</span></span>


[<span data-ttu-id="6fa0c-135">Instalando relatórios de monitoramento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fa0c-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="6fa0c-136">Usar relatórios de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fa0c-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

