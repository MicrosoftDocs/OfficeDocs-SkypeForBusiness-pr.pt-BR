---
title: 'Lync Server 2013: mover usuários para outro pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Mover usuários para outro pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2018-02-09_

Você pode usar o painel de controle do Lync Server para atribuir usuários a um servidor ou pool específico.

<div>


> [!TIP]  
> Mover todos os usuários existentes de um pool de origem que esteja executando o Lync Server 2010 ou anterior para um pool de destino do Lync Server 2013 em um ambiente complexo do Active Directory pode resultar em uma replicação mais lenta do Active Directory. Para evitar isso, você pode usar filtros de pesquisa para mover os usuários de pools que executam o Lync Server 2010 ou anterior separadamente, ou você pode usar o Shell de gerenciamento do Lync Server para mover usuários com cmdlets. Além disso, a funcionalidade de filtro funciona com usuários do Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover os usuários selecionados para um servidor ou pool diferente

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e, em seguida, clique em **Localizar**.

5.  Na tabela, selecione um usuário ou usuários específicos na lista.

6.  No menu **ação** , clique em **mover usuários selecionados para o pool**.

7.  Em **mover usuários**, selecione o pool para o qual você deseja mover os usuários no **pool de registradores de destino**.

8.  Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .
    
    <div>
    

    > [!Caution]  
    > Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências programadas e contatos não serão movidos.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos os usuários de um servidor ou pool para um servidor ou pool diferente

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  No menu **ação** , clique em **mover todos os usuários para o pool**.

5.  Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool de registradores de origem**.

6.  No **pool de registradores de destino**, selecione o pool para o qual você deseja mover os usuários.

7.  Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .
    
    <div>
    

    > [!Caution]  
    > Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências programadas e contatos não serão movidos.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover os usuários de um pool para um pool diferente usando um filtro

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Em **pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.

5.  Nos critérios de pesquisa, selecione **pool de registradores**, selecione **igual a**, selecione o **FQDN do pool atual**e clique em **Localizar**.

6.  No menu **ação** , clique em **mover todos os usuários para o pool**.
    
    <div>
    

    > [!NOTE]  
    > Quando um filtro é aplicado a um conjunto de usuários existente, a opção <STRONG>mover todos os usuários para o pool</STRONG> está no contexto do subconjunto filtrado de usuários, e não <STRONG><EM>todos</EM></STRONG> os usuários possíveis.

    
    </div>

7.  Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool de registradores de origem**.

8.  No **pool de registradores de destino**, selecione o pool para o qual você deseja mover os usuários.

9.  Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .
    
    <div>
    

    > [!Caution]  
    > Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências programadas e contatos não serão movidos.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover os usuários de um pool para outro usando cmdlets do Windows PowerShell

1.  Dependendo de como você executa comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como membro das funções administrativas corretas do Lync Server 2013 da seguinte maneira:
    
    1.  Se você estiver executando os comandos no computador local (por exemplo, você fizer logon diretamente em um servidor front-end): faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Se você estiver executando os comandos remotamente em outro computador (por exemplo, se conectar ao seu computador e executar os comandos remotamente em um servidor front-end Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou ao CsAdministrator , faça logon em qualquer computador na sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Para mover usuários únicos, use o cmdlet Move-CsUser da seguinte maneira:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Onde o usuário mover é o usuário pilar Alverca, e o usuário será movido do pool inicial atribuído no momento para o pool pool01.contoso.net

4.  Para mover um grande número de usuários, use filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **mover-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Os comandos combinados do **Get-CsUser** e do **move-CsUser** podem fazer isso:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificando Propriedades de conta de usuário no Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

