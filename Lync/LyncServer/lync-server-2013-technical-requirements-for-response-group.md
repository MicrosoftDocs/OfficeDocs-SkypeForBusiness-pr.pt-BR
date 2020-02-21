---
title: 'Lync Server 2013: requisitos técnicos para o grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b07ddfa11f23c7e5183c243020c441db7219660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Requisitos técnicos para o grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Esta seção descreve os seguintes requisitos técnicos para o aplicativo de grupo de resposta:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de porta

  - Requisitos do arquivo de áudio

  - Requisitos da ferramenta de configuração do grupo de resposta

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

O aplicativo grupo de resposta tem os mesmos requisitos de hardware que os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

O aplicativo grupo de resposta tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Se você usar arquivos de áudio do Windows Media (. WMA) para música e anúncios do grupo de resposta, todos os servidores front-end ou servidores Standard Editions que executam o aplicativo de grupo de resposta deverão ter o tempo de execução do Windows Media Format instalado para servidores executando o Windows Server 2008 R2 ou Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.

Para mais detalhes sobre requisitos de áudio, consulte "Requisitos de arquivo de áudio" mais adiante nesta seção.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de porta

O aplicativo grupo de resposta usa as seguintes portas:

  - **Porta 5071**   usada para solicitações de escuta SIP

  - **Porta 8404**   usada para comunicações entre servidores
    
    <div>
    

    > [!NOTE]  
    > Essa porta é usada para o serviço de correspondência e é obrigatório quando o aplicativo grupo de resposta é implantado em um pool que tem mais de um servidor front-end.

    
    </div>

<div>


> [!NOTE]  
> Essas portas são as configurações padrão que podem ser alteradas com o uso do cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de grupo de resposta suporta o formato de arquivo Wave (. wav) e o formato de arquivo de áudio do Windows Media (. WMA) para mensagens do grupo de resposta, música em espera ou perguntas de resposta de voz interativa (IVR).

O formato de arquivo de áudio do Windows Media requer que o tempo de execução do Windows Media Format esteja instalado em servidores front-end executando o Windows Server 2008 R2 e o Windows Server 2008. Para mais detalhes, consulte "Requisitos de software", anteriormente nesta seção.

<div>

## <a name="supported-wave-file-formats"></a>Formatos de arquivo wave suportados

Todos os arquivos wave devem atender aos seguintes requisitos:

  - Arquivo de 8 ou 16 bits

  - Formato de modulação de código de pulso linear (LPCM), A-Law ou mu-Law

  - Mono ou estéreo

  - 4 MB ou menos

Para o melhor desempenho de arquivos wave, um  arquivo Wave mono, de 16 kHz e 16 bits é recomendado.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Formatos de arquivo de áudio Windows Media

Se você utilizar um arquivo de áudio Windows Media, considere utilizar taxas de bit baixos e verifique o desempenho do sistema sob carga.

Você pode utilizar o Microsoft Expression Encoder 4 para converter um arquivo para o formato Windows Media Audio. Para baixar o Expression Encoder 4, [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)consulte.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Requisitos de ferramenta de configuração de Grupo de resposta

A ferramenta de configuração do grupo de resposta oferece suporte às combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

<div>


> [!NOTE]  
> Há suporte para as versões de 32 bits e 64 bits dos sistemas operacionais. Somente versões de 32 bits do Internet Explorer são compatíveis.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemas operacionais e navegadores da Web suportados

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

## <a name="response-group-agent-console"></a>Console de agente do Grupo de resposta

O console de agente suporta as combinações de sistemas operacionais e navegadores da web descritas na tabela a seguir.

<div>


> [!NOTE]  
> Versões 32 bits ou 64 bits do sistema operacional são suportadas. Apenas versões 32 bits do Internet Explorer são suportadas.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemas operacionais e navegadores da Web suportados

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
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
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
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
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

