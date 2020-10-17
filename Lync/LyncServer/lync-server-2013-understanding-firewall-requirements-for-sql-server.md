---
title: 'Lync Server 2013: Noções básicas sobre requisitos de firewall para o SQL Server'
description: 'Lync Server 2013: Noções básicas sobre requisitos de firewall para o SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434474b36ced0fe64b9398f7d0e6136ff523a93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542377"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="f1d2a-103">Noções básicas sobre requisitos de firewall para o SQL Server com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1d2a-103">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1d2a-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f1d2a-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f1d2a-105">Para uma implantação do Standard Edition, as exceções de firewall são criadas automaticamente durante a instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-105">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="f1d2a-106">No entanto, para implantações Enterprise Edition, você deve configurar as exceções de firewall manualmente no servidor back-end do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-106">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="f1d2a-107">O protocolo TCP/IP permite o uso de determinada porta uma vez para um certo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-107">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="f1d2a-108">Isso significa que, para o servidor baseado no SQL Server, é possível atribuir a instância de banco de dados padrão à porta TCP padrão 1433.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-108">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="f1d2a-109">Para qualquer outra instância, você precisa usar o SQL Server Configuration Manager para atribuir portas exclusivas e não usadas.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-109">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="f1d2a-110">Este tópico aborda:</span><span class="sxs-lookup"><span data-stu-id="f1d2a-110">This topic covers:</span></span>

  - <span data-ttu-id="f1d2a-111">Requisitos para uma exceção de firewall ao usar a instância padrão</span><span class="sxs-lookup"><span data-stu-id="f1d2a-111">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="f1d2a-112">Requisitos para uma exceção de firewall para o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="f1d2a-112">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="f1d2a-113">Requisitos para portas de escuta estática ao usar instâncias nomeadas</span><span class="sxs-lookup"><span data-stu-id="f1d2a-113">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="f1d2a-114">Requisitos para uma exceção de firewall ao usar a instância padrão</span><span class="sxs-lookup"><span data-stu-id="f1d2a-114">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="f1d2a-115">Se você estiver usando a instância padrão do SQL Server para qualquer banco de dados ao implantar o Lync Server 2013, os seguintes requisitos de regra de firewall são usados para ajudar a garantir a comunicação do pool de front-ends para a instância padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-115">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1d2a-116">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f1d2a-116">Protocol</span></span></th>
<th><span data-ttu-id="f1d2a-117">Porta</span><span class="sxs-lookup"><span data-stu-id="f1d2a-117">Port</span></span></th>
<th><span data-ttu-id="f1d2a-118">Direção</span><span class="sxs-lookup"><span data-stu-id="f1d2a-118">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1d2a-119">TCP</span><span class="sxs-lookup"><span data-stu-id="f1d2a-119">TCP</span></span></p></td>
<td><p><span data-ttu-id="f1d2a-120">1433</span><span class="sxs-lookup"><span data-stu-id="f1d2a-120">1433</span></span></p></td>
<td><p><span data-ttu-id="f1d2a-121">Entrada para SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1d2a-121">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="f1d2a-122">Requisitos para uma exceção de firewall para o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="f1d2a-122">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="f1d2a-123">O serviço SQL Server Browser localizará as instâncias do banco de dados e comunicará a porta que a instância (nomeada ou padrão) está configurada para usar.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-123">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1d2a-124">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f1d2a-124">Protocol</span></span></th>
<th><span data-ttu-id="f1d2a-125">Porta</span><span class="sxs-lookup"><span data-stu-id="f1d2a-125">Port</span></span></th>
<th><span data-ttu-id="f1d2a-126">Direção</span><span class="sxs-lookup"><span data-stu-id="f1d2a-126">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1d2a-127">VIA</span><span class="sxs-lookup"><span data-stu-id="f1d2a-127">UDP</span></span></p></td>
<td><p><span data-ttu-id="f1d2a-128">1434</span><span class="sxs-lookup"><span data-stu-id="f1d2a-128">1434</span></span></p></td>
<td><p><span data-ttu-id="f1d2a-129">Entrada</span><span class="sxs-lookup"><span data-stu-id="f1d2a-129">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="f1d2a-130">Requisitos para portas de escuta estáticas ao usar instâncias nomeadas</span><span class="sxs-lookup"><span data-stu-id="f1d2a-130">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="f1d2a-131">Ao usar instâncias nomeadas na configuração do SQL Server para bancos de dados que dão suporte ao Lync Server 2013, configure as portas estáticas usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-131">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="f1d2a-132">Após a atribuição das portas estáticas a cada instância nomeada, crie exceções para cada porta estática no firewall.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-132">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1d2a-133">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f1d2a-133">Protocol</span></span></th>
<th><span data-ttu-id="f1d2a-134">Porta</span><span class="sxs-lookup"><span data-stu-id="f1d2a-134">Port</span></span></th>
<th><span data-ttu-id="f1d2a-135">Direção</span><span class="sxs-lookup"><span data-stu-id="f1d2a-135">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1d2a-136">TCP</span><span class="sxs-lookup"><span data-stu-id="f1d2a-136">TCP</span></span></p></td>
<td><p><span data-ttu-id="f1d2a-137">Definido estaticamente</span><span class="sxs-lookup"><span data-stu-id="f1d2a-137">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="f1d2a-138">Entrada</span><span class="sxs-lookup"><span data-stu-id="f1d2a-138">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="f1d2a-139">Documentação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1d2a-139">SQL Server Documentation</span></span>

<span data-ttu-id="f1d2a-140">A documentação do Microsoft SQL Server 2012 fornece orientação detalhada sobre como configurar o acesso de firewall para os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="f1d2a-140">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="f1d2a-141">Para obter detalhes sobre o Microsoft SQL Server 2012, consulte "Configurando o Firewall do Windows para permitir o acesso ao SQL Server" em [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) .</span><span class="sxs-lookup"><span data-stu-id="f1d2a-141">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

