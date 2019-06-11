---
title: 'Lync Server 2013: desabilitar ou habilitar novamente a conta de usuário para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Desabilitar ou habilitar novamente a conta de usuário para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-04-04_

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Lync Server 2013 sem perder as configurações do Lync Server que você configurou para a conta de usuário. Como você não perde as configurações da conta de usuário do Lync Server, é possível habilitar novamente uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta do usuário.

<div>


> [!WARNING]  
> Simplesmente desabilitar uma conta de usuário no Active Directory <STRONG>não</STRONG> impedirá que um usuário se conecte ou use o Lync Server. Isso ocorre porque o Lync usa autenticação de certificado que simplifica o processo de autenticação e esses certificados de cliente são válidos por 180 dias. Se quiser parar de desabilitar contas do Active Directory que foram habilitadas para o Lync de ter acesso ao Lync Server, você deve usar o cmdlet <STRONG>Disable-CsUser</STRONG> ou usar o <STRONG>painel de controle do Lync Server</STRONG> conforme apresentado neste artigo. Quando o usuário estiver desativado no Lync e o repositório de gerenciamento central tiver sido replicado no ambiente, os usuários não poderão mais se conectar. Além disso, os usuários que entrarem no seu acesso serão desconectados.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Para desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja desabilitar ou reabilitar, e, em seguida, clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que você deseja desabilitar ou habilitar novamente.

6.  No menu **ação** , siga um destes procedimentos:
    
      - Para desativar temporariamente a conta de usuário do Lync Server 2013, clique em **desabilitar temporariamente para Lync Server**.
    
      - Para habilitar a conta de usuário do Lync Server 2013, clique em **habilitar novamente para Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usando o Windows PowerShell para desabilitar ou habilitar novamente as contas de usuário

As contas de usuário podem ser desabilitadas temporariamente e, em seguida, reativadas posteriormente usando-se o cmdlet **set-CsUser** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-disable-a-user-account"></a>Para desabilitar uma conta de usuário

  - Para desativar temporariamente uma conta de usuário, defina o valor da propriedade Enabled como false ($False). Por exemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Para habilitar novamente uma conta de usuário

  - Para habilitar novamente uma conta de usuário desabilitada, defina o valor da propriedade Enabled como true ($True). Por exemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Adicionar e habilitar a conta de usuário para o Lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Habilitando e desabilitando usuários do Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

