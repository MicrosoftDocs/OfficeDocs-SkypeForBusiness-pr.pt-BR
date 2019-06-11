---
title: 'Lync Server 2013: Configurar a política global para Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configurar a política global para Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

Você pode usar a política global padrão sozinha para habilitar as configurações de chat persistente para todos os usuários em sua implantação. Você também pode especificar políticas adicionais para sites e usuários para controlar se o chat persistente está habilitado ou desabilitado para usuários e sites específicos.

Não é possível excluir a política global. Se você tentar excluí-lo, a configuração será redefinida para os valores padrão.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.<BR>Para definir as configurações de servidor de chat persistente, consulte <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções do servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar a política global para chats persistentes

1.  Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) na documentação de operações.
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar cmdlets do Windows PowerShell. Para obter detalhes, consulte Configurando o <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  No painel de controle do Lync Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.

4.  Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar Política de Chat Persistent - Global**, siga este procedimento:
    
      - Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.
    
      - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para centralSiteName).
    
      - Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

