---
title: 'Lync Server 2013: Preparando a infraestrutura e os sistemas'
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
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Preparando a infraestrutura e os sistemas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

A implantação do Lync Server 2013 requer o uso do construtor de topologias para definir e publicar o design da topologia. Para identificar os componentes necessários para a sua topologia, use o construtor de topologias para criar e salvar um design de topologia. Antes de publicar sua topologia no construtor de topologias, faça o seguinte:

  - Adquirir e instalar o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores obrigatórios (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores que executam serviços de informações da Internet ( IIS) e servidores proxy inversos, conforme apropriado), adaptadores de rede, balanceadores de carga de hardware e dispositivos de armazenamento (como servidores de arquivos). Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.

  - Certifique-se de que a infraestrutura de rede atenda aos requisitos. Para obter detalhes, consulte [requisitos de infraestrutura de rede para o Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.

  - Configurar os serviços de domínio do Active Directory. Para publicar e habilitar a topologia, você precisa que os servidores internos sejam representados por contas de computador no AD DS. Isso é feito por meio da junção dos computadores com o AD DS. Para obter detalhes sobre como preparar o AD DS, consulte [preparando os serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Crie um compartilhamento de arquivos. Os servidores de edição padrão podem hospedar o compartilhamento de arquivos para o arquivo necessário, enquanto em uma implantação empresarial, o compartilhamento de arquivos não pode ser hospedado no servidor front-end. As permissões e associações de grupo necessárias para implantar e configurar a ACL (lista de controle de acesso) na pasta e o compartilhamento devem ser definidas corretamente para que o construtor de topologias seja concluído com êxito. Verifique se a pessoa que está executando o construtor de topologia tem as seguintes permissões e associações de Grupo:
    
      - Membro de administradores locais
    
      - Membro de usuários do domínio
    
      - Controle total sobre o compartilhamento e a pasta do armazenamento de arquivos

  - Para a edição Enterprise, instale e configure o SQL Server. Para que a configuração do SQL Server seja bem-sucedida, o servidor baseado no SQL Server deve estar online e a pessoa que publica a topologia é um administrador local no SQL Server e deve ser um membro do grupo sysadmin do SQL Server na instância do SQL Server.

Depois de concluir todas as tarefas de preparação conforme descrito neste tópico, mas antes de publicar a topologia, você também precisará executar as outras tarefas de preparação, incluindo a instalação dos sistemas operacionais Windows e outros softwares de pré-requisito, a configuração IIS e Configurando o DNS. Para obter detalhes sobre essas tarefas, consulte [requisitos do sistema para servidores que executam o Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configurar o IIS para o Lync Server 2013](lync-server-2013-configure-iis.md)e [preparar a infraestrutura e os sistemas para o Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Além disso, você deve se familiarizar com os requisitos do cliente e clientes. Para obter detalhes, consulte [implantando clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configuração de hardware para Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuração de software no Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparando Serviços de Domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configurar o SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar registros DNS no Lync Server 2013 para um pool de Front-Ends ou servidor Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Instalar ferramentas administrativas do Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

