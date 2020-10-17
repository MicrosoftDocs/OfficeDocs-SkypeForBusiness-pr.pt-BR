---
title: 'Lync Server 2013: remover uma conta de usuário do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 782077cc532dc751076d3152467de865fe799a29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536508"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a>Remover uma conta de usuário do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Lync Server 2013.

<div>


> [!NOTE]  
> Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário. Se quiser desabilitar temporariamente uma conta de usuário, confira o tópico <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">desabilitar ou reabilitar a conta de usuário do Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Para remover uma conta de usuário usando o Shell de gerenciamento do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Encontrar**.

5.  Na tabela, clique na conta de usuário que deseja remover.

6.  No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.

7.  Na caixa de diálogo, selecione **OK** para remover o usuário.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Removendo contas de usuário usando cmdlets do Windows PowerShell

Você pode remover contas de usuário usando o cmdlet Disable-CsUser. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-user-account"></a>Para remover uma conta de usuário

  - Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser. Por exemplo:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Após este comando ser executado, não há forma de reabilitar a conta e suas configurações anteriores. Ao invés disso, você precisará usar o cmdlet Enable-CsUser para criar uma nova conta para Ken Myer.

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Desabilitar ou reabilitar a conta de usuário do Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Habilitando e desabilitando usuários para o Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

