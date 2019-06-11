---
title: 'Lync Server 2013: restaurar o servidor que hospeda o repositório de gerenciamento central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Uma implantação do Lync Server tem um único repositório central de gerenciamento, uma cópia do que é replicada para cada servidor executando uma função de servidor do Lync Server. Este tópico descreve como restaurar um servidor back-end ou Standard Edition que hospeda o repositório de gerenciamento central.

Para localizar o pool em que o servidor de gerenciamento central está localizado, abra o construtor de topologias, clique em **Lync Server**e examine o painel à direita em **servidor de gerenciamento central**.

Se o servidor back-end que hospeda o repositório de gerenciamento central estiver em uma instalação espelhada e o banco de dados espelho ainda estiver funcional, recomendamos que você faça um backup desse espelho ainda funcional e execute uma restauração completa no banco de dados primário e no banco de dados espelho, usando este backup, seguindo o procedimento de restauração abaixo. Isso é necessário porque a restauração de back-end exige a modificação e a publicação da topologia, e isso pode ser feito apenas se o CMS primário que hospeda o CMS estiver operacional. Observe também que as funções de banco de dados principal e espelho não poderão ser trocadas se não for possível publicar a topologia.

<div>


> [!NOTE]  
> Se um servidor back-end do servidor ou da edição Standard que não hospeda o repositório de gerenciamento central falhar, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurando um servidor back-end do Enterprise Edition no Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurando um servidor Standard Edition no Lync Server 2013</A>. Se um servidor back-end que hospeda o repositório de gerenciamento central estiver em uma configuração espelhada e somente o espelho falhar, consulte <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurando um servidor back-end do Enterprise Edition espelhado no Lync Server 2013-Mirror</A>. Se houver falha em qualquer outro servidor, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurando um servidor membro do Enterprise Edition no Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração. Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Para restaurar o repositório de gerenciamento central

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação do servidor da sua organização para executar esta etapa.

    
    </div>

2.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins e do grupo Administradores local, faça logon no servidor que você está restaurando.

3.  Se você estiver restaurando um servidor Standard Edition, restaure o repositório de arquivos copiando o repositório de arquivos apropriado de $Backup para o local do repositório de arquivos no servidor e, em seguida, compartilhe a pasta.
    
    <div>
    

    > [!IMPORTANT]  
    > O caminho e o nome do arquivo do repositório de arquivos restaurados devem ser exatamente os mesmos do armazenamento de arquivos em backup para que os componentes que usam os arquivos possam acessá-los.

    
    </div>

4.  Siga um destes procedimentos:
    
      - Se você estiver instalando um servidor Standard Edition, navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação do \\Lync\\Server\\localizado em setup AMD64 setup. exe. No assistente de implantação, clique em **preparar primeiro servidor Standard Edition** e siga o assistente para instalar o repositório de gerenciamento central.
    
      - Se você estiver instalando um servidor de back-end corporativo, instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes das instâncias iguais aos da falha.
        
        <div>
        

        > [!NOTE]  
        > Dependendo do servidor que você está restaurando e na sua implantação, o servidor pode incluir vários bancos de dados posicionados ou separados. Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo as permissões e os logons do SQL Server.

        
        </div>

5.  Em um servidor front-end, inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

6.  Crie novamente o repositório de gerenciamento central. Na linha de comando, digite:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por exemplo:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Defina o ponto de controle dos serviços de domínio Active Directory para o repositório de gerenciamento central. Na linha de comando, digite:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por exemplo:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Se você perder o ponto de conexão, poderá executar novamente esse cmdlet.

    
    </div>

8.  Importar os dados do repositório de gerenciamento central de $Backup. Na linha de comando, digite:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Por exemplo:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Habilite as alterações que você acabou de fazer. Na linha de comando, digite:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Depois de habilitar a topologia, você pode encontrar o documento de topologia no banco de dados.

    
    </div>

10. Se você estiver restaurando um servidor back-end do Enterprise Edition que também hospedava o CMS ou se precisar recriar um espelho do CMS, siga esta etapa. Caso contrário, pule para a etapa 11.
    
    Instale os bancos de dados autônomos da seguinte maneira:
    
    1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.
    
    2.  Clique em **baixar topologia da implantação existente**e, em seguida, clique em **OK**.
    
    3.  Selecione a topologia e, em seguida, clique em **salvar**. Clique em **Sim** para confirmar sua seleção.
    
    4.  Clique com o botão direito do mouse no nó do **Lync Server 2013** e clique em **instalar banco de dados**.
    
    5.  Siga o assistente de **instalação de banco de dados** . Se você estiver restaurando um banco de dados diferente do repositório de gerenciamento central neste servidor, na página **criar bancos** de dados, selecione os bancos de dados que você deseja recriar.
        
        <div>
        

        > [!NOTE]  
        > Somente bancos de dados autônomos são exibidos na página <STRONG>criar bancos de dados</STRONG> . Bancos de dados posicionados são criados quando você executa o assistente de implantação do Lync Server.

        
        </div>
    
    6.  Se você estiver restaurando um servidor back-end espelhado, continue a acompanhar o restante do assistente até chegar à solicitação de criar banco de dados espelho. Selecione o banco de dados que você deseja instalar e conclua o processo.
    
    7.  Siga o restante do assistente e clique em **concluir**.
    
    <div>
    

    > [!TIP]  
    > Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.

    
    </div>

11. Se você estiver restaurando um servidor Standard Edition, navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação \\do\\Lync\\Server localizado em setup AMD64 setup. exe. Use o assistente de implantação do Lync Server para fazer o seguinte:
    
    1.  Execute a **etapa 1: instalar o repositório de configuração local** para instalar os arquivos de configuração local.
    
    2.  Execute a **etapa 2: configurar ou remover componentes do Lync Server** para instalar as funções de servidor do Lync Server.
    
    3.  Execute a **etapa 3: solicitar, instalar ou atribuir certificados** para atribuir os certificados.
    
    4.  Execute a **etapa 4: Iniciar serviços** para iniciar serviços no servidor.
    
    Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.

12. Restaure os dados do usuário executando o seguinte:
    
    1.  Copie ExportedUserData. zip de $Backup\\ para um diretório local.
    
    2.  Antes de restaurar os dados do usuário, você deve parar os serviços do Lync. Para fazer isso, digite:
        
            Stop-CsWindowsService
    
    3.  Para restaurar os dados do usuário, na linha de comando, digite:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por exemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Reinicie os serviços do Lync digitando:
        
            Start-CsWindowsService

13. Restaurar dados de informações de localização para o repositório de gerenciamento central. Na linha de comando, digite:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Por exemplo:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Se você implantou o grupo de resposta nesse pool ou no servidor Standard Edition, restaure os dados de configuração do grupo de resposta. Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Se você estiver restaurando um servidor back-end que inclui o arquivamento ou o monitoramento de bancos de dados, restaure os dados de arquivamento ou monitoramento usando uma ferramenta de gerenciamento do SQL Server, como o SQL Server Management Studio. Para obter detalhes, consulte Restaurando o [monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

