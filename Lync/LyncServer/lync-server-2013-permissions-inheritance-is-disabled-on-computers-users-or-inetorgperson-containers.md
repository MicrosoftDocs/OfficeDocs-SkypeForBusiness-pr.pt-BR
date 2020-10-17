---
title: 'Lync Server 2013: a herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson'
description: 'Lync Server 2013: a herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545157"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>A herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-19_

Em um serviço de domínio do Active Directory bloqueado, os usuários e os objetos de computador costumam ser colocados em unidades organizacionais (UOs) específicas com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de GPOs (objetos de política de grupo) para impor políticas de segurança.

A preparação do domínio e a ativação do servidor definem as entradas de controle de acesso (ACEs) exigidas pelo Lync Server 2013. Quando a herança de permissões está desabilitada, os grupos de segurança do Lync Server não podem herdar essas ACEs. Quando essas permissões não são herdadas, os grupos de segurança do Lync Server não podem acessar as configurações e os dois problemas a seguir surgem:

  - Para administrar usuários, InetOrgPersons e contatos, e para operar servidores, os grupos de segurança do Lync Server exigem ACEs definidas pelo procedimento de preparação do domínio em conjuntos de propriedades de cada usuário, comunicação em tempo real (RTC), pesquisa de usuário RTC e informações públicas. Quando a herança de permissões está desabilitada, os grupos de segurança não herdam essas ACEs e não podem gerenciar servidores ou usuários.

  - Para descobrir servidores e pools, os servidores que executam o Lync Server dependem de ACEs definidas pela ativação em objetos relacionados ao computador, incluindo o contêiner da Microsoft e o objeto Server. Quando a herança de permissões está desabilitada, os grupos de segurança, servidores e pools não herdam essas ACEs e não podem beneficiar-se delas.

Para resolver esses problemas, o Lync Server fornece o cmdlet **Grant-CsOuPermission** . Este cmdlet define ACEs do Lync Server necessárias diretamente em um contêiner especificado e unidades organizacionais e os objetos dentro do contêiner ou unidade organizacional.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Definir permissões para os objetos Usuário, InetOrgPerson e Contato após executar a preparação do domínio

Em um ambiente bloqueado do Active Directory onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou unidades organizacionais que possuem os objetos Usuários ou InetOrgPerson dentro do domínio. Nessa situação, é necessário executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que possua objetos Usuário ou InetOrgPerson para os quais a herança de permissões está desabilitada. Se você tiver uma topologia de floresta central, também deverá realizar esse procedimento nos contêineres ou UOs que possuem os objetos de contato. Para obter detalhes sobre as topologias de floresta central, consulte [supported Active Directory topologias in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte. O parâmetro ObjectType especifica o tipo de objeto. O parâmetro OU especifica a unidade organizacional.

Esse cmdlet adiciona as ACEs necessárias diretamente nos contêineres ou UO especificadas e nos objetos Usuário ou InetOrgPerson dentro do contêiner. Se a OU em que esse comando é executado tiver UOs filhas com objetos User ou InetOrgPerson, as permissões não serão aplicadas nesses. Você precisará executar o comando em cada OU filho individualmente. Este é um cenário comum com implantações de hospedagem do Lync por exemplo, OU pai = locatários OCS, DC = CONTOSO, DC = LOCAL e filho OU = Tenant1, OU = locatários do OCS, DC = CONTOSO, DC = LOCAL.

Você precisa de direitos de usuário equivalentes à associação de grupo de administradores de domínio para executar esse cmdlet. Se as ACEs de usuário autenticado também tiverem sido removidas no ambiente bloqueado, você deverá conceder a essa conta as ACEs de leitura de acesso aos contêineres ou UOs relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores de empresa.

**Para definir as ACEs necessárias para os objetos Usuário, InetOrgPerson e Contato**

1.  Faça logon em um computador associado ao domínio com uma conta que seja membro do grupo Admins. do Domínio ou que possua direitos de usuário equivalentes.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.
    
    Por exemplo:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  No arquivo de log, procure **\<Success\>** o resultado de execução no final de cada tarefa para verificar se as permissões foram definidas e, em seguida, feche a janela log. Uma alternativa é executar o seguinte comando para determinar se as permissões foram definidas:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Por exemplo:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Definir permissões para os objetos Computador após executar a preparação do domínio

Em um ambiente bloqueado do Active Directory no qual a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou UOs com objetos Computador dentro do domínio. Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner OU unidade organizacional que tenha computadores que executam o Lync Server onde a herança de permissões está desabilitada. O parâmetro ObjectType especifica o tipo de objeto.

Esse procedimento adiciona as ACEs necessárias diretamente nos contêineres especificados.

Você precisa de direitos de usuário equivalentes à associação de grupo de administradores de domínio para executar esse cmdlet. Se as ACEs de usuário autenticado também tiverem sido removidas, você deverá conceder a essa conta ACEs de acesso de leitura nos contêineres relevantes no domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores de empresa.

**Para definir as ACEs necessárias aos objetos de computador**

1.  Faça logon no computador do domínio com uma conta que seja membro do grupo Admins. do Domínio ou que possua direitos de usuário equivalentes.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.
    
    Por exemplo:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  No exemplo de arquivo de log C: \\ Logs \\OUPermissions.xml, você procuraria o **\<Success\>** resultado da execução no final de cada tarefa e verificará se não há erros e, em seguida, feche o log. É possível executar o seguinte cmdlet para testar as permissões:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Por exemplo:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Se você executar a preparação de domínio no domínio raiz da floresta em um ambiente do Active Directory bloqueado, lembre-se de que o Lync Server requer acesso ao esquema do Active Directory e aos contêineres de configuração.<BR>Se a permissão de usuário autenticado padrão for removida do esquema ou dos contêineres de configuração no AD &nbsp; DS, somente os membros do grupo Administradores de esquema (para o contêiner de esquema) ou administradores corporativos (para o contêiner de configuração) terão permissão para acessar o contêiner fornecido. Como Setup.exe, os cmdlets do Shell de gerenciamento do Lync Server e o painel de controle do Lync Server exigem acesso a esses contêineres, a instalação e a instalação das ferramentas administrativas falharão, a menos que o usuário que estiver executando a instalação tenha direitos de usuário equivalentes aos membros do grupo Administradores de esquema e administradores corporativos.<BR>Para corrigir essa situação, é necessário conceder ao grupo RTCUniversalGlobalWriteGroup acesso de Leitura e Gravação nos contêineres Esquema e Configuração.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

