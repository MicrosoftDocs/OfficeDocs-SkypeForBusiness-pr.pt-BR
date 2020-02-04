---
title: 'Lync Server 2013: Configurando intervalos de porta para seus servidores de borda'
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
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="2cdcf-102">Configurando intervalos de porta para seus servidores de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cdcf-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cdcf-103">_**Tópico da última modificação:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="2cdcf-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="2cdcf-104">Com os servidores de borda, você não precisa configurar intervalos de porta separados para compartilhamento de áudio, vídeo e aplicativos; da mesma forma, os intervalos de porta usados para servidores de borda não precisam corresponder aos intervalos de porta usados com os servidores de conferência, aplicativo e mediação.</span><span class="sxs-lookup"><span data-stu-id="2cdcf-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="2cdcf-105">Antes de continuarmos com o nosso exemplo, é importante enfatizar que, enquanto essa opção existe, recomendamos que você não altere os intervalos de porta, pois isso pode afetar negativamente alguns cenários se você sair do intervalo de porta 50000.</span><span class="sxs-lookup"><span data-stu-id="2cdcf-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="2cdcf-106">Por exemplo, suponha que você tenha configurado seus servidores de conferência, aplicativo e mediação para usar estes intervalos de porta:</span><span class="sxs-lookup"><span data-stu-id="2cdcf-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cdcf-107">Tipo de pacote</span><span class="sxs-lookup"><span data-stu-id="2cdcf-107">Packet Type</span></span></th>
<th><span data-ttu-id="2cdcf-108">Porta inicial</span><span class="sxs-lookup"><span data-stu-id="2cdcf-108">Starting Port</span></span></th>
<th><span data-ttu-id="2cdcf-109">Número de portas reservadas</span><span class="sxs-lookup"><span data-stu-id="2cdcf-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cdcf-110">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2cdcf-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="2cdcf-111">40803</span><span class="sxs-lookup"><span data-stu-id="2cdcf-111">40803</span></span></p></td>
<td><p><span data-ttu-id="2cdcf-112">8348</span><span class="sxs-lookup"><span data-stu-id="2cdcf-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cdcf-113">Áudio</span><span class="sxs-lookup"><span data-stu-id="2cdcf-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="2cdcf-114">49152</span><span class="sxs-lookup"><span data-stu-id="2cdcf-114">49152</span></span></p></td>
<td><p><span data-ttu-id="2cdcf-115">8348</span><span class="sxs-lookup"><span data-stu-id="2cdcf-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cdcf-116">Vídeo</span><span class="sxs-lookup"><span data-stu-id="2cdcf-116">Video</span></span></p></td>
<td><p><span data-ttu-id="2cdcf-117">57500</span><span class="sxs-lookup"><span data-stu-id="2cdcf-117">57500</span></span></p></td>
<td><p><span data-ttu-id="2cdcf-118">8034</span><span class="sxs-lookup"><span data-stu-id="2cdcf-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cdcf-119"><strong>Totais</strong></span><span class="sxs-lookup"><span data-stu-id="2cdcf-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="2cdcf-120">24730</span><span class="sxs-lookup"><span data-stu-id="2cdcf-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2cdcf-121">Como você pode ver, os intervalos de portabilidade de áudio, vídeo e compartilhamento de aplicativos começam na porta 40803 e englobam um total de 24732 portas.</span><span class="sxs-lookup"><span data-stu-id="2cdcf-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="2cdcf-122">Se preferir, você pode configurar um servidor de borda específico para usar esses valores de porta gerais executando um comando semelhante a este de dentro do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2cdcf-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="2cdcf-123">Ou use o seguinte comando para configurar simultaneamente todos os servidores de borda em sua organização:</span><span class="sxs-lookup"><span data-stu-id="2cdcf-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="2cdcf-124">Você pode verificar as configurações de porta atuais para seus servidores de borda usando o comando do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2cdcf-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="2cdcf-125">Novamente, enquanto fornecemos essas opções, recomendamos que você deixe as coisas como elas são para a configuração de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="2cdcf-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

