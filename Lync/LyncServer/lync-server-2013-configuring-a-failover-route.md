---
title: 'Lync Server 2013: Configurando uma rota de failover'
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="e92f7-102">Configurando uma rota de failover no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e92f7-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e92f7-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e92f7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e92f7-p101">O exemplo abaixo mostra como um administrador pode definir uma rota de failover para utilizar se o Dallas-GW1 for desativado para manutenção ou estiver indisponível por qualquer outro motivo. As seguintes tabelas ilustram a alteração de configuração necessária.</span><span class="sxs-lookup"><span data-stu-id="e92f7-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="e92f7-p102">Tabela 1. Política de usuário</span><span class="sxs-lookup"><span data-stu-id="e92f7-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e92f7-108">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="e92f7-108">User policy</span></span></th>
<th><span data-ttu-id="e92f7-109">Uso do telefone</span><span class="sxs-lookup"><span data-stu-id="e92f7-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e92f7-110">Política de Chamada Padrão</span><span class="sxs-lookup"><span data-stu-id="e92f7-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="e92f7-111">Local</span><span class="sxs-lookup"><span data-stu-id="e92f7-111">Local</span></span></p>
<p><span data-ttu-id="e92f7-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="e92f7-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e92f7-113">Política Local de Redmond</span><span class="sxs-lookup"><span data-stu-id="e92f7-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="e92f7-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="e92f7-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e92f7-115">Política de Chamada de Dallas</span><span class="sxs-lookup"><span data-stu-id="e92f7-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="e92f7-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="e92f7-116">DallasUsers</span></span></p>
<p><span data-ttu-id="e92f7-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="e92f7-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="e92f7-p103">Tabela 2. Rotas</span><span class="sxs-lookup"><span data-stu-id="e92f7-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="e92f7-120">Nome da rota</span><span class="sxs-lookup"><span data-stu-id="e92f7-120">Route name</span></span></th>
<th><span data-ttu-id="e92f7-121">Padrão do número</span><span class="sxs-lookup"><span data-stu-id="e92f7-121">Number pattern</span></span></th>
<th><span data-ttu-id="e92f7-122">Uso do telefone</span><span class="sxs-lookup"><span data-stu-id="e92f7-122">Phone usage</span></span></th>
<th><span data-ttu-id="e92f7-123">Tronco</span><span class="sxs-lookup"><span data-stu-id="e92f7-123">Trunk</span></span></th>
<th><span data-ttu-id="e92f7-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="e92f7-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e92f7-125">Rota Local de Redmond</span><span class="sxs-lookup"><span data-stu-id="e92f7-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="e92f7-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e92f7-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e92f7-127">Local</span><span class="sxs-lookup"><span data-stu-id="e92f7-127">Local</span></span></p>
<p><span data-ttu-id="e92f7-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="e92f7-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="e92f7-129">Tronco 1</span><span class="sxs-lookup"><span data-stu-id="e92f7-129">Trunk1</span></span></p>
<p><span data-ttu-id="e92f7-130">Tronco 2</span><span class="sxs-lookup"><span data-stu-id="e92f7-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="e92f7-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="e92f7-131">Red-GW1</span></span></p>
<p><span data-ttu-id="e92f7-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="e92f7-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e92f7-133">Rota Local de Dallas</span><span class="sxs-lookup"><span data-stu-id="e92f7-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="e92f7-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e92f7-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e92f7-135">Local</span><span class="sxs-lookup"><span data-stu-id="e92f7-135">Local</span></span></p></td>
<td><p><span data-ttu-id="e92f7-136">Tronco 3</span><span class="sxs-lookup"><span data-stu-id="e92f7-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="e92f7-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="e92f7-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e92f7-138">Rota Universal</span><span class="sxs-lookup"><span data-stu-id="e92f7-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="e92f7-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="e92f7-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="e92f7-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="e92f7-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="e92f7-141">Tronco 1</span><span class="sxs-lookup"><span data-stu-id="e92f7-141">Trunk1</span></span></p>
<p><span data-ttu-id="e92f7-142">Tronco 2</span><span class="sxs-lookup"><span data-stu-id="e92f7-142">Trunk2</span></span></p>
<p><span data-ttu-id="e92f7-143">Tronco 3</span><span class="sxs-lookup"><span data-stu-id="e92f7-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="e92f7-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="e92f7-144">Red-GW1</span></span></p>
<p><span data-ttu-id="e92f7-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="e92f7-145">Red-GW2</span></span></p>
<p><span data-ttu-id="e92f7-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="e92f7-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e92f7-147">Rota de Usuários de Dallas</span><span class="sxs-lookup"><span data-stu-id="e92f7-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="e92f7-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="e92f7-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="e92f7-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="e92f7-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="e92f7-150">Tronco 3</span><span class="sxs-lookup"><span data-stu-id="e92f7-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="e92f7-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="e92f7-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e92f7-p104">Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="e92f7-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

