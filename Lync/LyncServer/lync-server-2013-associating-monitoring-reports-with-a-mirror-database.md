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
ms.openlocfilehash: 48dbf5530a071bc1f23f9d2c05d82e151f51f645
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="c575d-102">Associando relatórios de monitoramento a um banco de dados espelho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c575d-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c575d-103">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c575d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c575d-104">Se você configurar um espelho para seu banco de dados de monitoramento, o banco de dados espelho assumirá o controle como o banco de dados primário se ocorrer um failover.</span><span class="sxs-lookup"><span data-stu-id="c575d-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="c575d-105">No entanto, se você usar os relatórios de monitoramento do Lync Server e ocorrer um failover, poderá achar que seus relatórios de monitoramento não estão se conectando ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="c575d-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="c575d-106">Isso ocorre porque, quando você instala relatórios de monitoramento, você especifica apenas o local do banco de dados primário; Você não especifica o local do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="c575d-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="c575d-107">Para obter relatórios de monitoramento para failover automático para o banco de dados espelho, você deve adicionar o banco de dados espelho como um "parceiro de failover" aos dois bancos de dados usados pelos relatórios de monitoramento (um banco de dados para dados de registro de detalhes de chamadas e o outro para a qualidade de Dados da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="c575d-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="c575d-108">(Observe que esta etapa deve ser executada após a instalação dos relatórios de monitoramento.) Você pode adicionar as informações do parceiro de failover editando manualmente os valores da cadeia de caracteres de conexão usados por esses dois bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="c575d-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="c575d-109">Para fazer isso, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="c575d-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="c575d-110">Use o Internet Explorer para abrir a página inicial do **SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="c575d-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="c575d-111">A URL da home page do Reporting Services inclui:</span><span class="sxs-lookup"><span data-stu-id="c575d-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="c575d-112">O prefixo **http:** .</span><span class="sxs-lookup"><span data-stu-id="c575d-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="c575d-113">O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="c575d-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="c575d-114">A cadeia de **caracteres\_/Reports**.</span><span class="sxs-lookup"><span data-stu-id="c575d-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="c575d-115">O nome da instância do banco de dados onde os relatórios de monitoramento são instalados (por exemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="c575d-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="c575d-116">Por exemplo, se o SQL Server Reporting Services foi instalado no computador atl-sql-001.litwareinc.com e os relatórios de monitoramento usam a instância de banco de archinst, a URL da página inicial teria a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="c575d-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="c575d-117">Após acessar a página inicial do Reporting Services, clique em **LyncServerReports**e em **relatórios\_de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="c575d-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="c575d-118">Isso levará você à página **de\_conteúdo de relatórios** dos relatórios de monitoramento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c575d-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="c575d-119">Na página **de\_conteúdo relatórios** , clique na fonte de dados **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="c575d-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="c575d-120">Na página **CDRDB** , na guia **Propriedades** , procure a caixa de texto chamada **sequência de conexão**.</span><span class="sxs-lookup"><span data-stu-id="c575d-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="c575d-121">A cadeia de caracteres de conexão atual terá uma aparência semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="c575d-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="c575d-122">**Fonte de dados = (local\\) archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="c575d-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="c575d-123">Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados para o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="c575d-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="c575d-124">Por exemplo, se o servidor se chamar ATL-Mirror-001 e o banco de dados espelho estiver na instância do archinst, você precisará adicionar para especificar o banco de dados espelho usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c575d-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="c575d-125">**Parceiro de failover = ATL-Mirror-\\001 archinst**</span><span class="sxs-lookup"><span data-stu-id="c575d-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="c575d-126">A cadeia de conexão editada terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="c575d-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="c575d-127">**Fonte de dados = (local\\) archinst; Parceiro de failover = ATL-Mirror-\\001 archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="c575d-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="c575d-128">Depois de atualizar a cadeia de conexão, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c575d-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="c575d-129">Na página **CDRDB** , clique no link **relatórios\_de conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="c575d-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="c575d-130">Clique na fonte de dados do **QMSDB** e edite a cadeia de caracteres de conexão para o banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="c575d-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="c575d-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c575d-131">For example:</span></span>
    
    <span data-ttu-id="c575d-132">**Fonte de dados = (local\\) archinst; Parceiro de failover = ATL-Mirror-\\001 archinst; Initial Catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="c575d-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="c575d-133">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c575d-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c575d-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="c575d-134">See Also</span></span>


[<span data-ttu-id="c575d-135">Instalando Relatórios de Monitoramento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c575d-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="c575d-136">Usando relatórios de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c575d-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

