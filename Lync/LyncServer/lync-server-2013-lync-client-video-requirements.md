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

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Requisitos de vídeo do cliente do Lync para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-01-29_

Esta seção descreve o suporte de hardware de vídeo para chamadas com vídeo do Lync 2013 e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, Tablet e dispositivo móvel.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Recursos e requisitos de vídeo do Windows para área de trabalho e Tablet

O Lync 2013 introduz a aceleração de hardware para codificação e decodificação de vídeo com base no padrão de codificação de vídeo avançado H. 264/MPEG-4 Part 10. Esse recurso permite que computadores com velocidades baixas de clock da CPU codifiquem e decodifiquem vídeo de maior resolução. Os requisitos de hardware de vídeo variam de acordo com a configuração do computador e a resolução de vídeo desejada.

<div>

## <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Recurso</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Decodificação H.264 acelerada por hardware usando DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>A placa gráfica deve suportar DirectX 9.0 e expor o modo de decodificação DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>O driver mais recente da placa gráfica deve estar instalado.</p></li>
</ul>
<div>

> [!NOTE]  
> Para obter detalhes sobre os modos de decodificação, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.


</div></td>
</tr>
<tr class="even">
<td><p>Codificação H.264 acelerada por hardware: requisitos de chipset</p></td>
<td><p>As seguintes soluções de codificação de vídeo acelerada por hardware da Intel têm suporte:</p>
<ul>
<li><p>Os chipsets Intel HD 2000, 2500, 3000 e 4000 de terceira geração são de segunda geração (ou versões posteriores) com codificadores de vídeo de hardware integrados. A instalação do driver Intel HD Graphics 15.28.9.2884 ou driver mais recente contendo os seguintes itens é necessária:</p>
<ul>
<li><p>Driver de vídeo 9.17.10.2884 ou driver mais recente</p></li>
<li><p>HMFT (Hardware media foundation transform) versão 3.12.10.31 ou HMFT mais recente</p></li>
</ul></li>
</ul>
<p>As seguintes soluções de codificação de vídeo aceleradas para hardware AMD são suportadas (requer atualizações do CU1 para o Lync Server 2013):</p>
<ul>
<li><p>O Mecanismo de Codec de Vídeo da AMD, que está disponível em diversas placas gráficas e nas unidades de processamento aceleradas integradas de Processadores Acelerados AMD A-Series. O driver do Mecanismo de Codec de Vídeo AMD 9.12.0.0 ou superior deve ser instalado.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codificação H.264 acelerada por hardware: requisitos de câmera</p></td>
<td><p>Câmera de vídeo USB com codificador de hardware H.264 integrado em conformidade com a especificação USB Video Class (UVC) versão 1.5.</p>
<div>

> [!NOTE]  
> O Lync 2013 suporta UVC 1,5 câmeras com Windows 8 ou Windows 8,1, que inclui suporte para UVC 1,5. Como o Windows 7 não inclui suporte para o UVC 1,5, o Lync 2013 trata câmeras UVC 1,5 como câmeras normais sem suporte para codificação de hardware.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinação de recursos de codificação e decodificação de vídeo H. 264

Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de determinada configuração de computador:

  - Suporte para decodificação acelerada por hardware usando DXVA

  - Suporte para codificação acelerada por hardware

  - Número de núcleos físicos

  - Índice de Experiência do Windows (WEI)

A Ferramenta de Avaliação de Sistema do Windows (WinSAT) determina o WEI. Quando você executa a ferramenta do WinSAT, ele gera um documento XML formal de avaliação no computador no diretório de repositório de\\documentos\\do\\WinSAT do% windir% performance. Esse arquivo XML contém as duas pontuações a seguir que são particularmente importantes para determinar as capacidades de codificação e decodificação:

  - O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.

  - O valor de GraphicsScore indica a capacidade de codificação acelerada por hardware do computador.

As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação de diferentes tipos de PC, dependendo da aceleração de hardware que eles suportam. Para resoluções iguais ou maiores que 640x360, a taxa de quadros máxima suportada é de 30 quadros por segundo (fps). Para resoluções menores que 640x360, a taxa de quadros máxima suportada é de 15 fps.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Computador sem DXVA e sem codificador acelerado por hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Capacidade de resolução do codificador</th>
<th>Capacidade de resolução do decodificador</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 a 15fps para cenários apenas de recepção)</p></td>
<td><p>1 Núcleo e VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 Núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 Núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 Núcleos e VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Núcleos e VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>N/D</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Computador com DXVA, mas sem codificador acelerado por hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Capacidade de resolução do codificador</th>
<th>Capacidade de resolução do decodificador</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 Núcleo e VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 Núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 Núcleos e VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Núcleos e VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Núcleos e VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> A pontuação WinSAT no Windows 7 está limitada ao máximo de 7,9. Dessa forma, a capacidade de codificação de um computador sem um codificador acelerado por hardware pode ser atingida somente no Windows 8 ou no Windows 8.1, onde a pontuação WinSAT máxima é 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Computador com DXVA e codificador acelerado por hardware Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Capacidade de resolução do codificador</th>
<th>Capacidade de resolução do decodificador</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>Toda a segunda e a terceira geração Intel HD Graphics</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Segunda e terceira geração Intel HD Graphics e GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Recursos de vídeo do dispositivo móvel

A tabela a seguir descreve a capacidade máxima de vídeo para dispositivos móveis compatíveis. Para obter mais informações sobre o suporte a dispositivos móveis, consulte [planejando para clientes móveis no Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<th>Recurso</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Resolução máxima de codificação H.264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S e posterior</p></td>
<td><p>VGA: iPad 2 e posterior/iPad mini 1 e posterior</p>
<p>720P: iPad Air/iPad mini 2/iPad Pro e posterior</p></td>
<td><p>Até VGA, dependendo do modelo do dispositivo</p></td>
</tr>
<tr class="even">
<td><p>Resolução máxima de decodificação H.264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S e posterior</p></td>
<td><p>VGA: iPad 2 e posterior/iPad mini 1 e posterior</p>
<p>720P: iPad Air/iPad mini 2/iPad Pro e posterior</p></td>
<td><p>Até VGA, dependendo do modelo do dispositivo</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

