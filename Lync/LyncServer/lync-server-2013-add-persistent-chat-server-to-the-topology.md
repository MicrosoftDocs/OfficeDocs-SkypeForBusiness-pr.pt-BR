---
title: 'Lync Server 2013: Adicionar Servidor de Chat Persistente à topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Adicionar Servidor de Chat Persistente à topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

Você deve incorporar o Lync Server 2013, o suporte persistente do servidor de chat em sua topologia antes de poder configurar sua implantação para dar suporte ao servidor de chat persistente. As informações neste tópico descrevem como usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à sua topologia existente.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Para adicionar um servidor de chat persistente a uma topologia

Execute as etapas a seguir para instalar um único pool de servidores de chat persistente sem uma configuração de recuperação de desastres. Para configurar um pool de servidor de chat persistente ampliado para alta disponibilidade e recuperação de desastres, consulte Configurando o [servidor de chat persistente para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) na documentação de implantação.

Para implantar vários pools de servidores de chat persistentes, repita o mesmo processo para cada pool.

1.  Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para instalar um servidor do Lync Server 2013, você deve usar uma conta que seja membro do grupo <STRONG>Administradores de domínio</STRONG> e o <STRONG>RTCUniversalS erverAdmins</STRONG> grupo, e que tem permissões de controle total (ou seja, ler, gravar e modificar) no repositório de arquivos que você vai usar para o repositório de arquivos persistente do servidor de chat (ou seja, o construtor de topologia pode configurar as DACLs obrigatórias) ou uma conta com direitos equivalentes.

    
    </div>

2.  Iniciar o construtor de topologias.

3.  Na árvore de console, navegue até o nó de pools de **chat persistente** e expanda-o para selecionar um pool de servidores de chat persistente, ou clique com o botão direito do mouse no nó e selecione **novo pool de chat persistente**. You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.
    
    Você pode escolher entre um **Pool de múltiplos computadores** ou um **Pool de computador único**. Escolha o primeiro se estiver planejando ter mais de um servidor front-end persistente do servidor de chat em seu pool de servidores de chat persistente. É possível escolher agora ou depois, já que após a criação do pool de computador único não é possível adicionar outros servidores. Se você escolher um pool de vários computadores, insira os nomes dos servidores de front-end persistentes do servidor de chat que compõem o pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Se a função de servidor de chat persistente estiver sendo instalada em um servidor&nbsp;do Lync Server 2013 Standard Edition, o FQDN precisará corresponder ao FQDN do servidor Standard Edition.

    
    </div>

4.  Defina um **nome de exibição** simples para o pool do servidor de chat persistente. O nome de exibição pode ser usado por clientes personalizados, especialmente quando há vários pools de servidores de chat persistentes, para diferenciar os quartos.

5.  Defina a porta usada pelo servidor de chat persistente para se comunicar com os servidores front-end do Lync Server. A porta padrão é 5041.

6.  Se sua organização requerer suporte à conformidade, marque a caixa de seleção **Habilitar conformidade**. Se escolhido, o serviço de conformidade do servidor de chat persistente é instalado no mesmo computador que o servidor front-end persistente do servidor de chat. Você será solicitado a selecionar um servidor back-end do SQL Server para conformidade com o servidor de chat persistente mais tarde.

7.  Atribua afinidade de site ao pool de servidores de chat persistente. Marque a caixa de seleção **usar este pool como \<padrão\> para o site SiteName** ou **Use este pool como padrão para todos os sites** para designar este pool de servidores de chat persistente como o pool padrão para o site atual ou todos os sites. Quando o cliente Lync 2013 é usado para criar e gerenciar salas, o pool padrão associado ao site do usuário é usado pela criação e pela experiência de gerenciamento da sala para que possa rotear operações de criação e gerenciamento da sala para esse pool. Isso só se aplica quando você tem vários pools de servidores de chat persistentes implantados e deseja usar os recursos de criação e gerenciamento de salas do servidor de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Você pode personalizar os recursos de criação e gerenciamento de sala usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente.<BR>Para obter detalhes sobre como configurar bancos de dados de backup do SQL Server para recuperação de desastres, consulte Configurando o <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">servidor de chat persistente para alta disponibilidade e recuperação de desastres no Lync Server 2013</A> na documentação de implantação.

    
    </div>

8.  Defina o **repositório SQL para o back-end persistente do servidor de chat (onde o conteúdo da sala de chat está armazenado)** seguindo um destes procedimentos:
    
      - Para usar um banco de dados existente do SQL Server, na lista suspensa, clique no nome do banco de dados do SQL Server que você deseja usar.
    
      - Para especificar um novo banco de dados do SQL Server, clique em **novo**e, em **definir novo SQL Store**, execute o seguinte procedimento:
    
    <!-- end list -->
    
      - No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo banco de dados do SQL Server.
    
      - Selecione **Instância padrão** para usar a instância padrão ou **Instância nomeada** para especificar uma instância diferente e especifique a instância que deseja usar.

9.  Defina o banco de dados de conformidade do SQL Server se você tiver habilitado a conformidade.
    
    <div>
    

    > [!IMPORTANT]  
    > Para obter detalhes sobre como configurar os espelhos do SQL Server para alta disponibilidade para o banco de dados persistente do servidor de chat e o banco de dados de conformidade do servidor de chat persistente, consulte Configurando o <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013</A> na documentação de implantação.

    
    </div>

10. Defina o repositório de arquivos. Os repositórios de arquivos são pastas em que são armazenadas cópias de todos os arquivos enviados para o repositório de arquivos (por exemplo, para armazenar anexos de arquivos publicados em salas de chat). No caso de uma topologia de servidor de chat persistente de vários servidores, isso deve ser um caminho UNC (Convenção Universal de nomenclatura); e para uma topologia de servidor de chat persistente de servidor único, pode ser um caminho de arquivo local.
    
    Para usar um repositório de arquivos existente, execute as etapas a seguir:
    
      - Em **servidor de arquivos FQDN**, ESPECIFIQUE o FQDN do repositório de arquivos no qual você deseja criar o novo repositório de arquivos.
    
      - Em **Compartilhamento de arquivos**, especifique o repositório de arquivos que deseja usar.
    
    <div>
    

    > [!IMPORTANT]  
    > Você pode definir o repositório de arquivos no construtor de topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido que você define antes de publicar a topologia.

    
    </div>

11. Selecione o pool de servidores front-end a ser usado como um próximo nó para este pool de servidores de chat persistente. Este é o pool de servidores front-ends que poderá rotear solicitações persistentes do servidor de chat para esse pool.

12. Para salvar a configuração, clique em **Concluir**. O pool de servidores de chat persistente aparece no construtor de topologia acompanhado por suas configurações de pool específicas.
    
    Para publicar agora sua topologia atualizada à qual você tem o servidor de chat persistente, consulte [publicar a topologia atualizada no Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]  
    > Com o construtor de topologias já aberto, você pode passar para a etapa 3 em <A href="lync-server-2013-publish-the-updated-topology.md">publicar a topologia atualizada no Lync Server 2013</A> para começar a publicar sua topologia atualizada.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

