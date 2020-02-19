---
title: 'Lync Server 2013: configuração de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Configuração de hardware para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Configurar o hardware e outros componentes necessários na infraestrutura de que você precisa para implementar sua topologia requer que, antes de publicar sua topologia no construtor de topologias, faça o seguinte:

  - Instale o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores necessários (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores que executam os serviços de informações da Internet (IIS) e servidores de proxy reverso, conforme apropriado), adaptadores de rede, balanceadores de carga de hardware e dispositivos de armazenamento (como servidores de arquivos). Confirme que seguiu as recomendações de número e velocidade dos adaptadores de rede. Se você for usar balanceadores de carga de hardware, certifique-se de ter as informações corretas do fornecedor para configurá-las para uso com o Lync Server 2013. Se você estiver usando um servidor de arquivos ou outro servidor para hospedar o compartilhamento de arquivos exigido pelo Lync Server, certifique-se de que o servidor está disponível e pronto para a configuração do compartilhamento de arquivos. Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.

  - Certifique-se de que a infraestrutura de rede atende aos requisitos. Para obter detalhes, consulte [Network Infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.

  - Configurar os serviços de domínio do Active Directory. A configuração do AD DS inclui prepará-lo e definir todos os componentes que você deseja implementar nele. Para obter detalhes sobre como preparar o AD DS, consulte [preparação de serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.

  - Configure as permissões exigidas para criar o compartilhamento de arquivo. As permissões para o uso de compartilhamentos de arquivos pelo Lync Server 2013 são automaticamente configuradas pelo construtor de topologias quando você publica sua topologia. No entanto, a conta de usuário usada para publicar a topologia deve ter controle total (leitura/gravação/modificação) no compartilhamento de arquivos para que o construtor de topologia configure as permissões necessárias. Para garantir que o compartilhamento de arquivos possa ser gerenciado corretamente durante o processo de publicação do construtor de topologia, o usuário ou grupo de domínio do qual o usuário é membro deve ser membro do grupo local de administradores no computador onde o compartilhamento de arquivo está localizado. Em um cenário com diversos domínios, o usuário o grupo do Domínio A deve ser tornado membro do grupo local de Administradores na máquina no Domínio B em que o compartilhamento de arquivos será localizado.
    
    Para obter detalhes sobre a atualização usando os compartilhamentos de arquivos em um sistema de arquivos distribuídos (DFS), consulte [Configurar o armazenamento de arquivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > O compartilhamento de arquivos do Lync Server 2013, Enterprise Edition, não pode ser localizado no servidor front-end.

    
    </div>

  - Instale e configure o balanceador de carga de hardware para serviços Web. Com o balanceamento de carga do Sistema de Nome de Domínio (DNS) implantado, você ainda precisa usar balanceadores de carga de hardware para esses pools, mas somente para o tráfego de HTTP/HTTPS. O balanceador de carga de hardware é usado para o tráfego de HTTPS dos clientes pelas portas 443 e 80. Embora você ainda precise de balanceadores de carga de hardware para esses pools, sua configuração e administração será principalmente para o tráfego HTTP/HTTPS, aos quais os administradores dos balanceadores de carga de hardware estão acostumados.

Depois de concluir todas as tarefas de preparação descritas neste tópico, mas antes de publicar a topologia, também é necessário:

  - [Instalar sistemas operacionais e software de pré-requisito nos servidores do Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurar o IIS para Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configurar o SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar registros DNS no Lync Server 2013 para um pool de front-ends ou servidor Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

