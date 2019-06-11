---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="40991-102">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40991-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40991-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="40991-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="40991-104">tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="40991-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="40991-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="40991-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40991-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="40991-106">Column</span></span></th>
<th><span data-ttu-id="40991-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="40991-107">Type</span></span></th>
<th><span data-ttu-id="40991-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="40991-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40991-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="40991-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="40991-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="40991-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="40991-111">GUID principal do domínio que está sendo monitorado.</span><span class="sxs-lookup"><span data-stu-id="40991-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40991-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="40991-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="40991-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="40991-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="40991-114">FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para a sincronização dos serviços de domínio Active Directory. Tem valor informativo.</span><span class="sxs-lookup"><span data-stu-id="40991-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40991-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="40991-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="40991-116">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="40991-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="40991-117">Cookie de sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="40991-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40991-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="40991-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="40991-119">datetime</span><span class="sxs-lookup"><span data-stu-id="40991-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="40991-120">Carimbo de data/hora com o tempo de atualização de linha.</span><span class="sxs-lookup"><span data-stu-id="40991-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40991-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="40991-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="40991-122">datetime</span><span class="sxs-lookup"><span data-stu-id="40991-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="40991-123">Tempo até que a linha esteja bloqueada para alterações.</span><span class="sxs-lookup"><span data-stu-id="40991-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="40991-124">Isso faz parte de um mecanismo de travamento do software que garante que apenas um dos serviços de chat faça a sincronização do Active Directory de cada vez.</span><span class="sxs-lookup"><span data-stu-id="40991-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="40991-125">As</span><span class="sxs-lookup"><span data-stu-id="40991-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40991-126">Coluna (s)</span><span class="sxs-lookup"><span data-stu-id="40991-126">Column(s)</span></span></th>
<th><span data-ttu-id="40991-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="40991-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40991-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="40991-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="40991-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="40991-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40991-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="40991-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="40991-131">Chave estrangeira com pesquisa na tabela principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="40991-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

