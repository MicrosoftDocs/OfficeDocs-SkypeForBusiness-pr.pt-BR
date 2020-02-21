---
title: 'Lync Server 2013: requisitos de vídeo do cliente do Lync'
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
ms.openlocfilehash: c15eb698babcce1cd104dd7206c037b95d402992
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Requisitos de vídeo do cliente Lync para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-01-29_

Esta seção descreve o suporte de hardware de vídeo para chamadas de vídeo do Lync 2013 e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, Tablet e dispositivo móvel.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Recursos e requisitos de vídeo do Windows para área de trabalho e Tablet

O Lync 2013 introduz a aceleração de hardware para codificação e decodificação de vídeo com base no padrão de codificação de vídeo avançado H. 264/MPEG-4 parte 10. Este recurso permite que computadores com velocidades reduzidas de relógio de CPU codifiquem e decodifiquem vídeo de resolução mais alta. Os requisitos de hardware de vídeo variam dependendo da configuração do computador e da resolução de vídeo desejada.

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
<td><p>Decodificação H. 264 acelerada por hardware usando o DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>A placa gráfica deve suportar o DirectX 9,0 e deve expor o modo de decodificação de DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>O driver mais recente da placa gráfica deve estar instalado.</p></li>
</ul>
<div>

> [!NOTE]  
> Para obter detalhes sobre os modos de decodificação, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.


</div></td>
</tr>
<tr class="even">
<td><p>Codificação H. 264 acelerada por hardware: requisitos de chipset</p></td>
<td><p>As seguintes soluções de codificação de vídeo aceleradas por hardware Intel têm suporte:</p>
<ul>
<li><p>A segunda e terceira geração Intel HD Graphics 2000, 2500, 3000 e 4000 (ou versões posteriores) com codificadores de vídeo de hardware integrados. É necessário instalar o driver Intel HD Graphics 15.28.9.2884 ou o driver mais recente que contém o seguinte:</p>
<ul>
<li><p>9.17.10.2884 de driver de vídeo ou o driver mais recente</p></li>
<li><p>Hardware Media Foundation Transform (HMFT) versão 3.12.10.31 ou o HMFT mais recente</p></li>
</ul></li>
</ul>
<p>As seguintes soluções de codificação de vídeo aceleradas para hardware AMD são suportadas (requer atualizações do CU1 para o Lync Server 2013):</p>
<ul>
<li><p>Mecanismo de codec de vídeo AMD, disponível em várias placas gráficas distintas e em unidades de processamento aceleradas integradas de processadores AMD A-Series Accelerated. O driver do mecanismo do codec de vídeo AMD 9.12.0.0 ou superior deve estar instalado.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codificação H. 264 acelerada por hardware: requisitos de câmera</p></td>
<td><p>Câmeras de vídeo USB com o codificador de hardware H. 264 integrado que está em conformidade com a especificação de classe de vídeo USB (UVC) versão 1,5.</p>
<div>

> [!NOTE]  
> O Lync 2013 suporta UVC 1,5 câmeras com Windows 8 ou Windows 8,1, que inclui suporte para o UVC 1,5. Como o Windows 7 não inclui suporte para o UVC 1,5, o Lync 2013 trata as câmeras do UVC 1,5 como câmeras normais sem suporte para codificação de hardware.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinação de recursos de codificação e decodificação de vídeo H. 264

Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de uma configuração de computador específica:

  - Suporte para decodificação acelerada por hardware usando DXVA

  - Suporte para codificação acelerada por hardware

  - Número de núcleos físicos

  - Índice de experiência do Windows (WEI)

A ferramenta de avaliação de sistema do Windows (WinSAT) determina o WEI. Quando você executa a ferramenta WinSAT, ela gera um documento XML formal de avaliação no computador no diretório de repositório do WinSAT\\\\do\\desempenho% windir%. Este arquivo XML contém as duas pontuações a seguir de importância específica para determinar as funcionalidades de codificação e decodificação:

  - O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.

  - O valor GraphicsScore indica a capacidade de codificação acelerada por hardware do computador.

As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação para diferentes tipos de computador, dependendo da aceleração de hardware que eles suportam. Para resoluções do 640x360 e superior, a taxa de quadros máxima com suporte é de 30 quadros por segundo (FPS). Para resoluções inferiores a 640x360, a taxa de quadros máxima compatível é de 15 fps.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Computador sem DXVA e codificador acelerado por hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolução de codificador compatível</th>
<th>Resolução de decodificador compatível</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 em 15fps para cenários de recebimento apenas)</p></td>
<td><p>1 núcleo e VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 núcleos e VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos e VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Não disponível</p></td>
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
<th>Resolução de codificador compatível</th>
<th>Resolução de decodificador compatível</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920 x 1080</p></td>
<td><p>1 núcleo e VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos e VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos e VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos e VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> A Pontuação do WinSAT no Windows 7 está limitada a um máximo de 7,9. Portanto, o recurso de codificação para um computador sem um codificador acelerado de hardware só pode ser alcançado no Windows 8 ou no Windows 8,1, onde a pontuação de WinSAT máxima é 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Computador com DXVA e com codificador acelerado por hardware Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolução de codificador compatível</th>
<th>Resolução de decodificador compatível</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Todos os gráficos Intel HD de segunda e 3ª geração</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2ª e 3ª geração Intel HD Graphics e GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Recursos de vídeo do dispositivo móvel

A tabela a seguir descreve os recursos de vídeo máximo para dispositivos móveis compatíveis. Para obter mais informações sobre o suporte a dispositivos móveis, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<td><p>Resolução máxima de codificação H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S e posterior</p></td>
<td><p>VGA: iPad 2 e posterior/iPad mini 1 e posterior</p>
<p>720p: iPad Air/iPad mini 2/iPad pro e posterior</p></td>
<td><p>Até VGA, dependendo do modelo do dispositivo</p></td>
</tr>
<tr class="even">
<td><p>Resolução máxima de decodificação H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S e posterior</p></td>
<td><p>VGA: iPad 2 e posterior/iPad mini 1 e posterior</p>
<p>720p: iPad Air/iPad mini 2/iPad pro e posterior</p></td>
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

