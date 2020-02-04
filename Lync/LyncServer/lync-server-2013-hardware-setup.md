---
title: 'Lync Server 2013: Configuração de hardware'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Configuração de hardware para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

A configuração do hardware e de outros componentes necessários na infraestrutura em que você precisa implementar a topologia requer que, antes de publicar sua topologia no construtor de topologias, faça o seguinte:

  - Instale o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores necessários (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores que executam serviços de informações da Internet (IIS) e servidores proxy inversos, conforme apropriado), adaptadores de rede, balanceadores de carga de hardware e dispositivos de armazenamento (como servidores de arquivos). Confirme se você seguiu as recomendações para o número e a velocidade de adaptadores de rede. Se você estiver usando balanceadores de carga de hardware, verifique se você tem as informações adequadas do fornecedor para configurá-los para uso com o Lync Server 2013. Se você estiver usando um servidor de arquivos ou outro servidor para armazenar o compartilhamento de arquivos exigido pelo Lync Server, verifique se o servidor está disponível e pronto para a configuração do compartilhamento de arquivos. Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.

  - Certifique-se de que a infraestrutura de rede atenda aos requisitos. Para obter detalhes, consulte [requisitos de infraestrutura de rede para o Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.

  - Configurar os serviços de domínio do Active Directory. Configurar o AD DS inclui preparar o AD DS e definir todos os componentes que você deseja implantar no AD DS. Para obter detalhes sobre como preparar o AD DS, consulte [preparando os serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.

  - Configure as permissões necessárias para criar o compartilhamento de arquivos. As permissões para uso de compartilhamentos de arquivos pelo Lync Server 2013 são automaticamente configuradas pelo construtor de topologias quando você publica sua topologia. No entanto, a conta de usuário usada para publicar a topologia deve ter controle total (leitura/gravação/modificação) no compartilhamento de arquivos para que o construtor de topologias configure as permissões necessárias. Para verificar se o compartilhamento de arquivos pode ser gerenciado corretamente durante o processo de publicação do construtor de topologia, o usuário ou grupo de domínio do qual o usuário é membro deve ser membro do grupo Administradores local no computador onde o compartilhamento de arquivos está localizado. Em um cenário de vários domínios, o domínio um usuário ou grupo deve ser membro do grupo Administradores local na máquina do domínio B em que o compartilhamento de arquivos será localizado.
    
    Para obter detalhes sobre a atualização usando compartilhamentos de arquivos em um sistema de arquivos distribuídos (DFS), consulte [Configurar o armazenamento de arquivos para o Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > O compartilhamento de arquivos do Lync Server 2013, Enterprise Edition, não pode ser localizado no servidor front-end.

    
    </div>

  - Instale e configure o balanceador de carga de hardware para serviços Web. Com o balanceamento de carga do sistema de nomes de domínio (DNS) implantado, você ainda precisa usar balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTP/HTTPS. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80. Embora você ainda precise de balanceadores de carga de hardware para esses pools, sua configuração e Administração serão principalmente para tráfego HTTP/HTTPS, para o qual os administradores dos balanceadores de carga de hardware estão acostumados.

Depois de concluir todas as tarefas de preparação, conforme descrito neste tópico, mas antes de publicar a topologia, você também precisa:

  - [Instalar sistemas operacionais e software de pré-requisito nos servidores para Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurar o IIS para Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configurar o SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar registros DNS no Lync Server 2013 para um pool de Front-Ends ou servidor Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

