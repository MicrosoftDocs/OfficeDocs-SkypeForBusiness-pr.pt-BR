---
title: Introdução
description: Inicial.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565277"
---
# <a name="introduction"></a><span data-ttu-id="bd098-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="bd098-103">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd098-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="bd098-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="bd098-105">A ferramenta de desempenho e stress do Lync Server 2013 (chamada de LyncPerfTool) pode simular a carga de usuário dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="bd098-105">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd098-106">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="bd098-106">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="bd098-107">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="bd098-107">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd098-108">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="bd098-108">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bd098-109">Voz sobre IP (VoIP), incluindo simulação de rede telefônica pública comutada (PSTN)</span><span class="sxs-lookup"><span data-stu-id="bd098-109">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd098-110">Conferência de cliente de acesso Web</span><span class="sxs-lookup"><span data-stu-id="bd098-110">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="bd098-111">Microsoft Lync 2013 Attendant</span><span class="sxs-lookup"><span data-stu-id="bd098-111">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd098-112">Grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="bd098-112">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="bd098-113">Expansão de lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="bd098-113">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd098-114">Consulta catálogo de endereços e catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="bd098-114">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="bd098-115">Enhanced 9-1-1 (E9-1-1) chamadas e perfil de local (plano de discagem)</span><span class="sxs-lookup"><span data-stu-id="bd098-115">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd098-116">Múltipla</span><span class="sxs-lookup"><span data-stu-id="bd098-116">MultiView</span></span></p></td>
<td><p><span data-ttu-id="bd098-117">Exibir vários fluxos de uma conferência</span><span class="sxs-lookup"><span data-stu-id="bd098-117">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd098-118">A ferramenta de desempenho e stress do Lync Server 2013 oferece suporte à geração e à Federação de carga entre pools por meio de uma configuração avançada apenas.</span><span class="sxs-lookup"><span data-stu-id="bd098-118">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="bd098-119">A ferramenta também não simula a carga do usuário para os seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="bd098-119">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="bd098-120">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="bd098-120">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="bd098-121">Chat persistente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd098-121">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="bd098-122">Como resultado, a ferramenta de estresse e desempenho do Lync Server 2013 não dará suporte ao teste dos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="bd098-122">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="bd098-123">Chat persistente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd098-123">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="bd098-124">Cenários de integração do Exchange</span><span class="sxs-lookup"><span data-stu-id="bd098-124">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="bd098-125">Aplicativos e arquivos incluídos na ferramenta de estresse e desempenho do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd098-125">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="bd098-126">Os seguintes aplicativos estão incluídos na ferramenta de estresse e desempenho do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="bd098-126">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd098-127">Ferramenta</span><span class="sxs-lookup"><span data-stu-id="bd098-127">Tool</span></span></th>
<th><span data-ttu-id="bd098-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="bd098-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd098-129">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="bd098-129">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="bd098-130">A ferramenta de provisionamento de usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd098-130">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="bd098-131">Essa ferramenta é usada para criar usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="bd098-131">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd098-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="bd098-132">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="bd098-133">A ferramenta de configuração de carregamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd098-133">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="bd098-134">Essa ferramenta é usada para configurar as características da carga de usuário para simular.</span><span class="sxs-lookup"><span data-stu-id="bd098-134">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd098-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="bd098-135">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="bd098-136">A ferramenta de desempenho e stress do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd098-136">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="bd098-137">LyncPerfTool é a ferramenta que simula a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="bd098-137">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd098-138">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="bd098-138">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="bd098-139">O default. TMX é necessário para usar a ferramenta de registro em log do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd098-139">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd098-140">Exemplo de scripts de provisionamento</span><span class="sxs-lookup"><span data-stu-id="bd098-140">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="bd098-141">Estes exemplos são usados para configurar a topologia para executar testes de carga, com base em cenários específicos</span><span class="sxs-lookup"><span data-stu-id="bd098-141">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

