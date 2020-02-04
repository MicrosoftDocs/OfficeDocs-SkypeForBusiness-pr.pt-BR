---
title: 'Lync Server 2013: Configurando cenários de exemplo de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="7d2fb-102">Configurar cenários de exemplo de vídeo para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d2fb-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d2fb-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7d2fb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7d2fb-104">O Lync 2013 adiciona novos recursos de vídeo para dar suporte a 1920 x 1080 de vídeo e galeria de visão geral de alta definição (HD) e vídeo.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="7d2fb-105">As medições com base nos dados do cliente mostram que a largura de banda de vídeo típica aumentou apenas um pouco em comparação com o Lync 2010, mas a largura de banda máxima do fluxo de vídeo aumentou devido ao suporte total a HD (para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em [requisitos de largura de banda para tráfego de mídia no Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="7d2fb-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="7d2fb-106">Portanto, os administradores podem querer restringir a largura de banda do vídeo para certos usuários (como os usuários de uma filial que têm menos capacidade de rede) e ajudam a garantir a melhor qualidade de vídeo possível para outros usuários (como executivos).</span><span class="sxs-lookup"><span data-stu-id="7d2fb-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="7d2fb-107">A tabela a seguir fornece uma lista de configurações recomendadas para configurar o vídeo para diferentes capacidades de rede.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="7d2fb-108">Essas configurações impedirão que alguns cenários do usuário enviem e recebam vídeos com resolução mais alta (veja a coluna mais à direita).</span><span class="sxs-lookup"><span data-stu-id="7d2fb-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="7d2fb-109">A configuração mínima fará com que o vídeo da Galeria fique indisponível, devido ao máximo de recebimento máximo de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="7d2fb-110">Configurações de vídeo recomendadas</span><span class="sxs-lookup"><span data-stu-id="7d2fb-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="7d2fb-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="7d2fb-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="7d2fb-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="7d2fb-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="7d2fb-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="7d2fb-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="7d2fb-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="7d2fb-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="7d2fb-115">Resolução de vídeo esperada para vídeo de boa qualidade</span><span class="sxs-lookup"><span data-stu-id="7d2fb-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d2fb-116">Melhor</span><span class="sxs-lookup"><span data-stu-id="7d2fb-116">Best</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-117">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-117">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-118">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-118">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-119">8000</span><span class="sxs-lookup"><span data-stu-id="7d2fb-119">8000</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-120">8000</span><span class="sxs-lookup"><span data-stu-id="7d2fb-120">8000</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-121">Ponto a ponto: até 1920 x 1080 resolução de vídeo</span><span class="sxs-lookup"><span data-stu-id="7d2fb-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="7d2fb-122">Modo de exibição de Galeria: até 2 1920 x 1080 vídeos ou vários vídeos de resolução menores</span><span class="sxs-lookup"><span data-stu-id="7d2fb-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d2fb-123">Corretamente</span><span class="sxs-lookup"><span data-stu-id="7d2fb-123">Good</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-124">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-124">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-125">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-125">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-126">2500</span><span class="sxs-lookup"><span data-stu-id="7d2fb-126">2500</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-127">2500</span><span class="sxs-lookup"><span data-stu-id="7d2fb-127">2500</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-128">Ponto a ponto: até 1280 x 720 resolução de vídeo</span><span class="sxs-lookup"><span data-stu-id="7d2fb-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="7d2fb-129">Modo de exibição de Galeria: até 5 640 x 360 de resolução de vídeo</span><span class="sxs-lookup"><span data-stu-id="7d2fb-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d2fb-130">Média</span><span class="sxs-lookup"><span data-stu-id="7d2fb-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-131">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-131">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-132">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-132">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-133">1000</span><span class="sxs-lookup"><span data-stu-id="7d2fb-133">1000</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-134">1000</span><span class="sxs-lookup"><span data-stu-id="7d2fb-134">1000</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-135">Ponto a ponto: até 960 x 540 resolução de vídeo</span><span class="sxs-lookup"><span data-stu-id="7d2fb-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="7d2fb-136">Modo de exibição de Galeria: até 5 424 x 240 de resolução de vídeo</span><span class="sxs-lookup"><span data-stu-id="7d2fb-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d2fb-137">Nível</span><span class="sxs-lookup"><span data-stu-id="7d2fb-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-138">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7d2fb-138">True</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-139">Falso</span><span class="sxs-lookup"><span data-stu-id="7d2fb-139">False</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-140">350</span><span class="sxs-lookup"><span data-stu-id="7d2fb-140">350</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-141">350</span><span class="sxs-lookup"><span data-stu-id="7d2fb-141">350</span></span></p></td>
<td><p><span data-ttu-id="7d2fb-142">Ponto a ponto: até 424 x 240 resolução de vídeo</span><span class="sxs-lookup"><span data-stu-id="7d2fb-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="7d2fb-143">Modo de exibição de Galeria: não disponível</span><span class="sxs-lookup"><span data-stu-id="7d2fb-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7d2fb-144">Você pode usar as informações da tabela anterior para implantar o novo vídeo e a Galeria de alta definição do recurso Exibir recursos de videoconferência para alguns usuários da sua organização, ao mesmo tempo em que permite diferentes resoluções de vídeo para outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="7d2fb-145">No exemplo a seguir, o administrador acumula os novos recursos de vídeo com a melhor qualidade de vídeo disponível somente para executivos.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="7d2fb-146">Para os funcionários em uma filial remota com capacidade de rede baixa, apenas a configuração mínima da tabela anterior é implantada.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="7d2fb-147">Para todos os outros funcionários, a configuração "bom" da tabela anterior é implantada.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="7d2fb-148">Para distribuir os novos recursos para os executivos, o administrador cria uma política de conferência chamada ExecutiveVideo.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="7d2fb-149">Esta política de conferência tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7d2fb-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="7d2fb-150">VideoBitRateKB é definido como 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="7d2fb-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="7d2fb-151">TotalReceiveVideoBitRateKB é definido como 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="7d2fb-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="7d2fb-152">AllowMultiview é definido como true</span><span class="sxs-lookup"><span data-stu-id="7d2fb-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="7d2fb-153">EnableMultiviewJoin é definido como true</span><span class="sxs-lookup"><span data-stu-id="7d2fb-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="7d2fb-154">Para os funcionários da filial, o administrador cria uma política de conferência chamada BranchOfficeVideo.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="7d2fb-155">Esta política de conferência tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7d2fb-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="7d2fb-156">VideoBitRateKB é definido como 350 kbps</span><span class="sxs-lookup"><span data-stu-id="7d2fb-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="7d2fb-157">TotalReceiveVideoBitRateKB é definido como 350 kbps</span><span class="sxs-lookup"><span data-stu-id="7d2fb-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="7d2fb-158">AllowMultiview é definido como true</span><span class="sxs-lookup"><span data-stu-id="7d2fb-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="7d2fb-159">EnableMultiviewJoin é definido como false</span><span class="sxs-lookup"><span data-stu-id="7d2fb-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="7d2fb-160">Para todos os outros funcionários, o administrador cria uma política de conferência chamada StandardVideo.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="7d2fb-161">Esta política de conferência tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7d2fb-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="7d2fb-162">VideoBitRateKB é definido como 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="7d2fb-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="7d2fb-163">TotalReceiveVideoBitRateKB é definido como 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="7d2fb-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="7d2fb-164">AllowMultiview é definido como true</span><span class="sxs-lookup"><span data-stu-id="7d2fb-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="7d2fb-165">EnableMultiviewJoin é definido como true</span><span class="sxs-lookup"><span data-stu-id="7d2fb-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="7d2fb-166">O administrador atribui uma política de conferência aos usuários da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7d2fb-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="7d2fb-167">A política de conferência ExecutiveVideo é atribuída aos executivos.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="7d2fb-168">A política de conferência BranchOfficeVideo é atribuída a todos os funcionários da filial do escritório.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="7d2fb-169">A política de conferência StandardVideo é atribuída a todos os outros funcionários.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="7d2fb-170">Essas atribuições de política de conferência resultam na seguinte experiência do usuário:</span><span class="sxs-lookup"><span data-stu-id="7d2fb-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="7d2fb-171">Todas as conferências organizadas por qualquer modo de exibição da Galeria de suporte do usuário, mas os funcionários da filial não podem experimentar o modo de exibição de galeria.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="7d2fb-172">Para qualquer conferência de dois participantes ou de vários participantes, os executivos podem enviar vídeo HD de 1920 x 1080 Full HD, se o hardware e o link de rede forem compatíveis com ele e puderem receber vídeo em HD de 1920 x 1080 para os outros clientes participantes.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="7d2fb-173">Os funcionários que não são executivos experimentam resoluções mais baixas do que os executivos em suas conferências de dois participantes ou de vários participantes, mas ainda têm uma boa resolução.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="7d2fb-174">Os funcionários que estiverem na filial receberão uma boa qualidade de vídeo em chamadas de dois participantes quando o Lync exibir o tamanho padrão da janela de vídeo; no entanto, se a janela do Lync estiver maximizada para tela inteira, a resolução do vídeo não aumentará.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="7d2fb-175">Para conferências com vários participantes, os funcionários da filial verão apenas um vídeo ativo.</span><span class="sxs-lookup"><span data-stu-id="7d2fb-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

