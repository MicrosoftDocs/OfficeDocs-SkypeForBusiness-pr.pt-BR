---
title: 'Lync Server 2013: restaurando um servidor back-end Enterprise Edition'
description: 'Lync Server 2013: restaurando um servidor back-end Enterprise Edition.'
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
ms.openlocfilehash: a2147aec00714704195399449e5d5e4d6ce609fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555207"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Restaurando um servidor back-end Enterprise Edition no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-18_

Use o procedimento descrito neste tópico nos dois casos a seguir:

  - Os bancos de dados primário e espelho de um servidor back-end Enterprise Edition espelhado falha.

  - Um servidor de back-end Enterprise Edition que não é espelhado falha.

Se você tiver um back-end do Enterprise Edition espelhado e apenas o espelho ou banco de dados primário falhar, consulte [restaurando um servidor back-end do espelhado Enterprise Edition no Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar o banco de dados primário e [restaurar um servidor de back-end Enterprise Edition espelhado no Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar o espelho.

Se o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se um servidor membro Enterprise Edition que não seja o servidor back-end falhar, consulte [restaurando um servidor membro Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração. Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Para restaurar um servidor back-end Enterprise Edition

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.

    
    </div>

2.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.

3.  Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância o mesmo que antes da falha.
    
    <div>
    

    > [!NOTE]  
    > Dependendo da sua implantação, o servidor back-end pode incluir vários bancos de dados posicionados ou separados. Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo logons e permissões do SQL Server.

    
    </div>

4.  Após instalar o SQL Server, execute o seguinte procedimento:
    
    1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.
    
    2.  Clique em **Baixar Topologia da implantação existente** e clique em **OK**.
    
    3.  Selecione a topologia e clique em **Salvar**. Clique em **Sim** para confirmar sua seleção.
    
    4.  Clique com o botão direito do mouse no nó **Lync Server 2013** e clique em **publicar topologia**.
    
    5.  Siga o assistente **Publicar a Topologia**. Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.
        
        <div>
        

        > [!NOTE]  
        > Somente os bancos de dados autônomos são exibidos na página <STRONG>Criar bancos de dados</STRONG>.

        
        </div>
    
    6.  Se você estiver restaurando um back-end espelhado, continue a seguir o restante do assistente até que o prompt **criar banco de dados espelho** seja exibido. Selecione o banco de dados que você deseja instalar e conclua o processo.
    
    7.  Siga o restante do assistente e clique em **Concluir**.
    
    <div>
    

    > [!TIP]  
    > Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento. Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.

    
    </div>

5.  Restaure os dados do usuário executando o seguinte:
    
    1.  Copie ExportedUserData.zip de $Backup \\ para um diretório local.
    
    2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.
    
    3.  Antes de restaurar os dados do usuário, você deve interromper os serviços do Lync. Para fazer isso, digite:
        
            Stop-CsWindowsService
    
    4.  Para restaurar os dados do usuário, na linha de comando, digite:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por exemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Reinicie os serviços do Lync digitando:
        
            Start-CsWindowsService

6.  Se você implantou o grupo de resposta nesse pool, restaure os dados de configuração do grupo de resposta. Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Se você estiver restaurando um servidor back-end que incluiu bancos de dados de arquivamento ou monitoramento, restaure os dados de arquivamento ou monitoramento usando uma ferramenta do SQL Server, como o SQL Server Management Studio. Para obter detalhes, consulte [restaurando o monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

