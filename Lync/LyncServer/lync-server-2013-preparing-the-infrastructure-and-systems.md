---
title: 'Lync Server 2013: preparando a infraestrutura e os sistemas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb33552fde0da6dc91f21eeecaf1ea5e85d72159
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Preparando a infraestrutura e os sistemas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

A implantação do Lync Server 2013 requer o uso do construtor de topologias para definir e publicar o design de topologia. Para identificar os componentes necessários para sua topologia, use o construtor de topologias para criar e salvar um design de topologia. Antes de publicar sua topologia no construtor de topologias, faça o seguinte:

  - Adquirir e instalar o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores necessários (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores executando o serviços de informações da Internet ( IIS) e servidores proxy reversos, conforme apropriado, adaptadores de rede, balanceadores de carga de hardware e dispositivos de armazenamento (como servidores de arquivos). Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.

  - Certifique-se de que a infraestrutura de rede atende aos requisitos. Para obter detalhes, consulte [Network Infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.

  - Configurar os serviços de domínio do Active Directory. Para publicar e habilitar a topologia, é necessário que os servidores internos sejam representados por contas de computador no AD DS. Para isso, é preciso unir os computadores ao AD DS. Para obter detalhes sobre como preparar o AD DS, consulte [preparação de serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Crie um compartilhamento de arquivos. Servidores Standard Edition podem hospedar o compartilhamento de arquivos para o arquivo necessário, enquanto em uma implantação do Enterprise o compartilhamento de arquivos não pode ser hospedada no servidor de front end. As permissões e associações de grupo necessárias para implantar e configurar a lista de controle de acesso (ACL) na pasta e o compartilhamento devem ser definidos corretamente para que o Construtor de Topologias seja concluído com sucesso. Você deve verificar se a pessoa que está executando o construtor de topologia tem as seguintes permissões e associações de Grupo:
    
      - Membro de Administradores Locais
    
      - Membro de Usuários do Domínio
    
      - Controle total sobre o compartilhamento e a pasta do repositório de arquivos

  - Para o Enterprise Edition, instale e configure o SQL Server. Para que a instalação do SQL Server seja concluída com sucesso, o servidor com base no SQL Server deve estar online e a pessoa que estiver publicando a topologia deve ser administradora local no SQL Server e membro do grupo sysadmin na instância do SQL Server.

Depois de concluir todas as tarefas de preparação conforme descrito neste tópico, mas antes de publicar a topologia, também é necessário executar outras tarefas de preparação, incluindo a instalação dos sistemas operacionais Windows e os demais softwares de pré-requisito, configurar o IIS e o DNS. Para obter detalhes sobre essas tarefas, consulte [requisitos do sistema para servidores que executam o Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure o IIS para o Lync Server 2013](lync-server-2013-configure-iis.md)e [preparar a infraestrutura e os sistemas para o Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Além disso, você deve estar familiarizado com os clientes e seus requisitos. Para obter detalhes, consulte [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configuração de hardware para o Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuração de software para o Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparando os Serviços de Domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configurar o SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar registros DNS no Lync Server 2013 para um pool de front-ends ou servidor Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Instalar ferramentas administrativas do Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

