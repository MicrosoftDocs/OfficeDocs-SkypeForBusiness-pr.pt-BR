---
title: Suporte ao armazenamento de arquivos do Lync Server 2013
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
ms.openlocfilehash: 1cc2250020b7456515f06bcb308ca4cea4430a56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Suporte ao armazenamento de arquivos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-16_

O Lync Server 2013 usa o mesmo repositório de arquivos para todo o armazenamento de arquivos. O suporte ao armazenamento de arquivos inclui o seguinte:

  - Um compartilhamento de arquivos no DAS (armazenamento de conexão direta) ou uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e um conjunto redundante de discos independentes (RAID) para repositórios de arquivos. Para obter detalhes sobre os requisitos de armazenamento, consulte [requisitos técnicos para servidores front-end, mensagens instantâneas e presença no Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) e [requisitos de hardware e software para o diretor no Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) na documentação de planejamento. Para obter detalhes sobre o sistema operacional do DFS para Windows Server 2008, consulte o guia passo a passo do DFS para o Windows [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)Server 2008 em.

  - Um cluster compartilhado para o compartilhamento de arquivos. Se você usar um cluster compartilhado, deverá usar servidores de cluster executando o Windows Server 2008 ou o Windows Server 2008 R2. O uso de servidores de cluster executando uma versão mais antiga do Windows pode resultar em problemas de permissão que impedem a disponibilidade de alguns recursos. Use o Administrador de cluster para criar compartilhamentos de arquivo. Para obter detalhes sobre como usar o administrador de cluster, consulte o artigo 284838 da base de dados de conhecimento da Microsoft, "como criar um compartilhamento de [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)arquivo de cluster de servidor com cluster. exe" em.

</div>

<span> </span>

</div>

</div>

</div>

