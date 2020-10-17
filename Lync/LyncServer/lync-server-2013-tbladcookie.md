---
title: 'Lync Server 2013: tblADCookie'
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
ms.openlocfilehash: bf372f3dfc39f3ca90cbe0019af09e8d9dd33d26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509508"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="9f314-102">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f314-102">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f314-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9f314-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9f314-104">A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.</span><span class="sxs-lookup"><span data-stu-id="9f314-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="9f314-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="9f314-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f314-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="9f314-106">Column</span></span></th>
<th><span data-ttu-id="9f314-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f314-107">Type</span></span></th>
<th><span data-ttu-id="9f314-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f314-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f314-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9f314-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="9f314-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="9f314-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9f314-111">GUID principal do domínio em monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9f314-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f314-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="9f314-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="9f314-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="9f314-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="9f314-114">FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para sincronização dos serviços de domínio do Active Directory. Tem valor informativo.</span><span class="sxs-lookup"><span data-stu-id="9f314-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f314-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="9f314-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="9f314-116">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="9f314-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="9f314-117">Cookie da Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f314-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f314-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="9f314-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="9f314-119">datetime</span><span class="sxs-lookup"><span data-stu-id="9f314-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f314-120">Carimbo de data/hora com a data/hora de atualização da linha.</span><span class="sxs-lookup"><span data-stu-id="9f314-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f314-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="9f314-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="9f314-122">datetime</span><span class="sxs-lookup"><span data-stu-id="9f314-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f314-p101">Tempo até que a linha seja bloqueada para alterações. Isso faz parte de um mecanismo de interloque do software que garante que apenas um dos Servidores de Chat faça a sincronização do Active Directory por vez.</span><span class="sxs-lookup"><span data-stu-id="9f314-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9f314-125">Chaves</span><span class="sxs-lookup"><span data-stu-id="9f314-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f314-126">Coluna (s)</span><span class="sxs-lookup"><span data-stu-id="9f314-126">Column(s)</span></span></th>
<th><span data-ttu-id="9f314-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f314-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f314-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9f314-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="9f314-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="9f314-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f314-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9f314-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="9f314-131">Chave estrangeira com pesquisa na tabela Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="9f314-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

