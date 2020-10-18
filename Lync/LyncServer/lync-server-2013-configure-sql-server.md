---
title: 'Lync Server 2013: configurar o SQL Server'
description: 'Lync Server 2013: configurar o SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2330dc4548e5157b7f29567551df4c89ee15998b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576707"
---
# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="5ce99-103">Configurar o SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce99-103">Configure SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ce99-104">_**Última modificação do tópico:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="5ce99-104">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="5ce99-105">Para cada banco de dados implantado, você pode usar uma única instância do SQL Server para todos os bancos de dados da implantação do Lync Server 2013 que podem ser colocados em um servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5ce99-105">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="5ce99-106">Para obter detalhes sobre a colocação de banco de dados, consulte [supported Server em colocação no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="5ce99-106">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5ce99-107">Além disso, cada instância do SQL Server deve estar instalada e disponível antes de concluir as etapas no construtor de topologias que definem os bancos de dados ou criar manualmente os bancos de dados com os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ce99-107">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5ce99-108">Para obter detalhes sobre a capacidade de suporte do SQL Server, confira [configuração de hardware para o Lync Server 2013](lync-server-2013-hardware-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5ce99-108">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="5ce99-109">Para instalar o Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5ce99-109">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="5ce99-110">Consulte a documentação do Microsoft SQL Server 2012 em: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx> .</span><span class="sxs-lookup"><span data-stu-id="5ce99-110">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

