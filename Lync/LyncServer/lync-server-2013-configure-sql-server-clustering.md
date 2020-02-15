---
title: 'Lync Server 2013: configurar clustering do SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984e7d7e287e9177fff5798c9cb20ab476591f46
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurar o cluster do SQL Server para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-10_

O Microsoft Lync Server 2013 suporta clustering para o SQL Server 2012 e o SQL Server 2008 R2. Para obter detalhes sobre o que é suportado, confira [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md).

Você deve configurar e configurar o cluster do SQL Server antes de instalar e implantar o servidor front-end Enterprise Edition e o banco de dados back-end. Para obter as práticas recomendadas e as instruções de instalação do clustering de failover <http://technet.microsoft.com/library/hh231721.aspx>no SQL Server 2012, consulte. Para clustering de failover no SQL Server 2008, <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>consulte.

Ao instalar o SQL Server, você deve instalar o SQL Server Management Studio para gerenciar os locais para o banco de daods e os locais para o arquivo de log. O SQL Server Management Studio é instalado como um componente opcional ao instalar o SQL Server.

<div>


> [!IMPORTANT]  
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server, é necessário ser um membro do grupo sysadmin do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo sysadmin do SQL Server, será necessário solicitar sua adição ao grupo até que os arquivos do banco de dados sejam implantados. Se você não puder se tornar um membro do grupo sysadmin, forneça ao seu administrador de banco de dados do SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário adequados que você precisa para realizar os procedimentos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Para configurar o cluster de SQL Server

1.  Depois de concluir a instalação e a configuração do cluster do SQL Server, defina o repositório do SQL Server no construtor de topologias usando o nome de cluster virtual da instância do SQL Server (conforme configurado na configuração para o cluster do SQL Server) e a instância nome do banco de dados do SQL Server. Diferente de um servidor único baseado em SQL Server, você usará o FQDN (nome de domínio totalmente qualificado) do nó virtual para um servidor baseado em SQL Server em cluster.
    
    <div>
    

    > [!NOTE]  
    > Os nós de cluster individuais do Windows Server não precisam ser configurados para o construtor de topologias. Você usará somente o nome do cluster SQL Server virtual.

    
    </div>

2.  Se você estiver usando o construtor de topologias para implantar seus bancos de dados, você deve ser membro do grupo sysadmin do SQL Server. Se você é membro do grupo sysadmin do SQL Server, mas não tem privilégios no domínio (por exemplo, uma função de administrador de banco de dados do SQL Server), você tem os direitos para criar os bancos de dados, mas não para ler as informações necessárias no Lync Server. Para obter detalhes sobre os direitos e permissões de usuário necessários para implantar o Lync Server, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Certifique-se que o padrão de pasta de banco de dados e de pasta de arquivos de log sejam mapeados corretamente para os discos compartilhados no cluster de SQL Server usando o SQL Server Management Studio. Esse é um procedimento necessário se você for criar bancos de dados usando o Construtor de Topologia.
    
    <div>
    

    > [!NOTE]  
    > Se você não tiver instalado o SQL Server Management Studio, poderá instalá-lo executando novamente a instalação do SQL Server e selecionando a ferramenta de gerenciamento como um recurso adicionado para a implantação existente do SQL Server.

    
    </div>

4.  Instale os bancos de dados para o servidor baseado em SQL Server usando o construtor de topologias ou os cmdlets do Windows PowerShell. Para usar o construtor de topologias, use o procedimento a seguir. Para usar os cmdlets do Windows PowerShell, consulte [instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Para criar bancos de dados usando o construtor de topologias

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > O procedimento a seguir pressupõe que você tenha definido e configurado sua topologia no construtor de topologias. Para obter detalhes sobre como definir sua topologia, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">definindo e configurando a topologia no Lync Server 2013</A>. Para usar o Construtor de Topologia para publicar e configurar o banco de dados, faça logon como um usuário com os direitos de usuário e associações de grupo corretas. Para obter detalhes sobre os direitos e associações de grupo necessários, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.

    
    </div>

2.  No construtor de topologias, à medida que você publicar a topologia, na página **criar bancos de dados** , clique em **avançado**.

3.  A página **Selecionar Local de Arquivo de Banco de Dados** tem duas opções que determinam como os arquivos de banco de dados serão implantados no cluster de SQL Server. Selecione uma das seguintes opções:
    
      - **Determina automaticamente o local do arquivo do banco de dados.** Essa seleção usa um algoritmo para determinar os locais de log e arquivo de dados do banco de dados com base na configuração de unidade no servidor baseado em SQL Server. Os arquivos serão distribuídos de uma forma que tenta fornecer o melhor desempenho.
    
      - Usar padrões de instância do SQL Server. Selecionar essa opção instalará os arquivos de log e de dados de acordo com as configurações da instância do SQL Server. Após a implantação dos arquivos do banco de dados no SQL Server, o administrador do banco de dados do SQL Server pode querer realocar os arquivos para otimizar o desempenho de seus requisitos de configuração do SQL Server específicos.

4.  Conclua a publicação da topologia e verifique se não ocorreram erros durante a operação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

