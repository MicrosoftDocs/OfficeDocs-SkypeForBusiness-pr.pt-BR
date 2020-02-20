---
title: 'Lync Server 2013: Adicionar servidor de chat persistente à topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b857c63b08906ada2cee2611960717f97e7a3cc1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Adicionar servidor de chat persistente à topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

Você deve incorporar o suporte do Lync Server 2013, persistent chat Server em sua topologia antes de poder configurar sua implantação para suportar o servidor de chat persistente. As informações neste tópico descrevem como usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à sua topologia existente.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Para adicionar um servidor de chat persistente a uma topologia

Execute as seguintes etapas para instalar um único pool de servidores de chat persistente sem uma configuração de recuperação de desastres. Para configurar um pool de servidor de chat persistente estendido para alta disponibilidade e recuperação de desastre, confira [Configurando servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) na documentação de implantação.

Para implantar vários pools do servidor de chat persistente, repita o mesmo processo para cada pool.

1.  Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para instalar um servidor do Lync Server 2013, você deve usar uma conta que seja membro do grupo <STRONG>Administradores de domínio</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no repositório de arquivos que você usará para o repositório de arquivos do servidor de chat persistente (ou seja, para que o construtor de topologias possa configurar as DACLs necessárias) ou uma conta com direitos equivalentes.

    
    </div>

2.  Inicie o Construtor de topologia.

3.  Na árvore do console, navegue até o nó **pools de chat persistente** e expanda-o para selecionar um pool de servidor de chat persistente ou clique com o botão direito do mouse no nó e selecione **novo pool de chat persistente**. Você deve definir o FQDN (nome de domínio totalmente qualificado) do pool e indicar se o pool será um pool de servidor único ou uma implantação de pool de vários servidores.
    
    Você pode escolher um **pool de vários computadores** ou um **pool de computador único**. Escolha a primeira vez se estiver planejando ter mais de um servidor front-end do servidor de chat persistente em seu pool de servidor de chat persistente. Faça esta escolha agora ou posteriormente, porque depois de criar um pool de computador único, não será possível adicionar mais servidores a ele posteriormente. Se você escolher um pool de vários computadores, insira os nomes dos servidores de front-end do servidor de chat persistente individuais que compõem o pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Se a função de servidor de chat persistente estiver sendo instalada em um servidor&nbsp;do Lync Server 2013 Standard Edition, o FQDN precisará corresponder ao FQDN do servidor Standard Edition.

    
    </div>

4.  Defina um **nome de exibição** simples para o pool do servidor de chat persistente. O nome de exibição pode ser usado por clientes personalizados, especialmente quando há vários pools de servidores de chat persistentes, para diferenciar salas.

5.  Definir a porta usada pelo servidor de chat persistente para se comunicar com os servidores front-end do Lync Server. A porta padrão é 5041.

6.  Se sua organização requer suporte de conformidade, marque a caixa de seleção **habilitar conformidade** . Se escolhido, o serviço de conformidade do servidor de chat persistente é instalado no mesmo computador que o servidor de front-end do servidor de chat persistente. Você será solicitado a selecionar um servidor back-end do SQL Server para conformidade do servidor de chat persistente mais tarde.

7.  Atribua afinidade de site para o pool do servidor de chat persistente. Marque a caixa de seleção **usar este pool como \<padrão\> para o site SiteName** ou **Use este pool como padrão para todos os sites** para designar esse pool de servidor de chat persistente como o pool padrão para o site atual ou todos os sites. Quando o cliente Lync 2013 é usado para criar e gerenciar salas, o pool padrão associado ao site do usuário é usado pela experiência de criação e gerenciamento da sala para que possa encaminhar operações de criação e gerenciamento de salas a esse pool. Isso só se aplica quando você tem vários pools de servidores de chat persistente implantados e deseja usar os recursos de criação e gerenciamento de sala do servidor de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Você pode personalizar os recursos de criação e gerenciamento de sala usando o Software Development Kit (SDK) do servidor de chat persistente.<BR>Para obter detalhes sobre como configurar bancos de dados de backup do SQL Server para recuperação de desastre, consulte <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> na documentação de implantação.

    
    </div>

8.  Defina o **repositório SQL para back-end do servidor de chat persistente (onde o conteúdo da sala de bate-papo é armazenado)** executando um dos seguintes procedimentos:
    
      - Para usar um banco de dados existente do SQL Server, na lista suspensa, clique no nome do banco de dados do SQL Server que você deseja usar.
    
      - Para especificar um novo banco de dados do SQL Server, clique em **novo**e em **definir novo repositório SQL**, execute o seguinte procedimento:
    
    <!-- end list -->
    
      - Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo banco de dados do SQL Server.
    
      - Selecione **instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, selecione **instância nomeada**e especifique a instância que você deseja usar.

9.  Defina o banco de dados de conformidade do SQL Server se você tiver habilitado a conformidade.
    
    <div>
    

    > [!IMPORTANT]  
    > Para obter detalhes sobre como configurar os espelhos do SQL Server para alta disponibilidade para o banco de dados do servidor de chat persistente e o banco de dados de conformidade do servidor de chat persistente, consulte <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> na documentação de implantação.

    
    </div>

10. Defina o repositório de arquivos. Um repositório de arquivos é uma pasta onde uma cópia de qualquer arquivo carregado no repositório de arquivos é armazenada (por exemplo, armazenando anexos de arquivo postados em uma sala de chat). No caso de uma topologia de servidor de chat persistente de vários servidores, este deve ser um caminho UNC (Convenção de nomenclatura universal); e para uma topologia de servidor de chat persistente de servidor único, pode ser um caminho de arquivo local.
    
    Para usar um repositório de arquivos existente, siga estas etapas:
    
      - Em **FQDN do servidor de arquivos**, ESPECIFIQUE o FQDN do repositório de arquivos em que você deseja criar o novo repositório de arquivos.
    
      - Em **compartilhamento de arquivos**, especifique o repositório de arquivos que você deseja usar.
    
    <div>
    

    > [!IMPORTANT]  
    > Você pode definir o repositório de arquivos no construtor de topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido antes de publicar a topologia.

    
    </div>

11. Selecione o pool de servidor front-end a ser usado como próximo salto para este pool de servidor de chat persistente. Este é o pool do servidor front-end que poderá rotear solicitações persistentes do servidor de chat para este pool.

12. Para salvar a configuração, clique em **concluir**. O pool do servidor de chat persistente aparece no construtor de topologia acompanhado por suas configurações de pool específicas.
    
    Para publicar agora sua topologia atualizada para a qual você tem o servidor de chat persistente, confira [publicar a topologia atualizada no Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]  
    > Com o construtor de topologias já aberto, você pode prosseguir para a etapa 3 em <A href="lync-server-2013-publish-the-updated-topology.md">publicar a topologia atualizada no Lync Server 2013</A> para começar a publicar sua topologia atualizada.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

