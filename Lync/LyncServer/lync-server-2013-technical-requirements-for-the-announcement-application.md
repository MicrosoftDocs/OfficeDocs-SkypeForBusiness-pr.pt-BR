---
title: 'Lync Server 2013: Requisitos técnicos para o aplicativo Comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Requisitos técnicos para o aplicativo Comunicado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Esta seção descreve os seguintes requisitos técnicos para o aplicativo de lançamento:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de porta

  - Requisitos de arquivo de áudio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

O aplicativo de anúncio tem os mesmos requisitos de hardware que os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

O aplicativo de anúncio tem os mesmos requisitos de sistema operacional e pré-requisitos de software dos servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Todos os servidores de front-end ou servidores Standard Edition que executam o aplicativo de anúncio devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. O tempo de execução do Windows Media Format ou do Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que o aplicativo de anúncio reproduz para anúncios e música.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de porta

O aplicativo de anúncio usa a seguinte porta:

  - **Porta 5071**   usada para solicitações de escuta SIP

<div>


> [!NOTE]  
> Essa porta é a definição padrão, que você pode modificar usando o cmdlet  <STRONG>Set-CsApplicationServer</STRONG>. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de anúncio aceita o formato de arquivo Wave (. wav) e o formato de áudio do Windows Media (. WMA) para músicas e anúncios. Os requisitos de arquivo de áudio para o aplicativo de anúncio são iguais aos do aplicativo de grupo de resposta. Para obter detalhes, consulte [requisitos técnicos para o grupo de resposta no Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

