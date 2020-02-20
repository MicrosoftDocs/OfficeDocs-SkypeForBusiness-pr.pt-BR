---
title: 'Lync Server 2013: criar uma política de site para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b682191b0170a3915f44d54daa426ca5ce4544
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Criar uma política de site para chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

Para cada site implantado, você pode criar uma política de chat persistente específica do site.

A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.<BR>Para definir as definições de configuração do servidor de chat persistente, confira <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções de servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para criar uma política de chat persistente para um site

1.  Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar os cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

4.  Clique em **Novo** e, em seguida, em **Política de site**.

5.  Em **Selecionar um Site**, clique no site para o qual a política será aplicada.

6.  Em **Nova Política de Chat Persistente**, faça o seguinte:
    
      - Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).
    
      - Em **Descrição**, forneça detalhes sobre o que é a política de site (por exemplo, política de sala de chat para Redmond).
    
      - Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

