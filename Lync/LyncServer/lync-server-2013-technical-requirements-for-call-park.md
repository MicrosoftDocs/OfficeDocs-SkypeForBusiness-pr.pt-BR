---
title: 'Lync Server 2013: requisitos técnicos para estacionamento de chamada'
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
ms.openlocfilehash: 8b5fb5f86dd575daf603bd0a21235184346bca05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533948"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Requisitos técnicos para estacionamento de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Esta seção descreve os seguintes requisitos técnicos para estacionamento de chamada:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de porta

  - Requisitos do arquivo de áudio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

O aplicativo de estacionamento de chamada tem os mesmos requisitos de hardware que os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

O aplicativo de estacionamento de chamada tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Todos os servidores front-end e servidores Standard Edition onde o aplicativo de estacionamento de chamada é implantado devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. O tempo de execução do Windows Media Format ou o Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que chamam o estacionamento de música em espera.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de porta

O aplicativo de estacionamento de chamada usa a seguinte porta:

  - **Porta 5075**     Usado para solicitações de escuta SIP.

<div>


> [!NOTE]  
> Esta porta é uma configuração padrão, que pode ser alterado usando o cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de estacionamento de chamada suporta apenas arquivos de áudio do Windows Media (. WMA) para música em espera. É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera. Para baixar o Expression Encoder 4, consulte "Expression Encoder 4" em [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) . Use a ferramenta para converter o arquivo no formato .wma. O formato recomendado para arquivos de música de espera do Estacionamento de Chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.

<div>


> [!NOTE]  
> O arquivo convertido é reproduzido no telefone somente a 16 kHz, mesmo que tenha sido gravado a 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

