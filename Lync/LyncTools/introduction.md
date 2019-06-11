---
title: Introdução
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="a8450-102">Introdução</span><span class="sxs-lookup"><span data-stu-id="a8450-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8450-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a8450-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a8450-104">A ferramenta de stress e desempenho do Lync Server 2013 (conhecida como LyncPerfTool) pode simular a carga do usuário dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="a8450-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8450-105">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="a8450-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="a8450-106">Conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="a8450-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8450-107">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a8450-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a8450-108">Voz sobre IP (VoIP), incluindo simulação de rede telefônica pública comutada (PSTN)</span><span class="sxs-lookup"><span data-stu-id="a8450-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8450-109">Conferência de cliente de acesso Web</span><span class="sxs-lookup"><span data-stu-id="a8450-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="a8450-110">Microsoft Lync 2013 Attendant</span><span class="sxs-lookup"><span data-stu-id="a8450-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8450-111">Grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="a8450-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="a8450-112">Expansão da lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="a8450-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8450-113">Consulta de download e catálogo de endereços do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="a8450-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="a8450-114">Avançado 9-1-1 (E9-1-1) chamadas e perfil de local (plano de discagem)</span><span class="sxs-lookup"><span data-stu-id="a8450-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8450-115">Múltipla</span><span class="sxs-lookup"><span data-stu-id="a8450-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="a8450-116">Exibir vários fluxos de uma conferência</span><span class="sxs-lookup"><span data-stu-id="a8450-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a8450-117">A ferramenta de stress e desempenho do Lync Server 2013 oferece suporte à geração e agrupamento de carga entre pools somente com a configuração avançada.</span><span class="sxs-lookup"><span data-stu-id="a8450-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="a8450-118">A ferramenta também não simula a carga do usuário para os seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="a8450-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="a8450-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="a8450-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="a8450-120">Chat persistente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a8450-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="a8450-121">Como resultado, a ferramenta de stress e desempenho do Lync Server 2013 não será compatível com o teste dos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="a8450-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="a8450-122">Chat persistente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a8450-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="a8450-123">Cenários de integração do Exchange</span><span class="sxs-lookup"><span data-stu-id="a8450-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="a8450-124">Aplicativos e arquivos incluídos na ferramenta de stress e desempenho do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8450-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="a8450-125">Os seguintes aplicativos estão incluídos na ferramenta de stress e desempenho do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a8450-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8450-126">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="a8450-126">Tool</span></span></th>
<th><span data-ttu-id="a8450-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="a8450-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8450-128">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="a8450-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="a8450-129">A ferramenta de provisionamento de usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8450-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="a8450-130">Esta ferramenta é usada para criar usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="a8450-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8450-131">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="a8450-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="a8450-132">A ferramenta de configuração de carregamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8450-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="a8450-133">Esta ferramenta é usada para configurar as características da carga de usuário a ser simulada.</span><span class="sxs-lookup"><span data-stu-id="a8450-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8450-134">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="a8450-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="a8450-135">A ferramenta de stress e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8450-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="a8450-136">LyncPerfTool é a ferramenta que simula a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8450-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8450-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="a8450-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="a8450-138">Default. TMX é necessário para usar a ferramenta de log do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8450-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8450-139">Exemplo de scripts de provisionamento</span><span class="sxs-lookup"><span data-stu-id="a8450-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="a8450-140">Esses exemplos são usados para configurar a topologia para executar testes de carga com base em cenários específicos</span><span class="sxs-lookup"><span data-stu-id="a8450-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

