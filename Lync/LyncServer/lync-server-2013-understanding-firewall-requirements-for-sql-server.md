---
title: 'Lync Server 2013: Compreendendo os requisitos de firewall para Servidor SQL'
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
ms.openlocfilehash: dba3296ee01f997857660d2a3f328f663d32cf99
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="7cffb-102">Compreendendo os requisitos de firewall para Servidor SQL com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cffb-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cffb-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7cffb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7cffb-104">Para uma implantação de edição padrão, as exceções de firewall são criadas automaticamente durante a instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cffb-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="7cffb-105">No entanto, para implantações do Enterprise Edition, você deve configurar as exceções de firewall manualmente no servidor back-end do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cffb-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="7cffb-106">O protocolo TCP/IP permite que uma determinada porta seja usada uma vez para um determinado endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7cffb-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="7cffb-107">Isso significa que, para o servidor baseado no SQL Server, você pode atribuir à instância de banco de dados padrão a porta TCP 1433.</span><span class="sxs-lookup"><span data-stu-id="7cffb-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="7cffb-108">Para quaisquer outros casos, você precisará usar o Gerenciador de configuração do SQL Server para atribuir portas exclusivas e não utilizadas.</span><span class="sxs-lookup"><span data-stu-id="7cffb-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="7cffb-109">Este tópico aborda:</span><span class="sxs-lookup"><span data-stu-id="7cffb-109">This topic covers:</span></span>

  - <span data-ttu-id="7cffb-110">Requisitos para uma exceção de firewall ao usar a instância padrão</span><span class="sxs-lookup"><span data-stu-id="7cffb-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="7cffb-111">Requisitos para uma exceção de firewall para o serviço do navegador do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7cffb-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="7cffb-112">Requisitos para portas de escuta estática ao usar instâncias nomeadas</span><span class="sxs-lookup"><span data-stu-id="7cffb-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="7cffb-113">Requisitos para uma exceção de firewall ao usar a instância padrão</span><span class="sxs-lookup"><span data-stu-id="7cffb-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="7cffb-114">Se você estiver usando a instância padrão do SQL Server para qualquer banco de dados ao implantar o Lync Server 2013, os seguintes requisitos de regra de firewall são usados para ajudar a garantir a comunicação do pool de front-ends para a instância padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cffb-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cffb-115">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7cffb-115">Protocol</span></span></th>
<th><span data-ttu-id="7cffb-116">Porta</span><span class="sxs-lookup"><span data-stu-id="7cffb-116">Port</span></span></th>
<th><span data-ttu-id="7cffb-117">Direção</span><span class="sxs-lookup"><span data-stu-id="7cffb-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cffb-118">TCP</span><span class="sxs-lookup"><span data-stu-id="7cffb-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="7cffb-119">1433</span><span class="sxs-lookup"><span data-stu-id="7cffb-119">1433</span></span></p></td>
<td><p><span data-ttu-id="7cffb-120">Entrada do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7cffb-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="7cffb-121">Requisitos para uma exceção de firewall para o serviço do navegador do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7cffb-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="7cffb-122">O serviço de navegador do SQL Server localizará instâncias de banco de dados e comunicará a porta que a instância (nomeada ou padrão) está configurada para usar.</span><span class="sxs-lookup"><span data-stu-id="7cffb-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cffb-123">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7cffb-123">Protocol</span></span></th>
<th><span data-ttu-id="7cffb-124">Porta</span><span class="sxs-lookup"><span data-stu-id="7cffb-124">Port</span></span></th>
<th><span data-ttu-id="7cffb-125">Direção</span><span class="sxs-lookup"><span data-stu-id="7cffb-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cffb-126">UDP</span><span class="sxs-lookup"><span data-stu-id="7cffb-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="7cffb-127">1434</span><span class="sxs-lookup"><span data-stu-id="7cffb-127">1434</span></span></p></td>
<td><p><span data-ttu-id="7cffb-128">Entrada</span><span class="sxs-lookup"><span data-stu-id="7cffb-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="7cffb-129">Requisitos para portas de escuta estática ao usar instâncias nomeadas</span><span class="sxs-lookup"><span data-stu-id="7cffb-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="7cffb-130">Ao usar instâncias nomeadas na configuração do SQL Server para bancos de dados que ofereçam suporte ao Lync Server 2013, você configura portas estáticas usando o Gerenciador de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cffb-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="7cffb-131">Após a atribuição das portas estáticas a cada instância nomeada, você cria exceções para cada porta estática do firewall.</span><span class="sxs-lookup"><span data-stu-id="7cffb-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cffb-132">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7cffb-132">Protocol</span></span></th>
<th><span data-ttu-id="7cffb-133">Porta</span><span class="sxs-lookup"><span data-stu-id="7cffb-133">Port</span></span></th>
<th><span data-ttu-id="7cffb-134">Direção</span><span class="sxs-lookup"><span data-stu-id="7cffb-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cffb-135">TCP</span><span class="sxs-lookup"><span data-stu-id="7cffb-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="7cffb-136">Definido estaticamente</span><span class="sxs-lookup"><span data-stu-id="7cffb-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="7cffb-137">Entrada</span><span class="sxs-lookup"><span data-stu-id="7cffb-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="7cffb-138">Documentação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7cffb-138">SQL Server Documentation</span></span>

<span data-ttu-id="7cffb-139">A documentação do Microsoft SQL Server 2012 fornece orientações detalhadas sobre como configurar o acesso do firewall para bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="7cffb-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="7cffb-140">Para obter detalhes sobre o Microsoft SQL Server 2012, consulte "Configurando o Firewall do Windows para permitir [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)o acesso ao SQL Server" em.</span><span class="sxs-lookup"><span data-stu-id="7cffb-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

