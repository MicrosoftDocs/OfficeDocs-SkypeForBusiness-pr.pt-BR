---
title: 'Lync Server 2013: configurar plataformas do sistema'
description: 'Lync Server 2013: configurar plataformas de sistema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd02c519d5632b7aa5732fbd9b880f7d1084b50f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550437"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configurar plataformas de sistema no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Antes de iniciar a implantação do servidor de chat persistente, você deve instalar o sistema operacional necessário no hardware que atenda aos requisitos do sistema nos servidores:

Para obter detalhes sobre o hardware suportado para servidores que executam o Lync Server 2013, servidores de banco de dados e servidores de arquivos, consulte [hardware suportado para o Lync server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte. Para obter detalhes sobre sistemas operacionais e software de banco de dados suportados, consulte [Server Software and Infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte. Para obter detalhes sobre os requisitos do Windows Update, consulte [Additional Server Support and Requirements in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) na documentação de suporte.

O servidor front-end do servidor de chat persistente, **PersistentChatService**, pode ser implantado em um ou mais computadores autônomos em um pool do Lync Server 2013 Enterprise Edition. Eles não podem ser colocados nos servidores front-end do Lync Server Enterprise Edition. O servidor de chat persistente pode ser implantado pelo bootstrapper, assim como outras funções do Lync Server. Os **Serviços Web de chat persistente para upload/download de arquivo**e **Serviços Web de chat persistente para gerenciamento de salas de chat** são componentes da Web implantados nos servidores Front-End do Lync Server 2013.

Um servidor front-end único de servidor de chat persistente pode oferecer suporte A 20.000 usuários ativos. Você pode ter um pool de servidores de chat persistente com até 4 front-ends ativos suportando um total de 80.000 usuários simultâneos. O servidor back-end de chat persistente, **PersistentChatStore**, armazena as salas de chat e as categorias. Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado em seu pool Enterprise Edition; Embora ofereçamos suporte à colocação do servidor back-end do Lync Server 2013 e ao **PersistentChatStore** na mesma instância do SQL Server.

Se sua organização exigir o suporte de conformidade, você poderá instalá-lo usando o construtor de topologias. O serviço de conformidade do servidor de chat persistente está instalado no mesmo computador que o servidor de front-end do servidor de chat persistente. Um banco de dados separado é exigido para conformidade. Para obter detalhes sobre os requisitos de conformidade para o servidor de chat persistente, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com o software de banco de dados do SQL Server instalado. O construtor de topologias suporta vários pools de servidores de chat persistente. Siga as mesmas instruções de implantação para implantar vários pools de servidores de chat persistente, como faria para qualquer pool de [implantação do Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

Você também pode implantar o servidor de chat persistente com o Lync Server 2013 Standard Edition. Nesse caso, o servidor front-end do **PersistentChatService** é colocado no servidor Standard Edition, e você pode implantar o servidor back-end do **PersistentChatStore** na instância local do SQL Server Express.

<div>


> [!IMPORTANT]  
> Não há suporte para o servidor de chat persistente &nbsp; Standard Edition para alta disponibilidade. Desempenho e escala será limitado. Além disso, damos suporte somente a novas &nbsp; implantações do servidor do servidor de chat persistente. Não há suporte para uma atualização do Lync Server 2010, o servidor de chat de grupo para um servidor de chat persistente do Lync Server 2013 &nbsp; persistent &nbsp; Standard Edition.



</div>

<div>

## <a name="see-also"></a>Confira também


[Suporte e requisitos adicionais do servidor no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Suporte a infraestrutura e software de servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

