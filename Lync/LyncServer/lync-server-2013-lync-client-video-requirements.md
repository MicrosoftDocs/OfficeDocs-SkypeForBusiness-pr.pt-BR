---
title: 'Lync Server 2013: requisitos de vídeo do cliente do Lync'
description: 'Lync Server 2013: requisitos de vídeo do cliente do Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570477"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="cc960-103">Requisitos de vídeo do cliente Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc960-103">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc960-104">_**Última modificação do tópico:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="cc960-104">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="cc960-105">Esta seção descreve o suporte de hardware de vídeo para chamadas de vídeo do Lync 2013 e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, Tablet e dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="cc960-105">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="cc960-106">Recursos e requisitos de vídeo do Windows para área de trabalho e Tablet</span><span class="sxs-lookup"><span data-stu-id="cc960-106">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="cc960-107">O Lync 2013 introduz a aceleração de hardware para codificação e decodificação de vídeo com base no padrão de codificação de vídeo avançado H. 264/MPEG-4 parte 10.</span><span class="sxs-lookup"><span data-stu-id="cc960-107">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="cc960-108">Este recurso permite que computadores com velocidades reduzidas de relógio de CPU codifiquem e decodifiquem vídeo de resolução mais alta.</span><span class="sxs-lookup"><span data-stu-id="cc960-108">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="cc960-109">Os requisitos de hardware de vídeo variam dependendo da configuração do computador e da resolução de vídeo desejada.</span><span class="sxs-lookup"><span data-stu-id="cc960-109">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="cc960-110">Requisitos de hardware de vídeo</span><span class="sxs-lookup"><span data-stu-id="cc960-110">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc960-111">Recurso</span><span class="sxs-lookup"><span data-stu-id="cc960-111">Feature</span></span></th>
<th><span data-ttu-id="cc960-112">Requisito</span><span class="sxs-lookup"><span data-stu-id="cc960-112">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc960-113">Decodificação H. 264 acelerada por hardware usando o DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="cc960-113">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cc960-114">A placa gráfica deve suportar o DirectX 9,0 e deve expor o modo de decodificação de DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="cc960-114">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="cc960-115">O driver mais recente da placa gráfica deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="cc960-115">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="cc960-116">Para obter detalhes sobre os modos de decodificação, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .</span><span class="sxs-lookup"><span data-stu-id="cc960-116">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-117">Codificação H. 264 acelerada por hardware: requisitos de chipset</span><span class="sxs-lookup"><span data-stu-id="cc960-117">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="cc960-118">As seguintes soluções de codificação de vídeo aceleradas por hardware Intel têm suporte:</span><span class="sxs-lookup"><span data-stu-id="cc960-118">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc960-119">A segunda e terceira geração Intel HD Graphics 2000, 2500, 3000 e 4000 (ou versões posteriores) com codificadores de vídeo de hardware integrados.</span><span class="sxs-lookup"><span data-stu-id="cc960-119">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="cc960-120">É necessário instalar o driver Intel HD Graphics 15.28.9.2884 ou o driver mais recente que contém o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc960-120">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc960-121">9.17.10.2884 de driver de vídeo ou o driver mais recente</span><span class="sxs-lookup"><span data-stu-id="cc960-121">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="cc960-122">Hardware Media Foundation Transform (HMFT) versão 3.12.10.31 ou o HMFT mais recente</span><span class="sxs-lookup"><span data-stu-id="cc960-122">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="cc960-123">As seguintes soluções de codificação de vídeo aceleradas para hardware AMD são suportadas (requer atualizações do CU1 para o Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="cc960-123">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="cc960-124">Mecanismo de codec de vídeo AMD, disponível em várias placas gráficas distintas e em unidades de processamento aceleradas integradas de processadores AMD A-Series Accelerated.</span><span class="sxs-lookup"><span data-stu-id="cc960-124">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="cc960-125">O driver do mecanismo do codec de vídeo AMD 9.12.0.0 ou superior deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="cc960-125">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc960-126">Codificação H. 264 acelerada por hardware: requisitos de câmera</span><span class="sxs-lookup"><span data-stu-id="cc960-126">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="cc960-127">Câmeras de vídeo USB com o codificador de hardware H. 264 integrado que está em conformidade com a especificação de classe de vídeo USB (UVC) versão 1,5.</span><span class="sxs-lookup"><span data-stu-id="cc960-127">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cc960-128">O Lync 2013 suporta UVC 1,5 câmeras com Windows 8 ou Windows 8,1, que inclui suporte para o UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="cc960-128">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="cc960-129">Como o Windows 7 não inclui suporte para o UVC 1,5, o Lync 2013 trata as câmeras do UVC 1,5 como câmeras normais sem suporte para codificação de hardware.</span><span class="sxs-lookup"><span data-stu-id="cc960-129">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="cc960-130">Determinação de recursos de codificação e decodificação de vídeo H. 264</span><span class="sxs-lookup"><span data-stu-id="cc960-130">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="cc960-131">Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de uma configuração de computador específica:</span><span class="sxs-lookup"><span data-stu-id="cc960-131">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="cc960-132">Suporte para decodificação acelerada por hardware usando DXVA</span><span class="sxs-lookup"><span data-stu-id="cc960-132">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="cc960-133">Suporte para codificação acelerada por hardware</span><span class="sxs-lookup"><span data-stu-id="cc960-133">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="cc960-134">Número de núcleos físicos</span><span class="sxs-lookup"><span data-stu-id="cc960-134">Number of physical cores</span></span>

  - <span data-ttu-id="cc960-135">Índice de experiência do Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="cc960-135">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="cc960-136">A ferramenta de avaliação de sistema do Windows (WinSAT) determina o WEI.</span><span class="sxs-lookup"><span data-stu-id="cc960-136">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="cc960-137">Quando você executa a ferramenta WinSAT, ela gera um documento XML formal de avaliação no computador no diretório de repositório do WinSAT do desempenho% windir% \\ \\ \\ .</span><span class="sxs-lookup"><span data-stu-id="cc960-137">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="cc960-138">Este arquivo XML contém as duas pontuações a seguir de importância específica para determinar as funcionalidades de codificação e decodificação:</span><span class="sxs-lookup"><span data-stu-id="cc960-138">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="cc960-139">O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.</span><span class="sxs-lookup"><span data-stu-id="cc960-139">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="cc960-140">O valor GraphicsScore indica a capacidade de codificação acelerada por hardware do computador.</span><span class="sxs-lookup"><span data-stu-id="cc960-140">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="cc960-141">As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação para diferentes tipos de computador, dependendo da aceleração de hardware que eles suportam.</span><span class="sxs-lookup"><span data-stu-id="cc960-141">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support.</span></span> <span data-ttu-id="cc960-142">Para resoluções do 640x360 e superior, a taxa de quadros máxima com suporte é de 30 quadros por segundo (FPS).</span><span class="sxs-lookup"><span data-stu-id="cc960-142">For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps).</span></span> <span data-ttu-id="cc960-143">Para resoluções inferiores a 640x360, a taxa de quadros máxima compatível é de 15 fps.</span><span class="sxs-lookup"><span data-stu-id="cc960-143">For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="cc960-144">Computador sem DXVA e codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="cc960-144">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc960-145">Resolução de codificador compatível</span><span class="sxs-lookup"><span data-stu-id="cc960-145">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="cc960-146">Resolução de decodificador compatível</span><span class="sxs-lookup"><span data-stu-id="cc960-146">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="cc960-147">Requisito</span><span class="sxs-lookup"><span data-stu-id="cc960-147">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc960-148">424x240</span><span class="sxs-lookup"><span data-stu-id="cc960-148">424x240</span></span></p></td>
