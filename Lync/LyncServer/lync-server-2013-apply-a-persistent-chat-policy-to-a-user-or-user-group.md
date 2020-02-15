---
title: 'Lync Server 2013: aplicar uma política de chat persistente a um usuário ou grupo de usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c32fea58eafc8728144885826c822c7485441a7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Aplicar uma política de chat persistente a um usuário ou grupo de usuários no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

Se um usuário tiver sido habilitado para o Lync Server 2013, você poderá aplicar as políticas adequadas a usuários específicos para habilitá-los ou desabilitá-los para o servidor de chat persistente.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.<BR>Para definir as definições de configuração do servidor de chat persistente, confira <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções de servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync Server 2013</A> na documentação de implantação.



</div>

Use o procedimento neste tópico para aplicar uma política de usuário de chat persistente criada anteriormente a uma ou mais contas de usuário ou grupos de usuários.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário de chat persistente a uma conta de usuário

1.  Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar usuário do Lync Server** , em **política de chat persistente**, selecione a política de usuário de chat persistente que você deseja aplicar.
    
    <div>
    

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam a política efetiva padrão. Essas configurações são aplicadas automaticamente pelo servidor.

    
    </div>

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

