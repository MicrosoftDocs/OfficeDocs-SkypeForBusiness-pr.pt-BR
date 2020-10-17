---
title: 'Lync Server 2013: componentes e topologias para monitoramento'
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
ms.openlocfilehash: bf9724089eeed36d48cbce8e1872078e3940beae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502518"
---
# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="cc39f-102">Componentes e topologias para monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc39f-102">Components and topologies for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc39f-103">_**Última modificação do tópico:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="cc39f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="cc39f-104">Como os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada servidor de front-end, não é necessário configurar um servidor para atuar como o servidor de monitoramento; cada servidor de front-end já funciona como um servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="cc39f-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="cc39f-105">No entanto, será necessário instalar e configurar um banco de dados para atuar como o armazenamento de dados de backend para seus dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="cc39f-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="cc39f-106">O Microsoft Lync Server 2013 pode usar qualquer um dos seguintes bancos de dados como o armazenamento de backend para monitoramento:</span><span class="sxs-lookup"><span data-stu-id="cc39f-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="cc39f-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="cc39f-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="cc39f-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="cc39f-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="cc39f-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="cc39f-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="cc39f-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="cc39f-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="cc39f-111">Observe que você deve usar as edições de 64 bits desses bancos de dados; as versões de 32 bits do SQL Server não podem ser usadas como o armazenamento de backend para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="cc39f-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="cc39f-112">Da mesma forma, o Lync Server 2013 não é compatível com as edições Express do SQL Server 2008 ou SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="cc39f-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="cc39f-113">Para obter mais informações sobre os requisitos de banco de dados para o Lync Server 2013, consulte o tópico [suporte a software de banco de dados no Lync server 2013](lync-server-2013-database-software-support.md) no guia de suporte do lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc39f-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="cc39f-114">Tenha em mente que o SQL Server deve ser instalado e configurado antes de implantar e configurar o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="cc39f-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="cc39f-115">No entanto, você só precisa implantar o SQL Server em si; Você não precisa configurar os bancos de dados de monitoramento com antecedência.</span><span class="sxs-lookup"><span data-stu-id="cc39f-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="cc39f-116">Em vez disso, esses bancos de dados serão criados automaticamente quando você publicar sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc39f-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="cc39f-117">Os dados de monitoramento podem compartilhar uma instância do SQL Server com outros tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="cc39f-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="cc39f-118">Normalmente, o banco de dados de registro de detalhes da chamada (LcsCdr) e o banco de dados de qualidade da experiência (QoEMetrics) compartilham a mesma instância do SQL; também é comum que os dois bancos de dados de monitoramento estejam na mesma instância SQL que o banco de dados de arquivamento (LcsLog).</span><span class="sxs-lookup"><span data-stu-id="cc39f-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="cc39f-119">Sobre o único requisito real com instâncias do SQL Server é que qualquer instância do SQL Server está limitada à seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc39f-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="cc39f-120">Uma instância do banco de dados de backend do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc39f-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="cc39f-121">(Como regra geral, não é recomendável que seu banco de dados de monitoramento seja colocado na mesma instância SQL ou mesmo no mesmo computador, como banco de dados de back-end.</span><span class="sxs-lookup"><span data-stu-id="cc39f-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="cc39f-122">Embora tecnicamente possível, você corre o risco de o banco de dados de monitoramento usar espaço em disco necessário para o banco de dados de back-end.</span><span class="sxs-lookup"><span data-stu-id="cc39f-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="cc39f-123">Uma instância do banco de dados de registro de detalhes das chamadas.</span><span class="sxs-lookup"><span data-stu-id="cc39f-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="cc39f-124">Uma instância do banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="cc39f-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="cc39f-125">Uma instância do banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="cc39f-125">One instance of the archiving database.</span></span>

<span data-ttu-id="cc39f-126">Em outras palavras, não é possível ter duas instâncias do banco de dados LcsCdr na mesma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc39f-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="cc39f-127">Se você precisar de várias instâncias do banco de dados do LcsCdr, será necessário configurar várias instâncias do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc39f-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="cc39f-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc39f-128">See Also</span></span>


[<span data-ttu-id="cc39f-129">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc39f-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

