---
title: 'Lync Server 2013: Suporte a armazenamento de arquivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Suporte a armazenamento de arquivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-16_

O Lync Server 2013 usa o mesmo armazenamento de arquivos para todo o armazenamento de arquivos. O suporte para armazenamento de arquivos inclui o seguinte:

  - Um compartilhamento de arquivos no armazenamento de conexão direta (DAS) ou em uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e uma matriz redundante de discos independentes (RAID) para armazenamentos de arquivos. Para obter detalhes sobre requisitos de armazenamento, consulte [requisitos técnicos para servidores front-end, mensagens instantâneas e presença no Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) e [requisitos de hardware e software para o diretor do Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) na documentação de planejamento. Para obter detalhes sobre o sistema operacional do DFS para Windows Server 2008, consulte o guia passo a passo do DFS para Windows Server [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)2008 em.

  - Um cluster compartilhado para o compartilhamento de arquivos. Se você usa um cluster compartilhado, deve usar os servidores de cluster que executam o Windows Server 2008 ou o Windows Server 2008 R2. Usar servidores de cluster executando uma versão mais antiga do Windows pode resultar em problemas de permissão que impedem a disponibilidade de alguns recursos. Use o administrador de cluster para criar os compartilhamentos de arquivos. Para obter detalhes sobre como usar o administrador de cluster, consulte o artigo 284838 da base de dados de conhecimento Microsoft, "como criar um compartilhamento de arquivos [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)de cluster de servidor com cluster. exe" em.

</div>

<span> </span>

</div>

</div>

</div>

