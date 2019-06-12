---
title: 'Lync Server 2013: Atribuir políticas de conferência para suporte de usuários anônimos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94ff3fe520b776d6f6043abb66f9926da5acaa22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Atribuir políticas de conferência para suporte de usuários anônimos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Por padrão, todos os usuários são impedidos de convidar usuários anônimos para participarem de uma reunião. Você controla quem pode convidar usuários anônimos Configurando uma política de conferência para dar suporte a usuários anônimos e aplicar essa política de conferência a usuários específicos. Para obter detalhes sobre como configurar as políticas de conferência para dar suporte a usuários anônimos, consulte [criar ou modificar uma política de conferência no Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [gerenciar Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Use o procedimento desta seção para aplicar uma política de conferência que você já tenha criado a um ou mais usuários ou grupos de usuários.

<div>


> [!NOTE]  
> Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para a sua organização. Para obter detalhes, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar uma política de usuário para a participação anônima em reuniões

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **conferência**e siga um destes procedimentos:
    
    1.  Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Crie um nome exclusivo no campo **nome** que indica a capa da política do usuário (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).
    
    2.  Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

4.  Na caixa de diálogo **políticas de conferência** , marque a caixa de seleção **permitir que os participantes convidem usuários anônimos** .

5.  Clique em **Confirmar**.

6.  Na barra de navegação à esquerda, clique em **usuários**e procure a conta de usuário que você deseja configurar.

7.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

8.  Em **Editar o usuário do Lync Server** na **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.
    
    <div>
    

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação do servidor padrão e são aplicadas automaticamente pelo servidor.

    
    </div>

Para permitir que os usuários convidem usuários anônimos para conferências, você também deve habilitar o suporte a usuários anônimos em sua organização. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) na documentação de implantação ou a documentação de operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

