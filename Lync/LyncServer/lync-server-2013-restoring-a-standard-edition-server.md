---
title: 'Lync Server 2013: restaurando um servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 101cf0cb2fc4073e2b79aa008187465f84d2d439
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Restaurando um servidor Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Se um servidor padrão da edição que não hospeda o repositório de gerenciamento central falhar, siga os procedimentos desta seção. Se o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração. Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Para restaurar um servidor Standard Edition

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação do servidor da sua organização para executar esta etapa.

    
    </div>

2.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins e do grupo Administradores local, faça logon no servidor que você está restaurando.

3.  Restaure o repositório de arquivos copiando o repositório de arquivos apropriado de $Backup para o local do repositório de arquivos no servidor e compartilhar a pasta.
    
    <div>
    

    > [!IMPORTANT]  
    > O caminho e o nome do arquivo do repositório de arquivos restaurados devem ser exatamente os mesmos do armazenamento de arquivos em backup para que os componentes que usam os arquivos possam acessá-los.

    
    </div>

4.  Executar o construtor de topologias:
    
    1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.
    
    2.  Clique em **baixar topologia da implantação existente**e, em seguida, clique em **OK**.
    
    3.  Selecione a topologia e, em seguida, clique em **salvar**. Clique em **Sim** para confirmar sua seleção.

5.  Navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação do Lync \\Server\\localizado\\em setup AMD64 setup. exe. Use o assistente de implantação do Lync Server para fazer o seguinte:
    
    1.  Execute a **etapa 1: instalar o repositório de configuração local** para instalar os arquivos de configuração local.
    
    2.  Execute a **etapa 2: configurar ou remover componentes do Lync Server** para instalar as funções de servidor do Lync Server.
    
    3.  Execute a **etapa 3: solicitar, instalar ou atribuir certificados** para atribuir os certificados.
    
    4.  Execute a **etapa 4: Iniciar serviços** para iniciar serviços no servidor.
    
    Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.

6.  Restaure os dados do usuário executando o seguinte:
    
    1.  Copie ExportedUserData. zip de $Backup\\ para um diretório local.
    
    2.  Antes de restaurar os dados do usuário, você deve parar os serviços do Lync. Para fazer isso, digite:
        
            Stop-CsWindowsService
    
    3.  Para restaurar os dados do usuário, na linha de comando, digite:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por exemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Reinicie os serviços do Lync digitando:
        
            Start-CsWindowsService

7.  Se você implantou o grupo de resposta neste servidor Standard Edition, restaure os dados de configuração do grupo de resposta. Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Se você implantou o chat persistente neste servidor Standard Edition, restaure o banco de dados de chat persistente (MGC. MDF).
    
    Se você usou o backup do SQL Server para fazer backup do banco de dados de chat persistente, use os procedimentos de restauração do SQL Server para restaurá-lo.
    
    Se você usou o cmdlet Export-CsPersistentChatData para fazer o backup, use import-CsPersistentChatData para restaurá-lo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

