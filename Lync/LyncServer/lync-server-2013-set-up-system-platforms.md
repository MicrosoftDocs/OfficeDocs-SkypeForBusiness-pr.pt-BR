---
title: 'Lync Server 2013: Configurar plataformas de sistema'
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
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configurar plataformas de sistema no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Antes de iniciar a implantação do servidor de chat persistente, você deve instalar o sistema operacional necessário em hardware que atenda aos requisitos do sistema em servidores:

Para obter detalhes sobre o hardware com suporte para servidores que executam o Lync Server 2013, servidores de banco de dados e servidores de arquivos, consulte [hardware com suporte para o Lync server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte. Para obter detalhes sobre os sistemas operacionais e o software de banco de dados com suporte, consulte [suporte a infraestrutura e software do servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte. Para obter detalhes sobre os requisitos do Windows Update, consulte [suporte e requisitos adicionais do servidor no Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) na documentação de suporte.

O servidor de front-end do servidor de chat persistente, **PersistentChatService**, pode ser implantado em um ou mais computadores autônomos em um pool do Lync Server 2013 Enterprise Edition. Eles não podem ser posicionados nos servidores front-end do Lync Server Enterprise Edition. O servidor de chat persistente pode ser implantado pelo bootstrapper, exatamente como outras funções do Lync Server. Os **Serviços Web de chat persistente para o download/download de arquivo**e os **Serviços Web de chat persistente para o gerenciamento de salas de chat** são componentes da Web implantados nos servidores de Front-End do Lync Server 2013.

Um servidor front-end único de servidor de chat persistente pode oferecer suporte a usuários ativos do 20.000. Você pode ter um pool de servidores de chat persistente com até 4 front-ends ativos oferecendo suporte a um total de 80.000 usuários simultâneos. O servidor back-end de chat persistente, **PersistentChatStore**, armazena as salas de chat e as categorias. Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado no pool da Enterprise Edition; Embora possamos dar suporte à colocação do servidor back-end do Lync Server 2013 e **PersistentChatStore** na mesma instância do SQL Server.

Se a sua organização requer suporte à conformidade, você pode instalá-la usando o construtor de topologias. O serviço de conformidade do servidor de chat persistente está instalado no mesmo computador que o servidor front-end persistente do servidor de chat. Um banco de dados separado é necessário para conformidade. Para obter detalhes sobre os requisitos de conformidade do servidor de chat persistente, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com software de banco de dados do SQL Server instalado. O construtor de topologias suporta vários pools de servidores de chat persistentes. Siga as mesmas instruções de implantação para implantar vários pools de servidores de chat persistentes como faria para qualquer pool de [implantação do Lync server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

Você também pode implantar o servidor de chat persistente com o Lync Server 2013 Standard Edition. Nesse caso, o servidor front-end **PersistentChatService** é posicionado no servidor Standard Edition, e você pode implantar o servidor back-end do **PersistentChatStore** na instância local do SQL Server Express.

<div>


> [!IMPORTANT]  
> Não oferecemos suporte à edição do servidor&nbsp;de chat padrão persistente para alta disponibilidade. O desempenho e a escala serão limitados. Além disso, oferecemos apenas novas implantações&nbsp;persistentes de servidor de edição de servidor de chat persistente. Não oferecemos suporte a uma atualização do Lync Server 2010, do servidor de chat em grupo para um&nbsp;servidor de chat&nbsp;persistente do Lync Server 2013 Standard Edition.



</div>

<div>

## <a name="see-also"></a>Confira também


[Suporte adicional e requisitos de servidor no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Hardware suportado para Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Suporte a software e à infraestrutura de servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planejando o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

