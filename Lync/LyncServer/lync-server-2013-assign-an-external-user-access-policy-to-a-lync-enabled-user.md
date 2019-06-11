---
title: 'Lync Server 2013: Atribuir uma política de usuário externo a um usuário habilitado do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Se um usuário foi habilitado para o Lync Server, você pode configurar a Federação do SIP, a Federação do XMPP, o acesso de usuário remoto e a conectividade de mensagens instantâneas (IM) públicas no painel de controle do Lync Server aplicando as políticas apropriadas a usuários específicos. Por exemplo, se você criou uma política para dar suporte ao acesso de usuário remoto, deve aplicá-la ao usuário antes que o usuário possa se conectar ao Lync Server de um local remoto e colaborar com usuários internos do local remoto.

<div>


> [!NOTE]  
> Para dar suporte ao acesso de usuário externo, você deve habilitar o suporte para cada tipo de acesso de usuário externo ao qual você deseja dar suporte e configurar as políticas adequadas e outras opções para controlar seu uso. Para obter detalhes, consulte Configurando o <A href="lync-server-2013-configuring-support-for-external-user-access.md">suporte para acesso de usuários externos no Lync server 2013</A> na documentação de implantação ou gerenciando a <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Federação e acesso externo ao Lync Server 2013</A> na documentação de operações.



</div>

Use o procedimento deste tópico para aplicar uma política de acesso externo do usuário criada anteriormente a uma ou mais contas de usuário.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário externa a uma conta de usuário

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar usuário do Lync Server** na **política de acesso externo**, selecione a política de usuário que você deseja aplicar.
    
    <div>
    

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de política global e do servidor padrão.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Atribuindo políticas de acesso externo por usuário usando cmdlets do Windows PowerShell

Políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsExternalAccessPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para atribuir uma política de acesso externo por usuário a um único usuário

  - Esse comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para atribuir uma política de acesso externo por usuário a vários usuários

  - Esse comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários que têm contas na UO Estados Unidos no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar a atribuição de uma política de acesso externo por usuário

  - Esse comando cancela a atribuição de qualquer política de acesso externo por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