<td><p><span data-ttu-id="cc960-149">424x240 (640x360 em 15fps para cenários de recebimento apenas)</span><span class="sxs-lookup"><span data-stu-id="cc960-149">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="cc960-150">1 núcleo e VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="cc960-150">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-151">640x360</span><span class="sxs-lookup"><span data-stu-id="cc960-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="cc960-152">640x360</span><span class="sxs-lookup"><span data-stu-id="cc960-152">640x360</span></span></p></td>
<td><p><span data-ttu-id="cc960-153">2 núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="cc960-153">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc960-154">640x360</span><span class="sxs-lookup"><span data-stu-id="cc960-154">640x360</span></span></p></td>
<td><p><span data-ttu-id="cc960-155">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="cc960-155">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cc960-156">2 núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="cc960-156">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-157">640x360</span><span class="sxs-lookup"><span data-stu-id="cc960-157">640x360</span></span></p></td>
<td><p><span data-ttu-id="cc960-158">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-158">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-159">4 núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="cc960-159">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc960-160">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="cc960-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cc960-161">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="cc960-161">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cc960-162">4 núcleos e VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="cc960-162">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-163">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="cc960-163">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cc960-164">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-164">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-165">4 núcleos e VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="cc960-165">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc960-166">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-167">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-167">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-168">N/D</span><span class="sxs-lookup"><span data-stu-id="cc960-168">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="cc960-169">Computador com DXVA, mas sem codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="cc960-169">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc960-170">Resolução de codificador compatível</span><span class="sxs-lookup"><span data-stu-id="cc960-170">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="cc960-171">Resolução de decodificador compatível</span><span class="sxs-lookup"><span data-stu-id="cc960-171">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="cc960-172">Requisito</span><span class="sxs-lookup"><span data-stu-id="cc960-172">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc960-173">424x240</span><span class="sxs-lookup"><span data-stu-id="cc960-173">424x240</span></span></p></td>
<td><p><span data-ttu-id="cc960-174">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-174">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-175">1 núcleo e VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="cc960-175">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-176">640x360</span><span class="sxs-lookup"><span data-stu-id="cc960-176">640x360</span></span></p></td>
<td><p><span data-ttu-id="cc960-177">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-177">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-178">2 núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="cc960-178">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc960-179">960x540</span><span class="sxs-lookup"><span data-stu-id="cc960-179">960x540</span></span></p></td>
<td><p><span data-ttu-id="cc960-180">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-180">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-181">2 núcleos e VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="cc960-181">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-182">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="cc960-182">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cc960-183">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-183">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-184">4 núcleos e VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="cc960-184">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc960-185">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-186">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-186">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-187">4 núcleos e VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="cc960-187">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="cc960-188">A Pontuação do WinSAT no Windows 7 está limitada a um máximo de 7,9.</span><span class="sxs-lookup"><span data-stu-id="cc960-188">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="cc960-189">Portanto, o recurso de codificação para um computador sem um codificador acelerado de hardware só pode ser alcançado no Windows 8 ou no Windows 8,1, onde a pontuação de WinSAT máxima é 9,9.</span><span class="sxs-lookup"><span data-stu-id="cc960-189">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="cc960-190">Computador com DXVA e com codificador acelerado por hardware Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="cc960-190">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc960-191">Resolução de codificador compatível</span><span class="sxs-lookup"><span data-stu-id="cc960-191">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="cc960-192">Resolução de decodificador compatível</span><span class="sxs-lookup"><span data-stu-id="cc960-192">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="cc960-193">Requisito</span><span class="sxs-lookup"><span data-stu-id="cc960-193">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc960-194">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="cc960-194">1280x720</span></span></p></td>
<td><p><span data-ttu-id="cc960-195">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-195">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-196">Todos os gráficos Intel HD de segunda e 3ª geração</span><span class="sxs-lookup"><span data-stu-id="cc960-196">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-197">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-198">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="cc960-198">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="cc960-199">2ª e 3ª geração Intel HD Graphics e GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="cc960-199">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="cc960-200">Recursos de vídeo do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="cc960-200">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="cc960-201">A tabela a seguir descreve os recursos de vídeo máximo para dispositivos móveis compatíveis.</span><span class="sxs-lookup"><span data-stu-id="cc960-201">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="cc960-202">Para obter mais informações sobre o suporte a dispositivos móveis, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="cc960-202">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc960-203">Recurso</span><span class="sxs-lookup"><span data-stu-id="cc960-203">Feature</span></span></th>
<th><span data-ttu-id="cc960-204">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="cc960-204">Windows Phone</span></span></th>
<th><span data-ttu-id="cc960-205">iPhone</span><span class="sxs-lookup"><span data-stu-id="cc960-205">iPhone</span></span></th>
<th><span data-ttu-id="cc960-206">iPad</span><span class="sxs-lookup"><span data-stu-id="cc960-206">iPad</span></span></th>
<th><span data-ttu-id="cc960-207">Android</span><span class="sxs-lookup"><span data-stu-id="cc960-207">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc960-208">Resolução máxima de codificação H. 264</span><span class="sxs-lookup"><span data-stu-id="cc960-208">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="cc960-209">VGA</span><span class="sxs-lookup"><span data-stu-id="cc960-209">VGA</span></span></p></td>
<td><p><span data-ttu-id="cc960-210">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="cc960-210">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="cc960-211">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="cc960-211">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="cc960-212">720p: iPhone 5S e posterior</span><span class="sxs-lookup"><span data-stu-id="cc960-212">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="cc960-213">VGA: iPad 2 e posterior/iPad mini 1 e posterior</span><span class="sxs-lookup"><span data-stu-id="cc960-213">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="cc960-214">720p: iPad Air/iPad mini 2/iPad pro e posterior</span><span class="sxs-lookup"><span data-stu-id="cc960-214">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="cc960-215">Até VGA, dependendo do modelo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc960-215">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc960-216">Resolução máxima de decodificação H. 264</span><span class="sxs-lookup"><span data-stu-id="cc960-216">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="cc960-217">VGA</span><span class="sxs-lookup"><span data-stu-id="cc960-217">VGA</span></span></p></td>
<td><p><span data-ttu-id="cc960-218">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="cc960-218">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="cc960-219">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="cc960-219">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="cc960-220">720p: iPhone 5S e posterior</span><span class="sxs-lookup"><span data-stu-id="cc960-220">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="cc960-221">VGA: iPad 2 e posterior/iPad mini 1 e posterior</span><span class="sxs-lookup"><span data-stu-id="cc960-221">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="cc960-222">720p: iPad Air/iPad mini 2/iPad pro e posterior</span><span class="sxs-lookup"><span data-stu-id="cc960-222">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="cc960-223">Até VGA, dependendo do modelo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc960-223">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

