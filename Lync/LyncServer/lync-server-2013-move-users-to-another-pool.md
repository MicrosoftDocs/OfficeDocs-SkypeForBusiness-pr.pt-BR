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
ms.openlocfilehash: b103e2911812932026799bda154190aa6f46fc56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Mover usuários para outro pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2018-02-09_

Você pode usar o painel de controle do Lync Server para atribuir usuários a um servidor ou pool específico.

<div>


> [!TIP]  
> Mover todos os usuários existentes de um pool de origem que esteja executando o Lync Server 2010 ou anterior para um pool de destino do Lync Server 2013 em um ambiente do Active Directory complexo pode resultar em uma replicação mais lenta do Active Directory. Para evitar isso, você pode usar filtros de pesquisa para mover os usuários de pools que estão executando o Lync Server 2010 ou anterior separadamente ou pode usar o Shell de gerenciamento do Lync Server para mover usuários com cmdlets. Além disso, a funcionalidade de filtro funciona com os usuários do Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover os usuários selecionados para um outro servidor ou pool

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome de conta do SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) da linha da conta de usuário que você deseja e clique em **Localizar**.

5.  Na tabela, selecione um usuário específico ou usuários na lista.

6.  No menu **Ação**, clique em **Mover usuários selecionados para o pool**.

7.  Em **Mover Usuários**, selecione o pool para o qual você deseja mover os usuários em **Pool de registradores de destino**.

8.  (Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.
    
    <div>
    

    > [!Caution]  
    > Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências e contatos agendados não serão movidos.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos os usuários de um servidor ou pool para outro servidor ou pool

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  No menu **Ação**, clique em **Mover todos os usuários para o pool**.

5.  Em **Mover Usuários**, selecione o pool que contém as contas de usuário que você deseja mover para o **Pool de registradores de origem**.

6.  Em **Pool de registradores de destino **, selecione o pool para o qual você deseja mover os usuários.

7.  (Opcional) Se o pool ou o servidor de destino estiver indisponível, selecione a caixa de diálogo **Forçar**.
    
    <div>
    

    > [!Caution]  
    > Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências e contatos agendados não serão movidos.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuários de um pool para um pool diferente usando um filtro

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Em **pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.

5.  Nos Critérios de pesquisa, selecione **Pool de Registradores**, selecione **Igual a**, selecione **FQDN Atual do Pool** e clique em **Localizar**.

6.  No menu **Ação**, clique em **Mover todos os usuários para o pool**.
    
    <div>
    

    > [!NOTE]  
    > Quando um filtro é aplicado a um conjunto existente de usuários, a opção <STRONG>mover todos os usuários para o pool</STRONG> está no contexto do subconjunto filtrado de usuários, e não de <STRONG><EM>todos</EM></STRONG> os usuários possíveis.

    
    </div>

7.  Em **Mover Usuários**, selecione o pool que contenha as contas de usuário que você deseja mover no **Pool de registradores de origem**.

8.  Em **Pool de registradores de destino **, selecione o pool para o qual você deseja mover os usuários.

9.  (Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.
    
    <div>
    

    > [!Caution]  
    > Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências e contatos agendados não serão movidos.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuários de um pool para outro usando cmdlets do Windows PowerShell

1.  Dependendo de como você executa os comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como um membro das funções administrativas corretas do Lync Server 2013, da seguinte maneira:
    
    1.  Se você estiver executando os comandos na máquina local (por exemplo, você faz logon diretamente em um servidor front-end): faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Se você estiver executando os comandos remotamente em outro computador (por exemplo, você faz logon no seu computador e executa os comandos remotamente em um servidor front-end Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou à CsAdministrator função, faça logon em qualquer computador em sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Para mover usuários único, use o cmdlet Move-CsUser da seguinte maneira:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Quando o usuário a ser movido for Pilar Ackerman, e for movido de seu pool doméstico atribuído atualmente para o pool pool01.contoso.net

4.  Para mover muitos usuários, use os filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Os comandos combinados do **Get-CsUser** e do **Move-CsUser** podem resultar nisto:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificando Propriedades da conta de usuário no Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

