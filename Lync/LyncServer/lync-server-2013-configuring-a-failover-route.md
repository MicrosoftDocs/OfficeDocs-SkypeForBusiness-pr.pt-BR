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
ms.openlocfilehash: 17477c647d2e5dd5918225486c43b93a29509fb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="b4fc9-102">Configurando uma rota de failover no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4fc9-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4fc9-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b4fc9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b4fc9-p101">O exemplo abaixo mostra como um administrador pode definir uma rota de failover para utilizar se o Dallas-GW1 for desativado para manutenção ou estiver indisponível por qualquer outro motivo. As seguintes tabelas ilustram a alteração de configuração necessária.</span><span class="sxs-lookup"><span data-stu-id="b4fc9-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="b4fc9-p102">Tabela 1. Política de usuário</span><span class="sxs-lookup"><span data-stu-id="b4fc9-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4fc9-108">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="b4fc9-108">User policy</span></span></th>
<th><span data-ttu-id="b4fc9-109">Uso do telefone</span><span class="sxs-lookup"><span data-stu-id="b4fc9-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4fc9-110">Política de Chamada Padrão</span><span class="sxs-lookup"><span data-stu-id="b4fc9-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-111">Local</span><span class="sxs-lookup"><span data-stu-id="b4fc9-111">Local</span></span></p>
<p><span data-ttu-id="b4fc9-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="b4fc9-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4fc9-113">Política Local de Redmond</span><span class="sxs-lookup"><span data-stu-id="b4fc9-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="b4fc9-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4fc9-115">Política de Chamada de Dallas</span><span class="sxs-lookup"><span data-stu-id="b4fc9-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="b4fc9-116">DallasUsers</span></span></p>
<p><span data-ttu-id="b4fc9-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="b4fc9-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="b4fc9-p103">Tabela 2. Rotas</span><span class="sxs-lookup"><span data-stu-id="b4fc9-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="b4fc9-120">Nome da rota</span><span class="sxs-lookup"><span data-stu-id="b4fc9-120">Route name</span></span></th>
<th><span data-ttu-id="b4fc9-121">Padrão de número</span><span class="sxs-lookup"><span data-stu-id="b4fc9-121">Number pattern</span></span></th>
<th><span data-ttu-id="b4fc9-122">Uso do telefone</span><span class="sxs-lookup"><span data-stu-id="b4fc9-122">Phone usage</span></span></th>
<th><span data-ttu-id="b4fc9-123">Trunk</span><span class="sxs-lookup"><span data-stu-id="b4fc9-123">Trunk</span></span></th>
<th><span data-ttu-id="b4fc9-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="b4fc9-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4fc9-125">Rota Local de Redmond</span><span class="sxs-lookup"><span data-stu-id="b4fc9-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b4fc9-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-127">Local</span><span class="sxs-lookup"><span data-stu-id="b4fc9-127">Local</span></span></p>
<p><span data-ttu-id="b4fc9-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="b4fc9-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-129">Trunk1</span></span></p>
<p><span data-ttu-id="b4fc9-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="b4fc9-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-131">Vermelho-GW1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-131">Red-GW1</span></span></p>
<p><span data-ttu-id="b4fc9-132">Vermelho-GW2</span><span class="sxs-lookup"><span data-stu-id="b4fc9-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4fc9-133">Rota Local de Dallas</span><span class="sxs-lookup"><span data-stu-id="b4fc9-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b4fc9-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-135">Local</span><span class="sxs-lookup"><span data-stu-id="b4fc9-135">Local</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="b4fc9-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4fc9-138">Rota Universal</span><span class="sxs-lookup"><span data-stu-id="b4fc9-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="b4fc9-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="b4fc9-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-141">Trunk1</span></span></p>
<p><span data-ttu-id="b4fc9-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="b4fc9-142">Trunk2</span></span></p>
<p><span data-ttu-id="b4fc9-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="b4fc9-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-144">Vermelho-GW1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-144">Red-GW1</span></span></p>
<p><span data-ttu-id="b4fc9-145">Vermelho-GW2</span><span class="sxs-lookup"><span data-stu-id="b4fc9-145">Red-GW2</span></span></p>
<p><span data-ttu-id="b4fc9-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4fc9-147">Rota de Usuários de Dallas</span><span class="sxs-lookup"><span data-stu-id="b4fc9-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="b4fc9-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="b4fc9-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="b4fc9-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="b4fc9-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="b4fc9-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b4fc9-p104">Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="b4fc9-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

