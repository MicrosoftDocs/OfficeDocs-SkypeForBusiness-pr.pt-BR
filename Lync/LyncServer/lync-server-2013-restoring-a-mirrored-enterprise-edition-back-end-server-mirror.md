---
title: Restaurando um servidor back-end Enterprise Edition de espelhamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 658b271bc71a78c564c42fc96126ce276071709c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-espelho

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-19_

Se você tiver um servidor back-end Enterprise Edition em uma configuração espelhada e apenas o espelho falhar, siga os procedimentos desta seção. Se o banco de dados primário e o espelho falharem, consulte [restaurando um servidor de back-end Enterprise Edition no Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se apenas o primário falhar, consulte [restaurando um servidor back-end do Enterprise Edition espelhado no Lync Server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Se o banco de dados que hospeda o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se um servidor membro Enterprise Edition que não seja o servidor back-end falhar, consulte [restaurando um servidor membro Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração. Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Para restaurar um banco de dados de espelho do servidor back-end Enterprise Edition

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Desinstale o espelhamento. Primeiro, digite o seguinte cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por exemplo:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Faça isso para todos os tipos de banco de dados neste servidor.

4.  Crie um servidor novo ou limpo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) (DB1.contoso.com) como o computador com falha, instale o sistema operacional e restaure ou registre novamente os certificados. Este servidor funcionará como o novo espelho.

5.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no novo servidor.

6.  Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância o mesmo que antes da falha.

7.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.

8.  Use o construtor de topologias para instalar o banco de dados espelho. Execute o seguinte:
    
      - Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.
    
      - Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **instalar banco de dados**.
    
      - Siga o assistente de **instalação de banco de dados** . Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.
    
      - Siga o assistente até que um prompt de **criar banco de dados espelho** seja exibido. Selecione o banco de dados que você deseja instalar e conclua esse processo.
        
        <div>
        

        > [!TIP]
        > Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento. Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

