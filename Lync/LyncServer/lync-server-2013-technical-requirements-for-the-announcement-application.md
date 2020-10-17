---
title: 'Lync Server 2013: requisitos técnicos para o aplicativo comunicado'
description: 'Lync Server 2013: requisitos técnicos para o aplicativo comunicado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550307"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Requisitos técnicos para o aplicativo de anúncio no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Esta seção descreve os seguintes requisitos técnicos para o aplicativo de comunicado:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de porta

  - Requisitos do arquivo de áudio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

O aplicativo de comunicado tem os mesmos requisitos de hardware que os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

O aplicativo de comunicado tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Todos os servidores front-end ou servidores Standard Edition que executam o aplicativo de anúncio devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. O tempo de execução do Windows Media Format ou o Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que o aplicativo de anúncio reproduz para anúncios e música.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de porta

O aplicativo de comunicado usa a seguinte porta:

  - **Porta 5071**     Usado para solicitações de escuta SIP

<div>


> [!NOTE]  
> Essa porta é a definição padrão, que você pode modificar usando o cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de anúncio suporta o formato de arquivo Wave (. wav) e o formato de arquivo de áudio do Windows Media (. WMA) para música e comunicados. Os requisitos de arquivo de áudio para o aplicativo de comunicado são os mesmos do aplicativo grupo de resposta. Para obter detalhes, consulte [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

