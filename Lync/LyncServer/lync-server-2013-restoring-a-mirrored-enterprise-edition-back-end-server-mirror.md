---
title: Restaurando um servidor back-end do espelhado Enterprise Edition-Mirror
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Restaurando um servidor back-end da edição Enterprise espelhada no Lync Server 2013-Mirror

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-19_

Se você tiver um servidor back-end do Enterprise Edition em uma configuração espelhada e somente o espelho falhar, siga os procedimentos desta seção. Se o banco de dados primário e o espelhamento falharem, consulte [restaurando um servidor back-end do Enterprise Edition no Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se apenas o principal falhar, consulte [restaurando um servidor back-end do espelhado Enterprise Edition no Lync Server 2013-primário](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Se o banco de dados que hospeda o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se um servidor membro da edição Enterprise que não for o servidor back-end falhar, consulte [restaurando um servidor membro da Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração. Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Para restaurar um banco de dados espelho do servidor back-end do Enterprise Edition

1.  Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Desinstale o espelhamento. Primeiro, digite o seguinte cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por exemplo:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Faça isso para todos os tipos de banco de dados neste servidor.

4.  Crie um servidor limpo ou novo que tenha o mesmo nome de domínio totalmente qualificado (FQDN) (DB1.contoso.com) que o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados. Este servidor funcionará como o novo espelho.

5.  Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon no novo servidor.

6.  Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes das instâncias iguais aos anteriores à falha.

7.  Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.

8.  Use o construtor de topologias para instalar o banco de dados espelho. Faça o seguinte:
    
      - Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.
    
      - Clique com o botão direito do mouse no nó do Lync Server 2013, clique em **topologia**e clique em **instalar banco de dados**.
    
      - Siga o assistente de **instalação de banco de dados** . Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.
    
      - Siga o assistente até que o prompt **criar banco de dados espelho** seja exibido. Selecione o banco de dados que você deseja instalar e conclua esse processo.
        
        <div>
        

        > [!TIP]
        > Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

