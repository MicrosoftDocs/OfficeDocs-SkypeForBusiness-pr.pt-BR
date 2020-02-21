---
title: 'Lync Server 2013: publicando a topologia atualizada para adicionar bancos de dados de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff09dc330c7194ebe3657220c20a6138dc2f9a4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Publicar a topologia atualizada para adicionar bancos de dados de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Depois de atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o arquivamento. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.

<div>

## <a name="to-publish-your-updated-topology"></a>Para publicar a topologia atualizada

1.  Em um computador que está executando o Lync Server 2013, ou em que as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo de <STRONG>Administradores de domínio</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, para que o construtor de topologias possa configurar a lista de controle de acesso discricional necessária (DACLs) ou uma conta com direitos equivalentes.

    
    </div>

2.  Abra a topologia que você criou na seção anterior usando o construtor de topologias.

3.  Na árvore do console, clique com o botão direito do mouse em **Lync Server 2013**e clique em **publicar topologia**.

4.  Na página **Publicar topologia**, clique em **Avançar**.

5.  Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. Para obter detalhes sobre os direitos e permissões de administrador necessários, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A> na documentação de implantação.<BR>Apenas bancos de dados em servidores SQL Server dedicados podem ser instalados usando o construtor de topologias. Os bancos de dados em servidores SQL Server colocados com outros componentes de servidor devem ser instalados executando a instalação local no computador.

    
    </div>

6.  Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. Para obter detalhes, consulte <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> na documentação de implantação.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

