---
title: 'Lync Server 2013: restaurar o servidor que hospeda o repositório de gerenciamento central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d3912402b48ce8aede4a53efea208c96bff825
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511388"
---
# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Uma implantação do Lync Server tem um único repositório de gerenciamento central, uma cópia do que é replicada para cada servidor que executa uma função de servidor do Lync Server. Este tópico descreve como restaurar um servidor back-end ou um servidor Standard Edition que hospeda o repositório de gerenciamento central.

Para localizar o pool onde o servidor de gerenciamento central está localizado, abra o construtor de topologias, clique em **Lync Server**e examine o painel direito em **servidor de gerenciamento central**.

Se o servidor back-end que hospeda o repositório de gerenciamento central estiver em uma instalação espelhada e o banco de dados de espelho ainda estiver funcional, recomendamos que você faça um backup desse espelho ainda em funcionamento e, em seguida, execute uma restauração completa no banco de dados primário e no banco de dados espelho, usando esse backup, seguindo o procedimento de restauração abaixo. Isso é necessário porque o back-end Restore requer a modificação e publicação da topologia, e isso só pode ser feito se o banco de dados primário que hospeda o CMS estiver operacional. Observe também que as funções de banco de dados principal e espelho não podem ser trocadas se a topologia não puder ser publicada.

<div>


> [!NOTE]  
> Se um servidor back-end ou um servidor Standard Edition que não hospeda o repositório de gerenciamento central falhar, confira <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurar um servidor de back-end Enterprise Edition no Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurar um servidor Standard Edition no Lync Server 2013</A>. Se um servidor back-end que hospeda o repositório de gerenciamento central estiver em uma configuração espelhada e apenas o espelho falhar, confira a <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restauração de um servidor back-end do espelhamento Enterprise Edition no Lync Server 2013-Mirror</A>. Se qualquer outro servidor falhar, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurando um servidor membro Enterprise Edition no Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração. Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Para restaurar o Repositório de Gerenciamento Central

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.

    
    </div>

2.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins e do grupo Administradores local, faça logon no servidor que você está restaurando.

3.  Se você estiver restaurando um servidor Standard Edition, restaure o repositório de arquivos copiando o repositório de arquivos apropriado de $Backup para o local do repositório de arquivos no servidor e, em seguida, compartilhe a pasta.
    
    <div>
    

    > [!IMPORTANT]  
    > O caminho e o nome de arquivo para o repositório de arquivos restaurados devem ser exatamente os mesmos do repositório de arquivos de backup para que os componentes que usam os arquivos possam acessá-los.

    
    </div>

4.  Siga um destes procedimentos:
    
      - Se você estiver instalando um servidor Standard Edition, navegue até a pasta ou a mídia de instalação do Lync Server e inicie o assistente de implantação do Lync Server localizado no \\ arquivo de instalação \\ AMD64 \\Setup.exe. No assistente de implantação, clique em **preparar primeiro servidor Standard Edition** e siga o assistente para instalar o repositório de gerenciamento central.
    
      - Se você estiver instalando um servidor back-end corporativo, instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância iguais aos anteriores à falha.
        
        <div>
        

        > [!NOTE]  
        > Dependendo do servidor que você está restaurando e em sua implantação, o servidor pode incluir vários bancos de dados posicionados ou separados. Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo logons e permissões do SQL Server.

        
        </div>

5.  Em um servidor front-end, inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.

6.  Recrie o repositório de gerenciamento central. Na linha de comando, digite:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por exemplo:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Defina o ponto de controle dos serviços de domínio do Active Directory para o repositório de gerenciamento central. Na linha de comando, digite:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por exemplo:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Se você perder o ponto de conexão, poderá executar esse cmdlet novamente.

    
    </div>

8.  Importe os dados do repositório de gerenciamento central a partir do $Backup. Na linha de comando, digite:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Por exemplo:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Habilite as alterações feitas por você. Na linha de comando, digite:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Após habilitar a topologia, você pode encontrar o documento da topologia no banco de dados.

    
    </div>

10. Se você estiver restaurando um servidor back-end Enterprise Edition que também hospedava o CMS, ou se precisar recriar um espelho do CMS, siga esta etapa. Caso contrário, pule para a etapa 11.
    
    Instale os bancos de dados autônomos fazendo o seguinte:
    
    1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.
    
    2.  Clique em **Baixar Topologia da implantação existente** e clique em **OK**.
    
    3.  Selecione a topologia e clique em **Salvar**. Clique em **Sim** para confirmar sua seleção.
    
    4.  Clique com o botão direito do mouse no nó **Lync Server 2013** e clique em **instalar banco de dados**.
    
    5.  Siga o assistente de **instalação de banco de dados** . Se você estiver restaurando um banco de dados diferente do repositório de gerenciamento central neste servidor, na página **criar bancos** de dados, selecione os bancos de dados que deseja recriar.
        
        <div>
        

        > [!NOTE]  
        > Somente os bancos de dados autônomos são exibidos na página <STRONG>Criar bancos de dados</STRONG>. Os bancos de dados colocados são criados quando você executa o assistente de implantação do Lync Server.

        
        </div>
    
    6.  Se você estiver restaurando um servidor back-end espelhado, continue a seguir o restante do assistente até chegar a uma solicitação de criar banco de dados espelho. Selecione o banco de dados que você deseja instalar e conclua o processo.
    
    7.  Siga o restante do assistente e clique em **Concluir**.
    
    <div>
    

    > [!TIP]  
    > Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.

    
    </div>

11. Se você estiver restaurando um servidor Standard Edition, navegue até a pasta ou a mídia de instalação do Lync Server e inicie o assistente de implantação do Lync Server localizado no \\ arquivo de instalação \\ AMD64 \\Setup.exe. Use o assistente de implantação do Lync Server para fazer o seguinte:
    
    1.  Execute **Etapa 1: Instalar Repositório de Configuração Local** para instalar os arquivos de configuração locais.
    
    2.  Execute **etapa 2: instalar ou remover componentes do Lync Server** para instalar as funções de servidor do Lync Server.
    
    3.  Execute **Etapa 3: Solicitar, Instalar ou Ceder Certificados** para atribuir os certificados.
    
    4.  Execute **Etapa 4: Iniciar os Serviços** para iniciar os serviços no servidor.
    
    Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.

12. Restaure os dados do usuário executando o seguinte:
    
    1.  Copie ExportedUserData.zip de $Backup \\ para um diretório local.
    
    2.  Antes de restaurar os dados do usuário, você deve interromper os serviços do Lync. Para fazer isso, digite:
        
            Stop-CsWindowsService
    
    3.  Para restaurar os dados do usuário, na linha de comando, digite:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por exemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Reinicie os serviços do Lync digitando:
        
            Start-CsWindowsService

13. Restaure os dados de informações do local para o repositório de gerenciamento central. Na linha de comando, digite:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Por exemplo:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Se você implantou o grupo de resposta nesse pool ou no servidor Standard Edition, restaure os dados de configuração do grupo de resposta. Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Se você estiver restaurando um servidor back-end que inclui bancos de dados de arquivamento ou monitoramento, restaure os dados de arquivamento ou monitoramento usando uma ferramenta de gerenciamento do SQL Server, como o SQL Server Management Studio. Para obter detalhes, consulte [restaurando o monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

