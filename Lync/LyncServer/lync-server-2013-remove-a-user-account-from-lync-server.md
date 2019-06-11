---
title: 'Lync Server 2013: remover uma conta de usuário do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Remover uma conta de usuário do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Lync Server 2013.

<div>


> [!NOTE]  
> A remoção de um usuário fará com que você perca todas as configurações que você configurou para a conta de usuário. Se você quiser desativar temporariamente uma conta de usuário, consulte o tópico <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">desabilitar ou habilitar novamente a conta de usuário do Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Para remover uma conta de usuário usando o Shell de gerenciamento do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja desabilitar ou reabilitar, e, em seguida, clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que você deseja remover.

6.  No menu **ação** , selecione **remover do Lync Server**, e uma caixa de diálogo será exibida.

7.  Na caixa de diálogo, selecione **OK** para remover o usuário.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Como remover contas de usuário usando cmdlets do Windows PowerShell

Você pode remover contas de usuário usando o cmdlet Disable-CsUser. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-user-account"></a>Para remover uma conta de usuário

  - Para remover uma conta de usuário, use o cmdlet Disable-CsUser. Por exemplo:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Depois que esse comando tiver sido executado, não será possível habilitar novamente a conta e suas configurações anteriores. Em vez disso, você precisará usar o cmdlet Enable-CsUser para criar uma conta de Nova reputação para Ken Myer.

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Desabilitar ou habilitar novamente a conta de usuário para o Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Habilitando e desabilitando usuários do Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

