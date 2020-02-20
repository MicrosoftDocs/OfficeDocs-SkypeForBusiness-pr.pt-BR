---
title: 'Lync Server 2013: configurar a política global para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c77093e640d51204a7e16b2b32df02afcefe0bd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configurar a política global para chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

Você pode usar a política global padrão sozinho para habilitar as configurações de chat persistente para todos os usuários em sua implantação. Você também pode especificar políticas adicionais para sites e usuários para controlar se o chat persistente está habilitado ou desabilitado para usuários e sites específicos.

Você não pode excluir a política global. Se você tentar excluí-la, a configuração será redefinida para os valores padrão.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.<BR>Para definir as definições de configuração do servidor de chat persistente, confira <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções de servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar a política global para chat persistente

1.  Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir as ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) na documentação operações.
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar os cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando os cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  No painel de controle do Lync Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.

4.  Clique em **Global** na lista de políticas, clique em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Política de Chat Persistente - Global**, faça o seguinte:
    
      - Em **Nome**, especifique um novo nome para a política global, se você não quiser usar o padrão de Global.
    
      - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para centralSiteName).
    
      - Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

