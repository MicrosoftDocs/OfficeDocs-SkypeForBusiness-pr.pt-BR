---
title: 'Lync Server 2013: publicar a topologia'
description: 'Lync Server 2013: publicar a topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453fe186a02c88a5dcd7308096b661058fc04aa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547717"
---
# <a name="publish-the-topology-in-lync-server-2013"></a>Publicar a topologia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-01_

Para publicar com sucesso, habilite ou desabilite uma topologia ao adicionar ou remover uma função do servidor, você deve estar conectado como um usuário que é um membro do RTCUniversalServerAdmins e dos grupos Administradores do Domínio. Também é possível delegar as permissões e direitos de administrador adequadas. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Para obter as alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é exigida.

Depois de definir sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central. O repositório de gerenciamento central fornece um armazenamento robusto, esquematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server 2013. Ele também valida os dados para ajudar a garantir a consistência da configuração. Todas as alterações feitas nesses dados de configuração acontecem no repositório de gerenciamento central, eliminando problemas de "fora de sincronização". Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo os servidores de borda.

<div>


> [!NOTE]  
> O SQL Server precisa de um mínimo de 20 GB de espaço livre em disco para publicar a topologia inicial com êxito e criar o servidor de gerenciamento central.



</div>

<div>


> [!NOTE]  
> Somente para o Enterprise Edition: para publicar a topologia, o servidor back-end baseado em SQL Server deve estar online e acessível com exceções de firewall no local. Para obter detalhes sobre como especificar exceções de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall Requirements for SQL Server with Lync server 2013</A>. Para obter detalhes sobre como configurar o SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configurar o SQL Server para o Lync Server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Para publicar uma topologia

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Selecione para abrir a topologia de um arquivo local. Se você estiver no computador em que você definiu a topologia, ela estará no local onde você a salvou nas etapas anteriores. Normalmente, essa será a pasta de documentos do usuário que configurou a topologia.

3.  Clique com o botão direito do mouse no nó **Lync Server 2013** e clique em **publicar topologia**.

4.  Na página **Publicar a Topologia**, clique em **Avançar**.

5.  Na página **criar bancos de dados** , selecione os bancos de dados que você deseja publicar.
    
    <div>
    

    > [!NOTE]  
    > Se você não tiver os direitos apropriados para criar os bancos de dados, você pode desmarcar as caixas de seleção ao lado desses bancos de dados e alguém com direitos apropriados pode criar os bancos de dados mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.

    
    </div>

6.  Opcionalmente, clique em **avançado**. As opções avançadas de posicionamento do arquivo de dados do SQL Server permitem que você selecione entre as seguintes opções:
    
      - **Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração do disco no servidor baseado em SQL Server, distribuindo os arquivos de log e de dados para o melhor local.
    
      - **Usar padrões de instância do SQL Server** – essa opção coloca os arquivos de log e de dados no servidor baseado em SQL Server usando as configurações da instância. Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar os locais ideais para logs e dados. O administrador do SQL Server normalmente moveria os arquivos de log e de dados para locais apropriados para os procedimentos de gerenciamento de organização e servidor baseados no SQL Server.
    
    Clique em **OK**, e depois clique em **Avançar**.

7.  Na página **selecionar servidor de gerenciamento central** , selecione um pool de front-ends.

8.  Opcionalmente, clique em **avançado**. As opções avançadas de posicionamento do arquivo de dados do SQL Server permitem que você selecione entre as seguintes opções:
    
      - **Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração do disco no servidor baseado em SQL Server, distribuindo os arquivos de log e de dados para o melhor local.
    
      - **Usar padrões de instância do SQL Server** – essa opção coloca os arquivos de log e de dados no servidor baseado em SQL Server usando as configurações da instância. Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar os locais ideais para logs e dados. O administrador do SQL Server normalmente moveria os arquivos de log e de dados para locais apropriados para os procedimentos de gerenciamento de organização e servidor baseados no SQL Server.
    
    Clique em **OK**.

9.  Clique em **Avançar** para concluir o processo de publicação.

10. Quando o processo de publicação for concluído, clique em **Finalizar**.
    
    Quando a topologia foi publicada com êxito, você pode começar a instalar uma réplica local do repositório de gerenciamento central em cada servidor que executa o Lync Server 2013 em sua topologia. Recomendamos que você comece com o primeiro pool de front-ends.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando servidores front-end e pools de front-ends para o Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

