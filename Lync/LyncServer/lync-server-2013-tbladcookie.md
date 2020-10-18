---
title: 'Lync Server 2013: tblADCookie'
description: 'Lync Server 2013: tblADCookie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573717"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="6b3f1-103">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b3f1-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b3f1-104">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="6b3f1-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="6b3f1-105">A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="6b3f1-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="6b3f1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b3f1-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="6b3f1-107">Column</span></span></th>
<th><span data-ttu-id="6b3f1-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="6b3f1-108">Type</span></span></th>
<th><span data-ttu-id="6b3f1-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="6b3f1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b3f1-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6b3f1-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-111">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="6b3f1-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-112">GUID principal do domínio em monitoramento.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b3f1-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="6b3f1-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="6b3f1-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-115">FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para sincronização dos serviços de domínio do Active Directory. Tem valor informativo.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b3f1-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="6b3f1-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-117">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="6b3f1-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-118">Cookie da Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b3f1-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="6b3f1-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-120">datetime</span><span class="sxs-lookup"><span data-stu-id="6b3f1-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-121">Carimbo de data/hora com a data/hora de atualização da linha.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b3f1-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="6b3f1-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-123">datetime</span><span class="sxs-lookup"><span data-stu-id="6b3f1-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-p101">Tempo até que a linha seja bloqueada para alterações. Isso faz parte de um mecanismo de interloque do software que garante que apenas um dos Servidores de Chat faça a sincronização do Active Directory por vez.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6b3f1-126">Chaves</span><span class="sxs-lookup"><span data-stu-id="6b3f1-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b3f1-127">Coluna (s)</span><span class="sxs-lookup"><span data-stu-id="6b3f1-127">Column(s)</span></span></th>
<th><span data-ttu-id="6b3f1-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="6b3f1-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b3f1-129">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6b3f1-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-130">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b3f1-131">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6b3f1-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="6b3f1-132">Chave estrangeira com pesquisa na tabela Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="6b3f1-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

