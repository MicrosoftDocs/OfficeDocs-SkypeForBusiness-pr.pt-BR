---
title: 'Lync Server 2013: Publicar a topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Publicar a topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-01_

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio. Também é possível delegar permissões e direitos de administrador adequados. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.

Depois de definir sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central. O repositório de gerenciamento central fornece um armazenamento robusto e schematized dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server 2013. Ele também valida os dados para ajudar a garantir a consistência de configuração. Todas as alterações nestes dados de configuração acontecem nesse repositório, eliminando problemas de "dessincronização". Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo os servidores de borda.

<div>


> [!NOTE]  
> O SQL Server precisa de no mínimo 20 GB de espaço livre em disco para a publicação bem-sucedida da topologia inicial e a criação do servidor de gerenciamento central.



</div>

<div>


> [!NOTE]  
> Para a Enterprise Edition somente: para publicar a topologia, o servidor back-end baseado em SQL Server deve estar online e acessível com exceções de firewall no lugar. Para obter detalhes sobre como especificar exceções de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">noções básicas sobre requisitos de firewall do SQL Server com o Lync Server 2013</A>. Para obter detalhes sobre como configurar o SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configurar o SQL Server para o Lync server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Para publicar uma topologia

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Selecione para abrir a topologia a partir de um arquivo local. Se estiver no computador em que você definiu a topologia, ela estará no local onde você a salvou nas etapas anteriores. Geralmente, essa será a pasta documentos do usuário que configurou a topologia.

3.  Clique com o botão direito do mouse no nó do **Lync Server 2013** e, em seguida, clique em **publicar topologia**.

4.  Na página **Publicar a topologia**, clique em **Avançar**.

5.  Na página **criar bancos de dados** , selecione os bancos de dados que você deseja publicar.
    
    <div>
    

    > [!NOTE]  
    > Se não tiver os direitos apropriados para criar os bancos de dados, você poderá desmarcar as caixas de seleção ao lado desses bancos de dados e, posteriormente, alguém com os direitos apropriados poderá criar os bancos de dados. Para obter detalhes, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permissões de implantação do SQL Server no Lync Server 2013</A>.

    
    </div>

6.  Opcionalmente, clique em  **Avançado**. As opções avançadas de posicionamento do arquivo de dados do SQL Server permitem que você selecione entre as seguintes opções:
    
      - **Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração de disco do servidor baseado no SQL Server, distribuindo os arquivos de log e de dados para o melhor local.
    
      - **Usar padrões de instância SQL Server**. Essa opção coloca arquivos de log e de dados no servidor baseado em SQL Server usando as configurações de instância. Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar locais ideais para logs e dados. O administrador do SQL Server normalmente moverá os arquivos de log e dados para locais apropriados para os procedimentos de gerenciamento de servidor e organização baseados em SQL Server.
    
    Clique em **OK** e, em seguida, em **Avançar**.

7.  Na página **selecionar servidor de gerenciamento central** , selecione um pool de front-end.

8.  Opcionalmente, clique em  **Avançado**. As opções avançadas de posicionamento de arquivos de dados do SQL Server permitem que você selecione entre as seguintes opções:
    
      - **Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração de disco do servidor baseado no SQL Server, distribuindo os arquivos de log e de dados para o melhor local.
    
      - **Usar padrões de instância SQL Server**. Essa opção coloca arquivos de log e de dados no servidor baseado em SQL Server usando as configurações de instância. Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar locais ideais para logs e dados. O administrador do SQL Server normalmente moverá os arquivos de log e dados para locais apropriados para os procedimentos de gerenciamento de servidor e organização baseados em SQL Server.
    
    Clique em **OK**.

9.  Clique em **Avançar** para concluir o processo de publicação.

10. Quando o processo de publicação for concluído, clique em **concluir**.
    
    Quando a topologia é publicada com êxito, você pode começar a instalar uma réplica local do repositório de gerenciamento central em cada servidor que executa o Lync Server 2013 na sua topologia. É recomendável começar com o primeiro pool de front-ends.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurand Servidores e pools Front-End para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

