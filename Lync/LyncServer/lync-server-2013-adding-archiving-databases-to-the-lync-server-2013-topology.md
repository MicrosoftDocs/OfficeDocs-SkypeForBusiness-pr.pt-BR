---
title: 'Lync Server 2013: adicionando bancos de dados de arquivamento à topologia 2013 do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d6f4ff4b3881f9dfbd4707d2956aa738b9a375
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Adicionando bancos de dados de arquivamento à topologia do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

É necessário incorporar o arquivamento à sua topologia antes de poder configurar sua implantação para suportar o arquivamento. As informações neste tópico explicam como usar o construtor de topologias para adicionar o arquivamento à sua topologia existente.

<div>


> [!NOTE]  
> Se você quiser usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013 para todos os usuários em sua implantação, não especifique o <STRONG>repositório do SQL Server</STRONG> ou use as informações de <STRONG>espelhamento do repositório do SQL Server</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Para adicionar suporte ao banco de dados de Arquivamento à sua topologia

1.  Em um computador que está executando o Lync Server 2013, ou em que as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo de <STRONG>Administradores de domínio</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, para que o construtor de topologias possa configurar a lista de controle de acesso discricional necessária (DACLs) ou uma conta com direitos equivalentes.

    
    </div>

2.  Inicie o Construtor de topologia.

3.  Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o Arquivamento e clique no nome do pool.

4.  No menu **Ação**, clique em **Editar Propriedades**.

5.  Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.

6.  Role a tela para baixo até **Arquivamento**.

7.  Marque a caixa de seleção **Arquivamento**.

8.  Em **arquivar repositório do SQL Server,** siga um destes procedimentos:
    
      - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar. Se todos os seus usuários estiverem hospedados no Microsoft Exchange Server 2013 ou superior, você poderá arquivar as comunicações do Lync para todos os seus usuários no Exchange. Nesse caso, você não precisa configurar o repositório de arquivamento do SQL Server.
    
      - Para especificar um novo repositório do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo repositório do SQL Server** , faça o seguinte:
        
          - Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.
        
          - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
        
          - Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.

9.  Se você quiser usar o espelhamento do repositório do SQL Server, selecione **habilitar espelhamento do repositório do SQL Server**e faça o seguinte:
    
      - Para usar um repositório existente do SQL Server para espelhamento, na caixa de listagem suspensa **espelhamento do repositório do SQL Server Store** , clique no nome do repositório do SQL Server que você deseja usar para espelhamento.
    
      - Para especificar um novo repositório do SQL Server para espelhamento, clique em **novo**e, em seguida, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:
        
        1.  Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.
        
        2.  Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
        
        3.  Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
      - Se você habilitar o espelhamento do SQL Server e quiser incluir uma testemunha de espelhamento do SQL Server (uma terceira instância separada do SQL Server que possa detectar a integridade do servidor SQL Server principal e das instâncias de espelho), marque a caixa de seleção **usar testemunha de espelhamento do SQL Server para habilitar failover automático** e siga um destes procedimentos:
        
        1.  Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.
        
        2.  Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
        
        3.  Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.

10. Para salvar a configuração, clique em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

