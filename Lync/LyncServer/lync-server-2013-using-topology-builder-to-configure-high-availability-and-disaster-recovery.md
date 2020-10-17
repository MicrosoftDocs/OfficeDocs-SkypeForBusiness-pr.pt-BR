---
title: Usando o construtor de topologias para configurar alta disponibilidade e recuperação de desastre
description: Usando o construtor de topologias para configurar alta disponibilidade e recuperação de desastre.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547317"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="33ff2-103">Usando o construtor de topologias para configurar alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33ff2-103">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33ff2-104">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="33ff2-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="33ff2-105">Execute as seguintes etapas no construtor de topologias para configurar alta disponibilidade e recuperação de desastre para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="33ff2-105">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="33ff2-106">Adicione os bancos de dados espelho e os repositórios secundários de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33ff2-106">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="33ff2-107">Edite as propriedades do serviço do servidor de chat persistente para:</span><span class="sxs-lookup"><span data-stu-id="33ff2-107">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="33ff2-108">Ativar espelhamento do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="33ff2-108">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="33ff2-109">Adicione o repositório principal de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33ff2-109">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="33ff2-110">Habilite o banco de dados de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33ff2-110">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="33ff2-111">Adicione o repositório do SQL Server secundário de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33ff2-111">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="33ff2-112">Adicione o espelho do SQL Server Store para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="33ff2-112">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="33ff2-113">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="33ff2-113">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

