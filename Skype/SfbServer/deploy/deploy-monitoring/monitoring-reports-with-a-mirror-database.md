---
title: Associar Relatórios de Monitoramento a um banco de dados espelho no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumo: Saiba como associar relatórios de monitoramento a um banco de dados espelho usado pelo Skype for Business Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802161"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="a5401-103">Associar Relatórios de Monitoramento a um banco de dados espelho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5401-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="a5401-104">**Resumo:** Saiba como associar relatórios de monitoramento a um banco de dados espelho usado pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5401-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="a5401-105">Monitorar relatórios com um banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="a5401-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="a5401-106">Se você configurar um espelho para o banco de dados de monitoramento, esse banco de dados espelho assumirá como o banco de dados principal se ocorrer um failover.</span><span class="sxs-lookup"><span data-stu-id="a5401-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="a5401-107">No entanto, se você usar os Relatórios de Monitoramento do Skype for Business Server e ocorrer um failover, poderá descobrir que seus Relatórios de Monitoramento não estão se conectando ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="a5401-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="a5401-108">Isso acontece porque, ao instalar os Relatórios de Monitoramento, você especifica apenas o local do banco de dados primário; você não especifica o local do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="a5401-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="a5401-109">Para fazer com que os Relatórios de Monitoramento sejam automaticamente failover para o banco de dados espelho, você deve adicionar o banco de dados espelho como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe da Chamada e outro para dados de QoE (Qualidade da Experiência).</span><span class="sxs-lookup"><span data-stu-id="a5401-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="a5401-110">(Observe que esta etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações do parceiro de failover editando manualmente os valores de sequência de conexão usados por esses dois bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="a5401-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="a5401-111">Para fazer isso, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="a5401-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="a5401-112">Use o Internet Explorer para abrir a **home page do SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="a5401-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="a5401-113">A URL da home page do Reporting Services inclui:</span><span class="sxs-lookup"><span data-stu-id="a5401-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="a5401-114">O **prefixo http:**</span><span class="sxs-lookup"><span data-stu-id="a5401-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="a5401-115">O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="a5401-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="a5401-116">A cadeia de **caracteres /Reports_**.</span><span class="sxs-lookup"><span data-stu-id="a5401-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="a5401-117">O nome da instância do banco de dados onde os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="a5401-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="a5401-118">Por exemplo, se o SQL Server Reporting Services tiver sido instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem o arquivamento de instância de banco de dados, a URL da home page terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="a5401-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="a5401-119">Depois de acessar a home page do Reporting Services, clique em **ServerReports** e clique em **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="a5401-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="a5401-120">Isso levará você para a página **Reports_Content** para os Relatórios de Monitoramento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5401-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="a5401-121">Na página **Reports_Content,** clique na fonte de dados **CDRDB.**</span><span class="sxs-lookup"><span data-stu-id="a5401-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="a5401-122">Na página **CDRDB,** na guia **Propriedades,** procure a caixa de texto rotulada **Sequência de** conexão.</span><span class="sxs-lookup"><span data-stu-id="a5401-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="a5401-123">A cadeia de conexão atual será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a5401-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="a5401-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="a5401-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="a5401-125">Edite a cadeia de conexão para incluir o nome do servidor e a instância do banco de dados para o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="a5401-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="a5401-126">Por exemplo, se o servidor for nomeado como atl-mirror-001 e o banco de dados espelho estiver na instância archinst, você precisará adicionar para especificar o banco de dados espelho usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a5401-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="a5401-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="a5401-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="a5401-128">Sua sequência de conexão editada terá a aparência a seguir:</span><span class="sxs-lookup"><span data-stu-id="a5401-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="a5401-129">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="a5401-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="a5401-130">Depois de atualizar a cadeia de conexão, clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a5401-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="a5401-131">Na página **CDRDB,** clique **Reports_Content** link.</span><span class="sxs-lookup"><span data-stu-id="a5401-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="a5401-132">Clique na **fonte de dados QMSDB** e edite a cadeia de conexão para o banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="a5401-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="a5401-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a5401-133">For example:</span></span>
    
    <span data-ttu-id="a5401-134">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="a5401-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="a5401-135">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a5401-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a5401-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5401-136">See also</span></span>

[<span data-ttu-id="a5401-137">Instalar relatórios de monitoramento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5401-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="a5401-138">Usando relatórios de monitoramento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5401-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
