---
title: 'Lync Server 2013: publicando a topologia atualizada para adicionar bancos de dados de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f39e5f35dbd088543456f09ddd49f6aa2f9325c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Publicando a topologia atualizada para adicionar bancos de dados de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Após atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o arquivamento. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.

<div>

## <a name="to-publish-your-updated-topology"></a>Para publicar sua topologia atualizada

1.  Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo <STRONG>Domain admins</STRONG> e o <STRONG>RTCUniversalServer Grupo Administradores</STRONG> e com permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, o construtor de topologia pode configurar a lista de controle de acesso discricional necessária (DACLs) ou uma conta com direitos equivalentes.

    
    </div>

2.  Abra a topologia que você criou na seção anterior usando o construtor de topologias.

3.  Na árvore de console, clique com o botão direito do mouse no **Lync Server 2013**e, em seguida, clique em **publicar topologia**.

4.  Na página **Publicar a topologia**, clique em **Avançar**.

5.  Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. Para obter detalhes sobre os direitos e permissões de administrador necessários, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permissões de implantação do SQL Server no Lync Server 2013</A> na documentação de implantação.<BR>Somente bancos de dados em servidores SQL Server dedicados podem ser instalados usando-se o construtor de topologias. Bancos de dados em servidores SQL Server que estão posicionados com outros componentes do servidor devem ser instalados executando-se a configuração local nesse computador.

    
    </div>

6.  Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. Para obter detalhes, consulte Configurando o <A href="lync-server-2013-configuring-support-for-archiving.md">suporte para arquivamento no Lync Server 2013</A> na documentação de implantação.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

