---
title: 'Lync Server 2013: Componentes e topologia para monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="4d566-102">Componentes e topologia para monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d566-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d566-103">_**Tópico da última modificação:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="4d566-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="4d566-104">Como os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada servidor front-end, você não precisa configurar um servidor para atuar como o Monitoring Server; cada servidor front-end já funciona como um Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="4d566-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="4d566-105">No entanto, você precisará instalar e configurar um banco de dados para atuar como o repositório de dados back-end para seus dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4d566-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="4d566-106">O Microsoft Lync Server 2013 pode usar qualquer um dos seguintes bancos de dados como o armazenamento de back-end para monitoramento:</span><span class="sxs-lookup"><span data-stu-id="4d566-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="4d566-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="4d566-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="4d566-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4d566-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="4d566-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="4d566-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="4d566-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4d566-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="4d566-111">Observe que você deve usar as edições de 64 bits desses bancos de dados; as versões de 32 bits do SQL Server não podem ser usadas como o armazenamento de back-end para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4d566-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="4d566-112">Da mesma forma, o Lync Server 2013 não é compatível com as edições Express do SQL Server 2008 ou do SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="4d566-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="4d566-113">Para obter mais informações sobre os requisitos de banco de dados do Lync Server 2013, consulte o tópico [suporte do software de banco de dados no Lync server 2013](lync-server-2013-database-software-support.md) no guia de suporte do lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d566-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="4d566-114">Lembre-se de que o SQL Server deve ser instalado e configurado antes da implantação e configuração do monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4d566-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="4d566-115">No entanto, você só precisa implantar o próprio SQL Server; Você não precisa configurar os bancos de dados de monitoramento com antecedência.</span><span class="sxs-lookup"><span data-stu-id="4d566-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="4d566-116">Em vez disso, esses bancos de dados serão automaticamente criados para você quando você publicar sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d566-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="4d566-p104">Os dados de monitoramento pode compartilhar uma instância do SQL Server com outros tipos de dados. Geralmente, o banco de dados de registro de detalhes das chamadas (LcsCdr) e o banco de dados de qualidade da experiência (QoEMetrics) compartilham a mesma instância SQL. Também é comum que os dois bancos de dados de monitoramento estejam na mesma instância SQL que o banco de dados de arquivamento (LcsLog). O único requisito real relacionado às instâncias do SQL Server é que qualquer instância do SQL Server é limitada ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="4d566-p104">Monitoring data can share a SQL Server instance with other types of data. Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog). About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="4d566-120">Uma instância do banco de dados back-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d566-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="4d566-121">Como regra geral, não recomendamos que seu banco de dados de monitoramento seja colocado na mesma instância SQL ou no mesmo computador que o banco de dados de back-end.</span><span class="sxs-lookup"><span data-stu-id="4d566-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="4d566-122">Embora isso seja tecnicamente possível, há o risco de o banco de dados de monitoramento usar espaço em disco necessário para o banco de dados de back-end.</span><span class="sxs-lookup"><span data-stu-id="4d566-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="4d566-123">Uma instância do banco de dados de registro de detalhes das chamadas.</span><span class="sxs-lookup"><span data-stu-id="4d566-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="4d566-124">Uma instância do banco de dados da Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="4d566-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="4d566-125">Uma instância do banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="4d566-125">One instance of the archiving database.</span></span>

<span data-ttu-id="4d566-126">Em outras palavras, você não pode ter duas instâncias do banco de dados LcsCdr na mesma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d566-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="4d566-127">Se precisar de várias instâncias do banco de dados do LcsCdr, será necessário configurar várias instâncias do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d566-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d566-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d566-128">See Also</span></span>


[<span data-ttu-id="4d566-129">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d566-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

