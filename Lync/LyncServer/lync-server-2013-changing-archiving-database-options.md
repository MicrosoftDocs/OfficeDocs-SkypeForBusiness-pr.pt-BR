---
title: 'Lync Server 2013: alterar as opções de banco de dados de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Alterar as opções de banco de dados de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Se você implantar o arquivamento usando o armazenamento do SQL Server para arquivar o armazenamento para qualquer um dos seus usuários, poderá fazer as seguintes alterações de armazenamento de banco de dados:

  - Use um banco de dados do SQL Server diferente para arquivar o armazenamento. Isso inclui o banco de dados de arquivamento principal e qualquer banco de dados que você usa para o espelhamento do SQL Server.

  - Alterne para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013. Se todos os usuários estiverem hospedados nos seus servidores Exchange 2013 e você quiser usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, remova os bancos de dados da loja do SQL Server da sua topologia.

Para fazer uma dessas alterações, você deve executar o construtor de topologias, fazer as alterações e, em seguida, publicar a topologia novamente. Você pode usar o construtor de topologias para fazer isso. Não especifique o **arquivamento do SQL Server Store** ou habilite as informações de espelhamento da **loja do SQL Server** , a menos que você tenha usuários do Lync que não são hospedados nos servidores Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Para alterar a opção de banco de dados de arquivamento

1.  Em um computador que esteja executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo <STRONG>Administradores de domínio</STRONG> e o <STRONG>RTCUniversalSer verAdmins</STRONG> grupo, e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivo que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, o construtor de topologia pode configurar as listas de controle de acesso discricional necessárias ( DACLs) ou uma conta com direitos equivalentes.

    
    </div>

2.  Iniciar o construtor de topologias.

3.  Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.

4.  No menu **Ação**, clique em **Editar propriedades**.

5.  Na caixa de diálogo **Editar propriedades**, clique em **Geral**.

6.  Role a tela para baixo até **Arquivamento**.

7.  Em **Arquivamento**, faça o seguinte:
    
      - Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:
        
          - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
        
          - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:
            
              - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
            
              - Para especificar uma nova loja do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo SQL Server Store** , faça o seguinte:
                
                  - Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.
                
                  - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
                
                  - Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
      - Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:
        
          - Para usar uma loja existente do SQL Server para espelhamento, na caixa de listagem suspensa de espelhamento do **repositório do SQL Server** , clique no nome da loja do SQL Server que você deseja usar para espelhamento.
        
          - Para especificar uma nova loja do SQL Server para espelhamento, clique em **novo**e, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:
            
            1.  No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.
            
            2.  Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
            
            3.  Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.
        
          - Se você habilitar o espelhamento do SQL Server e quiser adicionar ou alterar uma testemunha de espelhamento do SQL Server (uma terceira instância do SQL Server separada que pode detectar a integridade do servidor do SQL Server e das instâncias de espelhamento principais), selecione a **testemunha usar o espelhamento do SQL Server para Habilite** a caixa de seleção failover automático e siga um destes procedimentos:
            
            1.  Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.
            
            2.  Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
            
            3.  Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
      - Para alternar para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013 (se todos os usuários na sua implantação estiverem hospedados em seus servidores Exchange 2013), exclua todas as informações para arquivar bancos de dados.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você tiver usuários do Lync que não são hospedados nos servidores Exchange 2013, não exclua as informações da loja do SQL Server.

    
    </div>

8.  Para salvar a configuração, clique em **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > As alterações feitas no construtor de topologias não entram em vigor até que você publique a nova topologia. Para obter detalhes, consulte <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">publicando a topologia atualizada para adicionar bancos de dados de arquivamento no Lync Server 2013</A> na documentação de implantação.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

