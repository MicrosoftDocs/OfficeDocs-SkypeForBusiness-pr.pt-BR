---
title: 'Lync Server 2013: atribuir políticas de conferência para dar suporte a usuários anônimos'
description: 'Lync Server 2013: atribuir políticas de conferência para dar suporte a usuários anônimos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e94c3097e3e21f854e91fdee1ad0b33c3b9f53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566157"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Por padrão, todos os usuários são impedidos de convidar usuários anônimos a participar de uma reunião. Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos. Para obter detalhes sobre como configurar as políticas de conferência para dar suporte a usuários anônimos, consulte [create or Modify a Conferencing Policy in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Use o procedimento nesta seção para aplicar uma política de conferência que você já criou a um ou mais usuários ou grupos de usuários.

<div>


> [!NOTE]  
> Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para sua organização. Para obter detalhes, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure Policies to Control Public User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar uma política de usuário para participação anônima em reuniões

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência ** e siga um destes procedimentos:
    
    1.  Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Crie um nome exclusivo no campo **nome** que indique o que a política de usuário abrange (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).
    
    2.  Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e em **Mostrar detalhes**.

4.  Na caixa de diálogo **políticas de conferência** , marque a caixa de seleção **permitir que os participantes convidem usuários anônimos** .

5.  Clique em **Confirmar**.

6.  Na barra de navegação esquerda, clique em **usuários**, procure a conta de usuário que você deseja configurar.

7.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

8.  Em **Editar usuário do Lync Server** na **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.
    
    <div>
    

    > [!NOTE]  
    > As configurações <STRONG> &lt; automáticas &gt; </STRONG> aplicam as configurações de instalação padrão do servidor e são aplicadas automaticamente pelo servidor.

    
    </div>

Para habilitar usuários para convidar usuários anônimos para conferências, você também deve habilitar o suporte para usuários anônimos em sua organização. Para obter detalhes, consulte [Configure Policies to Control Public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) na documentação de implantação ou a documentação de operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

