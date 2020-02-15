---
title: Apresentação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3674742cedbdfb267326e0170703f3fbc3ba3b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="52c37-102">Introdução</span><span class="sxs-lookup"><span data-stu-id="52c37-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52c37-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="52c37-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="52c37-104">A ferramenta de desempenho e stress do Lync Server 2013 (chamada de LyncPerfTool) pode simular a carga de usuário dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="52c37-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c37-105">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="52c37-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="52c37-106">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="52c37-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c37-107">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="52c37-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="52c37-108">Voz sobre IP (VoIP), incluindo simulação de rede telefônica pública comutada (PSTN)</span><span class="sxs-lookup"><span data-stu-id="52c37-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c37-109">Conferência de cliente de acesso Web</span><span class="sxs-lookup"><span data-stu-id="52c37-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="52c37-110">Microsoft Lync 2013 Attendant</span><span class="sxs-lookup"><span data-stu-id="52c37-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c37-111">Grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="52c37-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="52c37-112">Expansão de lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="52c37-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c37-113">Consulta catálogo de endereços e catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="52c37-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="52c37-114">Enhanced 9-1-1 (E9-1-1) chamadas e perfil de local (plano de discagem)</span><span class="sxs-lookup"><span data-stu-id="52c37-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c37-115">Múltipla</span><span class="sxs-lookup"><span data-stu-id="52c37-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="52c37-116">Exibir vários fluxos de uma conferência</span><span class="sxs-lookup"><span data-stu-id="52c37-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52c37-117">A ferramenta de desempenho e stress do Lync Server 2013 oferece suporte à geração e à Federação de carga entre pools por meio de uma configuração avançada apenas.</span><span class="sxs-lookup"><span data-stu-id="52c37-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="52c37-118">A ferramenta também não simula a carga do usuário para os seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="52c37-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="52c37-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="52c37-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="52c37-120">Chat persistente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="52c37-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="52c37-121">Como resultado, a ferramenta de estresse e desempenho do Lync Server 2013 não dará suporte ao teste dos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="52c37-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="52c37-122">Chat persistente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="52c37-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="52c37-123">Cenários de integração do Exchange</span><span class="sxs-lookup"><span data-stu-id="52c37-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="52c37-124">Aplicativos e arquivos incluídos na ferramenta de estresse e desempenho do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52c37-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="52c37-125">Os seguintes aplicativos estão incluídos na ferramenta de estresse e desempenho do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="52c37-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c37-126">Ferramenta</span><span class="sxs-lookup"><span data-stu-id="52c37-126">Tool</span></span></th>
<th><span data-ttu-id="52c37-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="52c37-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c37-128">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="52c37-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="52c37-129">A ferramenta de provisionamento de usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52c37-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="52c37-130">Essa ferramenta é usada para criar usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="52c37-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c37-131">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="52c37-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="52c37-132">A ferramenta de configuração de carregamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52c37-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="52c37-133">Essa ferramenta é usada para configurar as características da carga de usuário para simular.</span><span class="sxs-lookup"><span data-stu-id="52c37-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c37-134">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="52c37-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="52c37-135">A ferramenta de desempenho e stress do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52c37-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="52c37-136">LyncPerfTool é a ferramenta que simula a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="52c37-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c37-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="52c37-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="52c37-138">O default. TMX é necessário para usar a ferramenta de registro em log do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52c37-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c37-139">Exemplo de scripts de provisionamento</span><span class="sxs-lookup"><span data-stu-id="52c37-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="52c37-140">Estes exemplos são usados para configurar a topologia para executar testes de carga, com base em cenários específicos</span><span class="sxs-lookup"><span data-stu-id="52c37-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

