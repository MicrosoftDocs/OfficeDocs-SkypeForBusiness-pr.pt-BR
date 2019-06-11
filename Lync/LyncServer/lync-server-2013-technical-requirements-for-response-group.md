---
title: 'Lync Server 2013: Requisitos técnicos do Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Requisitos técnicos do Grupo de Resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Esta seção descreve os seguintes requisitos técnicos para o aplicativo de grupo de resposta:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de porta

  - Requisitos de arquivo de áudio

  - Requisitos da ferramenta de configuração de grupo de resposta

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

O aplicativo grupo de resposta tem os mesmos requisitos de hardware que os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

O aplicativo grupo de resposta tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Se você usa arquivos de áudio do Windows Media (. WMA) para músicas e anúncios em grupo de resposta, todos os servidores front-end ou servidores Standard Editions que executam o aplicativo do grupo de resposta devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.

Para obter mais detalhes sobre os requisitos de áudio, consulte "requisitos de arquivo de áudio" mais adiante nesta seção.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de porta

O aplicativo grupo de resposta usa as seguintes portas:

  - **Porta 5071**   usada para solicitações de escuta SIP

  - **Porta 8404**   usada para comunicações entre servidores
    
    <div>
    

    > [!NOTE]  
    > Essa porta é usada para o serviço fazer correspondência e é necessária quando o aplicativo do grupo de resposta é implantado em um pool que tem mais de um servidor front-end.

    
    </div>

<div>


> [!NOTE]  
> Essas portas são configurações padrão que podem ser alteradas usando o cmdlet <STRONG>set-CsApplicationServer</STRONG> . Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de grupo de resposta suporta o formato de arquivo Wave (. wav) e o formato de áudio do Windows Media (. WMA) para perguntas sobre mensagens de grupo de resposta, música em espera ou reação de voz interativa (IVR).

O formato de arquivo de áudio do Windows Media requer que o tempo de execução do Windows Media Format seja instalado em servidores front-end que executam o Windows Server 2008 R2 e o Windows Server 2008. Para obter mais detalhes, consulte "requisitos de software", anteriormente nesta seção.

<div>

## <a name="supported-wave-file-formats"></a>Formatos de arquivo wave compatíveis

Todos os arquivos de ondas devem atender aos seguintes requisitos:

  - arquivo de 8 bits ou 16 bits

  - Formato de modulação de código de pulso linear (LPCM), A-lei ou MU-Law

  - Mono ou estéreo

  - 4 MB ou menos

Para obter o melhor desempenho de arquivos Wave, recomenda-se um arquivo wave de 16 kHz, mono e 16 bits.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Formatos de arquivo de áudio do Windows Media com suporte

Se você usar um arquivo de áudio do Windows Media, considere o uso de taxas de bits baixas e verifique se o desempenho do sistema está em carga.

Você pode usar o codificador do Microsoft Expression 4 para converter um arquivo para o formato de áudio do Windows Media. Para baixar o Expression Encoder 4, [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)consulte.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Requisitos da ferramenta de configuração de grupo de resposta

A ferramenta de configuração de grupo de resposta aceita as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

<div>


> [!NOTE]  
> Há suporte para as versões de 32 bits ou 64 bits dos sistemas operacionais. Só há suporte para as versões de 32 bits do Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Navegadores da Web e sistemas operacionais com suporte

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operacional</th>
<th>Navegador da Web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista com Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 com Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 com Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 com Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Console do agente do grupo de resposta

O console do agente tem suporte para as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

<div>


> [!NOTE]  
> Há suporte para as versões de 32 bits ou 64 bits dos sistemas operacionais. Só há suporte para as versões de 32 bits do Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Navegadores da Web e sistemas operacionais com suporte

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operacional</th>
<th>Navegador da Web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista com Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 com Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p>
<p>Firefox 10,0</p>
<p>Chrome 18,0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 com Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 com Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p>
<p>Firefox 10,0</p>
<p>Chrome 18,0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

