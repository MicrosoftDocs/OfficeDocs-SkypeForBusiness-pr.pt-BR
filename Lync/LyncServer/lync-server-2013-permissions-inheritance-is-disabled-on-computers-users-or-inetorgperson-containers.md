---
title: 'Lync Server 2013: Herança de permissões está desabilitado em computadores, usuários ou contêiners InetOrgPerson'
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Herança de permissões está desabilitado em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-19_

Em um serviço de domínio do Active Directory bloqueado, usuários e objetos de computador geralmente são colocados em unidades organizacionais específicas (UOs) com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de objetos de política de grupo (GPOs) para impor políticas de segurança.

A preparação do domínio e a ativação do servidor definem as entradas de controle de acesso (ACEs) necessárias pelo Lync Server 2013. Quando a herança de permissões está desabilitada, os grupos de segurança do Lync Server não podem herdar esses ACEs. Quando essas permissões não forem herdadas, os grupos de segurança do Lync Server não poderão acessar as configurações, e os dois problemas a seguir ocorrerão:

  - Para administrar usuários, InetOrgPersons e contatos, e para operar servidores, os grupos de segurança do Lync Server exigem ACEs definidas pelo procedimento de preparação do domínio em conjuntos de propriedades de cada usuário, comunicação em tempo real (RTC), pesquisa de usuário RTC e informações públicas . Quando a herança de permissões está desabilitada, os grupos de segurança não herdam esses ases e não podem gerenciar servidores ou usuários.

  - Para descobrir servidores e pools, os servidores que executam o Lync Server dependem de ACEs definidas pela ativação em objetos relacionados a computador, incluindo o contêiner da Microsoft e o objeto do servidor. Quando a herança de permissões está desabilitada, os grupos de segurança, os servidores e os pools não herdam esses ases e não podem tirar proveito dessas ACEs.

Para resolver esses problemas, o Lync Server fornece o cmdlet **Grant-CsOuPermission** . Esse cmdlet define ACEs necessárias do Lync Server diretamente em um contêiner especificado e unidades organizacionais e os objetos dentro do contêiner ou unidade organizacional.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Definir permissões para usuários, InetOrgPerson e objetos de contato após a execução da preparação do domínio

Em um ambiente do Active Directory bloqueado onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou unidades organizacionais que mantêm usuários ou objetos InetOrgPerson no domínio. Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que tenha objetos de usuário ou inetOrgPerson para os quais a herança de permissões esteja desabilitada. Se você tiver uma topologia de floresta central, também deverá executar esse procedimento nos recipientes ou nas UOs que mantêm objetos de contato. Para obter detalhes sobre as topologias de floresta central, consulte [topologias do Active Directory com suporte no Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte. O parâmetro ObjectType especifica o tipo de objeto. O parâmetro OU especifica a unidade organizacional.

Esse cmdlet adiciona as ACEs necessárias diretamente nos contêineres ou UOs especificados e nos objetos User ou InetOrgPerson dentro do contêiner. Se a UO na qual esse comando for executado tiver UOs filho com objetos User ou InetOrgPerson, as permissões não serão aplicadas. Será necessário executar o comando em cada UO filho individualmente. Esse é um cenário comum com implantações de hospedagem do Lync, por exemplo, Parent OU = locatários do OCS, DC = CONTOSO, DC = LOCAL e filho OU = Tenant1, OU = locatários do OCS, DC = CONTOSO, DC = LOCAL.

Você precisa de direitos de usuário equivalentes ao grupo de administradores de domínio para executar esse cmdlet. Se as ACEs do usuário autenticado também tiverem sido removidas no ambiente bloqueado, você deverá conceder a essa conta ACEs de leitura de acesso nos contêineres ou UOs relevantes do domínio raiz da floresta, conforme descrito em [permissões de usuário autenticado, removido no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores da empresa.

**Para definir ACEs necessárias para objetos de usuário, InetOrgPerson e contato**

1.  Faça logon em um computador associado ao domínio com uma conta que seja membro do grupo Domain admins ou que tenha direitos de usuário equivalentes.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.
    
    Por exemplo:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  No arquivo de log, procure o resultado de execução do ** \<sucesso\> ** no final de cada tarefa para verificar se as permissões foram definidas e, em seguida, feche a janela log. Ou, você pode executar o seguinte comando para determinar se as permissões foram definidas:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Por exemplo:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Definir permissões para objetos de computador após a execução da preparação do domínio

Em um ambiente do Active Directory bloqueado onde a herança de permissões está desabilitada, a preparação do domínio não define as ACEs necessárias nos contêineres ou nas UOs que armazenam objetos do computador dentro do domínio. Nessa situação, você deve executar o cmdlet **Grant-CsOuPermission** em cada contêiner ou UO que tenha computadores que executam o Lync Server onde a herança de permissões esteja desabilitada. O parâmetro ObjectType especifica o tipo de objeto.

Esse procedimento adiciona as ACEs necessárias diretamente nos contêineres especificados.

Você precisa de direitos de usuário equivalentes ao grupo de administradores de domínio para executar esse cmdlet. Se as ACEs do usuário autenticado também tiverem sido removidas, você deverá conceder a essa conta as ACEs de leitura de acesso aos recipientes relevantes no domínio raiz da floresta conforme descrito em [permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou usar uma conta que seja membro do grupo Administradores da empresa.

**Para definir ACEs necessárias para objetos de computador**

1.  Faça logon no computador do domínio com uma conta que seja membro do grupo Domain admins ou que tenha direitos de usuário equivalentes.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.
    
    Por exemplo:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  No exemplo de arquivo de log C\\:\\registra OUPermissions. xml, você procura o resultado de execução do ** \<sucesso\> ** no final de cada tarefa e verifica se não há erros e, em seguida, feche o log. Você pode executar o seguinte cmdlet para testar permissões:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Por exemplo:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Se você executar a preparação do domínio no domínio raiz da floresta em um ambiente do Active Directory bloqueado, lembre-se de que o Lync Server exige acesso ao esquema e aos contêineres de configuração do Active Directory.<BR>Se a permissão de usuário autenticado padrão for removida do esquema ou dos contêineres de&nbsp;configuração no AD DS, somente os membros do grupo Schema Admins (para contêiner de esquema) ou administradores de empresas (para contêiner de configuração) terão permissão para acessar o contêiner fornecido. Como setup. exe, cmdlets do Shell de gerenciamento do Lync Server e o painel de controle do Lync Server exigem acesso a esses contêineres, a configuração e a instalação das ferramentas administrativas falham, a menos que o usuário executando a instalação tenha direitos de usuário equivalentes ao esquema Associação de grupo Administradores e administradores corporativos.<BR>Para corrigir essa situação, você deve conceder ao grupo RTCUniversalGlobalWriteGroup o acesso de gravação, leitura para o esquema e os contêineres de configuração.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

