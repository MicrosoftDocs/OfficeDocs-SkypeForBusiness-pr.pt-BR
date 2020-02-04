---
title: 'Lync Server 2013: restaurando um servidor back-end do Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Restaurando um servidor back-end do Enterprise Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-18_

Use o procedimento descrito neste tópico nos dois casos a seguir:

  - Os bancos de dados primários e espelho de um servidor back-end da edição empresarial espelhada falham.

  - Um servidor back-end da edição Enterprise que não está espelhado falha.

Se você tiver um back-end da edição Enterprise espelhada e somente o espelho ou banco de dados primário falhar, consulte [restaurando um servidor back-end de edição do Enterprise Edition no Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar o banco de dados principal e [restaurar um servidor back-end do Enterprise Edition para o Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar o espelho.

Se o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se um servidor membro da edição Enterprise que não for o servidor back-end falhar, consulte [restaurando um servidor membro da Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração. Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Para restaurar um servidor back-end do Enterprise Edition

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação do servidor da sua organização para executar esta etapa.

    
    </div>

2.  Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.

3.  Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes das instâncias iguais aos anteriores à falha.
    
    <div>
    

    > [!NOTE]  
    > Dependendo da sua implantação, o servidor back-end pode incluir vários bancos de dados posicionados ou separados. Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo as permissões e os logons do SQL Server.

    
    </div>

4.  Depois de instalar o SQL Server, faça o seguinte:
    
    1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.
    
    2.  Clique em **baixar topologia da implantação existente**e, em seguida, clique em **OK**.
    
    3.  Selecione a topologia e, em seguida, clique em **salvar**. Clique em **Sim** para confirmar sua seleção.
    
    4.  Clique com o botão direito do mouse no nó do **Lync Server 2013** e, em seguida, clique em **publicar topologia**.
    
    5.  Siga o assistente **publicar a topologia** . Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.
        
        <div>
        

        > [!NOTE]  
        > Somente bancos de dados autônomos são exibidos na página <STRONG>criar bancos de dados</STRONG> .

        
        </div>
    
    6.  Se você estiver restaurando um back-end que foi espelhado, continue a acompanhar o restante do assistente até que o prompt **criar banco de dados espelho** seja exibido. Selecione o banco de dados que você deseja instalar e conclua o processo.
    
    7.  Siga o restante do assistente e clique em **concluir**.
    
    <div>
    

    > [!TIP]  
    > Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.

    
    </div>

5.  Restaure os dados do usuário executando o seguinte:
    
    1.  Copie ExportedUserData. zip de $Backup\\ para um diretório local.
    
    2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.
    
    3.  Antes de restaurar os dados do usuário, você deve parar os serviços do Lync. Para fazer isso, digite:
        
            Stop-CsWindowsService
    
    4.  Para restaurar os dados do usuário, na linha de comando, digite:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por exemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Reinicie os serviços do Lync digitando:
        
            Start-CsWindowsService

6.  Se você implantou o grupo de resposta nesse pool, restaure os dados de configuração do grupo de resposta. Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Se você estiver restaurando um servidor back-end que incluiu o arquivamento ou o monitoramento de bancos de dados, restaure os dados de arquivamento ou monitoramento usando uma ferramenta do SQL Server, como o SQL Server Management Studio. Para obter detalhes, consulte [restaurando o monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

