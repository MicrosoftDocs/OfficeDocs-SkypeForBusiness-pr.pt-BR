---
title: 'Lync Server 2013: desabilitar ou reabilitar a conta de usuário do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 502b4cc9c6ed70d0a418dbed7e844064939809d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Desabilitar ou reabilitar a conta de usuário do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-04-04_

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Lync Server 2013 sem perder as configurações do Lync Server que você configurou para a conta de usuário. Como você não perde as configurações da conta de usuário do Lync Server, você pode reabilitar uma conta de usuário previamente habilitada sem precisar reconfigurar a conta de usuário.

<div>


> [!WARNING]  
> Simplesmente desabilitar uma conta de usuário no Active Directory <STRONG>não</STRONG> impedirá que o usuário se conecte ou use o Lync Server. Isso ocorre porque o Lync usa autenticação de certificado que simplifica o processo de autenticação e esses certificados de cliente são válidos por 180 dias. Se quiser interromper a desabilitação de contas do Active Directory que foram habilitadas para que o Lync tenha acesso ao Lync Server, você deve usar o cmdlet <STRONG>Disable-CsUser</STRONG> ou usar o <STRONG>painel de controle do Lync Server</STRONG> conforme apresentado neste artigo. Quando o usuário estiver desabilitado no Lync e o repositório de gerenciamento central tiver sido replicado no ambiente, os usuários não poderão mais entrar. Além disso, os usuários que estiverem conectados serão desconectados.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Para desabilitar ou reabilitar uma conta de usuário previamente habilitada para o Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.

6.  No menu **Ação**, faça o seguinte:
    
      - Para desabilitar temporariamente a conta de usuário para o Lync Server 2013, clique em **desabilitar temporariamente para o Lync Server**.
    
      - Para habilitar a conta de usuário para o Lync Server 2013, clique em **reabilitar para o Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usando o Windows PowerShell para desabilitar ou reabilitar contas de usuário

As contas de usuário podem ser desabilitadas temporariamente e, posteriormente, habilitadas novamente, usando o cmdlet **set-CsUser** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-disable-a-user-account"></a>Para desabilitar uma conta de usuário

  - Para desabilitar uma conta temporariamente, defina o valor da propriedade Enabled como falso ($False). Por exemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Para reabilitar uma conta de usuário

  - Para reabilitar uma conta de usuário, defina o valor da propriedade Enabled como verdadeiro ($True). Por exemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Adicionar e habilitar a conta de usuário para o Lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Habilitando e desabilitando usuários para o Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

