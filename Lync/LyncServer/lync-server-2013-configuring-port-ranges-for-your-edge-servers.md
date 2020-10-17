---
title: 'Lync Server 2013: Configurando intervalos de portas para seus servidores de borda'
description: 'Lync Server 2013: Configurando intervalos de portas para seus servidores de borda.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c085a5dbc32bbf56842984eae2ef8896ab895c65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548247"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="e525b-103">Configurando intervalos de portas para seus servidores de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e525b-103">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e525b-104">_**Última modificação do tópico:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="e525b-104">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="e525b-105">Com servidores de borda, você não precisa configurar intervalos de porta separados para compartilhamento de áudio, vídeo e aplicativos; da mesma forma, os intervalos de portas usados para servidores de borda não precisam corresponder aos intervalos de porta usados com seus servidores de conferência, aplicativo e de mediação.</span><span class="sxs-lookup"><span data-stu-id="e525b-105">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="e525b-106">Antes de prosseguir com o nosso exemplo, é importante enfatizar que, enquanto essa opção existe, recomendamos que você não altere os intervalos de porta, pois isso pode afetar adversamente alguns cenários se você sair do intervalo de porta 50000.</span><span class="sxs-lookup"><span data-stu-id="e525b-106">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="e525b-107">Por exemplo, suponha que você tenha configurado seus servidores de conferência, aplicativo e mediação para usar estes intervalos de porta:</span><span class="sxs-lookup"><span data-stu-id="e525b-107">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e525b-108">Tipo de pacote</span><span class="sxs-lookup"><span data-stu-id="e525b-108">Packet Type</span></span></th>
<th><span data-ttu-id="e525b-109">Porta inicial</span><span class="sxs-lookup"><span data-stu-id="e525b-109">Starting Port</span></span></th>
<th><span data-ttu-id="e525b-110">Número de portas reservadas</span><span class="sxs-lookup"><span data-stu-id="e525b-110">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e525b-111">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e525b-111">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="e525b-112">40803</span><span class="sxs-lookup"><span data-stu-id="e525b-112">40803</span></span></p></td>
<td><p><span data-ttu-id="e525b-113">8348</span><span class="sxs-lookup"><span data-stu-id="e525b-113">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e525b-114">Áudio</span><span class="sxs-lookup"><span data-stu-id="e525b-114">Audio</span></span></p></td>
<td><p><span data-ttu-id="e525b-115">49152</span><span class="sxs-lookup"><span data-stu-id="e525b-115">49152</span></span></p></td>
<td><p><span data-ttu-id="e525b-116">8348</span><span class="sxs-lookup"><span data-stu-id="e525b-116">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e525b-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="e525b-117">Video</span></span></p></td>
<td><p><span data-ttu-id="e525b-118">57500</span><span class="sxs-lookup"><span data-stu-id="e525b-118">57500</span></span></p></td>
<td><p><span data-ttu-id="e525b-119">8034</span><span class="sxs-lookup"><span data-stu-id="e525b-119">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e525b-120"><strong>Totais</strong></span><span class="sxs-lookup"><span data-stu-id="e525b-120"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="e525b-121">24730</span><span class="sxs-lookup"><span data-stu-id="e525b-121">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e525b-122">Como você pode ver, os intervalos de porta para o compartilhamento de áudio, vídeo e aplicativos começam na porta 40803 e englobam um total de 24732 portas.</span><span class="sxs-lookup"><span data-stu-id="e525b-122">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="e525b-123">Se preferir, você poderá configurar um servidor de borda específico para que use esses valores de portas gerais executando um comando semelhante a este no Shell de Gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="e525b-123">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="e525b-124">Ou use o comando a seguir para configurar simultaneamente todos os servidores de borda na organização:</span><span class="sxs-lookup"><span data-stu-id="e525b-124">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="e525b-125">Você pode verificar as configurações de porta atuais para seus servidores de borda usando este comando do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="e525b-125">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="e525b-126">Novamente, embora forneçamos essas opções, recomendamos que você deixe as coisas como elas são para a configuração de porta.</span><span class="sxs-lookup"><span data-stu-id="e525b-126">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

