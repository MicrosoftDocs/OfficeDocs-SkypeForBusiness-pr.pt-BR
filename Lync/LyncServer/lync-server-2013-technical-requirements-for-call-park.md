---
title: 'Lync Server 2013: Requisitos técnicos para Estacionamento de Chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742d6ef62068e3e6e3bbd953e078b186e86bb497
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Requisitos técnicos para Estacionamento de Chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Esta seção descreve os seguintes requisitos técnicos para o parque de chamadas:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de porta

  - Requisitos de arquivo de áudio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

O aplicativo de estacionamento de chamadas tem os mesmos requisitos de hardware que os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

O aplicativo de estacionamento de chamadas tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Todos os servidores de front-end e servidores da edição padrão em que o aplicativo de estacionamento de chamada é implantado devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores com Windows Server 2012 ou Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. O tempo de execução do Windows Media Format ou do Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que chamam o estacionamento reproduz para música em espera.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de porta

O aplicativo de estacionamento de chamadas usa a seguinte porta:

  - **Porta 5075**   usada para solicitações de escuta SIP.

<div>


> [!NOTE]  
> Esta porta é uma configuração padrão, que pode ser alterada usando o cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de estacionamento de chamadas só dá suporte a arquivos de áudio do Windows Media (. WMA) para música em espera. É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera. Para baixar o Expression Encoder 4, consulte "Expression Encoder 4" [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)em. Use a ferramenta para converter o arquivo para o formato .wma. O formato recomendado para os arquivos de áudio da chamada com vídeo em espera é áudio de mídia 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.

<div>


> [!NOTE]  
> O arquivo convertido é reproduzido no telefone apenas em 16 kHz, mesmo que tenha sido gravado em 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

