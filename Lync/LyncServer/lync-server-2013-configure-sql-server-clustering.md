---
title: 'Lync Server 2013: configurar o agrupamento do SQL Server'
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
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurar o cluster do SQL Server para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-10_

O Microsoft Lync Server 2013 suporta clustering para SQL Server 2012 e SQL Server 2008 R2. Para obter detalhes sobre o que é suportado, consulte [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md).

Você deve configurar e configurar o cluster do SQL Server antes de instalar e implantar o servidor front-end do Enterprise Edition e o banco de dados back-end. Para obter práticas recomendadas e instruções de configuração para clustering de failover no SQL <http://technet.microsoft.com/en-us/library/hh231721.aspx>Server 2012, consulte. Para o cluster de failover no SQL Server 2008, <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>consulte.

Ao instalar o SQL Server, o SQL Server Management Studio deve ser instalado para gerenciar os locais de bases de dados e arquivos de log. O SQL Server Management Studio é instalado como componente opcional quando da instalação do SQL Server.

<div>


> [!IMPORTANT]  
> Para instalar e implantar os bancos de dados no servidor baseado no SQL Server, você deve ser membro do grupo sysadmin do SQL Server para o servidor baseado no SQL Server no qual está instalando os arquivos do banco de dados. Se você não for membro do grupo sysadmin do SQL Server, será necessário solicitar que você seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se não for possível tornar um membro do grupo sysadmin, você deve fornecer ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário adequados que você precisa para executar os procedimentos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permissões de implantação do SQL Server no Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Para configurar o agrupamento do SQL Server

1.  Depois de concluir a instalação e a configuração do cluster do SQL Server, defina a loja do SQL Server no construtor de topologias usando o nome do cluster virtual da instância do SQL Server (conforme configurado na configuração do agrupamento do SQL Server) e a instância nome do banco de dados do SQL Server. Diferente de um único servidor baseado no SQL Server, você usará o nome de domínio totalmente qualificado (FQDN) do nó virtual para um servidor de cluster com SQL Server.
    
    <div>
    

    > [!NOTE]  
    > Os nós de clusters individuais do Windows Server não precisam ser configurados para o construtor de topologias. Você usará somente o nome do cluster do SQL Server virtual.

    
    </div>

2.  Se você estiver usando o construtor de topologias para implantar seus bancos de dados, você deve ser membro do grupo sysadmin do SQL Server. Se você for membro do grupo sysadmin do SQL Server, mas não tiver privilégios no domínio (por exemplo, uma função de administrador de banco de dados do SQL Server), terá os direitos para criar os bancos de dados, mas não poderá ler as informações necessárias no Lync Server. Para obter detalhes sobre os direitos de usuário e as permissões necessárias para implantar o Lync Server, consulte [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Verifique se a pasta de banco de dados e os padrões de pasta de arquivos de log estão mapeados corretamente para os discos compartilhados no cluster do SQL Server usando o SQL Server Management Studio. Esse será um procedimento obrigatório se você criar bancos de dados usando o construtor de topologias.
    
    <div>
    

    > [!NOTE]  
    > Se você não instalou o SQL Server Management Studio, é possível instalá-lo executando novamente a instalação do SQL Server e selecionando a ferramenta de gerenciamento como um recurso adicionado para a implantação existente do SQL Server.

    
    </div>

4.  Instale os bancos de dados para o servidor baseado no SQL Server usando o construtor de topologias ou cmdlets do Windows PowerShell. Para usar o construtor de topologias, use o procedimento a seguir. Para usar cmdlets do Windows PowerShell, consulte [instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Para criar bancos de dados usando o construtor de topologias

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > O procedimento a seguir pressupõe que você definiu e configurou sua topologia no construtor de topologias. Para obter detalhes sobre como definir sua topologia, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">definindo e configurando a topologia no Lync Server 2013</A>. Para usar o construtor de topologias para publicar a topologia e configurar o banco de dados, você deve fazer logon como um usuário com os direitos de usuário e associações de grupo corretos. Para obter detalhes sobre os direitos obrigatórios e associações de grupo, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permissões de implantação do SQL Server no Lync Server 2013</A>.

    
    </div>

2.  No construtor de topologia, à medida que você publica a topologia, na página **criar bancos de dados** , clique em **avançado**.

3.  A página **selecionar local do arquivo de banco de dados** tem duas opções que determinam como os arquivos de banco de dados serão implantados no cluster do SQL Server. Selecione uma das seguintes opções:
    
      - **Determine automaticamente o local do arquivo de banco de dados.** Essa seleção usa um algoritmo para determinar os locais do log de banco de dados e do arquivo de dados com base na configuração da unidade no servidor baseado no SQL Server. Os arquivos serão distribuídos de forma a tentar fornecer o desempenho ideal.
    
      - Usar padrões de instância do SQL Server. Selecionar essa opção instalará os arquivos de log e de dados de acordo com as configurações da instância do SQL Server. Após a implantação dos arquivos de banco de dados no SQL Server, o administrador do banco de dados do SQL Server pode querer realocar os arquivos para otimizar o desempenho de seus requisitos de configuração específicos do SQL Server.

4.  Conclua a publicação da topologia e confirme se não houve erros durante a operação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

