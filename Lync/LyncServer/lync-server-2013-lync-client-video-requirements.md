---
title: 'Lync Server 2013: requisitos de vídeo do cliente do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="50d40-102">Requisitos de vídeo do cliente do Lync para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50d40-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50d40-103">_**Tópico da última modificação:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="50d40-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="50d40-104">Esta seção descreve o suporte de hardware de vídeo para chamadas com vídeo do Lync 2013 e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, Tablet e dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="50d40-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="50d40-105">Recursos e requisitos de vídeo do Windows para área de trabalho e Tablet</span><span class="sxs-lookup"><span data-stu-id="50d40-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="50d40-106">O Lync 2013 introduz a aceleração de hardware para codificação e decodificação de vídeo com base no padrão de codificação de vídeo avançado H. 264/MPEG-4 Part 10.</span><span class="sxs-lookup"><span data-stu-id="50d40-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="50d40-107">Esse recurso permite que computadores com velocidades baixas de clock da CPU codifiquem e decodifiquem vídeo de maior resolução.</span><span class="sxs-lookup"><span data-stu-id="50d40-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="50d40-108">Os requisitos de hardware de vídeo variam de acordo com a configuração do computador e a resolução de vídeo desejada.</span><span class="sxs-lookup"><span data-stu-id="50d40-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="50d40-109">Requisitos de hardware de vídeo</span><span class="sxs-lookup"><span data-stu-id="50d40-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50d40-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="50d40-110">Feature</span></span></th>
<th><span data-ttu-id="50d40-111">Requisito</span><span class="sxs-lookup"><span data-stu-id="50d40-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50d40-112">Decodificação H.264 acelerada por hardware usando DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="50d40-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50d40-113">A placa gráfica deve suportar DirectX 9.0 e expor o modo de decodificação DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="50d40-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="50d40-114">O driver mais recente da placa gráfica deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="50d40-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="50d40-115">Para obter detalhes sobre os modos de decodificação, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span><span class="sxs-lookup"><span data-stu-id="50d40-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-116">Codificação H.264 acelerada por hardware: requisitos de chipset</span><span class="sxs-lookup"><span data-stu-id="50d40-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="50d40-117">As seguintes soluções de codificação de vídeo acelerada por hardware da Intel têm suporte:</span><span class="sxs-lookup"><span data-stu-id="50d40-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="50d40-118">Os chipsets Intel HD 2000, 2500, 3000 e 4000 de terceira geração são de segunda geração (ou versões posteriores) com codificadores de vídeo de hardware integrados.</span><span class="sxs-lookup"><span data-stu-id="50d40-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="50d40-119">A instalação do driver Intel HD Graphics 15.28.9.2884 ou driver mais recente contendo os seguintes itens é necessária:</span><span class="sxs-lookup"><span data-stu-id="50d40-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="50d40-120">Driver de vídeo 9.17.10.2884 ou driver mais recente</span><span class="sxs-lookup"><span data-stu-id="50d40-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="50d40-121">HMFT (Hardware media foundation transform) versão 3.12.10.31 ou HMFT mais recente</span><span class="sxs-lookup"><span data-stu-id="50d40-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="50d40-122">As seguintes soluções de codificação de vídeo aceleradas para hardware AMD são suportadas (requer atualizações do CU1 para o Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="50d40-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="50d40-p103">O Mecanismo de Codec de Vídeo da AMD, que está disponível em diversas placas gráficas e nas unidades de processamento aceleradas integradas de Processadores Acelerados AMD A-Series. O driver do Mecanismo de Codec de Vídeo AMD 9.12.0.0 ou superior deve ser instalado.</span><span class="sxs-lookup"><span data-stu-id="50d40-p103">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors. The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d40-125">Codificação H.264 acelerada por hardware: requisitos de câmera</span><span class="sxs-lookup"><span data-stu-id="50d40-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="50d40-126">Câmera de vídeo USB com codificador de hardware H.264 integrado em conformidade com a especificação USB Video Class (UVC) versão 1.5.</span><span class="sxs-lookup"><span data-stu-id="50d40-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="50d40-127">O Lync 2013 suporta UVC 1,5 câmeras com Windows 8 ou Windows 8,1, que inclui suporte para UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="50d40-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="50d40-128">Como o Windows 7 não inclui suporte para o UVC 1,5, o Lync 2013 trata câmeras UVC 1,5 como câmeras normais sem suporte para codificação de hardware.</span><span class="sxs-lookup"><span data-stu-id="50d40-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="50d40-129">Determinação de recursos de codificação e decodificação de vídeo H. 264</span><span class="sxs-lookup"><span data-stu-id="50d40-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="50d40-130">Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de determinada configuração de computador:</span><span class="sxs-lookup"><span data-stu-id="50d40-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="50d40-131">Suporte para decodificação acelerada por hardware usando DXVA</span><span class="sxs-lookup"><span data-stu-id="50d40-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="50d40-132">Suporte para codificação acelerada por hardware</span><span class="sxs-lookup"><span data-stu-id="50d40-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="50d40-133">Número de núcleos físicos</span><span class="sxs-lookup"><span data-stu-id="50d40-133">Number of physical cores</span></span>

  - <span data-ttu-id="50d40-134">Índice de Experiência do Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="50d40-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="50d40-135">A Ferramenta de Avaliação de Sistema do Windows (WinSAT) determina o WEI.</span><span class="sxs-lookup"><span data-stu-id="50d40-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="50d40-136">Quando você executa a ferramenta do WinSAT, ele gera um documento XML formal de avaliação no computador no diretório de repositório de\\documentos\\do\\WinSAT do% windir% performance.</span><span class="sxs-lookup"><span data-stu-id="50d40-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="50d40-137">Esse arquivo XML contém as duas pontuações a seguir que são particularmente importantes para determinar as capacidades de codificação e decodificação:</span><span class="sxs-lookup"><span data-stu-id="50d40-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="50d40-138">O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.</span><span class="sxs-lookup"><span data-stu-id="50d40-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="50d40-139">O valor de GraphicsScore indica a capacidade de codificação acelerada por hardware do computador.</span><span class="sxs-lookup"><span data-stu-id="50d40-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="50d40-p106">As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação de diferentes tipos de PC, dependendo da aceleração de hardware que eles suportam. Para resoluções iguais ou maiores que 640x360, a taxa de quadros máxima suportada é de 30 quadros por segundo (fps). Para resoluções menores que 640x360, a taxa de quadros máxima suportada é de 15 fps.</span><span class="sxs-lookup"><span data-stu-id="50d40-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="50d40-143">Computador sem DXVA e sem codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="50d40-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50d40-144">Capacidade de resolução do codificador</span><span class="sxs-lookup"><span data-stu-id="50d40-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="50d40-145">Capacidade de resolução do decodificador</span><span class="sxs-lookup"><span data-stu-id="50d40-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="50d40-146">Requisito</span><span class="sxs-lookup"><span data-stu-id="50d40-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50d40-147">424x240</span><span class="sxs-lookup"><span data-stu-id="50d40-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="50d40-148">424x240 (640x360 a 15fps para cenários apenas de recepção)</span><span class="sxs-lookup"><span data-stu-id="50d40-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="50d40-149">1 Núcleo e VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="50d40-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-150">640x360</span><span class="sxs-lookup"><span data-stu-id="50d40-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="50d40-151">640x360</span><span class="sxs-lookup"><span data-stu-id="50d40-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="50d40-152">2 Núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="50d40-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d40-153">640x360</span><span class="sxs-lookup"><span data-stu-id="50d40-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="50d40-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="50d40-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="50d40-155">2 Núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="50d40-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-156">640x360</span><span class="sxs-lookup"><span data-stu-id="50d40-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="50d40-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-158">4 Núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="50d40-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d40-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="50d40-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="50d40-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="50d40-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="50d40-161">4 Núcleos e VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="50d40-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="50d40-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="50d40-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-164">4 Núcleos e VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="50d40-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d40-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-167">N/D</span><span class="sxs-lookup"><span data-stu-id="50d40-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="50d40-168">Computador com DXVA, mas sem codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="50d40-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50d40-169">Capacidade de resolução do codificador</span><span class="sxs-lookup"><span data-stu-id="50d40-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="50d40-170">Capacidade de resolução do decodificador</span><span class="sxs-lookup"><span data-stu-id="50d40-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="50d40-171">Requisito</span><span class="sxs-lookup"><span data-stu-id="50d40-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50d40-172">424x240</span><span class="sxs-lookup"><span data-stu-id="50d40-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="50d40-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-174">1 Núcleo e VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="50d40-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-175">640x360</span><span class="sxs-lookup"><span data-stu-id="50d40-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="50d40-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-177">2 Núcleos e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="50d40-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d40-178">960x540</span><span class="sxs-lookup"><span data-stu-id="50d40-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="50d40-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-180">2 Núcleos e VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="50d40-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="50d40-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="50d40-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-183">4 Núcleos e VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="50d40-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d40-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-186">4 Núcleos e VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="50d40-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="50d40-p107">A pontuação WinSAT no Windows 7 está limitada ao máximo de 7,9. Dessa forma, a capacidade de codificação de um computador sem um codificador acelerado por hardware pode ser atingida somente no Windows 8 ou no Windows 8.1, onde a pontuação WinSAT máxima é 9,9.</span><span class="sxs-lookup"><span data-stu-id="50d40-p107">The WinSAT score on Windows 7 is limited to a maximum of 7.9. Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="50d40-189">Computador com DXVA e codificador acelerado por hardware Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="50d40-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50d40-190">Capacidade de resolução do codificador</span><span class="sxs-lookup"><span data-stu-id="50d40-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="50d40-191">Capacidade de resolução do decodificador</span><span class="sxs-lookup"><span data-stu-id="50d40-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="50d40-192">Requisito</span><span class="sxs-lookup"><span data-stu-id="50d40-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50d40-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="50d40-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="50d40-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-195">Toda a segunda e a terceira geração Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="50d40-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="50d40-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="50d40-198">Segunda e terceira geração Intel HD Graphics e GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="50d40-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="50d40-199">Recursos de vídeo do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="50d40-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="50d40-200">A tabela a seguir descreve a capacidade máxima de vídeo para dispositivos móveis compatíveis.</span><span class="sxs-lookup"><span data-stu-id="50d40-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="50d40-201">Para obter mais informações sobre o suporte a dispositivos móveis, consulte [planejando para clientes móveis no Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="50d40-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="50d40-202">Recurso</span><span class="sxs-lookup"><span data-stu-id="50d40-202">Feature</span></span></th>
<th><span data-ttu-id="50d40-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="50d40-203">Windows Phone</span></span></th>
<th><span data-ttu-id="50d40-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="50d40-204">iPhone</span></span></th>
<th><span data-ttu-id="50d40-205">iPad</span><span class="sxs-lookup"><span data-stu-id="50d40-205">iPad</span></span></th>
<th><span data-ttu-id="50d40-206">Android</span><span class="sxs-lookup"><span data-stu-id="50d40-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50d40-207">Resolução máxima de codificação H.264</span><span class="sxs-lookup"><span data-stu-id="50d40-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="50d40-208">VGA</span><span class="sxs-lookup"><span data-stu-id="50d40-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="50d40-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="50d40-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="50d40-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="50d40-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="50d40-211">720p: iPhone 5S e posterior</span><span class="sxs-lookup"><span data-stu-id="50d40-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="50d40-212">VGA: iPad 2 e posterior/iPad mini 1 e posterior</span><span class="sxs-lookup"><span data-stu-id="50d40-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="50d40-213">720P: iPad Air/iPad mini 2/iPad Pro e posterior</span><span class="sxs-lookup"><span data-stu-id="50d40-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="50d40-214">Até VGA, dependendo do modelo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="50d40-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d40-215">Resolução máxima de decodificação H.264</span><span class="sxs-lookup"><span data-stu-id="50d40-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="50d40-216">VGA</span><span class="sxs-lookup"><span data-stu-id="50d40-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="50d40-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="50d40-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="50d40-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="50d40-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="50d40-219">720p: iPhone 5S e posterior</span><span class="sxs-lookup"><span data-stu-id="50d40-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="50d40-220">VGA: iPad 2 e posterior/iPad mini 1 e posterior</span><span class="sxs-lookup"><span data-stu-id="50d40-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="50d40-221">720P: iPad Air/iPad mini 2/iPad Pro e posterior</span><span class="sxs-lookup"><span data-stu-id="50d40-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="50d40-222">Até VGA, dependendo do modelo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="50d40-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

