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
ms.openlocfilehash: 02995141dfad6e91089fb80c7e9b09e4ef554edb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="a885d-102">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a885d-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a885d-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="a885d-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="a885d-104">A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.</span><span class="sxs-lookup"><span data-stu-id="a885d-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="a885d-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="a885d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a885d-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="a885d-106">Column</span></span></th>
<th><span data-ttu-id="a885d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="a885d-107">Type</span></span></th>
<th><span data-ttu-id="a885d-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="a885d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a885d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a885d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="a885d-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="a885d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="a885d-111">GUID principal do domínio em monitoramento.</span><span class="sxs-lookup"><span data-stu-id="a885d-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a885d-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="a885d-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="a885d-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="a885d-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="a885d-114">FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para sincronização dos serviços de domínio do Active Directory. Tem valor informativo.</span><span class="sxs-lookup"><span data-stu-id="a885d-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a885d-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="a885d-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="a885d-116">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="a885d-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="a885d-117">Cookie da Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a885d-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a885d-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a885d-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="a885d-119">datetime</span><span class="sxs-lookup"><span data-stu-id="a885d-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="a885d-120">Carimbo de data/hora com a data/hora de atualização da linha.</span><span class="sxs-lookup"><span data-stu-id="a885d-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a885d-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="a885d-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="a885d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a885d-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="a885d-p101">Tempo até que a linha seja bloqueada para alterações. Isso faz parte de um mecanismo de interloque do software que garante que apenas um dos Servidores de Chat faça a sincronização do Active Directory por vez.</span><span class="sxs-lookup"><span data-stu-id="a885d-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a885d-125">Chaves</span><span class="sxs-lookup"><span data-stu-id="a885d-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a885d-126">Coluna (s)</span><span class="sxs-lookup"><span data-stu-id="a885d-126">Column(s)</span></span></th>
<th><span data-ttu-id="a885d-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="a885d-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a885d-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a885d-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="a885d-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="a885d-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a885d-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a885d-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="a885d-131">Chave estrangeira com pesquisa na tabela Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="a885d-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

