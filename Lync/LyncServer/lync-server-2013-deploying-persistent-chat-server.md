---
title: 'Lync Server 2013: Implantando Servidor de Chat Persistente'
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
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Implantando Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-31_

Lync Server 2013, servidor de chat persistente faz parte da infraestrutura do Lync Server 2013.

A implantação do servidor de chat persistente exige que você:

  - Use o construtor de topologias para definir ou importar e publicar subseqüentemente a topologia e os componentes que você deseja implantar.

  - Preparar seu ambiente para a implantação de componentes persistentes do servidor de chat.

  - Instalar e configurar componentes do servidor de chat persistente para a sua implantação.

O servidor de chat persistente está disponível no Lync Server 2013 Enterprise Edition como um pool separado (não vem com os servidores front-end da Enterprise Edition). O servidor de chat persistente exige um servidor back-end do SQL Server no pool da edição Enterprise para armazenar o conteúdo da sala de chat e outros metadados relevantes. Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado, embora a colocação do servidor back-end do Lync Server 2013 e do **PersistentChatStore** na mesma instância do SQL Server seja compatível.

O servidor de chat persistente também pode ser implantado com o Lync Server 2013 Standard Edition. Nesse caso, o servidor front-end **PersistentChatService** é posicionado no computador com a Standard Edition, e o servidor back-end do **PersistentChatStore** pode ser implantado na instância local do SQL Server Express.

Para obter detalhes sobre as configurações de colocalização com suporte, consulte [colocação de servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Não oferecemos suporte à alta disponibilidade para o servidor&nbsp;de chat persistente Standard Edition. O desempenho e a escala serão limitados. Além disso, oferecemos suporte somente para o novo&nbsp;servidor persistente do servidor de chat persistente. Não oferecemos suporte à atualização do Lync Server 2010, do servidor de chat em grupo para&nbsp;um servidor de&nbsp;chat persistente do Lync Server 2013 Standard Edition.



</div>

Se a sua organização requer suporte à conformidade, você pode instalar o serviço de conformidade do servidor de chat persistente no servidor front-end do servidor de chat persistente. Um banco de dados separado é necessário para conformidade.

No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com software de banco de dados do SQL Server instalado.

Use o construtor de topologias para adicionar um servidor de chat persistente a suas implantações do Lync Server 2013. Você pode optar por adicionar um ou mais pools de servidores de chat persistentes usando o construtor de topologias. Siga as mesmas instruções de implantação para implantar vários pools persistentes do servidor de chat como faria com qualquer pool. Para obter detalhes, consulte [implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

Para obter detalhes sobre topologias disponíveis e os requisitos técnicos e de software para a instalação do servidor de chat persistente, consulte [planejando o servidor de chat persistente no Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento, [como o servidor de chat persistente funciona no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações e hardware compatível com o [Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.

Para obter detalhes sobre como adquirir certificados, criar o banco de dados do SQL Server e criar armazenamentos de arquivos, consulte [implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

Um servidor front-end único de servidor de chat persistente pode oferecer suporte a usuários ativos do 20.000. Você pode ter um pool de servidores de chat persistente com até quatro servidores front-end ativos que dão suporte a um total de 80.000 usuários simultâneos.

Também há suporte para o servidor de chat persistente em um servidor virtual. O servidor virtual pode oferecer suporte a até 20.000 usuários simultâneos se ele corresponder às especificações do servidor físico.

<div>


> [!IMPORTANT]  
> O servidor de chat persistente deve ser instalado em um sistema de arquivos NTFS para ajudar a reforçar a segurança do sistema de arquivos. FAT32 não é um sistema de arquivos com suporte para o servidor de chat persistente.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Como o servidor de chat persistente funciona no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lista de verificação de implantação para o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Requisitos técnicos para servidor de chat persistente no Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configurar sistemas e infraestrutura para o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Adicionando Servidor de Chat Persistente em sua implantação no Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Instalando o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Adicionando um administrador de Chat Persistente no Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configurando o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configurando Servidor de Chat Persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Configuração de solução de problemas do Servidor de Chat Persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configurando o Servidor de Chat Persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Failouver e failback do Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

