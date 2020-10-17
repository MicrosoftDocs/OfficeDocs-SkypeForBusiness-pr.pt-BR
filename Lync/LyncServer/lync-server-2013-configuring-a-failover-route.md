---
title: 'Lync Server 2013: Configurando uma rota de failover'
description: 'Lync Server 2013: Configurando uma rota de failover.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560487"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="bc77c-103">Configurando uma rota de failover no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc77c-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc77c-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="bc77c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="bc77c-p101">O exemplo abaixo mostra como um administrador pode definir uma rota de failover para utilizar se o Dallas-GW1 for desativado para manutenção ou estiver indisponível por qualquer outro motivo. As seguintes tabelas ilustram a alteração de configuração necessária.</span><span class="sxs-lookup"><span data-stu-id="bc77c-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="bc77c-p102">Tabela 1. Política de usuário</span><span class="sxs-lookup"><span data-stu-id="bc77c-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc77c-109">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="bc77c-109">User policy</span></span></th>
<th><span data-ttu-id="bc77c-110">Uso do telefone</span><span class="sxs-lookup"><span data-stu-id="bc77c-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc77c-111">Política de Chamada Padrão</span><span class="sxs-lookup"><span data-stu-id="bc77c-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="bc77c-112">Local</span><span class="sxs-lookup"><span data-stu-id="bc77c-112">Local</span></span></p>
<p><span data-ttu-id="bc77c-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="bc77c-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc77c-114">Política Local de Redmond</span><span class="sxs-lookup"><span data-stu-id="bc77c-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="bc77c-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="bc77c-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc77c-116">Política de Chamada de Dallas</span><span class="sxs-lookup"><span data-stu-id="bc77c-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="bc77c-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="bc77c-117">DallasUsers</span></span></p>
<p><span data-ttu-id="bc77c-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="bc77c-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="bc77c-p103">Tabela 2. Rotas</span><span class="sxs-lookup"><span data-stu-id="bc77c-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc77c-121">Nome da rota</span><span class="sxs-lookup"><span data-stu-id="bc77c-121">Route name</span></span></th>
<th><span data-ttu-id="bc77c-122">Padrão de número</span><span class="sxs-lookup"><span data-stu-id="bc77c-122">Number pattern</span></span></th>
<th><span data-ttu-id="bc77c-123">Uso do telefone</span><span class="sxs-lookup"><span data-stu-id="bc77c-123">Phone usage</span></span></th>
<th><span data-ttu-id="bc77c-124">Trunk</span><span class="sxs-lookup"><span data-stu-id="bc77c-124">Trunk</span></span></th>
<th><span data-ttu-id="bc77c-125">Gateway</span><span class="sxs-lookup"><span data-stu-id="bc77c-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc77c-126">Rota Local de Redmond</span><span class="sxs-lookup"><span data-stu-id="bc77c-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="bc77c-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="bc77c-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="bc77c-128">Local</span><span class="sxs-lookup"><span data-stu-id="bc77c-128">Local</span></span></p>
<p><span data-ttu-id="bc77c-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="bc77c-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="bc77c-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="bc77c-130">Trunk1</span></span></p>
<p><span data-ttu-id="bc77c-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="bc77c-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="bc77c-132">Vermelho-GW1</span><span class="sxs-lookup"><span data-stu-id="bc77c-132">Red-GW1</span></span></p>
<p><span data-ttu-id="bc77c-133">Vermelho-GW2</span><span class="sxs-lookup"><span data-stu-id="bc77c-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc77c-134">Rota Local de Dallas</span><span class="sxs-lookup"><span data-stu-id="bc77c-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="bc77c-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="bc77c-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="bc77c-136">Local</span><span class="sxs-lookup"><span data-stu-id="bc77c-136">Local</span></span></p></td>
<td><p><span data-ttu-id="bc77c-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="bc77c-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="bc77c-138">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="bc77c-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc77c-139">Rota Universal</span><span class="sxs-lookup"><span data-stu-id="bc77c-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="bc77c-140">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="bc77c-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="bc77c-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="bc77c-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="bc77c-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="bc77c-142">Trunk1</span></span></p>
<p><span data-ttu-id="bc77c-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="bc77c-143">Trunk2</span></span></p>
<p><span data-ttu-id="bc77c-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="bc77c-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="bc77c-145">Vermelho-GW1</span><span class="sxs-lookup"><span data-stu-id="bc77c-145">Red-GW1</span></span></p>
<p><span data-ttu-id="bc77c-146">Vermelho-GW2</span><span class="sxs-lookup"><span data-stu-id="bc77c-146">Red-GW2</span></span></p>
<p><span data-ttu-id="bc77c-147">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="bc77c-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc77c-148">Rota de Usuários de Dallas</span><span class="sxs-lookup"><span data-stu-id="bc77c-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="bc77c-149">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="bc77c-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="bc77c-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="bc77c-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="bc77c-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="bc77c-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="bc77c-152">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="bc77c-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bc77c-p104">Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="bc77c-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

