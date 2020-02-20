---
title: 'Lync Server 2013: Implantando servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Implantando o servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-31_

Lync Server 2013, servidor de chat persistente é parte da infraestrutura 2013 do Lync Server.

A implantação do servidor de chat persistente requer que você:

  - Use o construtor de topologias para definir ou importar e, em seguida, publicar sua topologia e os componentes que você deseja implantar.

  - Prepare seu ambiente para a implantação de componentes do servidor de chat persistente.

  - Instale e configure os componentes do servidor de chat persistente para sua implantação.

O servidor de chat persistente está disponível com o Lync Server 2013 Enterprise Edition como um pool separado (não colocado com os servidores de front-end Enterprise Edition). O servidor de chat persistente requer um servidor back-end do SQL Server em seu pool Enterprise Edition para armazenar o conteúdo da sala de chat e outros metadados relevantes. Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado, embora o servidor de back-end do Lync Server 2013 e o **PersistentChatStore** na mesma instância do SQL Server sejam posicionados.

O servidor de chat persistente também pode ser implantado com o Lync Server 2013 Standard Edition. Nesse caso, o servidor front-end do **PersistentChatService** é colocado no computador Standard Edition, e o servidor back-end do **PersistentChatStore** pode ser implantado na instância local do SQL Server Express.

Para obter detalhes sobre as configurações de colocal com suporte, consulte [colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Não há suporte para alta disponibilidade para o servidor&nbsp;de chat persistente Standard Edition. Desempenho e escala será limitado. Além disso, oferecemos suporte somente para o novo&nbsp;servidor do servidor de chat persistente. Não há suporte para atualizar o Lync Server 2010, o servidor de chat de grupo para&nbsp;um servidor do&nbsp;Lync Server 2013 persistent chat Server Standard Edition.



</div>

Se sua organização exigir o suporte de conformidade, você poderá instalar o serviço de conformidade do servidor de chat persistente no servidor front-end do servidor de chat persistente. Um banco de dados separado é exigido para conformidade.

No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com o software de banco de dados do SQL Server instalado.

Use o construtor de topologias para adicionar o servidor de chat persistente às implantações do Lync Server 2013. Você pode optar por adicionar um ou mais pools de servidores de chat persistentes usando o construtor de topologias. Siga as mesmas instruções de implantação para implantar vários pools de servidores de chat persistentes, como faria para qualquer pool. Para obter detalhes, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

Para obter detalhes sobre topologias disponíveis e os requisitos técnicos e de software para instalar o servidor de chat persistente, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento, [como o servidor de chat persistente funciona no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) na documentação de planejamento, documentação de implantação ou operações e [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.

Para obter detalhes sobre a aquisição de certificados, criação do banco de dados do SQL Server e criação de repositórios de arquivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

Um servidor front-end único de servidor de chat persistente pode oferecer suporte A 20.000 usuários ativos. Você pode ter um pool de servidores de chat persistente com até quatro servidores front-end ativos suportando um total de 80.000 usuários simultâneos.

O servidor de chat persistente também é compatível com um servidor virtual. O servidor virtual pode suportar até 20.000 usuários simultâneos se ele corresponder às especificações do servidor físico.

<div>


> [!IMPORTANT]  
> O servidor de chat persistente deve ser instalado em um sistema de arquivos NTFS para ajudar a aplicar a segurança do sistema de arquivos. FAT32 não é um sistema de arquivos com suporte para o servidor de chat persistente.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Como funciona o servidor de chat persistente no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lista de verificação de implantação para o servidor de chat persistente no Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Requisitos técnicos para o servidor de chat persistente no Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configurando sistemas e infraestrutura para o servidor de chat persistente no Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Adicionando servidor de chat persistente à sua implantação no Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Instalando o servidor de chat persistente no Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Adicionando um administrador de chat persistente no Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configurando o servidor de chat persistente no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Solucionando problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Failover e failback do servidor de chat persistente no Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

